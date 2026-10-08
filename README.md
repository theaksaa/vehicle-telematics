# Vehicle Telematics System

An end-to-end IoT vehicle telematics system for collecting, transmitting, processing, and visualizing real-time vehicle data.

The system combines embedded firmware, cellular communication, a secure MQTT infrastructure, a Java backend, and a web dashboard to monitor vehicle activity and analyze driving data.

## Features

- **Vehicle Telemetry** — Collect GPS location, speed, engine RPM, and other vehicle parameters through GNSS and CAN bus (OBD-II).
- **Cellular Connectivity** — Transmit telemetry over a cellular network using MQTT with mutual TLS authentication.
- **Vehicle Tracking** — Monitor fleet vehicles and their locations on an interactive map.
- **Trip History & Playback** — Explore recorded trips, visualize routes, and replay historical telemetry.
- **Driving Analytics** — Analyze vehicle speed, RPM, and other telemetry data using interactive charts.
- **Device Management** — Support device connectivity states and MQTT-based configuration channels.

## System Architecture

The system is divided into four independent components:

**Vehicle Sensors (CAN / GNSS)** → **Embedded Firmware** → **Cellular Network** → **MQTT Broker** → **Spring Boot Backend** → **React Dashboard**

The backend processes incoming telemetry, stores vehicle and trip data in PostgreSQL, and exposes it to the frontend through APIs.

## Repositories

| Component | Description |
|---|---|
| [Firmware](https://github.com/theaksaa/vehicle-telematics-firmware) | Zephyr RTOS firmware for collecting vehicle data through CAN/OBD-II and GNSS, and transmitting it over cellular MQTT. |
| [Backend](https://github.com/theaksaa/vehicle-telematics-backend) | Spring Boot application responsible for MQTT ingestion, data persistence, authentication, and REST APIs. |
| [Frontend](https://github.com/theaksaa/vehicle-telematics-frontend) | React dashboard for vehicle tracking, trip visualization, playback, and analytics. |
| [Infrastructure](https://github.com/theaksaa/vehicle-telematics-infrastructure) | Docker-based Eclipse Mosquitto MQTT broker with mutual TLS authentication and certificate management. |

## Technology Stack

| Layer | Technologies |
|---|---|
| Embedded | C, Zephyr RTOS, STM32, CAN Bus, OBD-II, GNSS |
| Connectivity | SIMCom A7670E, Cellular, MQTT, TLS/mTLS |
| Backend | Java 21, Spring Boot, Spring Security, Spring Data JPA, Flyway |
| Database | PostgreSQL |
| Frontend | React, TypeScript, Vite, Tailwind CSS, Leaflet |
| Infrastructure | Docker, Eclipse Mosquitto, OpenSSL |

## Getting Started

Each component is maintained in a separate repository and can be configured independently.

1. **Infrastructure** — Set up the MQTT broker and generate TLS certificates.
2. **Backend** — Configure the environment, start PostgreSQL, and run the Spring Boot application.
3. **Frontend** — Configure the backend URL and start the Vite development server.
4. **Firmware** — Build and flash the Zephyr application onto the supported STM32 board and configure the cellular connection.

Refer to the individual repositories for component-specific configuration and implementation details.

---

**Project Status:** Under active development.
