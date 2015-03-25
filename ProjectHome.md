FFmpeg customized for broadcast and professional usage.

Download: https://drive.google.com/folderview?id=0B0jxxycBojSwR3I4Vkp5Ul9tQXc&usp=sharing

What you can do with FFmbc:

  * Import your files in Final Cut Pro, AVID Media Composer, Adobe Premiere

  * Create XDCAM HD422 files in .mov or .mxf
  * Create XDCAM IMX/D-10 files in .mov or .mxf
  * Create AVID DNxHD files in .mov
  * Create DVCPROHD files in .mov or .mxf
  * Create ProRes 422 or 4444 files in .mov

  * Convert V210 Files
  * Convert HD YUV BT709 to SD BT601 and vice versa
  * Convert AVCIntra 50 and 100
  * Convert MPEG-TS files with SMPTE 302M audio
  * Convert AVCHD files correctly
  * Convert ProRes 422 and 4444 files

  * Rewrap IMX/D-10, AVCHD, DVCPROHD to Quicktime for editing in Final Cut Pro

  * Burn ASS or SRT subtitles files in videos

  * Merge and split your audio tracks
  * Create Quicktime files containing time code tracks
  * Color conversion from HD to SD

  * Read timecode tracks from MXF, Quicktime
  * Creating audio files (mp3 and m4a) with cover art
  * Keep or add covert art when converting your audio files
  * Faststart MP4 for streaming (replace header in front) automatically

Current stable release is version 0.7.1

FFmbc license is GPL v2

Please contact baptiste.coudurier@gmail.com for:
- consulting work
- commercial support

Several years of expertise in broadcast codecs: ProRes, DNxHD, IMX/D-10, AVC-Intra,
formats: MXF, GXF, MOV and usages: Avid, FCP, interlacing, time code, metadata.

Please support the project by donating. Thanks a lot.

Any help is welcome:
  * Documentation help
  * Wiki pages describing processes and workflow
  * File validation: testing files created by FFmbc with Avid Media Composer, Adobe Premiere, Sony Vegas, etc...

Please join Freenode irc channel #ffmbc to get online help.
Ask any question on the ffmbc-dev or ffmbc-discuss groups.

