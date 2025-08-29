# Processing pre-Apple photos

## Copying info from XMP to tiff

NB: `tifftool` and `exiftool` will display info in different forms. The output of `exiftool` is more likely to give the tag name used by `exiftool`. However, `exiftool` did not display the gibberish stored in the `Note` field.

On import, Apple ignores the XMP sidecar so, if possible, that info must be output to the tiff. This command should do that.

```shell
FNAME='01 2002-08 Quetico roll 1' ; exiftool -v -tagsfromfile "${FNAME}.xmp" "${FNAME}.tif"
```

Syntax is:

`exiftool [OPTIONS] -tagsFromFile SRCFILE [-[DSTTAG<]SRCTAG...] FILE...`

### GPS data

I added the location to the test photo with Apple Phots. `osxphotos inspect` shows:

```text
Location: 47 deg 57' 45.05" N, 91 deg 33' 32.27" W
```

The XMP created by Apple Photos:

```xml
<x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="XMP Core 6.0.0">
   <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about=""
            xmlns:exif="http://ns.adobe.com/exif/1.0/"
            xmlns:photoshop="http://ns.adobe.com/photoshop/1.0/"
            xmlns:dc="http://purl.org/dc/elements/1.1/">
         <exif:GPSLongitude>91.558964002674188</exif:GPSLongitude>
         <exif:GPSLongitudeRef>W</exif:GPSLongitudeRef>
         <exif:GPSHPositioningError>1</exif:GPSHPositioningError>
         <exif:GPSLatitudeRef>N</exif:GPSLatitudeRef>
         <exif:GPSLatitude>47.962512734449646</exif:GPSLatitude>
         <exif:GPSTimeStamp>2025-05-04T16:43:36Z</exif:GPSTimeStamp>
         <photoshop:DateCreated>2002-08-11T00:00:01-05:00</photoshop:DateCreated>
         <dc:description>Some text</dc:description>
      </rdf:Description>
   </rdf:RDF>
</x:xmpmeta>
```

The Exif Version 2.32 standard at
<https://web.archive.org/web/20190624045241if_/http://www.cipa.jp:80/std/documents/e/DC-008-Translation-2019-E.pdf> documents the GPS*Ref fields.

<https://exiftool.org/faq.html#Q14> says

> For EXIF GPS coordinates, the reference direction is specified separately with the EXIF:GPSLatitudeRef or EXIF:GPSLongitudeRef tag. GPSLatitudeRef may be written with a string containing "N", "North", "S" or "South", or with a signed coordinate value (positive for the northern hemisphere or negative for the south). GPSLongitudeRef accepts similar values, but for E/East (positive) and W/West (negative).
>
> For XMP GPS coordinates, the reference direction is specified within the XMP:GPSLatitude or XMP:GPSLongitude value, with west longitudes and south latitudes being specified either by negative coordinate values or by ending the string with "W" or "S".

