# BME260 and Oled SSH106 Display to control Humidity 

A System that consists of a BME260 humidty Sensor and an Oled Display mounted on a raspberry PI to get and display the humidity value in a room.
depending on the humidty value, the system chooses whether to increase or decrease humidity using a humidifier or dehumidifier.


![Layout](https://github.com/TitiLouati/Cplusplus-Raspi-Project-Humidity-sensor-Oled/blob/main/Humidity-Sensor-OledDisplay/BME260Oled.jpeg)

# Example 

This Project Consists of two modes : 

## Automatic 

In this mode the program measures the humidty in the room continuously and print the data on the Oled Display. when the humdity is less than 50 % then the

humidifier will be turned on until the humdity will be greater than 50 %. and if the humidty is greater than 70 % ,the dehumidifier will be turned on until the humdity 

will be less than 70 %. when the humidity is between 50% and 70% bother the humidifer and dehumidifier will be turned off.

in this project it will be used two leds instead of the humidifier and dehumidifier. 

## Manual 

in this mode the user can turn on the humidifier or the dehumidifier manualy from two push button . every single push on the button will give 60 second for the 

de/humidifier to work. the work timing will be printed on the Display , and every 10 second the  timming will be changed . 

the work mode will be printed on the screen too . 

# Program Construction

every node of the program will run at the same Time . The BME260 sensor and the Oled Display are using the same I2C communication interface port so they must run on different threads . the communication between the two threads will be synchronized through a mutex .

# Dependencies

install G++ compiler by instaling : libc6-armel-cross libc6-dev-armel-cross binutils-arm-linux-gnueabi libncurses5-dev build-essential bison flex libssl-dev. 

# Installation 

to install this project follow those steps: 


```
git clone https://github.com/TitiLouati/Cplusplus-Raspi-Project-Humidity-sensor-Oled.git

```
Then : 


```
g++ -o main main.cpp oled.cpp oled.h gpio.cpp gpio.h bme260.cpp bme260.h fonts.h

```
