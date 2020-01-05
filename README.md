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



# Creating Content

## Videos from PPT


## Images
Sime ffmpeg magic:

cat listt.txt | sed "s/^/file \'/" | sed "s/JPG/JPG\'/" > list.txt 

ffmpeg -f concat -r 1/2 -safe 0 -i list.txt -vf "scale=iw*min(1920/iw\,1080/ih):ih*min(1920/iw\,1080/ih), pad=1920:1080:(1920-iw*min(1920/iw\,1080/ih))/2:(1080-ih*min(1920/iw\,1080/ih))/2,fps=8,format=yuv420p" -crf 20 video.mp4



