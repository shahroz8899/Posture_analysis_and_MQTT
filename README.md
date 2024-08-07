# Posture_analysis_and_MQTT


# Image Receiver and Message Sender to Raspberry Pi

## Overview

This project consists of several Python scripts designed to work together to capture images, process them to find key points using OpenPose, and send posture information to a Raspberry Pi via MQTT. The Raspberry Pi controls LEDs based on the received posture information.

## Contents

- `image_receiver_and_massage_sender_to_rasberry.py`: Captures images, processes them using OpenPose, and sends posture information via MQTT.
- `mqtt_receiver.py`: Receives posture information via MQTT.
- `mqtt_sender.py`: Sends posture information via MQTT.
- `image_capture_mqtt.py`: Captures images periodically and publishes them to an MQTT topic.
- `massage_get_mqtt.py`: Receives posture information from MQTT and controls LEDs on the Raspberry Pi.

## Requirements

- Python 3.x
- OpenCV
- NumPy
- Paho-MQTT
- GPIO Zero (for controlling LEDs on Raspberry Pi)
- TensorFlow
- SciPy

## Installation

1. **Clone the Repository:**
    ```sh
    git clone https://github.com/shahroz8899/Posture_analysis_and_MQTT
    cd your_repository
    ```

2. **Install Required Libraries:**
    ```sh
    pip install opencv-python numpy paho-mqtt gpiozero tensorflow scipy
    ```

## Configuration

- Ensure your MQTT broker is configured and accessible. Update the MQTT broker details in the scripts if necessary.

## Running the Scripts

### Image Receiver and Message Sender

This script captures images, processes them to find key points using OpenPose, and sends posture information via MQTT.

```sh
python image_receiver_and_massage_sender_to_rasberry.py
```

### MQTT Receiver

This script listens for posture information sent via MQTT and performs further processing.

```sh
python mqtt_receiver.py
```

### MQTT Sender

This script sends posture information via MQTT.

```sh
python mqtt_sender.py
```

### Image Capture and MQTT Publisher

This script captures images periodically and publishes them to an MQTT topic.

```sh
python image_capture_mqtt.py
```

### Message Receiver and LED Controller

This script runs on the Raspberry Pi, receives posture information from MQTT, and controls LEDs accordingly.

```sh
python massage_get_mqtt.py
```

## File Descriptions

### `image_receiver_and_massage_sender_to_rasberry.py`
- Captures images using OpenCV.
- Uses a pre-trained model to find key points in the images.
- Sends posture information via MQTT.

### `mqtt_receiver.py`
- Receives posture information via MQTT for further processing.

### `mqtt_sender.py`
- Sends posture information via MQTT.

### `image_capture_mqtt.py`
- Captures images periodically.
- Publishes images to an MQTT topic.

### `massage_get_mqtt.py`
- Runs on Raspberry Pi.
- Receives posture information from MQTT.
- Controls LEDs based on the received posture information.

## Usage

1. Start the MQTT broker.
2. Run `image_capture_mqtt.py` to start capturing images and publishing them to the MQTT topic.
3. Run `image_receiver_and_massage_sender_to_rasberry.py` to process images and send posture information.
4. Run `massage_get_mqtt.py` on the Raspberry Pi to control the LEDs based on the received posture information.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- OpenPose for the pose estimation model.
- Paho MQTT for the MQTT library.
- GPIO Zero for the Raspberry Pi GPIO control.

---

