# Error running `osxphoto`

## Error with some pictures

This is the error that led me to update. Here's the text after updating and
entering the command `osxphotos inspect` when `Photos` is displaying certain
pictures. All known affected pictures are in Shared Albums. Information about
most pictures in a Shared Album (even the same Shared Album) is displayed
without error. If I "import" one of the affected pictures (i.e., copy it to the
local library), `osxphotos inspect` does *not* fail.

```text
1977:78: python3 -m osxphotos inspect
Using last opened Photos library: /Users/bvoris/Pictures/Photos Library.photoslibrary
╭─────────────────────────────── Traceback (most recent call last) ────────────────────────────────╮
│ in _run_module_as_main:198                                                                       │
│ in _run_code:88                                                                                  │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxpho │
│ tos/__main__.py:6 in <module>                                                                    │
│                                                                                                  │
│   3 from .cli.cli import cli_main                                                                │
│   4                                                                                              │
│   5 if __name__ == "__main__":                                                                   │
│ ❱ 6 │   cli_main()                                                                               │
│   7                                                                                              │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/click/ │
│ core.py:1442 in __call__                                                                         │
│                                                                                                  │
│   1439 │                                                                                         │
│   1440 │   def __call__(self, *args: t.Any, **kwargs: t.Any) -> t.Any:                           │
│   1441 │   │   """Alias for :meth:`main`."""                                                     │
│ ❱ 1442 │   │   return self.main(*args, **kwargs)                                                 │
│   1443                                                                                           │
│   1444                                                                                           │
│   1445 class _FakeSubclassCheck(type):                                                           │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/click/ │
│ core.py:1363 in main                                                                             │
│                                                                                                  │
│   1360 │   │   try:                                                                              │
│   1361 │   │   │   try:                                                                          │
│   1362 │   │   │   │   with self.make_context(prog_name, args, **extra) as ctx:                  │
│ ❱ 1363 │   │   │   │   │   rv = self.invoke(ctx)                                                 │
│   1364 │   │   │   │   │   if not standalone_mode:                                               │
│   1365 │   │   │   │   │   │   return rv                                                         │
│   1366 │   │   │   │   │   # it's not safe to `ctx.exit(rv)` here!                               │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/click/ │
│ core.py:1830 in invoke                                                                           │
│                                                                                                  │
│   1827 │   │   │   │   super().invoke(ctx)                                                       │
│   1828 │   │   │   │   sub_ctx = cmd.make_context(cmd_name, args, parent=ctx)                    │
│   1829 │   │   │   │   with sub_ctx:                                                             │
│ ❱ 1830 │   │   │   │   │   return _process_result(sub_ctx.command.invoke(sub_ctx))               │
│   1831 │   │                                                                                     │
│   1832 │   │   # In chain mode we create the contexts step by step, but after the                │
│   1833 │   │   # base command has been invoked.  Because at that point we do not                 │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/click/ │
│ core.py:1226 in invoke                                                                           │
│                                                                                                  │
│   1223 │   │   │   echo(style(message, fg="red"), err=True)                                      │
│   1224 │   │                                                                                     │
│   1225 │   │   if self.callback is not None:                                                     │
│ ❱ 1226 │   │   │   return ctx.invoke(self.callback, **ctx.params)                                │
│   1227 │                                                                                         │
│   1228 │   def shell_complete(self, ctx: Context, incomplete: str) -> list[CompletionItem]:      │
│   1229 │   │   """Return a list of completions for the incomplete value. Looks                   │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/click/ │
│ core.py:794 in invoke                                                                            │
│                                                                                                  │
│    791 │   │                                                                                     │
│    792 │   │   with augment_usage_errors(self):                                                  │
│    793 │   │   │   with ctx:                                                                     │
│ ❱  794 │   │   │   │   return callback(*args, **kwargs)                                          │
│    795 │                                                                                         │
│    796 │   def forward(self, cmd: Command, /, *args: t.Any, **kwargs: t.Any) -> t.Any:           │
│    797 │   │   """Similar to :meth:`invoke` but fills in default keyword                         │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxpho │
│ tos/cli/photo_inspect.py:565 in photo_inspect                                                    │
│                                                                                                  │
│   562 │   │   │   │   │   if photo := photosdb.get_photo(uuid):                                  │
│   563 │   │   │   │   │   │   layout["main"].update(                                             │
│   564 │   │   │   │   │   │   │   Panel(                                                         │
│ ❱ 565 │   │   │   │   │   │   │   │   inspect_photo(                                             │
│   566 │   │   │   │   │   │   │   │   │   photo,                                                 │
│   567 │   │   │   │   │   │   │   │   │   detected_text=detected_text_cache.get(uuid, None),     │
│   568 │   │   │   │   │   │   │   │   │   templates=template,                                    │
│                                                                                                  │
│ /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxpho │
│ tos/cli/photo_inspect.py:208 in inspect_photo                                                    │
│                                                                                                  │
│   205 │   │   )                                                                                  │
│   206 │   │   properties.append(                                                                 │
│   207 │   │   │   bold("Likes: ")                                                                │
│ ❱ 208 │   │   │   + trim(f"{', '.join(l.user for l in photo.likes) or '-'}", "Likes: ")          │
│   209 │   │   )                                                                                  │
│   210 │                                                                                          │
│   211 │   if beta and photo.shared_library:                                                      │
╰──────────────────────────────────────────────────────────────────────────────────────────────────╯
TypeError: sequence item 0: expected str instance, NoneType found
```

