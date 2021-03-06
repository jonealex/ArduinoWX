# ArduinoWX
*This is a small, cheap and easy weather station that sends data to "APRS.fi".*
## Hardware
__NodeMCU (ESP8266) + BME/BMP280__
## Wiring
![ArduinoWX wiring](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/04/bme_280_esp8266_bb.png?ssl=1)
> Note that BME/BMP pins can be SCK or SCL, and SDI or SDA.
## Setup
WiFi settings:
```
#define WSSID "" // SSID
#define PASSWD "" // PASSWORD
IPAddress staticIP(AAA,AAA,A,AAA); // YOUR ESP8266 IP ADDRESS
IPAddress gateway(BBB,BBB,B,B); // YOUR ROUTER IP ADDRESS
IPAddress subnet(CCC,CCC,CCC,C); // SUBNET MASK 
```
> If you want to get an automatic IP address, then comment or remove `WiFi.config(staticIP, gateway, subnet, dns);` on `setup()`.

APRS settings:
```
#define CALLSIGN "" // YOUR CALLSIGN (FOR WEATHER STATIONS ADD -13)
#define PASSCODE "" // GENERATE IT ON apps.magicbug.co.uk/passcode/
#define LATITUDE "" // LATITUDE WITH 4 DIGITS POINT 2 DIGITS
#define LONGITUDE "" // LONGITUDE WITH 5 DIGITS POINT 2 DIGITS
```
## V1.1
This version uses deep sleep to increase battery life and wakes up every 15 minutes.
