# 🔌 STM32 Ethernet Monitoring System

## 📖 Overview

This project implements an Ethernet-based monitoring system using an **STM32F103C8T6** microcontroller and **W5500** Ethernet module. The system features a web-based control panel for real-time monitoring and control of hardware peripherals.

### 🎯 Key Features

- 🌐 **Ethernet Communication**: W5500 with hardware TCP/IP stack
- 🖥️ **Web Dashboard**: Real-time control panel with AJAX polling
- 📡 **Ultrasonic Sensor**: HC-SR04 distance measurement with hardware timer
- 🎛️ **PWM Control**: LED brightness control via web slider
- 💡 **LED Control**: ON/OFF control from web interface
- 🖥️ **LCD Display**: 16x2 I2C display with menu system
- 📨 **Web-to-LCD Messaging**: Send messages from browser to LCD
- 🎛️ **Push Button**: Physical button for LCD mode switching
- 🔧 **Serial Debugging**: UART output for system monitoring

### 📋 Requirements Met

| Requirement | Status |
|-------------|--------|
| ARM Cortex-M3 Processor | fullfilled |
| I/O Interface (LCD, Button) | fullfilled |
| Sensor Interface | fullfilled |
| ARM Capabilities Exploitation | fullfilled |
| Communication Protocol (SPI, Ethernet) | fullfilled |
| Modern IDE (STM32CubeIDE) | fullfilled |
| Working Prototype |  |

---

## 🏗️ System Architecture

### Hardware Components

| Component | Quantity | Specification |
|-----------|----------|---------------|
| STM32F103C8T6 | 1 | ARM Cortex-M3, 72MHz |
| W5500 Ethernet Module | 1 | Hardware TCP/IP Stack |
| HC-SR04 Ultrasonic Sensor | 1 | 2cm-400cm Range |
| 16x2 LCD with I2C Backpack | 1 | 16x2 Characters |
| LEDs (Various Colors) | 3 | 5mm |
| Push Button | 1 | Tactile Switch |
| FT232 USB-TTL | 1 | Serial Debug |

### Pin Connections

| STM32 Pin | Function | Connected To |
|-----------|----------|--------------|
| PA5 | SPI SCK | W5500 |
| PA6 | SPI MISO | W5500 |
| PA7 | SPI MOSI | W5500 |
| PA4 | CS | W5500 |
| PA3 | RST | W5500 |
| PB6 | I2C SCL | LCD |
| PB7 | I2C SDA | LCD |
| PB0 | TRIG | HC-SR04 |
| PA8 | ECHO (TIM1) | HC-SR04 |
| PC14 | LED (ON/OFF) | LED |
| PA1 | PWM (TIM2) | LED |
| PA2 | Parking Alert | LED |
| PB1 | Button Input | Push Button |
| PA9 | UART TX | FT232 |

---

## 🛠️ Software Architecture

### Project Structure


### Key Functions

| Function | Description |
|----------|-------------|
| `W5500_Init()` | Initialize Ethernet module |
| `httpServer_setup()` | Setup HTTP server with CGI |
| `predefined_get_cgi_processor()` | Handle GET requests |
| `predefined_set_cgi_processor()` | Handle POST requests |
| `HAL_TIM_IC_CaptureCallback()` | Ultrasonic distance measurement |
| `led_Control()` | Control LED ON/OFF |
| `pwm_Set()` | Set PWM duty cycle |

### Serial Monitor Output
```text
=================================
STM32 System Started!
WIZCHIP Initialized
Checking Link Status..
Link: UP
Using Static IP..
Configuring DNS..
IP: 192.168.1.4
SUBNET: 255.255.255.0
GATEWAY: 192.168.1.1
DNS: 8.8.8.8
HTTP Server started on sockets 0 and 1
```

## 🚀 Getting Started

### Prerequisites

| Software | Version | Purpose |
|----------|---------|---------|
| STM32CubeIDE | Latest | Development |
| STM32CubeMX | Latest | Configuration |
| ST-Link Driver | Latest | Programming |
| Serial Terminal | Any | Debugging |

### Installation