## Error after updating with `port`

```text
: osxphotos version
/Users/bvoris/Library/Python/3.9/lib/python/site-packages/urllib3/__init__.py:35: NotOpenSSLWarning: urllib3 v2 only supports OpenSSL 1.1.1+, currently the 'ssl' module is compiled with 'LibreSSL 2.8.3'. See: https://github.com/urllib3/urllib3/issues/3020
  warnings.warn(
Traceback (most recent call last):
  File "/Users/bvoris/Library/Python/3.9/bin/osxphotos", line 5, in <module>
    from osxphotos.__main__ import cli_main
  File "/Users/bvoris/Library/Python/3.9/lib/python/site-packages/osxphotos/__init__.py", line 17, in <module>
    from .iphoto import (
  File "/Users/bvoris/Library/Python/3.9/lib/python/site-packages/osxphotos/iphoto.py", line 64, in <module>
    from .photoinfo import PhotoInfo
  File "/Users/bvoris/Library/Python/3.9/lib/python/site-packages/osxphotos/photoinfo.py", line 56, in <module>
    from .bookmark import resolve_bookmark_path
  File "/Users/bvoris/Library/Python/3.9/lib/python/site-packages/osxphotos/bookmark.py", line 12, in <module>
    def resolve_bookmark_path(bookmark_data: bytes) -> pathlib.Path | None:
TypeError: unsupported operand type(s) for |: 'type' and 'NoneType'
```

The title of the referenced GitHub issue is
`urllib3>=2.0 does not work with system Python on macOS`.

