# SistemEmbedded
### Disusun Oleh
- Sari Wahyuningsih 4.31.20.0.23

# Daftar Laporan JobSheet Sistem Embedded

- [JobSheet 1 - Dasar Pemrograman ESP32 Untuk Pemrosesan Data Input/Output Analog dan Digital](https://github.com/sariwhyu/JobSheet1)
- [JobSheet 1.1 - Jaringan Sensor Nirkabel Menggunakan ESP-NOW](https://github.com/sariwhyu/JobSheet1.1)
- [JobSheet 2 - Protokol Komunikasi dan Sensor](https://github.com/sariwhyu/JobSheet2)
- [JobSheet 3 - Topologi Jaringan Lokal dan WiFi](https://github.com/sariwhyu/JobSheet3)
- [Jobsheet4.1 - Cayenne(MQTT)+Sensor+Button+Website Monitoring](https://github.com/sariwhyu/TugasNo1)
- [Jobsheet4.2 - Adafruit.IO+Sensor+LED+Suara](https://github.com/sariwhyu/TugasNo2)
- [Jobsheet4.3 - ThingSpeak+Sensor](https://github.com/sariwhyu/TugasNo3)
- [Jobsheet4.4 - ESP Now+IOT](https://github.com/sariwhyu/TugasNo4)


# JobSheet 2 PROTOKOL KOMUNIKASI DAN SENSOR

## Alat & Bahan

-	ESP32
-	Breadboard
-	Kabel jumper
-	Sensor DHT 11, RFID
-	LED (5) dan Push Button (3)
-	Servo
-	Resistor 330,1K, 10K Ohm (@ 3)


## Coding

### ESP32 Capacitive Touch Sensor

```bash
  // set pin numbers
const int touchPin = 4; 
const int ledPin = 16;

// change with your threshold value
const int threshold = 20;
// variable for storing the touch pin value 
int touchValue;

void setup(){
  Serial.begin(115200);
  delay(1000); // give me time to bring up serial monitor
  // initialize the LED pin as an output:
  pinMode (ledPin, OUTPUT);
}

void loop(){
  // read the state of the pushbutton value:
  touchValue = touchRead(touchPin);
  Serial.print(touchValue);
  // check if the touchValue is below the threshold
  // if it is, set ledPin to HIGH
  if(touchValue < threshold){
    // turn LED on
    digitalWrite(ledPin, HIGH);
    Serial.println(" - LED on");
  }
  else{
    // turn LED off
    digitalWrite(ledPin, LOW);
    Serial.println(" - LED off");
  }
  delay(500);
}

```

### ESP32 Capacitive Touch Sensor BLINK

```bash
  // set pin numbers
const int touchPin = 4; 
const int ledPin = 16;

// change with your threshold value
const int threshold = 20;
// variable for storing the touch pin value 
int touchValue;

void setup(){
  Serial.begin(115200);
  delay(1000); // give me time to bring up serial monitor
  // initialize the LED pin as an output:
  pinMode (ledPin, OUTPUT);
}

void loop(){
  // read the state of the pushbutton value:
  touchValue = touchRead(touchPin);
  Serial.print(touchValue);
  // check if the touchValue is below the threshold
  // if it is, set ledPin to HIGH
  if(touchValue < threshold){
    // turn LED on
    digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(500);
    Serial.println(" - LED on");
    digitalWrite(ledPin, LOW);
    delay(500);
    Serial.println(" - LED off");
  }
  else{
    // turn LED off
    digitalWrite(ledPin, LOW);
    delay(500);
    Serial.println(" - LED off");
  }
}

```

### ESP32 Capacitive Touch Sensor RUNNING

```bash
  // set pin numbers
const int touchPin = 4; 
const int ledPin = 16;
const int ledPin1 = 17;
const int ledPin2 = 18;

// change with your threshold value
const int threshold = 20;
// variable for storing the touch pin value 
int touchValue;

void setup(){
  Serial.begin(115200);
  delay(1000); // give me time to bring up serial monitor
  // initialize the LED pin as an output:
  pinMode (ledPin, OUTPUT);
  pinMode (ledPin1, OUTPUT);
  pinMode (ledPin2, OUTPUT);
}

void loop(){
  // read the state of the pushbutton value:
  touchValue = touchRead(touchPin);
  Serial.print(touchValue);
  // check if the touchValue is below the threshold
  // if it is, set ledPin to HIGH
  if(touchValue < threshold){
    // turn LED on
    digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
  }
  else{
    // turn LED off
    digitalWrite(ledPin, LOW);
    Serial.println(" - LED off");
    digitalWrite(ledPin1, LOW);
    Serial.println(" - LED off");
    digitalWrite(ledPin2, LOW);
    Serial.println(" - LED off");
  }
  delay(500);
}

```

### ESP32 DHT11

```bash
  // REQUIRES the following Arduino libraries:
// - DHT Sensor Library: https://github.com/adafruit/DHT-sensor-library
// - Adafruit Unified Sensor Lib: https://github.com/adafruit/Adafruit_Sensor
#include "DHT.h"
#define DHTPIN 4 // Digital pin connected to the DHT sensor
// Uncomment whatever type you're using!
#define DHTTYPE DHT11 // DHT 11
//#define DHTTYPE DHT22 // DHT 22 (AM2302), AM2321
//#define DHTTYPE DHT21 // DHT 21 (AM2301)
DHT dht(DHTPIN, DHTTYPE);
void setup() {
Serial.begin(9600);
Serial.println(F("DHT11 Embedded System Test!"));
dht.begin();
}
void loop() {
// Wait a few seconds between measurements.
delay(2000);
// Reading temperature or humidity takes about 250 milliseconds!
// Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
float h = dht.readHumidity();
// Read temperature as Celsius (the default)
float t = dht.readTemperature();
// Read temperature as Fahrenheit (isFahrenheit = true)
float f = dht.readTemperature(true);
// Check if any reads failed and exit early (to try again).
if (isnan(h) || isnan(t) || isnan(f)) {
Serial.println(F("Failed to read from DHT sensor!"));
return;
}
// Compute heat index in Fahrenheit (the default)
float hif = dht.computeHeatIndex(f, h);
// Compute heat index in Celsius (isFahreheit = false)
float hic = dht.computeHeatIndex(t, h, false);
Serial.print(F("Humidity: "));
Serial.print(h);
Serial.print(F("% Temperature: "));
Serial.print(t);
Serial.print(F("°C "));
Serial.print(f);
Serial.print(F("°F Heat index: "));
Serial.print(hic);
Serial.print(F("°C "));
Serial.print(hif);
Serial.println(F("°F"));
}

```

### ESP32 RFID

```bash
  #include <SPI.h>
#include <MFRC522.h>
#define SS_PIN 21 // ESP32 pin GIO21
#define RST_PIN 22 // ESP32 pin GIO22
MFRC522 rfid(SS_PIN, RST_PIN);
byte keyTagUID[4] = {0xE3, 0x1A, 0xD6, 0x03};
void setup() {
Serial.begin(9600);
SPI.begin(); // init SPI bus
rfid.PCD_Init(); // init MFRC522
Serial.println("Tap RFID/NFC Tag on reader");
}
void loop() {
if (rfid.PICC_IsNewCardPresent()) { // new tag is available
if (rfid.PICC_ReadCardSerial()) { // NUID has been readed
MFRC522::PICC_Type piccType = rfid.PICC_GetType(rfid.uid.sak);
if (rfid.uid.uidByte[0] == keyTagUID[0] &&
rfid.uid.uidByte[1] == keyTagUID[1] &&
rfid.uid.uidByte[2] == keyTagUID[2] &&
rfid.uid.uidByte[3] == keyTagUID[3] ) {
Serial.println("Access is granted");
}
else
{
Serial.print("Access denied for user with UID:");
for (int i = 0; i < rfid.uid.size; i++) {
  Serial.print(rfid.uid.uidByte[i] < 0x10 ? " 0" : " ");
Serial.print(rfid.uid.uidByte[i], HEX);
}
Serial.println();
}
rfid.PICC_HaltA(); // halt PICC
rfid.PCD_StopCrypto1(); // stop encryption on PCD
}
}
}

```

## Hasil

https://github.com/sariwhyu/JobSheet2/blob/main/Blinksentuh.mp4

https://github.com/sariwhyu/JobSheet2/blob/main/Tapkartu2.mp4

https://github.com/sariwhyu/JobSheet2/blob/main/VID20221128102530.mp4

https://github.com/sariwhyu/JobSheet2/blob/main/VID20221205100358.mp4
