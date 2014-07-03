#Servo
JavaScript library for running the [Adafruit 16-Channel 12-bit PWM/Servo Driver](http://www.adafruit.com/product/815) with the [Tessel](http://tessel.io). The Adafruit 16-Channel 12-bit PWM/Servo Driver is capable of driving up to 16 servos at once.

This code was forked from the [tessel/servo-pca9685 repository](https://github.com/tessel/servo-pca9685) which contains a library for running the servo-pca9685 Tessel servo module. This module also uses the [NXP PCA9685](http://www.adafruit.com/datasheets/PCA9685.pdf) 16-channel, 12-bit PWM Fm+ I2C-bus LED controller. As result, only minor modifications to the original repository were needed to get it working with the Adafruit 16-Channel 12-bit PWM/Servo Driver.

###Installation
```sh
npm install servo-adafruit-pca9685
```

###Methods
&#x20;<a href="#api-servo-configure-whichServo-minPWM-maxPWM-callback-Sets-the-PWM-max-and-min-for-the-specified-servo" name="api-servo-configure-whichServo-minPWM-maxPWM-callback-Sets-the-PWM-max-and-min-for-the-specified-servo">#</a> servo<b>.configure</b>( whichServo, minPWM, maxPWM, callback() ) Sets the PWM max and min for the specified servo.  

&#x20;<a href="#api-servo-move-whichServo-positionOrSpeed-callback-positionOrSpeed-is-a-value-between-0-and-1-On-a-normal-servo-this-value-is-the-position-to-move-to-as-a-percent-of-the-total-available-rotational-range-On-a-continuous-rotation-servo-this-value-represents-the-rotation-speed-0-is-fast-in-one-direction-1-is-fast-in-the-other-direction-and-0-5-is-stopped" name="api-servo-move-whichServo-positionOrSpeed-callback-positionOrSpeed-is-a-value-between-0-and-1-On-a-normal-servo-this-value-is-the-position-to-move-to-as-a-percent-of-the-total-available-rotational-range-On-a-continuous-rotation-servo-this-value-represents-the-rotation-speed-0-is-fast-in-one-direction-1-is-fast-in-the-other-direction-and-0-5-is-stopped">#</a> servo<b>.move</b>( whichServo, positionOrSpeed, callback() ) positionOrSpeed is a value between 0 and 1. On a normal servo, this value is the position to move to as a percent of the total available rotational range. On a continuous rotation servo, this value represents the rotation speed: 0 is fast in one direction, 1 is fast in the other direction, and 0.5 is stopped.  

&#x20;<a href="#api-servo-read-whichServo-callback-Reads-the-current-approximate-position-target-for-the-specified-servo" name="api-servo-read-whichServo-callback-Reads-the-current-approximate-position-target-for-the-specified-servo">#</a> servo<b>.read</b>( whichServo, callback() ) Reads the current approximate position target for the specified servo.  

&#x20;<a href="#api-servo-setDutyCycle-whichServo-on-callback-Sets-the-duty-cycle-for-the-specified-servo-on-is-duty-cycle-uptime-range-from-0-1" name="api-servo-setDutyCycle-whichServo-on-callback-Sets-the-duty-cycle-for-the-specified-servo-on-is-duty-cycle-uptime-range-from-0-1">#</a> servo<b>.setDutyCycle</b>( whichServo, on, callback() ) Sets the duty cycle for the specified servo. on is duty cycle uptime, range from 0-1.  

&#x20;<a href="#api-servo-setModuleFrequency-Hertz-callback-Sets-the-PWM-frequency-in-Hz-for-the-PCA9685-chip" name="api-servo-setModuleFrequency-Hertz-callback-Sets-the-PWM-frequency-in-Hz-for-the-PCA9685-chip">#</a> servo<b>.setModuleFrequency</b>( Hertz, callback() ) Sets the PWM frequency in Hz for the PCA9685 chip.  

###Events
&#x20;<a href="#api-servo-on-error-callback-err-Emitted-upon-error" name="api-servo-on-error-callback-err-Emitted-upon-error">#</a> servo<b>.on</b>( 'error', callback(err) ) Emitted upon error.  

&#x20;<a href="#api-servo-on-ready-callback-Emitted-upon-first-successful-communication-between-the-Tessel-and-the-module" name="api-servo-on-ready-callback-Emitted-upon-first-successful-communication-between-the-Tessel-and-the-module">#</a> servo<b>.on</b>( 'ready', callback() ) Emitted upon first successful communication between the Tessel and the module.  

###Wiring
The Adafruit 16-Channel 12-bit PWM/Servo Driver cannot be plugged directly into a port like the Tessel servo module. Instead, it will need to be wired from the GPIO port. The pinout for the Tessel GPIO can be found [here](https://tessel.io/docs/hardware#pins-and-ports). Wiring is very straightforward:

* Tessel GPIO Pin 1 GND to Adafruit GND
* Tessel GPIO Pin 3 3V3 to Adafruit VCC
* Tessel GPIO Pin 5 SCL to Adafruit SCL
* Tessel GPIO Pin 7 SDA to Adafruit SDA

###License
MIT