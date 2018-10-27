# JHPWMDriver
A driver for the Adafruit 16-Channel 12-bit PWM/Servo Driver - I2C interface - PCA9685.
http://www.adafruit.com/product/815

Built for the NVIDIA Jetson TK1 Development Kit.

In order to run the example, edit example/servoExample.cpp and uncomment the lines:

// int servoMin = 120 ;

// int servoMax = 720 ;

and change the servoMin and servoMax values to values appropriate to the servos being used.

Members of the Jetson family have different I2C Bus layouts. Check the pinout diagrams to determine which Bus is being used for your particular model. Pinouts are available here: https://www.jetsonhacks.com/pinouts/

The default address for the PCA9685 is 0x40. On some Jetson models, this address is being used by other hardware. You may have to switch to another I2C bus.

In order to be able inspect the PCA9685, you may find it useful to install the i2c tools:

<blockquote>$ sudo apt-get install libi2c-dev i2c-tools</blockquote>

As an example, after installation, in a Terminal execute:

<blockquote>$ sudo i2cdetect -y -r 1</blockquote>

Replace the bus number 1 with the appropriate bus number.

You should see an entry of 0x40, which is the default address of the PCA9685. If you have soldered the address pins on the PCA9685 (as is the case if you are using multiple boards chained together) you should see the appropriate address.

You must have root permission to use the I2C bus, ie you must use sudo. To run the example:

<blockquote>$ sudo ./servoExample.cpp</blockquote>
