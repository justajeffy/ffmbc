# Introduction #

Installing FFmbc-06-rc3 on a Debian Testing Based System. My build system is a fresh install of Linux Mint Debian (LMDE). It's based on Debian Testing.

# How-To #

First, we need to update the sources list. Depending on your distribution, you may not need to do this. LMDE already has this repository added. I use pico as my text editor. Feel free to use nano, vi or emacs if you prefer.

Go to the Debian Multimedia repository site and download the keyring package. Follow the instructions for unpackaging it about half-way down the front page. Now update your sources list:

>sudo pico /etc/apt/sources.list

Add "deb http://www.debian-multimedia.org testing main" on a new line and save the file.

>sudo apt-get update
>sudo apt-get upgrade

Now you’re using the latest sources and packages.

I used to build x264 direct from source. I've found that the Debian Multimedia repository has a packaged version from February 12th, 2011 available. That's new enough, so I just installed the library package.

Next, install all the additional libraries we’ll need:

>sudo apt-get install build-essential yasm libgpac-dev libdirac-dev libgsm1-dev libschroedinger-dev libspeex-dev libvorbis-dev libopenjpeg-dev libdc1394-22-dev libsdl1.2-dev zlib1g-dev texi2html libfaac-dev libmp3lame-dev libtheora-dev libxvidcore4-dev libopencore-amrnb-dev libopencore-amrwb-dev frei0r-plugins-dev libcv-dev libvpx-dev libgavl1 libx264-dev

Now to configure FFmbc. There’s so many options, it’s sometimes hard to know which ones to choose. The list below is my personal preference, but do try ./configure –help to assist in choosing your own.

>./configure --enable-gpl --enable-version3 --enable-nonfree --enable-shared --enable-postproc --enable-runtime-cpudetect --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-frei0r --enable-libdc1394 --enable-libdirac --enable-libfaac --enable-libgsm --enable-libmp3lame --enable-libopenjpeg --enable-libschroedinger --enable-libspeex --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-pthreads --enable-libxvid --enable-zlib

After a successful configuration, all the enabled decoders, encoders and muxers will be displayed. There are some configuration dependencies here. If you don’t –enable-gpl things like postproc will fail at build time. Next….

>make

>sudo make install

“Make” will probably take quite a long time. Hopefully it will all proceed without any fatal errors.

In the past, I recommended manually building qt-faststart. A little utility that moved header atoms in mpeg4 files to allow for progressive downloads. This is not required for FFmbc as  -faststart is now a switch within the mp4 muxer.

Finally, it would still seem that simply typing “ffmbc” on the command line will throw an error regarding shared libraries (we did build FFmbc with –enable-shared). To fix this we do the following:

>sudo pico /etc/ls.so.conf

Add the line “/usr/local/lib” (without quotes) to this file and then save it. Read more about dynamically linked libraries here, specifically the fourth paragraph to explain what we just did. Then:

>sudo ldconfig

We're finished! Next thing for you to do is learn how to use it...... Most FFmpeg tutorials will be valid, as FFmbc is regularly synchronised on FFmpeg, but also read the information on the FFmbc project pages about how to use the XDCAM HD and IMX/D10 presets.

I did strike one problem trying to install FFmbc with OpenCV support. It's been reported and I'm sure will be addressed soon.

This How To taken directly from my blog post on Stream #0 - http://stream0.org