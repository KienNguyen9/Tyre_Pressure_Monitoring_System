# Tyre_Pressure_Monitoring_System
<h3>
  Abstract:
</h3>

The Tyre Pressure Monitoring System which is used today indicates only
whether the air pressure in any of the tyres is below a particular level of safety. This
avoidable signal has made it possible for the statistical death rate to come up to 650
deaths per year. This project displays values through continuous monitoring.
Therefore, this research proposed a method to cumulate the various factors of the tyre
and to display it to the driver for a safer experience. The proposed TPMS has an
electronic device unit that is attached to the tyre and transmits the values of the
pressure, temperature, and the wheel alignment to the unit to be placed inside the
vehicle, observable to the driver. This unit includes pressure sensors, microcontrollers,
RF transmission, and batteries. An alert is introduced which indicates if the pressure
exceeds the maximum or minimum safe pressure level. Several experiments have been
carried out to analyze the proposed system. The integrated TPMS has proven to be an
effective alternative to maintain the tyres and aims to improve the comfort and safety
of the driver.
<h3>
  1. Intr oduction
</h3>

According to research, there is an increase in the number of accidents that take place due to the
carelessness drawn towards the low air pressure in tyres. In India alone, 35-40% of accidents that have
taken place, occur due to tyre bursts in the past 5 Years. Tyre blowouts are one of the most common
reasons for accidents that take place. T. Xiangjun, proposed [1] the event of a sudden flat tire
accounted for 49.81% of highway accidents, in 2006. N. N. Hasan, A. Arif, [2] et al proposed the
current tyre pressure sensors indicate a symbol in the dashboard of the car that people usually tend to
ignore. Currently, there are two basic methods to measure tire pressure; direct and indirect. The direct
technique is implemented but with the use of a differential pressure sensor. This project will ensure
that the driver will have the exact air pressures of all the tyres of the car displayed continuously. It also
deals with the wear and tear of the tyre. One more aspect of the project is the temperature and wheel
alignment of the car. When the car is driven in the most moderate conditions, there is greater longevity
of the tyres while simultaneously provides a smoother and safer drive. In the currently used products,
they aren't available for the wear and tear of tyres. However, through more research and technological
interventions, we're looking forward to this product displaying.

- Tyre pressure is measured and displayed constantly.
- The wheel alignment that will help in parking and keeping the tyres in an optimum condition
during parking.
- The temperature sensor that indicates the wear and tear of the tyre, along with the frictional changes applied to it.
<h3>
  2. Literature Review
</h3>

Globally, we are heading towards a more secure and error-free future. Our project and the proposed
methodology aim toward the same. In the interest of having a safer drive, the tyre used plays an
important role and so does the maintenance of it. In the bigger picture, we are concentrating on the
three most important features of a tyre. According to research, these are three of the most wide-ranged
reasons that cause accidents.
![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/49888d52-fc28-469d-9c72-09cbcd225d91)

The unit can measure tire pressure whether the vehicle is still or in motion. The unit consists of a
pressure sensor, a pressure switch, a microcontroller, an RF transmitter, and a long-lasting battery
(+12volts) [1]. All units are switched ON and inserted into the tires. The alert message is displayed to
the driver when the pressure goes below the set threshold value of 25 PSI. The pressure sensor has
great sensitivity and takes 15 seconds to update its values.
The TPMS was first introduced in the 1980s in the European countries, generally as an additional
feature since it was safe, friendly, and environmentally friendly. Some researchers and manufacturers
define TPMS as a vehicle’s safety device to maintain a vehicle’s safety and check its condition,
especially its tire pressure condition. TPMS is broadly divided into two methods, namely WSB (Wheel
Speed Base) and PSB (Pressure Sensor Base).
This paper inclines towards Pressure Sensor Base, the pressure is directly proportional to the
produced voltage at the output terminal of the sensor.

<h3>
  3. Block Diagram and Description
</h3>

<h4>
  3.1. Transmitting side:
</h4>

The block diagram below represents the transmitting part of the tyre pressure monitoring system. The
proposed system can be understood in a pictorial format with the micro-controller differentiating
sensors from the TLP 433MHz transmitter. Firstly, the pressure sensor (MPX10DP) senses the
pressure of the tyre in PSI. Then this data reaches the Arduino through the analog pin (A0). The
Arduino board has an in-built function of converting the analog value into its digital equivalent.
Similarly, the accelerometer has its serial data and serial clock connected to A4 and A5 respectively.
The alignment of the car based on the pressure inside it is given by the accelerometer. Whether the car
is aligned to the left or right or straight will be the three possible outcomes from the accelerometer.
Along with these values the final parameter, temperature due to the friction caused in the tyre is also
displayed. The temperature sensor is connected to the PIN (D2) of the transmitter at a frequency of 433MHz. Amplitude shift keying is the modulation technique that is utilized in this transmitter and
receiver duo.