[Fix nonstandard Apple `.xmp` GPS tags](https://exiftool.org/forum/index.php?topic=14943.msg80465#msg80465) seems to say that the Apple output is flawed and that one must repair any XMP files created by Apple Photos that contains GPS information.

<https://discussions.apple.com/thread/255792059> claims this has been reported before.

A very old variation <https://discussions.apple.com/thread/1597910>

`exiftool` ignores the `exif:GPSLongitudeRef` and `exif:GPSLatitudeRef` tags and interprets this as **E** latitude.

```shell
exiftool  "${FNAME}.xmp" | grep -E 'Latitude|Longitude'
```

```text
GPS Longitude                   : 91 deg 33' 32.27" E
GPS Latitude                    : 47 deg 57' 45.05" N
GPS Latitude Ref                : North
GPS Longitude Ref               : East
```

From a jpeg where the location was added by the camera instead of manually, `exiftool` shows:

```text
GPS Version ID                  : 2.3.0.0
GPS Latitude Ref                : North
GPS Longitude Ref               : West
GPS Status                      : Measurement Active
GPS Img Direction Ref           : Magnetic North
GPS Img Direction               : 121
GPS Latitude                    : 48 deg 5' 3.76" N
GPS Longitude                   : 91 deg 14' 35.52" W
GPS Position                    : 48 deg 5' 3.76" N, 91 deg 14' 35.52" W
```

The XMP created from this file contains:

```text
   exif:GPSVersionID="2.3.0.0"
   exif:GPSLatitude="48,5.0627000N"
   exif:GPSLongitude="91,14.5920000W"
   exif:GPSStatus="A"
   exif:GPSImgDirectionRef="M"
   exif:GPSImgDirection="12100/100"
```

Unlike the XMP created by Apple Photos, the XMP created by `exiftool`, the value of`GPSLatitude` has "N" appended and the value of `GPSLongitude` has "W" appended, and there is no `GPSLongitudeRef` or `GPSLatitudeRef` tag.

<https://exiftool.org/forum/index.php?topic=10163.0> contains a statement "XMP doesn't store a separate reference direction."

Is it relevant that the tags start with `exif:`?

Something similar noted by someone migrating from Apple Photos <https://community.adobe.com/t5/lightroom-classic-discussions/exif-gps-data-gpslongituderef-gpslatituderef/td-p/10657507>

If I export the pictures in TIFF format, but not as original (so no XMP), `exiftool` displays the expected GPS values.

### A fix for GPS reference?

```shell
exiftool '-xmp-exif:gpslongitude<${xmp-exif:gpslongitude#}${xmp-exif:gpslongituderef#}'   '-xmp-exif:gpslatitude<${xmp-exif:gpslatitude#}${xmp-exif:gpslatituderef#}' *.xmp
```

Changes

```xml
<x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="XMP Core 6.0.0">
   <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about=""
            xmlns:exif="http://ns.adobe.com/exif/1.0/"
            xmlns:photoshop="http://ns.adobe.com/photoshop/1.0/"
            xmlns:dc="http://purl.org/dc/elements/1.1/">
         <exif:GPSLongitude>91.558964002674188</exif:GPSLongitude>
         <exif:GPSLongitudeRef>W</exif:GPSLongitudeRef>
         <exif:GPSHPositioningError>1</exif:GPSHPositioningError>
         <exif:GPSLatitudeRef>N</exif:GPSLatitudeRef>
         <exif:GPSLatitude>47.962512734449646</exif:GPSLatitude>
         <exif:GPSTimeStamp>2025-05-04T16:43:36Z</exif:GPSTimeStamp>
         <photoshop:DateCreated>2002-08-11T00:00:01-05:00</photoshop:DateCreated>
         <dc:description>Royce Dunbar packing at RedRock bunkhouse</dc:description>
         <dc:subject>
            <rdf:Seq>
               <rdf:li>Royce Dunbar</rdf:li>
               <rdf:li>Royce D</rdf:li>
            </rdf:Seq>
         </dc:subject>
      </rdf:Description>
   </rdf:RDF>
</x:xmpmeta>
```

to

```xml
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='Image::ExifTool 13.30'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>

 <rdf:Description rdf:about=''
  xmlns:dc='http://purl.org/dc/elements/1.1/'>
  <dc:description>Royce Dunbar packing at RedRock bunkhouse</dc:description>
  <dc:subject>
   <rdf:Seq>
    <rdf:li>Royce Dunbar</rdf:li>
    <rdf:li>Royce D</rdf:li>
   </rdf:Seq>
  </dc:subject>
 </rdf:Description>

 <rdf:Description rdf:about=''
  xmlns:exif='http://ns.adobe.com/exif/1.0/'>
  <exif:GPSHPositioningError>1</exif:GPSHPositioningError>
  <exif:GPSLatitude>47,57.75076407N</exif:GPSLatitude>
  <exif:GPSLatitudeRef>N</exif:GPSLatitudeRef>
  <exif:GPSLongitude>91,33.53784016W</exif:GPSLongitude>
  <exif:GPSLongitudeRef>W</exif:GPSLongitudeRef>
  <exif:GPSTimeStamp>2025-05-04T16:43:36Z</exif:GPSTimeStamp>
 </rdf:Description>

 <rdf:Description rdf:about=''
  xmlns:photoshop='http://ns.adobe.com/photoshop/1.0/'>
  <photoshop:DateCreated>2002-08-11T00:00:01-05:00</photoshop:DateCreated>
 </rdf:Description>
</rdf:RDF>
</x:xmpmeta>
```

## Update tiff description/notes fields

Some of the `Notes` are in UTF-16 Unicode. Apple's `Preview` and `Photos` apps renders in some non-Latin character set (gibberish). The following commands sets all caption/note/description fields to the value of `ImageDescription`.

```shell
FNAME='01 2002-08 Quetico roll 1' ; \
exiftool -ImageDescription="Royce packing in Redrock bunkhouse"  -overwrite_original  "${FNAME}.tif" && \
exiftool -UserComment="${ImageDescription}" -overwrite_original  "${FNAME}.tif" && \
exiftool -Notes="${ImageDescription}" -overwrite_original  "${FNAME}.tif" && \
exiftool -Caption-Abstract="${ImageDescription}" -overwrite_original  "${FNAME}.tif" &&
exiftool -xmp:Subject="<rdf:li xml:lang='x-default'>${ImageDescription}/rdf:li>" -overwrite_original "${FNAME}.tif"
```

It's worth checking if this can be one command.

When this is done, I see:

```text
: exiftool "${FNAME}.tif" | grep bunkhouse
Image Description               : Royce packing in Redrock bunkhouse
Description                     : Royce Dunbar packing at RedRock bunkhouse

: tiffinfo  "${FNAME}.tif" | grep bunkhouse
  ImageDescription: Royce packing in Redrock bunkhouse
    <rdf:li xml:lang='x-default'>Royce Dunbar packing at RedRock bunkhouse</rdf:li>
    <rdf:li xml:lang='x-default'>Royce packing in Redrock bunkhouse</rdf:li>
```

## Sending to an Apple shared album

The Mac `Photos` app fails to send a tiff or JPEG to a shared folder, with no detail given in the error. A workaround is to make an edit to the picture itself, e.g., auto levels. Then, when the picture is shared, a JPEG is sent.

Even if GPS information has been entered in `Photos`, if the original image file does not contain that information, it is not in the the shared album file. This is one of the reasons to [update the image file with the metadata](#copying-info-from-xmp-to-tiff).

## How to get this all to work, I hope

1. Copy the pictures to a directory on the Mac. Call this directory ORIG_DIR.
1. For all TIFF and JPEG, use `exiftool` to copy any XMP file into the picture file. (`Photos` ignores the XMP.)
1. Import the directory into an album in `Photos`. The rest calls this ORIG_ALBUM.
1. Use `Photos` to fix everything you're going to fix. Add tags, fix the caption, add GPS info, etc. Take the time to be sure you've done all you can/will because you don't want to repeat the rest of these steps.
1. While doing this, leave the Mac plugged in and Photos running for at least a day, maybe more. This gives `Photos` time to do facial recognition. Visit all the pictures and correct the face names as needed.
1. When you're really sure you're done making changes, select all of the pictures in ORIG_ALBUM and export them using Export as Unmodified Original with an XMP file to a different directory. Call this new directory NEW_DIR.
1. At least the first time, insure that the pictures files in NEW_DIR are unchanged from those in ORIG_DIR, using `diff` or some other tool.
1. [Use `exiftool` to fix the format of the GPS location.](#a-fix-for-gps-reference) I don't know if that command will damage files that already have it in the correct form, so check that first.
1. Delete the ORIG_ALBUM
1. Delete ORIG_DIR
1. Import the NEW_DIR into an album.

### Setting dates

For photos without a good timestamp but for which I know the date, the convention I used is to set the time to 00:00 with the second set to some index that gives the position of the file in the import directory. This has the advantage of making them appear in the correct order. A problem with this is that time zones can move the picture to the previous day. For a few pictures, I've been able to move the timestamp to a better guest because I see the same scene taken on the camera that did have the correct date and time.

Jim had an HP camera that lost its date setting when jostled. For this camera, I fix the date when I can, and leave the time alone. My thought is that this acts as a sequence number, at least until it's jostled again. For this camera, I mostly got from the date from the directory name that Jim created.

## [`exiftool` source](https://github.com/exiftool/exiftool)

Yup, it really is a perl script.

## A better way to update from Apple Photos

In this command "selected" says to update only the currently selected photo in Apple Photo. To update an entire album, use `--album`.

```shell
osxphotos push-exif --verbose --selected all
```

I don't see a way to update the xmp file.

This might work.

```shell
exiftool -tagsfromfile SRC.EXT DST.xmp
```

Testing with

```text
'/Users/bvoris/Linux-pictures/2002/2002_08 Quetico/2002-08 Quetico and DTL (Jim)/Aug 11 Sun/IM000956.JPG'
```

`exiftool` creates its own backup so the `cp` isn't necessary. `exiftool` will update an existing XMP, so if there is one, the output will be different than if there is not.

```shell
cp '/Users/bvoris/Linux-pictures/2002/2002_08 Quetico/2002-08 Quetico and DTL (Jim)/Aug 11 Sun/IM000956.JPG.xmp' '/Users/bvoris/Linux-pictures/2002/2002_08 Quetico/2002-08 Quetico and DTL (Jim)/Aug 11 Sun/IM000956.JPG.xmp.old'
exiftool -tagsfromfile '/Users/bvoris/Linux-pictures/2002/2002_08 Quetico/2002-08 Quetico and DTL (Jim)/Aug 11 Sun/IM000956.JPG' '/Users/bvoris/Linux-pictures/2002/2002_08 Quetico/2002-08 Quetico and DTL (Jim)/Aug 11 Sun/IM000956.JPG.xmp'
```

## Notes about `osxphotos --export`

What to do with `--sidecar-drop-ext`? Apple exports by dropping the extension and adding `.xmp`. E.g., the XMP for`file.jpg` is `file.xmp`. DigiKam prefers that the photo extension be left (e.g., `file.jpg.xmp`) so as to allow different XMP files for files with the same basename, e.g., `file.cr2.xmp` and `file.jpg.xmp`.

Maybe add `--touch-file` which "Sets the file's modification time to match photo date."

There is also an option to normalize extensions so `.jpg`, `.JPG`, `.jpeg`, etc. are collapsed to one.
