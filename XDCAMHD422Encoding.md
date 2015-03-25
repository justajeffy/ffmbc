# Introduction #

How to encode your content to XDCAMHD422 MXF or MOV

# Details #

Interlaced encoding: add: -tff or -bff before -target

## MXF ##

`ffmbc -i < file > -target xdcamhd422 < file.mxf >`

Note: XDCAM transfer supports no fewer than 2 mono tracks channels.
Use -newaudio and -map\_audio\_channel.

As an example, this command takes a stereo source file and makes an output file with two mono tracks.

`ffmbc -i < file > -target xdcamhd422 -an < file.mxf > -acodec pcm_s24le -ar 48000 -newaudio -acodec pcm_s24le -ar 48000 -newaudio -map_audio_channel 0:1:0:0:1:0 -map_audio_channel 0:1:1:0:2:0`

This output file is compatible with Sony XDCAM Viewer.

## MOV ##

`ffmbc -i < file > -target xdcamhd422 -vtag < tag > < file.mov >`

Select tag from the following:

  * "xd54" XDCAM HD422 720p24 CBR
  * "xd59" XDCAM HD422 720p60 CBR
  * "xd5a" XDCAM HD422 720p50 CBR
  * "xd5b" XDCAM HD422 1080i60 CBR
  * "xd5c" XDCAM HD422 1080i50 CBR
  * "xd5d" XDCAM HD422 1080p24 CBR
  * "xd5e" XDCAM HD422 1080p25 CBR
  * "xd5f" XDCAM HD422 1080p30 CBR