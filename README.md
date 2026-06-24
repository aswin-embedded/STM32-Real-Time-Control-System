# STM32 Real-Time Control System

## Overview

A real-time embedded control system developed using STM32F103 and STM32 HAL libraries. The project integrates ADC, PWM, UART communication, GPIO, timers, rotary encoder input, and servo motor control into a single application.

The system reads analog input from a potentiometer, controls LED brightness using PWM, adjusts servo position using a rotary encoder, supports UART command-based control, and provides real-time system monitoring through serial communication.

## Features

* ADC-based potentiometer reading
* PWM-based LED brightness control
* Servo motor control using PWM
* Rotary encoder-based servo angle adjustment
* Run/Stop system control using push button
* Servo reset functionality
* UART command interface
* Real-time UART status monitoring
* Heartbeat LED for system health indication

## Hardware/Peripherals Used

* STM32F103 Microcontroller
* ADC1
* TIM1 PWM
* TIM3 PWM
* USART2
* GPIO
* Rotary Encoder
* Push Buttons
* Potentiometer
* Servo Motor
* LED

## Functionality

### ADC and PWM Control

A potentiometer is connected to ADC1. The ADC value is continuously sampled and converted into a PWM duty cycle.

* ADC Range: 0–4095
* PWM Duty Cycle: 0–100%

The LED brightness changes according to the potentiometer position.

### Run/Stop Control

A push button toggles the system between:

* RUN Mode
* STOP Mode

In STOP mode the PWM output is disabled.

### Servo Control

A rotary encoder is used to adjust the servo angle.

* Minimum Angle: 0°
* Maximum Angle: 180°
* Default Position: 90°

The encoder rotation increases or decreases the servo position.

### Servo Reset

Pressing the encoder switch resets the servo position to 90°.

### UART Commands

The system accepts the following UART commands:

| Command | Function     |
| ------- | ------------ |
| R       | Run System   |
| S       | Stop System  |
| C       | Center Servo |

### UART Monitoring

The system periodically transmits:

* ADC Value
* PWM Duty Cycle
* System State
* Servo Angle

Example:

ADC:2048 | Duty:50 | State:RUN | Servo:90

### Heartbeat LED

A heartbeat LED toggles periodically to indicate that the firmware is running normally.

## Concepts Demonstrated

* STM32 HAL Development
* ADC Configuration
* PWM Generation
* Timer Configuration
* UART Communication
* GPIO Handling
* Rotary Encoder Interfacing
* Servo Motor Control
* Real-Time Embedded Systems
* Hardware-Software Integration

## Tools Used

* STM32CubeMX
* STM32CubeIDE
* Embedded C
* STM32 HAL Libraries
* Wokwi Simulator

## Future Improvements

* DMA-based ADC acquisition
* Interrupt-based UART reception
* FreeRTOS integration
* CAN communication support
* LCD/OLED status display