And yet I don't think I'm using the system (`/usr/bin/python3`) python. See
[version info](#version-info).

### workaround

`python3 -m osxphotos`

## Setting default python in MacPorts

As suggest by output of `port`

```shell
sudo port selfupdate && sudo port upgrade outdated
```

```text
  python313 has the following notes:
    To make this the default Python or Python 3 (i.e., the version run by the 'python' or 'python3' commands), run one or both of:

        sudo port select --set python python313
        sudo port select --set python3 python313
```

```shell
sudo port select --set python3 python313
```

```text
Selecting 'python313' for 'python3' succeeded. 'python313' is now active.
```

```shell
sudo port select --set cython cython313
```

```text
Selecting 'cython313' for 'cython' succeeded. 'cython313' is now active.
```

```shell
sudo port select --set pygments py311-pygments
```

```shell
export PATH="${HOME}/Library/Python/3.9/bin":"${PATH}"
```

```text
Selecting 'py311-pygments' for 'pygments' succeeded. 'py311-pygments' is now active.
```

## What `port` installed for `osxphotos`

```shell
port contents osxphotos
```

```text
Port osxphotos @0.72.2_0 contains:
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/bin/osxphotos
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos-0.72.2.dist-info/METADATA
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos-0.72.2.dist-info/RECORD
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos-0.72.2.dist-info/WHEEL
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos-0.72.2.dist-info/entry_points.txt
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos-0.72.2.dist-info/licenses/LICENSE
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos-0.72.2.dist-info/top_level.txt
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__init__.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__main__.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/__init__.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/__init__.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/__main__.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/__main__.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/_constants.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/_constants.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/_version.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/_version.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/adjustmentsinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/adjustmentsinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/albuminfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/albuminfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/bookmark.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/bookmark.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/commentinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/commentinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/compare_exif.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/compare_exif.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/compare_libraries.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/compare_libraries.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/configoptions.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/configoptions.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/crash_reporter.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/crash_reporter.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/datetime_formatter.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/datetime_formatter.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/datetime_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/datetime_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/debug.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/debug.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/dictdiff.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/dictdiff.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/disclaim.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/disclaim.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exif_datetime_updater.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exif_datetime_updater.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exif_orientation.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exif_orientation.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exifinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exifinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exiftool.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exiftool.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exifutils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exifutils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exifwriter.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exifwriter.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/export_db.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/export_db.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/export_db_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/export_db_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exportoptions.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/exportoptions.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/fileutil.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/fileutil.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/fingerprint.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/fingerprint.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/fingerprintquery.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/fingerprintquery.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/frozen_photoinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/frozen_photoinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/gitignorefile.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/gitignorefile.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/image_file_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/image_file_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/imageconverter.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/imageconverter.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/iphoto.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/iphoto.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/markdown_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/markdown_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/metadata_reader.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/metadata_reader.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/momentinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/momentinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/path_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/path_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/personinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/personinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photo_signature.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photo_signature.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photodates.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photodates.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoexporter.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoexporter.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_common.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_common.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_dict.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_dict.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_file.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_file.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_protocol.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoinfo_protocol.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photokit.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photokit.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photokit_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photokit_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoquery.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoquery.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photos_datetime.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photos_datetime.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photos_selection.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photos_selection.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photosalbum.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photosalbum.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoscript_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/photoscript_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/phototables.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/phototables.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/phototemplate.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/phototemplate.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/phototz.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/phototz.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/placeinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/placeinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/platform.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/platform.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/pyrepl.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/pyrepl.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/query_builder.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/query_builder.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/rehydrate.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/rehydrate.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/rich_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/rich_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/scoreinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/scoreinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/searchinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/searchinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/shareinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/shareinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/shareparticipant.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/shareparticipant.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sidecars.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sidecars.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlgrep.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlgrep.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlite3_datetime.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlite3_datetime.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlite_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlite_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlitekvstore.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/sqlitekvstore.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/strpdatetime_parts.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/strpdatetime_parts.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/tempdir.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/tempdir.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/template_counter.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/template_counter.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/text_detection.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/text_detection.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/timeutils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/timeutils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/timezones.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/timezones.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/touch_files.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/touch_files.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/unicode.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/unicode.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/uti.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/uti.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/__pycache__/utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/_constants.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/_version.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/adjustmentsinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/albuminfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/bookmark.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__init__.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/__init__.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/__init__.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/about.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/about.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/add_locations.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/add_locations.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/albums.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/albums.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/batch_edit.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/batch_edit.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/cli.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/cli.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/cli_commands.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/cli_commands.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/cli_params.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/cli_params.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/click_rich_echo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/click_rich_echo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/color_themes.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/color_themes.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/common.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/common.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/compare.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/compare.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/darkmode.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/darkmode.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/debug_dump.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/debug_dump.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/docs.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/docs.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/dump.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/dump.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/exiftool_cli.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/exiftool_cli.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/export.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/export.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/exportdb.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/exportdb.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/grep.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/grep.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/help.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/help.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/import_cli.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/import_cli.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/info.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/info.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/install_uninstall_run.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/install_uninstall_run.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/keywords.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/keywords.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/kvstore.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/kvstore.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/labels.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/labels.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/list.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/list.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/orphans.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/orphans.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/param_types.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/param_types.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/persons.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/persons.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/photo_inspect.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/photo_inspect.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/places.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/places.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/print_photo_info.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/print_photo_info.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/push_exif.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/push_exif.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/push_results.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/push_results.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/query.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/query.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/repl.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/repl.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/report_writer.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/report_writer.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/rich_progress.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/rich_progress.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/selfupdate.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/selfupdate.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/show_command.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/show_command.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/sidecar.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/sidecar.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/signaturequery.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/signaturequery.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/snap_diff.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/snap_diff.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/sync.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/sync.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/sync_results.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/sync_results.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/template_repl.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/template_repl.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/theme.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/theme.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/timewarp.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/timewarp.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/tutorial.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/tutorial.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/update_command.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/update_command.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/uuid.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/uuid.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/verbose.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/verbose.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/version.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/__pycache__/version.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/about.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/add_locations.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/albums.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/batch_edit.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/cli.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/cli_commands.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/cli_params.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/click_rich_echo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/color_themes.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/common.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/compare.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/darkmode.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/debug_dump.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/docs.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/dump.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/exiftool_cli.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/export.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/exportdb.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/grep.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/help.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/import_cli.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/info.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/install_uninstall_run.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/keywords.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/kvstore.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/labels.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/list.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/orphans.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/param_types.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/persons.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/photo_inspect.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/places.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/print_photo_info.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/push_exif.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/push_results.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/query.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/repl.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/report_writer.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/rich_progress.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/selfupdate.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/show_command.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/sidecar.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/signaturequery.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/snap_diff.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/sync.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/sync_results.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/template_repl.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/theme.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/timewarp.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/tutorial.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/update_command.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/uuid.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/verbose.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/cli/version.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/commentinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/compare_exif.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/compare_libraries.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/configoptions.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/crash_reporter.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/datetime_formatter.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/datetime_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/debug.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/dictdiff.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/disclaim.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/docs/README.md
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/docs/docs.zip
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exif_datetime_updater.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exif_orientation.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exifinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exiftool.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exiftool_filetypes.json
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exifutils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exifwriter.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/export_db.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/export_db_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/exportoptions.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/fileutil.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/fingerprint.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/fingerprintquery.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/frozen_photoinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/gitignorefile.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/image_file_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/imageconverter.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/iphoto.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/lib/libdisclaim_arm64.dylib
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/lib/libdisclaim_x86_64.dylib
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/markdown_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/metadata_reader.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/momentinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/path_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/personinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photo_signature.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photodates.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoexporter.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoinfo_common.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoinfo_dict.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoinfo_file.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoinfo_protocol.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photokit.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photokit_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoquery.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photos_datetime.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photos_selection.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosalbum.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photoscript_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__init__.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/__init__.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/__init__.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_comments.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_comments.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_exif.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_exif.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_faceinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_faceinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_scoreinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_scoreinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_searchinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_searchinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_shared_library.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_shared_library.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_syndicationinfo.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/_photosdb_process_syndicationinfo.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/photosdb.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/photosdb.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/photosdb_utils.cpython-313.opt-1.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/__pycache__/photosdb_utils.cpython-313.pyc
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/_photosdb_process_comments.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/_photosdb_process_exif.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/_photosdb_process_faceinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/_photosdb_process_scoreinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/_photosdb_process_searchinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/_photosdb_process_shared_library.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/_photosdb_process_syndicationinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/photosdb.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/photosdb/photosdb_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/phototables.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/phototemplate.cog.md
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/phototemplate.md
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/phototemplate.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/phototemplate.tx
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/phototz.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/placeinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/platform.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/pyrepl.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/queries/README.md
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/queries/cloud_album_owner.sql.mako
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/queries/referenced_live_photo.sql.mako
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/queries/shared_owner.sql.mako
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/queries/title.sql.mako
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/queries/uuid_from_fingerprint.sql.mako
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/query_builder.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/rehydrate.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/rich_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/scoreinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/searchinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/shareinfo.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/shareparticipant.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/sidecars.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/sqlgrep.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/sqlite3_datetime.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/sqlite_utils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/sqlitekvstore.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/strpdatetime_parts.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/tempdir.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/template_counter.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/templates/DESCRIPTION.txt
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/templates/xmp_sidecar.mako
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/templates/xmp_sidecar_beta.mako
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/text_detection.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/timeutils.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/timezones.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/touch_files.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/tutorial.md
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/unicode.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/uti.py
  /opt/local/Library/Frameworks/Python.framework/Versions/3.13/lib/python3.13/site-packages/osxphotos/utils.py
  /opt/local/bin/osxphotos
  /opt/local/share/doc/osxphotos/LICENSE
  /opt/local/share/doc/osxphotos/README.md
  /opt/local/share/doc/osxphotos/README.rst
```

## Version info

### `osxphotos` version

```shell
python3 -m osxphotos version
```

`You have the latest version of osxphotos: 0.72.2`

### python version

```shell
whence python3 && whence python && python3 --version && python --version
```

```text
/opt/local/bin/python3
/opt/local/bin/python
Python 3.13.7
Python 3.13.7
```

### openssl version

```shell
whence openssl && openssl --version
```

```text
/opt/local/bin/openssl
OpenSSL 3.5.2 5 Aug 2025 (Library: OpenSSL 3.5.2 5 Aug 2025)
```
