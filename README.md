# IoT-smart-street-light

# **IoT-Based Smart Street Light System – Documentation**

## **1. Introduction**

Traditional street-lighting systems often waste energy because they operate continuously without responding to environmental light conditions. An IoT-based Smart Street Light System automates this process by intelligently switching lights ON or OFF depending on ambient light levels. This improves energy efficiency, reduces operational costs, and minimizes manual intervention.

---

## **2. Objective**

The primary goal of this project is to design a smart street-light system using an ESP32 microcontroller and an LDR (Light Dependent Resistor). The system should:

* Detect ambient light levels.
* Turn the street light ON when it becomes dark.
* Turn it OFF when sufficient daylight is available.
* Transmit sensor data for monitoring (optional IoT extension).

---

## **3. System Overview**

The ESP32 continuously reads the analog value from the LDR sensor.

* **Low ambient light** → LDR resistance increases → ESP32 detects darkness → LED turns **ON**.
* **High ambient light** → LDR resistance decreases → ESP32 detects daylight → LED turns **OFF**.

The system can also be extended with Wi-Fi to upload data to cloud dashboards for remote monitoring.

---

## **4. Components Required**

### **Hardware**

* ESP32 Microcontroller
* LDR Sensor
* 220-ohm resistor
* 1k-ohm resistor
* LED (representing street light)
* Micro USB Cable

### **Software**

* Arduino IDE
* ESP32 Board Support Package

---

## **5. Working Principle**

### **5.1 LDR Sensor Function**

The LDR changes its resistance based on the intensity of light falling on it:

* **Bright light** → low resistance
* **Darkness** → high resistance

The ESP32 reads this change through an analog input pin (GPIO34).

### **5.2 Control Logic**

1. The ESP32 reads the analog value from the LDR.
2. If the value is below a fixed threshold (dark environment), the ESP32 outputs HIGH on GPIO23, lighting up the LED.
3. If the value is above the threshold (bright environment), the output becomes LOW, turning OFF the LED.

---

## **6. Circuit Explanation**

Based on the diagram:

* The LDR is connected to **GPIO34** of the ESP32.
* A suitable resistor is used to form a voltage divider with the LDR.
* The LED is connected to **GPIO23** through a **220-ohm resistor**.
* Both sensor and LED circuits share a common ground with ESP32.

---

## **7. Applications**

* Street light automation
* Smart city infrastructure
* Campus/parking-lot lighting
* Energy-saving lighting systems
* Remote monitoring of lighting status (IoT extension)

---

## **8. Advantages**

* Significant reduction in electricity consumption
* Eliminates need for manual switching
* Cost-effective and scalable
* Simple to deploy and maintain
* Real-time monitoring possible

---

## **9. Future Enhancements**

* Integration with IoT platforms like Blynk, ThingsBoard, Firebase
* Motion-based adaptive brightness control
* Solar-powered street-light system
* Automated fault detection

