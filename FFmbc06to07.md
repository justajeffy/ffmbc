# Introduction #

Two command line options changed between FFmbc 0.6 and FFmbc 0.7.

## Interlaced aware scaling ##

If you require interlaced aware scaling and you are using FFmbc 0.7 then add **:interl=1** to the end of any **-vf scale** command to enable interlaced aware scaling.

This is a change from previous FFmbc versions, which previously required only **:1** to be added the the end of a **-vf scale** command.

  * Non-interlaced aware scaling:
```
-vf scale=720:576
 or
-vf scale=720:576:interl=0
```
  * Force Interlaced scaling:
```
-vf scale=720:576:interl=1
```
  * Use interlaced scaling if the input is interlaced:
```
-vf scale=720:576:interl=-1
```

## Flagging interlaced material ##

If you are encoding interlaced material it is important that you flag it as such. This allows the encoder to optimise its encoding for interlaced material, and stops encoders from optimising out interlaced detail.

  * if you are encoding Top Field First (PAL SD D10, all (?) interlaced HD, and many others) then use the encoding parameter **-tff**
  * if you are encoding Bottom Field First (PAL SD DV, all (?) NTSC SD, and a few others) then use the encoding parameter **-bff**

This is a change from previous versions of FFmbc which used the **-top** command line option.

Also, you **DO NOT** need to use the **-flags +ildct+ilme** parameters any more when using **-tff** or **-bff**. Setting **-tff** or **-bff** automatically enables those parameters.

**-tff** is equivalent to **-top 1 -flags +ildct+ilme** on previous versions, and **-bff** is equivalent to **-top 0 -flags +ildct+ilme**.



REMEMBER: <u>always flag interlaced media as interlaced!</u>