# PIC16F690-Synchronized-Embedded-Game
Real-time distributed embedded system synchronized across two PIC16F690 microcontrollers using a custom bare-metal ISR serial protocol.

# Embedded Systems Architecture: Real-Time Synchronized Game (PIC16F690)

## Overview
This repository contains the bare-metal C firmware for a real-time, distributed embedded multiplayer game ("Fuego Cruzado") deployed across two independent Microchip PIC16F690 microcontrollers. The core challenge of this project was achieving deterministic real-time synchronization between autonomous processing units without the overhead of an RTOS.

## Key Technical Features
* **Custom Serial Protocol (ISR-Driven):** Engineered a low-latency, interrupt-based sychronous data transmission protocol from scratch to handle real-time game state synchronization (projectile physics, collisions, life cycles) without data corruption or blocking conditions.
* **Bare-Metal Concurrency:** Implemented an event-driven loop architecture using prioritized timers and hardware interrupts to manage concurrent subsystems (display multiplexing, input sampling, physics engine).
* **Hardware Integration:** Developed low-level drivers to interface with 8x8 LED matrices via the MAX7219 driver using bit-banging techniques, combined with ADC filtering for analog player inputs.

## Repository Structure
* `/src_node_A`: Firmware for the primary transmitter node (Player A).
* `/src_node_B`: Firmware for the receiver/transceiver node (Player B).
* `/docs`: Technical schematics and system architecture design documentation.

## Hardware Components
* Microcontroller: Microchip PIC16F690 (8-bit CMOS)
* Display: 8x8 LED Matrix controlled by MAX7219
* Compiler: Microchip XC8
