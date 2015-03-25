# Introduction #

How to burn subtitles on the video.
The video filter supports .srt and .ass files

You need libass compiled in your FFmbc binary to be able
to burn subtitles.

# Details #

Options:
  * file:       set subtitles file
  * font:       set font file
  * textcolor:  set text color
  * boxcolor:   set box background color (format is RRGGBBAA)
  * box:        a box will surround the text
  * fontsize:   set font size
  * text:       set text to be burned
  * vmargin:    set vertical margin

ffmbc -i < file > -vf sub=file=captions.srt:box=1:boxcolor=0x00000080:font=arial.ttf < out file >