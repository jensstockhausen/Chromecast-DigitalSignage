# Chromecast-DigitalSignage
Using a chromecast device for digital signage

## The Challenge
Setup a local infrastructure digital signeage. So no cloud solutions.
Enviroment is MS Windows driven thus no complicated linux solution possible. 
Content is (mostly) generated in PPT, or single images.

## The Solution
VLC has sinces version 3.0 the capability to stream directly to chromcast sticks.

Wrapping some scripts around the commandline shal do the trick
 -v  --sout="#chromecast{ip=192.168.X.X}" --demux-filter=demux_chromecast --playlist-autostart --loop --playlist-tree d:\data

