# raspberrypi_camera_streamer

A python program for streaming raspberry pi camera

This is just a fork of [yasinarabi github project](https://github.com/yasinarabi/raspberrypi_camera_streamer) 
original project with more detailed info on how to try it using a Raspbian Buster Linux distribution.

## Step-by-step procedure

Download the Raspbian Buster Line image from the [official Raspberry download page](https://www.raspberrypi.org/downloads/raspbian/) and write the microSD ussing [Balena Etcher](https://www.balena.io/etcher/) utility.

Boot the MicroSD on your Raspberry Pi, get the access to the command line and install python3-pycamera package

    sudo apt update
    sudo apt install python3-picamera

Enable the Raspberry Pi camera interface using

    sudo raspi-config

Check the IP address assigned to your Raspberry Pi by typing:

    ifconfig

Download on your home directory the file stream.py  

     wget https://raw.githubusercontent.com/tanzilli/raspberrypi_camera_streamer/master/stream.py
  
Launch stream.py

    python3 stream.py
  
Open a web browser on your PC and get the access to this URL:

* [http://raspberry_ip:8001/stream.mjpg]([http://raspberry_ip:8001/stream.mjpg)

## Launch stream.py at startup

Create a filed called __/lib/systemd/system/stream.service__ with the follow content:

    [Unit]
    Description=stream.py
    After=systemd-user-sessions.service

    [Service]
    ExecStart=python3 stream.py
    Restart=on-abort
    User=pi
    WorkingDirectory=/home/pi

    [Install]
    WantedBy=multi-user.target

## Enable the new service:

    sudo systemctl daemon-reload
    sudo systemctl enable stream.service
    sudo systemctl start stream.service

## Links

* [Python3-Picamera documentation](https://picamera.readthedocs.io/en/release-1.13/index.html)
 
  
