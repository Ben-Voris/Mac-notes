# Mac `Photos` issue after `Import` and `Consolidate`

To get a picture into `Photos`, the first step is to `Import` it. This seems to
add some of the metadata to a SQLite db, create a thumbnail in the Photos
directory, and put the path name of the imported photo into the db. At that
point, all appears to work as I expect. Note that some pages state that the
photo is copied into `Photos`. This does not seem to be true.

Then, to reduce the number of visible directories, I did what `Photos` calls
`Consolidate`, which copies the picture from the external directory into
`~/Photos`.

Once I do that, the `information` display of the `Photos` app flashes. The zoom
of the map display is continually reset, keywords cannot be entered, and spaces
(!) cannot be typed into the `Caption` field. About `Caption`: typing
`Hello there` gives `Hellothere`. A space can be entered by clicking on the
insertion point and then typing a space. That is, the field only accepts a space
when there is text on both sides.

While troubleshooting this bug, I used `exiftool` to display the metadata of the
the "consolidated" file and see that this step rewrites some of the metadata in
the new file. (I used `osxphotos` to get the file name within `~/Photos`.) I
don’t know if it updates the SQLite db with those changes.

I wondered if the exif data might contain something that Apple doesn’t like, so
I rewrote the metadata using `exiftool`’s `-unsafe` option. As I understand
this, `exiftool` reads the metadata and only outputs the parts that it
understands. A diff of the output of `exiftool` for the original and its output
file shows that the metadata is changed, , but I don’t know what to make of
them. Whatever that command does, it didn’t change the problem.

So far, this problem has affected pictures from Jim's Pixel and Canon (I think
rewritten by Lightroom) and from my Olympus TG-4.

The obvious workaround is to not run the “Consolidate” step, but damn, it's
weird.

See [Where are my imported
files?](https://help.apple.com/photos/mac/1.2/?lang=en#/pht12e7a8015)

See "Copy referenced files into a Photos library" in [Change where Photos stores
your files](https://help.apple.com/photos/mac/1.2/?lang=en#/pht1ed9b966d)
