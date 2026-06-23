# 🧠 STM32 Physics Engine & Game Development
### Embedded Real‑Time Physics Simulation using MPU6050 IMU and SWV ASCII Renderer

![STM32F407](https://img.shields.io/badge/MCU-STM32F407VG-blue)
![Language](https://img.shields.io/badge/Language-C-brightgreen)
![Interface](https://img.shields.io/badge/Interface-I2C%20%7C%20PWM%20%7C%20SWV-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 🎯 Overview
This project implements a **real‑time physics‑based game engine** on the **STM32F407VG** microcontroller.  
The player tilts the board to move a ball, avoids obstacles, and aims for the highest score.  
All game visuals are rendered as ASCII frames in the **SWV ITM Data Console**.

---

## 🧩 Features
- **IMU Tilt Control:** Reads MPU6050 accelerometer data via I2C for motion input.  
- **Physics Engine:** Calculates velocity, acceleration, and collision boundaries in real time.  
- **Particle System:** Generates dynamic effects for movement and collisions.  
- **Audio Feedback:** Uses TIM3 PWM output for sound effects.  
- **Flash Persistence:** Saves high score to Flash Sector 11.  
- **SWV ASCII Renderer:** Displays game frames and menus in the ITM Data Console.

---

## 🛠️ Hardware Setup
| Component | Connection | Description |
|------------|-------------|-------------|
| STM32F407VGTx | Main MCU | Runs the physics engine |
| MPU6050 | I2C1 (SCL = PB6, SDA = PB7) | Provides tilt data |
| USER Button | PA0 | Starts/restarts the game |
| SWO Pin | PB3 | Outputs ASCII frames via SWV |
| TIM3 | PWM Output | Generates sound effects |

---

## ⚙️ Software Configuration
- **Debug Interface:** Serial Wire (SWD)  
- **SWV Clock:** 2 MHz  
- **Core Clock:** 84 MHz  
- **Port 0:** Enabled for ITM output  
- **CubeMX:** SYS → Debug = Serial Wire  

---

## 📂 Project Structure
├── Core/
│   ├── Src/
│   │   ├── main.c
│   │   ├── physics.c
│   │   ├── game.c
│   │   ├── renderer.c
│   │   ├── audio.c
│   │   ├── mpu6050.c
│   │   └── flash.c
│   └── Inc/
│       ├── physics.h
│       ├── game.h
│       ├── renderer.h
│       ├── audio.h
│       ├── mpu6050.h
│       └── flash.h
├── Drivers/
│   └── STM32F4xx_HAL_Driver/
├── SWV_Output/
│   └── game_log.txt
└── README.md
