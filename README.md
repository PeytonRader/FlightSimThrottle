Magnetic Flight Sim Throttle Lever

Introduction
I undertook this project to create a high-precision, contactless throttle quadrant for flight simulation. Most consumer-grade throttles use potentiometers that rely on physical friction, which leads to "jitter" and mechanical failure over time. By utilizing AS5600 magnetic encoders, this project achieves 12-bit resolution (4,096 positions) without any physical contact between the sensor and the moving lever, ensuring long-term durability and precision.

Part Selection
Sensor Selection
For the primary movement sensors, I selected the AS5600 Magnetic Encoder. Unlike traditional analog sensors, these use the Hall Effect to measure the magnetic flux of a diametrically polarized magnet. This allows for extremely high-resolution digital output via I2C communication.

<img width="785" height="750" alt="image" src="https://github.com/user-attachments/assets/b80fde3e-f556-44db-ab92-b1a484443200" />

Microcontroller Selection
I selected a Raspberry Pi4 system to handle the I2C data acquisition. This allowed me to write Python scripts to process the raw digital data and convert it into usable degree values for flight simulation software.

<img width="808" height="470" alt="image" src="https://github.com/user-attachments/assets/f6f78b48-b2be-4456-ba2d-a24faa26d95b" />

CAD Model
The design underwent a significant evolution. I initially considered a rotation design with a quarter circle frame and 3 levers. <img width="2456" height="2560" alt="image" src="https://github.com/user-attachments/assets/9a30f6f9-527c-4294-8473-c64d672988d1" />
 However, to simplify the axle assembly, I switched to a single lever. Since it is my first time learning fusion 360, I worked together with Mr. Marc Aurele to create a design and modified the CAD to fit the design specifications. The CAD model was made for concept and needed to be scaled correctly so I took measurements of parts available in the classroom and redid the CAD to fit them.
 
<img width="201" height="371" alt="image" src="https://github.com/user-attachments/assets/f45b8620-27a8-4827-a449-435c607da7db" />

The assembly consists of:

The Bearing Block: A stationary housing that holds the sensors and bearings.

The Throttle Arm: Levers that rotate on a central bearing with embedded magnets.

Sensor Mount: Mount that aligns the AS5600 chip directly in front of the rotating magnets.

https://github.com/user-attachments/assets/a9f61354-9437-4d1e-970d-a95af74b0704

One of the challenges I faced was reading the degree angle output. The library for the sensor had a function to read the degree angle but it was outputing the raw angle (0-4096) so I calculated the degree angle with an equation.

Testing

<img width="847" height="508" alt="image" src="https://github.com/user-attachments/assets/78151433-ec35-464b-aa0a-56dbfd52fef0" />

While the magnet is not moving, there is a negligible fluctation in angle. I manually rotated the magnet in my testing which could have accounted for some error and fluctations.


Summary of Skills and Knowledge
This project was my first real experience with Mechatronic systems. I learned how to use Python libraries to talk to I2C sensors (AS5600) and how to write the math needed to turn raw 12-bit data into degrees. I also went from having zero experience to being able to perform CAD modeling in Fusion 360 to design custom mechanical parts.

Personal Reflection
The biggest takeaway for me was learning how to CAD for the real world. I had to learn how to work with constraints in Fusion 360 so I could modify my designs to fit the actual bearings and screws I had in the lab. I also learned to account for 3D printing tolerances, specifically how plastic expands. I designed the holes at 4.3mm for a 4.17mm bearing. This taught me that engineering is about constant troubleshooting and making things function through iteration and planning.

Connection
I plan to study Aerospace Engineering and want to improve my flight sim experience. Since I don’t have a physical throttle, building this allows me to recreate an aspect of the cockpit to help me learn to fly and understand aerospace principles. Designing this project gave me a head start on understanding the types of sensors and control systems used in real aircraft.
