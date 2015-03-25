# Introduction #

How to encode your content to IMX 30/50 MXF or MOV

# Details #

ffmbc -i < file > -target imx30 < file.mxf | file.mov >

ffmbc -i < file > -target imx50 < file.mxf | file.mov >

Note: in MXF, XDCAM transfer supports no less than 4 channels, so if your audio
stream is < 4 channels, the MXF muxer will mark it as 4 channels anyway.