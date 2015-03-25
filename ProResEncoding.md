# Introduction #

How to encode your content to ProRes

# Details #

The encoder behave differently based on 3 options:

  * -qscale < value > or -cqp < value >

Specify a fixed quantizer that will be used for every frame.
This is a VBR encoding method.

  * -profile < name > :
    * proxy
    * lt
    * std
    * hq

If bitrate is not specified, the bitrate will be automatically chosen
based on video resolution and will be similar to the apple encoder
for the same profile.

  * -b < bitrate >

Specify an approximately constant bit rate to use during encoding.

444 encoding: add -pix\_fmt yuv444p10 to your commandline options.