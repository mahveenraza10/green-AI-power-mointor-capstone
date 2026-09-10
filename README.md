# green-AI-power-monitor-capstone
A low-voltage USB energy monitor that measures the real-time power consumption of a 5V USB device and estimates operational CO₂e.
**Hardware side:** The Pico reads an INA219 current sensor over I²C and drives a visual LED bar graph, status LED, buzzer alert, and physical controls.

**Software side:** The Pico sends data over USB serial to the laptop, where a Python script handles the dashboard display, live graphing, session logging to CSV, and CO₂e estimation.

**Suitable loads:** a Raspberry Pi, a USB lamp, a fan, a microcontroller running different workloads. NOT mains voltage, NOT USB-C Power Delivery, NOT a desktop computer's power supply.

**Components** INA219 sensor, USB Type-A female breakout boards, LED Bar Graph, push button, LED, buzzer, potentiometer, resistors (220Ω, 330Ω, 1kΩ)
