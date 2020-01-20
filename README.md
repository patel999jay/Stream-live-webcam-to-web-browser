# Stream-live-webcam-to-web-browser
How to stream a webcam to a web browser in Ubuntu / Linux

Grrrrr this took hours to figure out.  I was trying to install MJPG-streamer and running VLC command lines and all this crap but nothing worked.

Found this veru useful.

First install `motion`:

    ~> sudo apt-get install motion

Then create a config file:

    ~> mkdir ~/.motion
    ~> nano ~/.motion/motion.conf

In it, the bare minimum to run a web server and view it on other computers:

    webcam_port 8081
    webcam_localhost off

Or you can use this modified config file whatever you want.

    stream_quality 98
    stream_maxrate 5
    stream_port 8080
    stream_localhost off
    output_pictures off
    framerate 30
    ffmpeg_video_codec mpeg4
    http://192.168.0.34:8080/jay.cgi //This is specific to my case, this might be different for you.
    width 320
    height 240
    auto_brightness off
    contrast 0
    saturation 0

Then run motion:

    ~> motion

Now you can view the webcam at 'http://192.168.0.34:8080/jay.cgi' 

If it doesn't work, try rebooting between steps or something.

Isn't that easy?  >:(

If you want to attach to domain, please this post <https://gist.github.com/endolith/2052778#gistcomment-2942512>
