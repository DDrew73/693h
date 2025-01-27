
Mobility team,

Thanks for volunteering to be a part of designing this important subsystem. I'm going to give you some general ideas for what I am looking for in this robot to guide your design, as well as a couple of things your Design Review 1 **must** include. 

At a high level, your subsystem group is responsible for:
- Wheels and motors
- Motor driver electronics, encoder electronics
- Power distribution to the motors
- PID controller tuning for the motors (RPM)
- Top-down motion capture for the robots

Here are some pointers to get you started:
- We should do top-down position tracking of the robots using something like WhyCon https://github.com/jiriUlr/whycon-ros / AprilTags https://github.com/christianrauch/apriltag_ros and include a cheap usb webcam in the kit. 
- Some TT motors come with embedded encoders, which could simplify design (e.g., https://www.hiwonder.com/products/tt-motor-plastic?variant=40452432298071&srsltid=AfmBOoqYtg5Yp8X2HhM_1UxTe5uOhzZg6eclLhZCLnoyyDC-aWa29SCf) 

At a minimum, your Design Review 1 must include content discussing: 
- motor (and gearing, if applicable) selection methodology
- motor driver electronics selection methodology
- estimated power draw (quiescent, average in motion, as a RPM/torque) and voltage/current requirements
- an overview of the tracking technique which will be used
- a project timeline between now and Design Review 2 (3/10) 

Note that I want to put in an order for parts to use in prototyping by February 3rd. This should be at the breadboard level, using either discrete components or breakout boards. 
- Do not worry about budget, but remember we are targeting ~$100 robots
- Assume you will use an instructor-supplied Arduino Nano ESP32 to interface with electronics. 
- No need to order wires / breadboards / passive components

You can find the sheet to put your parts here:
https://docs.google.com/spreadsheets/d/1gGh9VHhXkWhZPkldkP3rH2SYG9HW3y-EUHdndE54T2w/edit?usp=sharing 

Let me know if there are any questions!

Best,
Dr. Drew



Perception team,

Thanks for volunteering to be a part of designing this important subsystem. I'm going to give you some general ideas for what I am looking for in this robot to guide your design, as well as a couple of things your Design Review 1 **must** include. 

At a high level, your subsystem group is responsible for:
- Proximity / mapping / obstacle avoidance sensors
- Power distribution and drive electronics for the sensors
- Calibration and driver code for the sensors / outputs
- General input / output functionality, like an RGB LED, OLED screen, and button(s) 

Here are some pointers to get you started:
- The VL53L0X is a fantastic and relatively cheap sensor, we should use at least one
- Look into a ring of IR proximity sensors (e.g., used in the HeRo2), with something like the TCRT5000
- Neopixel single-pixel is an easy to use RGB with breakout board from Adafruit
- Cheap high quality OLED screens are now available; https://www.adafruit.com/product/326 is an example of a dev board for one
- Connecting GPIOs to every proximity sensor is not efficient; consider a multiplexer

At a minimum, your Design Review 1 must include content discussing: 
- an overview of the full sensor suite you envision
- a technical deep-dive into how at least two of the sensors you have selected work at a physical and electronic layer
- an overview of the full input/output suite you envision, including at least one concept of how they could be used in the final system
- concept sketches for the top enclosure which allows sensors to see and access to the input/outputs
- estimated power draw numbers for the sensors and outputs when active, as function of polling frequency, etc. 
- a project timeline between now and Design Review 2 (3/10) 

Note that I want to put in an order for parts to use in prototyping by February 3rd. This should be at the breadboard level, using either discrete components or breakout boards. 
- Do not worry about budget, but remember we are targeting ~$100 robots
- Assume you will use an instructor-supplied Arduino Nano ESP32 to interface with electronics. 
- No need to order wires / breadboards / passive components

You can find the sheet to put your parts here:
https://docs.google.com/spreadsheets/d/1gGh9VHhXkWhZPkldkP3rH2SYG9HW3y-EUHdndE54T2w/edit?usp=sharing 

Let me know if there are any questions!

Best,
Dr. Drew


Compute and Power team,

Thanks for volunteering to be a part of designing this important subsystem. I'm going to give you some general ideas for what I am looking for in this robot to guide your design, as well as a couple of things your Design Review 1 **must** include. 

At a high level, your subsystem group is responsible for:
- Microcontroller selection and programming
- Ensuring success of the wireless communication stack
- Battery selection and charging methodology / electronics
- Coordinating GPIO and power distribution routing among all the subsystems

Here are some pointers to get you started:
- The Arduino Nano ESP32 is a great little board. Look for the schematic and try to understand what parts of it are necessary and what parts we could jettison to save space. There are also examples of super tiny ESP32 dev boards, like https://www.adafruit.com/product/5395?gQT=2 
- You will almost certainly want to use a single cell lithium ion battery. You will likely need a 5V boost converter from that battery to the regulator input of the microcontroller electronics.
- Lots of lithium ion charging modules exist, like the TP4056. Ideally, though, the same usb connection can be used for programming the robots and charging the battery. 

At a minimum, your Design Review 1 must include content discussing: 
- a feature walkthrough of the esp32 (e.g., available GPIOs, radio), and what kind of supporting electronics you will need
- a description of your battery system, including the battery itself, charging electronics and procedure, and ensuring proper voltage regulation throughout the system
- lifetime estimates based on different example power draws, and charge time estimates based on datasheets
- a concept sketch 
- estimated power draw numbers for the sensors and outputs when active, as function of polling frequency, etc. 
- a project timeline between now and Design Review 2 (3/10) 

Note that I want to put in an order for parts to use in prototyping by February 3rd. This should be at the breadboard level, using either discrete components or breakout boards. 
- Do not worry about budget, but remember we are targeting ~$100 robots
- Assume you will use an instructor-supplied Arduino Nano ESP32 to interface with electronics during prototype testing (unless you are purchasing a replacement). 
- No need to order wires / breadboards / passive components

You can find the sheet to put your parts here:
https://docs.google.com/spreadsheets/d/1gGh9VHhXkWhZPkldkP3rH2SYG9HW3y-EUHdndE54T2w/edit?usp=sharing 

Let me know if there are any questions!

Best,
Dr. Drew

Control and Planning team,

Thanks for volunteering to be a part of designing this important subsystem. I'm going to give you some general ideas for what I am looking for in this robot to guide your design, as well as a couple of things your Design Review 1 **must** include. 

At a high level, your subsystem group is responsible for:
- microROS use on the embedded system chosen by the Compute and Power team
- Getting Ubuntu + ROS2 set up and organized on a bootable USB drive
- Gazebo simulation of our multi-robot system, with realistic robot models
- Designing the enclose which will house all the robots and supporting electronics (e.g., webcam, thumbstick, usb cable)

At a minimum, your Design Review 1 must include content discussing: 
- microROS explanation and simple demo
- ROS2 explanation and simple demo, either installed natively on one of your laptops or through a bootable USB-drive
- a block diagram with potential ROS topics/services necessary for basic multi-robot control tasks, to guide the other subsystem groups
- concept sketch for a full enclose, including secure mounting for the robots and peripherals
- a project timeline between now and Design Review 2 (3/10) 

Note that I want to put in an order for parts to use in prototyping by February 3rd. This should be at the breadboard level, using either discrete components or breakout boards. 
- Do not worry about budget, but remember we are targeting ~$100 robots
- Assume you will use an instructor-supplied Arduino Nano ESP32 at first, unless you tell me this is a bad idea for microROS
- I already ordered some USB3.0 thumb drives to use; I will give you them in class

You can find the sheet to put your parts here:
https://docs.google.com/spreadsheets/d/1gGh9VHhXkWhZPkldkP3rH2SYG9HW3y-EUHdndE54T2w/edit?usp=sharing 

Let me know if there are any questions!

Best,
Dr. Drew








