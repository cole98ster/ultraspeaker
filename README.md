# UltraSpeaker

UltraSpeaker is an ESP32-based ultrasonic directional speaker that projects audible sound toward a targeted listener using ultrasonic audio modulation. The system uses motion and ultrasonic sensing to detect a nearby user and provides a local web interface for remote control.

The project began as an Arduino-based prototype and was later migrated to ESP32. The ESP32 migration eliminated the need for an external waveform generator, simplified the driver circuit, and improved processing performance and system reliability.

## Features

- **Directional audio projection:** Uses ultrasonic modulation to create a focused beam of audible sound.
- **Human detection:** Uses a motion sensor and ultrasonic sensor to detect nearby users.
- **Local web control:** Allows users to enable or disable the speaker and sensors from a device on the same network.
- **ESP32-based control:** Handles signal generation, sensor input, Wi-Fi networking, and web-server functionality.
- **Simplified hardware design:** Removes the external waveform generator required by the original Arduino prototype.

## How It Works

Parametric speakers use high-frequency ultrasonic waves that interact with air to demodulate into audible sound. By modulating an ultrasonic carrier wave with an audio signal, the system can project sound in a narrower direction than a conventional speaker.

In this project, the ESP32 generates and controls the ultrasonic signal, reads input from the motion and ultrasonic sensors, and hosts a local web server. When a user is detected, the system can activate the directional speaker and allow the user to control it through a browser.

## Hardware

- ESP32 development board
- Ultrasonic transducer(s)
- Audio modulation / driver circuit
- Motion sensor
- Ultrasonic distance sensor
- Power supply and supporting circuitry
- Custom enclosure designed in SolidWorks

The original prototype used an Arduino Uno WiFi Rev 2 and an external waveform generator. The final version uses the ESP32 to simplify the circuit and improve performance.

## Software

- **Platform:** ESP32
- **Language:** C/C++
- **IDE:** Arduino IDE
- **Web interface:** Local Wi-Fi server
- **Sensors:** Motion detection and ultrasonic distance sensing
- **CAD:** SolidWorks

## Getting Started

### Prerequisites

- Arduino IDE or PlatformIO
- ESP32 board support installed
- USB cable for programming the ESP32
- Required Arduino libraries for Wi-Fi, web server, and sensor modules

### Installation

1. Clone the repository:

```bash
git clone [https://github.com/cole98ster/ultraspeaker.git](https://github.com/cole98ster/ultraspeaker.git)
cd ultraspeaker
```

2. Open the project in Arduino IDE or PlatformIO.

3. Install the required ESP32 board package and libraries.

4. Update the Wi-Fi credentials in the firmware:

```cpp
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";
```

5. Select your ESP32 board and upload the firmware.

## Usage

1. Power on the ESP32.
2. Connect to the same Wi-Fi network as the device.
3. Open the ESP32’s local IP address in a web browser.
4. Use the web interface to enable or disable the speaker and sensors.
5. Move within range of the sensors to test detection and audio activation.

## Project Structure

```text
ultraspeaker/
├── src/               # ESP32 firmware source code
├── old/               # Original Arduino Code used with the driver circuit
└── README.md
```

## Development Notes

The initial version used an Arduino Uno WiFi Rev 2 to drive an external waveform generator and produce a stable 40 kHz sine wave. While functional, this approach required additional hardware and increased circuit complexity.

The system was later migrated to ESP32, allowing the microcontroller to handle signal generation directly. This reduced component count, simplified the driver circuit, and enabled more reliable web-based control.

## Safety

Ultrasonic audio equipment can produce high-frequency sound that may be uncomfortable at close range or high volume. Use appropriate caution when testing the system, avoid prolonged close-range exposure, and follow safe operating practices for all electronic components.

## Future Improvements

- Add real-time audio streaming from a phone or computer
- Improve beam-steering and targeting
- Add a mobile-friendly control interface
- Integrate battery power and power-management features
- Improve enclosure design for acoustics and durability
- Add automatic calibration for sensor thresholds

## Credits

Initial circuit concepts and ultrasonic speaker theory were informed by publicly available educational resources, including GreatScott!’s parametric speaker content on YouTube.

## Author

**Cole Neild**  
[LinkedIn](https://www.linkedin.com/in/cole-neild/)  
[GitHub](https://github.com/cole98ster)
