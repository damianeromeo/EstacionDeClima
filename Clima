#include <DHT.h>
int dhtPin = 2;
DHT dht(dhtPin, DHT11);  // esto es igual a 11, https://github.com/adafruit/DHT-sensor-library/blob/master/DHT.h
void setup() 
{
  Serial.begin(9600);
  dht.begin();
  delay(5000);
}
void loop() 
{
  delay(5000);
  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature();
  float temperatureF = dht.readTemperature(true);
  if(isnan(humidity) || isnan(temperature) || isnan(temperatureF))
  {
    Serial.println("Error en la lectura del sensor");
    return;
  }
  float hic = dht.computeHeatIndex(temperature, humidity, false);
  float hif = dht.computeHeatIndex(temperatureF, humidity);  
  
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.print("%  Temperature: ");
  Serial.print(temperature);
  Serial.print("°C ");
  Serial.print(temperatureF);
  Serial.print("°F  Heat index: ");
  Serial.print(hic);
  Serial.print("°C ");
  Serial.print(hif);
  Serial.println("°F");  
}
