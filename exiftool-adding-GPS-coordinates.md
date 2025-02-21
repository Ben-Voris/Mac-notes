# `exiftool` writing coordinates

This is useful if you know the coordinates and do not have a track and so
cannot use the `-geotag` option.

For example, Google reports a location (near Brad’s place) as:
39.11035754852665, -119.05983329789824

Note this Google gives 14 digits after the decimal, which is likely more than
is useful, but it's what it shows.

## Set the exiftool coordinate format

`-coordFormat "%.14f degrees"`

## Adding coordinates

Help only says:

```text
(Note that geotagging from known GPS coordinates is done by writing the GPS tags
directly rather than using the -geotag option.)
```

Though it does say directly that they *are* options, there are a list of
options, like `GPSLatitude`, under `-geotag`

## Example command

```shell
exiftool 20151220132619-4.CR2.xmp \
-coordFormat "%.14f degrees" \
-GPSLatitude=39.11035754852665 \
-GPSLongitude=-119.05983329789824
```

This adds `exif:` to the `xmp` file, which includes:

```xml
  <exif:GPSLatitude>39,6.62145291N</exif:GPSLatitude>
  <exif:GPSLongitude>119,3.58999787W</exif:GPSLongitude>
```

By default, `exiftool` displays this as

```text
GPS Latitude                    : 39 deg 6' 37.29" N
GPS Longitude                   : 119 deg 3' 35.40" W
GPS Latitude Ref                : North
GPS Longitude Ref               : West
GPS Position                    : 39 deg 6' 37.29" N, 119 deg 3' 35.40" W
```

## Warning about `digikam`

Unfortunately, `digikam` ignores these tags and worse, deletes them when it
writes metadata.
