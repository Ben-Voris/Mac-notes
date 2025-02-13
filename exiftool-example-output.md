# Example output for a JPEG

I found the hex string file name by poking around and generated the following
output with the shell command:

```shell
find ~/Pictures -name '0FB91698-EF23-48BF-96A9-F7902A77E118*' -exec exiftool "{}" \;
```

1. [./resources/renders/0/0FB91698-EF23-48BF-96A9-F7902A77E118_1_201_a.jpeg](#1-resourcesrenders)
    - A version of \#6 but cropped as the Photo app displays it.This file
      contains GPS data.
2. [./resources/renders/0/0FB91698-EF23-48BF-96A9-F7902A77E118.plist](#2-plist)
    - A plist is a XML document. This one contains an encoded data block that I
      cannot interpret. Whatever it is, it is still gibberish when decoded with
      base64. `exiftool` can decode at least part of this file.
3. [./resources/derivatives/0/0FB91698-EF23-48BF-96A9-F7902A77E118_1_105_c.jpeg](#3-resourcesderivatives)
    - A smaller version of \#1
4. [./resources/derivatives/masters/0/0FB91698-EF23-48BF-96A9-F7902A77E118_4_5005_c.jpeg](#4-resourcesderivativesmasters)
   - A smaller version of \#3
5. [./resources/caches/compute/0/0FB91698-EF23-48BF-96A9-F7902A77E118_5_5_c_14.dat](#5-dat-file)
    - `strings(1)` shows that this file file has the title embedded in it.
      `exiftool` does not decode it.
6. [./originals/0/0FB91698-EF23-48BF-96A9-F7902A77E118.jpeg](#6-originals)
    - The appears to be the original picture, without any edits. This file
      contains GPS data.

## 1 resources/renders

```text
ExifTool Version Number         : 13.19
File Name                       : 0FB91698-EF23-48BF-96A9-F7902A77E118_1_201_a.jpeg
Directory                       : /Users/bvoris/Pictures/Photos Library.photoslibrary/resources/renders/0
File Size                       : 381 kB
File Modification Date/Time     : 2018:11:17 21:02:26-07:00
File Access Date/Time           : 2025:02:12 15:07:09-07:00
File Inode Change Date/Time     : 2025:02:12 15:10:13-07:00
File Permissions                : -rw-------
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Exif Byte Order                 : Big-endian (Motorola, MM)
Make                            : Apple
Camera Model Name               : iPhone 6s Plus
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Software                        : 12.1
Modify Date                     : 2018:11:17 21:02:26
Exposure Time                   : 1/4
F Number                        : 2.2
Exposure Program                : Program AE
ISO                             : 64
Exif Version                    : 0221
Date/Time Original              : 2018:11:17 21:02:26
Create Date                     : 2018:11:17 21:02:26
Components Configuration        : Y, Cb, Cr, -
Shutter Speed Value             : 1/4
Aperture Value                  : 2.2
Brightness Value                : -0.3426268685
Exposure Compensation           : 0
Metering Mode                   : Spot
Flash                           : Auto, Did not fire
Focal Length                    : 4.2 mm
Subject Area                    : 3371 1811 753 756
Maker Note Version              : 10
Run Time Flags                  : Valid
Run Time Value                  : 86905262582166
Run Time Scale                  : 1000000000
Run Time Epoch                  : 0
AE Stable                       : Yes
AE Target                       : 94
AE Average                      : 101
AF Stable                       : Yes
Acceleration Vector             : 0.01901177503 -0.9801526063 -0.1676488668
Focus Distance Range            : 0.39 - 0.82 m
OIS Mode                        : 2
Image Capture Type              : Unknown (5)
Live Photo Video Index          : 0
Photos App Feature Flags        : 0
Signal To Noise Ratio           : 0
Sub Sec Time Original           : 248
Sub Sec Time Digitized          : 248
Flashpix Version                : 0100
Color Space                     : sRGB
Exif Image Width                : 1199
Exif Image Height               : 1686
Sensing Method                  : One-chip color area
Scene Type                      : Directly photographed
Exposure Mode                   : Auto
White Balance                   : Auto
Focal Length In 35mm Format     : 29 mm
Scene Capture Type              : Standard
Lens Info                       : 4.150000095mm f/2.2
Lens Make                       : Apple
Lens Model                      : iPhone 6s Plus back camera 4.15mm f/2.2
GPS Latitude Ref                : North
GPS Longitude Ref               : West
GPS Altitude Ref                : Above Sea Level
GPS Time Stamp                  : 04:02:25
GPS Speed Ref                   : km/h
GPS Speed                       : 0.94
GPS Img Direction Ref           : True North
GPS Img Direction               : 105.0434188
GPS Dest Bearing Ref            : True North
GPS Dest Bearing                : 105.0434188
GPS Date Stamp                  : 2018:11:18
GPS Horizontal Positioning Error: 50 m
XMP Toolkit                     : XMP Core 5.4.0
Creator Tool                    : 12.1
Date Created                    : 2018:11:17 21:02:26
Current IPTC Digest             : d41d8cd98f00b204e9800998ecf8427e
IPTC Digest                     : d41d8cd98f00b204e9800998ecf8427e
Image Width                     : 1199
Image Height                    : 1686
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Run Time Since Power Up         : 24:08:25
Aperture                        : 2.2
Image Size                      : 1199x1686
Megapixels                      : 2.0
Scale Factor To 35 mm Equivalent: 7.0
Shutter Speed                   : 1/4
Create Date                     : 2018:11:17 21:02:26.248
Date/Time Original              : 2018:11:17 21:02:26.248
GPS Altitude                    : 821.9 m Above Sea Level
GPS Date/Time                   : 2018:11:18 04:02:25Z
GPS Latitude                    : 43 deg 37' 1.50" N
GPS Longitude                   : 116 deg 12' 22.07" W
Circle Of Confusion             : 0.004 mm
Field Of View                   : 63.7 deg
Focal Length                    : 4.2 mm (35 mm equivalent: 29.0 mm)
GPS Position                    : 43 deg 37' 1.50" N, 116 deg 12' 22.07" W
Hyperfocal Distance             : 1.82 m
Light Value                     : 4.9
Lens ID                         : iPhone 6s Plus back camera 4.15mm f/2.2
```

## 2 plist

```text
ExifTool Version Number         : 13.19
File Name                       : 0FB91698-EF23-48BF-96A9-F7902A77E118.plist
Directory                       : /Users/bvoris/Pictures/Photos Library.photoslibrary/resources/renders/0
File Size                       : 973 bytes
File Modification Date/Time     : 2025:02:06 15:34:29-07:00
File Access Date/Time           : 2025:02:12 14:38:35-07:00
File Inode Change Date/Time     : 2025:02:06 15:34:29-07:00
File Permissions                : -rw-r--r--
File Type                       : PLIST
File Type Extension             : plist
MIME Type                       : application/xml
Adjustment Base Version         : 0
Adjustment Editor Bundle ID     : com.apple.mobileslideshow
Adjustment Format Identifier    : com.apple.photo
Adjustment Format Version       : 1.4
Adjustment Render Types         : 18944
Adjustment Timestamp            : 2018:11:18 04:02:26Z
```

## 3 resources/derivatives

```text
ExifTool Version Number         : 13.19
File Name                       : 0FB91698-EF23-48BF-96A9-F7902A77E118_1_105_c.jpeg
Directory                       : /Users/bvoris/Pictures/Photos Library.photoslibrary/resources/derivatives/0
File Size                       : 141 kB
File Modification Date/Time     : 2025:02:06 16:52:22-07:00
File Access Date/Time           : 2025:02:12 15:07:13-07:00
File Inode Change Date/Time     : 2025:02:12 15:07:09-07:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Exif Byte Order                 : Big-endian (Motorola, MM)
Make                            : Apple
Camera Model Name               : iPhone 6s Plus
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Software                        : 12.1
Modify Date                     : 2018:11:17 21:02:26
Exposure Time                   : 1/4
F Number                        : 2.2
Exposure Program                : Program AE
ISO                             : 64
Exif Version                    : 0221
Date/Time Original              : 2018:11:17 21:02:26
Create Date                     : 2018:11:17 21:02:26
Components Configuration        : Y, Cb, Cr, -
Shutter Speed Value             : 1/4
Aperture Value                  : 2.2
Brightness Value                : -0.3426268685
Exposure Compensation           : 0
Metering Mode                   : Spot
Flash                           : Auto, Did not fire
Focal Length                    : 4.2 mm
Subject Area                    : 3371 1811 753 756
Sub Sec Time Original           : 248
Sub Sec Time Digitized          : 248
Flashpix Version                : 0100
Color Space                     : sRGB
Exif Image Width                : 747
Exif Image Height               : 1050
Sensing Method                  : One-chip color area
Scene Type                      : Directly photographed
Exposure Mode                   : Auto
White Balance                   : Auto
Focal Length In 35mm Format     : 29 mm
Scene Capture Type              : Standard
Lens Info                       : 4.150000095mm f/2.2
Lens Make                       : Apple
Lens Model                      : iPhone 6s Plus back camera 4.15mm f/2.2
GPS Latitude Ref                : North
GPS Longitude Ref               : West
GPS Altitude Ref                : Above Sea Level
GPS Time Stamp                  : 04:02:25
GPS Speed Ref                   : km/h
GPS Speed                       : 0.94
GPS Img Direction Ref           : True North
GPS Img Direction               : 105.0434188
GPS Dest Bearing Ref            : True North
GPS Dest Bearing                : 105.0434188
GPS Date Stamp                  : 2018:11:18
GPS Horizontal Positioning Error: 50 m
Current IPTC Digest             : c9b00e5b72ea8021a6d892258e043c7c
Coded Character Set             : UTF8
Application Record Version      : 2
Digital Creation Time           : 21:02:26
Digital Creation Date           : 2018:11:17
Date Created                    : 2018:11:17
Time Created                    : 21:02:26
IPTC Digest                     : c9b00e5b72ea8021a6d892258e043c7c
Image Width                     : 747
Image Height                    : 1050
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Aperture                        : 2.2
Image Size                      : 747x1050
Megapixels                      : 0.784
Scale Factor To 35 mm Equivalent: 7.0
Shutter Speed                   : 1/4
Create Date                     : 2018:11:17 21:02:26.248
Date/Time Original              : 2018:11:17 21:02:26.248
GPS Altitude                    : 821.9 m Above Sea Level
GPS Date/Time                   : 2018:11:18 04:02:25Z
GPS Latitude                    : 43 deg 37' 1.50" N
GPS Longitude                   : 116 deg 12' 22.07" W
Date/Time Created               : 2018:11:17 21:02:26
Digital Creation Date/Time      : 2018:11:17 21:02:26
Circle Of Confusion             : 0.004 mm
Field Of View                   : 63.7 deg
Focal Length                    : 4.2 mm (35 mm equivalent: 29.0 mm)
GPS Position                    : 43 deg 37' 1.50" N, 116 deg 12' 22.07" W
Hyperfocal Distance             : 1.82 m
Light Value                     : 4.9
Lens ID                         : iPhone 6s Plus back camera 4.15mm f/2.2
```

## 4 resources/derivatives/masters

```text
ExifTool Version Number         : 13.19
File Name                       : 0FB91698-EF23-48BF-96A9-F7902A77E118_4_5005_c.jpeg
Directory                       : /Users/bvoris/Pictures/Photos Library.photoslibrary/resources/derivatives/masters/0
File Size                       : 40 kB
File Modification Date/Time     : 2025:02:06 15:34:29-07:00
File Access Date/Time           : 2025:02:12 15:08:56-07:00
File Inode Change Date/Time     : 2025:02:12 15:08:53-07:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 72
Y Resolution                    : 72
Exif Byte Order                 : Big-endian (Motorola, MM)
Color Space                     : sRGB
Exif Image Width                : 360
Exif Image Height               : 506
Image Width                     : 360
Image Height                    : 506
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 360x506
Megapixels                      : 0.182
```

## 5 dat file

```text
ExifTool Version Number         : 13.19
File Name                       : 0FB91698-EF23-48BF-96A9-F7902A77E118_5_5_c_14.dat
Directory                       : /Users/bvoris/Pictures/Photos Library.photoslibrary/resources/caches/compute/0
File Size                       : 1438 bytes
File Modification Date/Time     : 2025:02:08 17:43:29-07:00
File Access Date/Time           : 2025:02:12 14:52:07-07:00
File Inode Change Date/Time     : 2025:02:08 17:43:29-07:00
File Permissions                : -rw-r--r--
Error                           : Unknown file type
```

## 6 originals

```text
ExifTool Version Number         : 13.19
File Name                       : 0FB91698-EF23-48BF-96A9-F7902A77E118.jpeg
Directory                       : /Users/bvoris/Pictures/Photos Library.photoslibrary/originals/0
File Size                       : 1739 kB
File Modification Date/Time     : 2018:11:17 21:02:26-07:00
File Access Date/Time           : 2025:02:12 15:11:42-07:00
File Inode Change Date/Time     : 2025:02:12 15:11:40-07:00
File Permissions                : -rw-------
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
Exif Byte Order                 : Big-endian (Motorola, MM)
Make                            : Apple
Camera Model Name               : iPhone 6s Plus
Orientation                     : Rotate 90 CW
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Software                        : 12.1
Modify Date                     : 2018:11:17 21:02:26
Y Cb Cr Positioning             : Centered
Exposure Time                   : 1/4
F Number                        : 2.2
Exposure Program                : Program AE
ISO                             : 64
Exif Version                    : 0221
Date/Time Original              : 2018:11:17 21:02:26
Create Date                     : 2018:11:17 21:02:26
Components Configuration        : Y, Cb, Cr, -
Shutter Speed Value             : 1/4
Aperture Value                  : 2.2
Brightness Value                : -0.3426268685
Exposure Compensation           : 0
Metering Mode                   : Spot
Flash                           : Auto, Did not fire
Focal Length                    : 4.2 mm
Subject Area                    : 3371 1811 753 756
Maker Note Version              : 10
Run Time Flags                  : Valid
Run Time Value                  : 86905262582166
Run Time Scale                  : 1000000000
Run Time Epoch                  : 0
AE Stable                       : Yes
AE Target                       : 94
AE Average                      : 101
AF Stable                       : Yes
Acceleration Vector             : 0.01901177503 -0.9801526063 -0.1676488668
Focus Distance Range            : 0.39 - 0.82 m
OIS Mode                        : 2
Image Capture Type              : Unknown (5)
Live Photo Video Index          : 0
Photos App Feature Flags        : 0
Signal To Noise Ratio           : 0
Sub Sec Time Original           : 248
Sub Sec Time Digitized          : 248
Flashpix Version                : 0100
Color Space                     : sRGB
Exif Image Width                : 4032
Exif Image Height               : 3024
Sensing Method                  : One-chip color area
Scene Type                      : Directly photographed
Exposure Mode                   : Auto
White Balance                   : Auto
Focal Length In 35mm Format     : 29 mm
Scene Capture Type              : Standard
Lens Info                       : 4.15mm f/2.2
Lens Make                       : Apple
Lens Model                      : iPhone 6s Plus back camera 4.15mm f/2.2
GPS Latitude Ref                : North
GPS Longitude Ref               : West
GPS Altitude Ref                : Above Sea Level
GPS Time Stamp                  : 04:02:25
GPS Speed Ref                   : km/h
GPS Speed                       : 0.94
GPS Img Direction Ref           : True North
GPS Img Direction               : 105.0434188
GPS Dest Bearing Ref            : True North
GPS Dest Bearing                : 105.0434188
GPS Date Stamp                  : 2018:11:18
GPS Horizontal Positioning Error: 50 m
Compression                     : JPEG (old-style)
Thumbnail Offset                : 2192
Thumbnail Length                : 9764
Image Width                     : 4032
Image Height                    : 3024
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Run Time Since Power Up         : 24:08:25
Aperture                        : 2.2
Image Size                      : 4032x3024
Megapixels                      : 12.2
Scale Factor To 35 mm Equivalent: 7.0
Shutter Speed                   : 1/4
Create Date                     : 2018:11:17 21:02:26.248
Date/Time Original              : 2018:11:17 21:02:26.248
Thumbnail Image                 : (Binary data 9764 bytes, use -b option to extract)
GPS Altitude                    : 821.9 m Above Sea Level
GPS Date/Time                   : 2018:11:18 04:02:25Z
GPS Latitude                    : 43 deg 37' 1.50" N
GPS Longitude                   : 116 deg 12' 22.07" W
Circle Of Confusion             : 0.004 mm
Field Of View                   : 63.7 deg
Focal Length                    : 4.2 mm (35 mm equivalent: 29.0 mm)
GPS Position                    : 43 deg 37' 1.50" N, 116 deg 12' 22.07" W
Hyperfocal Distance             : 1.82 m
Light Value                     : 4.9
Lens ID                         : iPhone 6s Plus back camera 4.15mm f/2.2
```
