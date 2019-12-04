# raspberrypi_camera_streamer

A python program for streaming raspberry pi camera

This is a fork of [yasinarabi github project](yasinarabi/raspberrypi_camera_streamer) added with more info on
how to try it using a Raspbian Buster Linux distribution.

## Step-by-step procedure

Download the Raspbian Buster Line image from the [official Raspberry download page](https://www.raspberrypi.org/downloads/raspbian/) and write the microSD ussing [Balena Etcher](https://www.balena.io/etcher/) utility.

Boot the MicroSD on your Raspberry Pi, get the access to the command line and install python3-pycamera package

    sudo apt update
    sudo apt install python3.py

Check the IP address assigned to your Raspberry Pi by typing:

    ifconfig

Download on your home directory the file stream.py  

     wget .....
  
Launch stream.py

    python3 stream.py
  
Open a web browser on your PC and get the access to this URL:

* http://raspberry_ip:8001/stream.mjpg
 
 
  
