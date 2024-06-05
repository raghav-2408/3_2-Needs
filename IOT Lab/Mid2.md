# Week 6

`WriteSingleField`
```c
#define TS_ENABLE_SSL 

#include <ESP8266WiFi.h>
#include <WiFiClientSecure.h>
#include "secrets.h"
#include "ThingSpeak.h" 

char ssid[] = SECRET_SSID;   // your network SSID (name) 
char pass[] = SECRET_PASS;   // your network password
int keyIndex = 0;            // your network key Index number (needed only for WEP)
WiFiClientSecure  client;

unsigned long myChannelNumber = SECRET_CH_ID;
const char * myWriteAPIKey = SECRET_WRITE_APIKEY;

int number = 0;

const char * fingerprint = NULL; // use SECRET_SHA1_FINGERPRINT for fingerprint check

void setup() {
  Serial.begin(115200);  // Initialize serial
  while (!Serial) {
    ; 
  }
  
  WiFi.mode(WIFI_STA);

  if(fingerprint!=NULL){
    client.setFingerprint(fingerprint);
  }
  else{
    client.setInsecure(); 
  }
  
  ThingSpeak.begin(client);  // Initialize ThingSpeak
}

void loop() {

  if(WiFi.status() != WL_CONNECTED){
    Serial.print("Attempting to connect to SSID: ");
    Serial.println(SECRET_SSID);
    while(WiFi.status() != WL_CONNECTED){
      WiFi.begin(ssid, pass);  
      Serial.print(".");
      delay(5000);     
    } 
    Serial.println("\nConnected.");
  }

  int x = ThingSpeak.writeField(myChannelNumber, 1, number, myWriteAPIKey);
  if(x == 200){
    Serial.println("Channel update successful.");
  }
  else{
    Serial.println("Problem updating channel. HTTP error code " + String(x));
  }

  // change the value
  number++;
  if(number > 99){
    number = 0;
  }
  
  delay(5000); 
}

```

`secrets.h`

```c
#define SECRET_SSID "MySSID"		// replace MySSID with your WiFi network name
#define SECRET_PASS "MyPassword"	// replace MyPassword with your WiFi password

#define SECRET_CH_ID 000000			// replace 0000000 with your channel number
#define SECRET_WRITE_APIKEY "XYZ"   // replace XYZ with your channel write API Key

// ThingSpeak Certificate Fingerprint, Expiration Date: August 3, 2022 at 8:00:00 AM EST 
#define SECRET_SHA1_FINGERPRINT "27 18 92 DD A4 26 C3 07 09 B9 7A E6 C5 21 B9 5B 48 F7 16 E1"
```
