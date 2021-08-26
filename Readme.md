flutter + webrtc => python + aiortc + opencv
======

This demo project should help you to get setup sending a video feed from a flutter app to a python backend to allow you to then perform some image processing on the video frames using OpenCV.

Running the server
-------

First install the required packages:

.. code-block:: console
    
    $ cd server
    $ pip install aiohttp aiortc opencv-python

When you start the example, it will create an HTTP server which you
can connect to from your browser:

.. code-block:: console
    
    $ cd server
    $ python server.py

You can then browse to the following page with your browser:

http://127.0.0.1:8080

Once you click `Start` the browser will send the audio and video from its
webcam to the server.

The server will play a pre-recorded audio clip and send the received video back
to the browser, optionally applying a transform to it.

In parallel to media streams, the browser sends a 'ping' message over the data
channel, and the server replies with 'pong'.

Additional options
------------------

If you want to enable verbose logging, run:

.. code-block:: console

    $ cd server
    $ python server.py -v

Running the server in docker
-------

.. code-block:: console
    
    $ cd server
    $ docker build -t aiortc_server .

    $ docker run -p 8080:8080 -it --rm aiortc_server

You can then browse to the following page with your browser:

http://127.0.0.1:8080


Setting up flutter
------------------

...

Credits
-------

The server files were borrowed from the aiortc github project.

https://github.com/aiortc/aiortc