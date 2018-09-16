# nginx-rtmp-hls-live-streaming-Server-Installation

Installation
install on debian based distribution

step 1:
git clone https://github.com/AysadKozanoglu/RTMP_MEDIA_STREAMING_SERVER.git

step 2:
cd RTMP_MEDIA_STREAMING_SERVER && chmod +x install-rtmp-server.sh && ./install-rtmp-server.sh

after installation you will see DONE message.

Beginning to stream to your server with your local pc or similar
use ffmpeg to stream to your server like now:

ffmpeg -i http://trtcanlitv-lh.akamaihd.net/i/TRT1HD_1@181842/index_1500_av-b.m3u8 -vcodec copy \
   -vprofile baseline -acodec aac -strict -2 -f flv -r 15 rtmp://<your-server-IP>/show/trthd

or you can stream your own desktop screen like this in live

ffmpeg -f x11grab -r 15 -s 1280x720 -i :0.0+0,24 -vcodec libx264  \ 
       -threads 0 -f flv rtmp://<your-server-IP>/show/MyScreen
you can watch your live streams with vlc or similar player with below links now:

http://<your-server-IP>:8080/rtmp-hls/trthd.m3u8

or

http://<your-server-IP>:8080/rtmp-hls/MyScreen.m3u8

statistic and status
you can use the following link to see your server statistics:

http://<your-server-IP>:8080/stat
