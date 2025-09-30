# Mac `Photos` issue after `Import` and `Consolidate`

Starting with a photo file (jpeg, etc.) on disk, the first step to get it into
`Photos` is to `Import` it. This seems to add some of the metadata to a SQLite
db, create a thumbnail in the Photos directory, and put the path name of the
imported photo into the db. At that point, all appears to work as I expect.
(Note that some pages state that the photo is copied into `Photos`. While
`Photos` does create a thumbnail in one of the directories under
`~/Pictures/Photos\ Library.photoslibrary/resources/`, the path that `Photos`
stores is the path at the time of import. This behavior implies that the file
must continue to exist.

`Photos` has an operation `Consolidate` under under `File`, which copies the
picture from the external directory into `~/Photos`. This has the potentially
nice side-effect of decluttering the visible file system.

But, once that is done, the `information` display of Version 10.0 (770.0.170) of
`Photos` app starts flashing. The zoom of the map display is continually reset,
keywords cannot be entered, and spaces at the end of `Caption` are quickly
deleted. For example typing `Hello there` into `Caption` results in
`Hellothere`. A space that is entered by clicking in within the text and then
entering a space is kept. I.e., the field only keeps a space when there is text
on both sides. Note however that if keywords and a caption are entered before
executing `Consolidate`, they are kept.

While troubleshooting this bug, I used `exiftool` to display the metadata of the
the "consolidated" file and see that this step rewrites some of the metadata in
the new file. (I used `osxphotos` to get the file name within `~/Photos`.) I
don’t know if `Photos` updates its SQLite db with those changes.

I wondered if the exif data might contain something that Apple doesn’t like, so
I rewrote the metadata using `exiftool`’s `-unsafe` option. As I understand
this, `exiftool` reads the metadata and only outputs the parts that it
understands. A diff of the output of `exiftool` for the original and its output
file shows that the metadata is changed, , but I don’t know what to make of
them. Whatever that command does, it didn’t change the problem.

So far, this problem has affected pictures from Jim's Pixel and Canon (I think
rewritten by Lightroom) and from my Olympus TG-4.

One workaround to update keywords and caption are to use `osxphotos`. For
example, this command operates on the photo currently displayed in `Photos` and
adds the keywords "Quetico" and "Landscape" and changes `Caption` to `Cliffs of
Ottertrack Lake`

```shell
osxphotos batch-edit --keyword Quetico --keyword Landscape --description "Cliffs of Ottertrack Lake"
```

Another obvious workaround is to not run the “Consolidate” step.

See [Where are my imported
files?](https://help.apple.com/photos/mac/1.2/?lang=en#/pht12e7a8015)

See "Copy referenced files into a Photos library" in [Change where Photos stores
your files](https://help.apple.com/photos/mac/1.2/?lang=en#/pht1ed9b966d)
