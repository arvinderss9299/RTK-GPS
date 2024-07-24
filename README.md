# RTK GNSS Data Collection and Analysis

## Project Overview

This repository contains code and documentation for a GNSS (Global Navigation Satellite System) data collection and analysis project. The objective of this project was to evaluate the performance of RTK (Real-Time Kinematic) GNSS systems in various environments and conditions. The project involved setting up GNSS hardware, collecting data, and performing detailed analysis on the collected datasets.

## Hardware and Sensors

The following hardware components were used in this project:

- **2 x GNSS/RTK Processing Boards**
- **2 x GNSS Antennas**
- **2 x 915 MHz Telemetry Radios** (for specific board configurations)
- **RTK GNSS Systems**:
  - EMLID Reach with Ublox NEO-M8T
  - UBLOX C009-FPP with UBLOX ZED-F9P

### Hardware Setup

The RTK GNSS system setup involves configuring a base RTK unit and a rover RTK unit, with communication between them via telemetry radios or Wi-Fi. The base unit is stationary and transmits correction data to the rover unit, which is connected to a laptop via USB-serial to receive corrected GNSS data.

For detailed setup instructions, refer to the device manual:

- **Device A**: Testing Telemetry Radios
- **Device B**: EMLID Reach RTK Setup
- **Device C**: UBLOX C009-F9P Eval Board

Ensure all sensors are configured to output NMEA strings over USB-serial. Your ROS (Robot Operating System) messages should include GNSS fix status (e.g., GNSS fix, RTK float mode, RTK fix) for effective analysis.

## Data Collection

Data was collected in two scenarios:

1. **Stationary Data**: Collected for 10 minutes with the base station fixed and the rover in RTK float or RTK fix mode.
2. **Dynamic Data**: Collected with the rover moving in a structured path (e.g., forward X meters, right Y meters, and back to the starting point).

Datasets were collected at:
- A location with partial occlusion and reflections (e.g., outside a building)
- An open location with minimal obstructions (e.g., a park or parking garage roof)

## Data Analysis

The collected UTM (Universal Transverse Mercator) data was analyzed to evaluate RTK GNSS navigation performance. The analysis included:
- Plotting and statistical evaluation of the data
- Assessing error estimates and noise distribution in the signal

For detailed analysis, see the `analysis` directory.

## How to Use

1. **Clone the Repository**: 
   ```bash
   git clone https://gitlab.com/your-username/gnss-data-analysis.git

2. **Setup Hardware**: Follow the setup instructions of your GNSS hardware.

3. **Run Data Collection**: Use the provided scripts to collect data from your GNSS setup.

4. **Analyze Data** Utilize the provided Python scripts in the analysis directory to process and visualize the collected data.