[![](https://www.paypal.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=YZXVPDXN68FDG)

FFmbc-0.7.2:
**Support XAVC in Quicktime** Remove ffplay

FFmbc-0.7.1:
  * Support AVCIntra 23.98p in MXF

FFmbc-0.7:
  * Sync on FFmpeg git 7cbb856efe6ccab7485bb96ad3887472a6519ffa
  * New -tff and -bff cli options, -top is removed
  * AVCIntra decoding is now supported
  * Parallel frame multi-threaded decoding is now enabled
  * Prores 422 and Prores 4444 decoding
  * When writing MXF files, use more correct key for KLV Fill packets
  * DVCPROHD encoding in Quicktime or MXF format is now supported
  * Fix detection of some DVCAM files
  * Fix decoding artefact in bottom rows of Quantel DVCPROHD 1080i files
  * Support reading AVID MXF OpAtom DNxHD files
  * New video filter 'sub' to burn ASS and SRT subtitles
  * New 'dvcam', 'dvcpro', 'dvcpro50', 'dvcprohd' targets
  * Detect right to left languages in subtitle burning filter
  * Correctly write drop frame system timecode and continuity count in MXF files
  * Correctly use global file duration when displaying information about Quicktime files
  * Correctly compute aspect ratio from clean aperture in Quicktime files
  * Display starting system timecode for MXF files
  * FFprobe now correctly displays width and height for files using h264 cropping
  * DV muxer changed to only accept big endian pcm
  * Audio sync disabled by default for GXF files
  * Prores encoder with support for interlaced, 422 and 444
  * Support writing AFD information in MXF files
  * Support V210 and uncompressed 4:2:2 UYVY in MXF files
  * Support P2 MXF files
  * Support Op1a MXF DNxHD files
  * Fix avisynth RGB24/32 upside-down decoding
  * Fix DPX encoding, now compatible with Nuke
  * Improved MXF muxer compatibility with Sony Vegas Pro 11
  * Support encoding H.264 10 bit and 4:2:2 with x264
  * Improved Quicktime muxer compatibility with Final Cut Pro and XDCAMHD 422
  * Commandline options -vcodec,-acodec,-scodec are not reset anymore between streams
  * Faster V210 decoding
  * Support writing MXF DNxHD files
  * .mpg extension will now produce MPEG-2 PS by default
  * Removed IMX bitstream filters, formatting is now done automatically
  * Framerate now needs to be explicitely specified when reading raw uncompressed video files
  * H264 encoding in MXF format is now supported
  * Progressive Quicktime files created will now be properly recognized by FCP
  * New filters from BBC: waveform monitor, w3fdif deinterlacing, stretch4to3, repeatframe
  * New -metadata\_tags cli option to see what metadata tags are supported in each output format
  * Export MPEG-2 GOP timecode as metadata
  * Correctly read interlaced information from DV files
  * DV files produced are now more standard compliant
  * Improved quality for the ProRes encoder
  * Support creating AVCIntra Quicktime files compatible with FCP
  * New avcintra100 target supported for Quicktime and MXF files

FFmbc-0.6.1:
  * Fix compilation on OSX with Xcode 4.1
  * MPEG-2 3:2 pulldown encoding is now supported
  * Fix > 16bit pcm stream copy in wav

FFmbc-0.6:
  * Fix auto-rotate iphone 4 files
  * Increase maximum number of audio channel mappings to 64
  * New "aspect" option to pad filter, to pad video to a specific display aspect ratio
  * New parameter to crop filter to keep display aspect ratio when cropping
  * Improve yuv 4:2:2 to rgb conversion quality
  * Fix aspect ratio handling with libavfilter
  * Re-enabled shared libraries support
  * Fix DNxHD colors in Quicktime
  * Print correct ratecontrol and bitrate information when encoding
  * Write id3v2 v2.3 tags in mp3 files, compatible with Windows
  * Support stream copying and muxing of AMR NB packed frames
  * Flash F4V muxer, to allow muxing vp6 and mp3 the way Flash supports it
  * New options for libx264 codec, update your commandlines parameters
  * You can now specify -preset, -tune and -fastfirstpass with libx264 codec
  * Print progression time in hh:mm:ss.us instead of secs
  * New "faststart" option in mov/mp4 muxer that automatically replace the header in front
  * Print ETA if duration is known
  * New "tinterlace" filter ported from mplayer
  * Allow one video filter chain per output stream
  * Fix yadif filter output, it was missing one frame previously
  * New "imx50" and "imx30" targets, to make encoding simpler
  * If audio channel count is less than 4 in MXF D10, automatically set it to 4
  * Automatically set vbv buffer size to the maximum when encoding mpeg-2 cbr
  * New "xdcamhd422" target
  * Support DVCAM 4:2:0 in GXF
  * Write aspect ratio information in GXF files
  * With libx264 codec, correctly support specifying a custom 2pass log file
  * When duplicating frames, correctly duplicate the previous frame
  * Enhance -metadata option, can now take comma separated tag=value pairs
  * Experimental mplayer filters support using -vf mp
  * Mux DVCPRO HD in quicktime correctly
  * Allow DNxHD encoding with Avid Nitris compatibility
  * Fix decoding of 16bit png files
  * Reenable -s commandline option
  * New filter colormatrix to convert between bt 601 and bt 709
  * Hide mmx/sse2 internal symbols, to allow creating a shared library from static libraries
  * Support multiple external reference files per track in Quicktime files
  * Fix -t and -vframes by considering output
  * Mpeg-2 encoder now sets correct aspect ratio even with square pixels
  * Mpeg-2 encoder now writes sequence display extension if color primaries are specified
  * Dithering when downsampling from 10 bits to 8 bits
  * Options are now reset between -i, output files and -newaudio,-newvideo parameters
  * Display starting time code for MXF and Quicktime files
  * Remove FFserver
  * Fix Avisynth input audio stream timebase

FFmbc-0.5:
  * Sync on FFmpeg svn [r25202](https://code.google.com/p/ffmbc/source/detail?r=25202)
  * Yadif video deinterlacing filter
  * Overlay video filter
  * Fade video filter
  * HQDn3d video filter
  * Rename ffmpeg binary to ffmbc
  * Disable shared libraries
  * Remove -s resizing output cli option, use -vf scale
  * 23.98 and 24 fps support in MXF muxer
  * Mpeg-2 aspect ratio bitstream filter, to change aspect ratio without reencoding
  * Fix an issue with -async and audiomerge
  * Fix an issue with the fade filter
  * Write interlacing information in mov files, fix deinterlacing with quicktime player
  * Correctly support interlaced in yuv4mpeg and quicktime
  * Display interlacing when printing information
  * Fix an issue with resampling and audiomerge

FFmbc-0.4:
  * Sync on FFmpeg svn [r21845](https://code.google.com/p/ffmbc/source/detail?r=21845)
  * Full support for reading and writing covert art in mp3 and iTunes m4a,m4v,mp4
  * "-coverfile" commandline option to set a cover file. png,jpg,bmp supported
  * Correctly write Quicktime metadata as utf-8
  * Fixed a bug with temporal offset when muxing mpeg-2 long gop in MXF
  * Huge speedup when opening Quicktime and mpeg-4 files
  * Timecode for Quicktime and MXF files can now be set when stream copying
  * Added x264 sources in contrib directory, git 5b86182d1240b441f28462abf3d40b7371de5ba3
  * Enable pthreads by default
  * Fixed a bug with interlaced VC-3 decoding
  * Integrate libavfilter. New commandline option -vf, see doc/libavfiter.texi
  * Auto-rotate iPhone 3GS files
  * Support lyrics in mp3 and iTunes m4a,m4v,mp4
  * Automatically set current UTC time in created files
  * New AVFMT\_HAS\_PTS flag in AVInputFormat to specify that format has pts
  * Write and read metadata "reel\_name" in mov timecode track if present
  * MPEG TS muxer now produces streams playable by VLC and Quicktime

FFmbc-0.3:
  * Sync on FFmpeg svn [r20539](https://code.google.com/p/ffmbc/source/detail?r=20539)
  * Write Quicktime timecode track
  * Set closed gop flag for first gop when encoding with b frames
  * Search relative path when open Quicktime reference files

FFmbc-0.2:
  * Sync on FFmpeg svn [r19958](https://code.google.com/p/ffmbc/source/detail?r=19958)
  * Advanced Metadata support
  * S302M decoder
  * XDCAM HD 422 muxer
  * MXF 720p muxing
  * New RM demuxer

FFmbc-0.1:
  * D10/IMX bitstream filter to remove klv header from D10/IMX elementary stream to be copied in MXF
  * "-map\_audio\_channel" commandline option to split and merge audio channels
  * "-timecode" commandline option to set timecode start when encoding