![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/35693033-80ec-4d33-84b5-5cb165745f68)

P.S: Pressure sensor
A.S: Acceleration sensor
T.S: Temperature sensor

<h4>
  3.2 Receiving side
</h4>

The above block diagram represents the receiving part of the tyre pressure monitoring system.
Identical to that of the transmitting part, the receiver side of the system also contains Arduino UNO as
its brain. The receiving module is simpler when compared to that of the transmitter with the RF
receiver and the LCD along with Arduino UNO. The RF receiver is connected to the PIN (D2) to
receive the data packet sent by the transmitter. The L.C.D pins are connected to the pins ranging from
(D8) –(D13). The potentiometer connected to the L.C.D functions to increase or decrease the
brightness of the display.

![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/3ef45fb1-bcf0-41d1-9629-7bdae9d944c7)

<h4>
  4. Program Flow Process
</h4>
   
Firstly, a Radio head library is installed in the Arduino IDE for enabling RF communication at
433MHz frequency. Later, the tyre pressure is sensed by the MPX10DP Pressure sensor in Pound
per Square Inch (PSI). This value along with the temperature and acceleration is transmitted by the
RF communication module with the help of the inbuilt functions of the library included.
![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/4783d683-d826-4f3d-904f-dbd030ea1eed)

![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/a9c1f484-437f-4e51-8356-859ab3d191cb)

At the receiver end, the transmitted values are received and the pressure value is examined for a drop
below 25 PSI. Once the value is below the threshold, the LCD would display an alert message to the
driver.

<h3>
  5. Results and Discussions
</h3>
The transmitting module can be seen in the below figure. This module is an interface of many
sensors like temperature sensor, pressure sensor, and accelerometer. Among these, the pressure sensor attached to the tyre is the most important one. This pressure sensor is a dual-port
uncompensated silicon sensor for level indicators. It is a silicon piezoresistive pressure sensor,
directly proportional to the applied pressure outputs a linear and accurate voltage [3]. This standard
uncompensated sensor permits manufacturers to design and add their external temperature
compensation and signal conditioning networks. It is used for sensing & Instrumentation,
Industrialization, Automation & Process Control.
![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/e2c344fe-6ab7-4ec6-883d-70be43679699)

The other sensors are for additional parameters like temperature and acceleration. The
ADXL335, generally known as an accelerometer, is an electromechanical device that measures the
force of acceleration due to gravity in g unit [4]. The analog voltage output proportional to the
acceleration along x, y, and z axes is measured and given by it. The microcontroller can process
these voltages by converting them to digital signals using ADC.
The DHT11 is a basic, ultra-low-cost digital temperature and humidity sensor. It uses a capacitive
humidity sensor and a thermistor to measure the surrounding air and spits out a digital signal on the
data pin (no analog input pins needed). Thus it is used in this application.

![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/b6bed309-a2cd-42cf-a2cd-eca01a2bdb73)

Both in transmitter and receiver there are a few components that are in common and they are the
microcontroller Arduino UNO and RF transmitter-receiver.
The above two figures 6 and 8 show the realized systems of transmitter and receiver modules.
Below figure 9 shows the alert message that is displayed on the LCD. For the transmitting and the
receiving unit, any small general-purpose microcontroller can be used. For ease, Arduino UNO was
used. It is also capable of the UART protocol, which makes it suitable for RF transmission. The
number of pins is sufficient enough to control the LCD at the receiver. At the same time, it also
provides ADC channels at the transmitting side.
The TLP 433MHz transmitter and receiver work on the ASK modulation technique. This pair of
communication devices is one of the least expensive data communication options we get in the
market.

![image](https://github.com/KienNguyen9/Tyre_Pressure_Monitoring_System/assets/136218538/b3a4eac1-3fe1-4613-ac92-b9c9b6dfba90)

<h3>
  6. Conclusions and Future Work
</h3>

The response obtained during the testing of the system gave stable and reliable outputs. This design
is just a prototype that is capable of displaying only the pressure, acceleration, temperature of a
single tyre. It is possible to extend this idea onto the other tyres of the vehicle without any confusion
between them by adding an ID to each tyre. There is a chance for a size reduction, by using a PIC
microcontroller instead of Arduino UNO. The reduction in size or the change in the microcontroller
will not affect the working of the system. These modifications will make the system more users
friendly.
At the receiver end, the transmitted values are received and the pressure value is examined for a drop
below 25 PSI. Once the value is below the threshold, the LCD would display an alert message to the
driver.

