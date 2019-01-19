# ffprocess

Fork of the grate the work of [rootlogin/ffprocess](https://github.com/rootlogin/ffprocess)
 
A small docker container including ffmpeg to batch convert your media library to a defined h264/aac profile.
improves compatibility for UNRAID

-> [DockerHub](https://hub.docker.com/r/andreasrichardf/ffprocess/)

## Features

 * Made for Docker.
 * Converts files only if needed.
 * You can set a maximum framerate and resolution.
 * Truncates all streams that are not video, audio or subtitles.
 * Removes not needed additional video streams like embedded images.
 
## Dependencies when used standalone
   
 * FFMpeg with libfdk_aac, libx264 and any codec that you have in your library.
 * Image based on the great work from [jrottenberg/ffmpeg](https://hub.docker.com/r/jrottenberg/ffmpeg/)

## Usage

**With docker:**

```
usage: docker run -v /my/media/folder:/data rootlogin/ffprocess
                    [-h] [--quality QUALITY] [--preset PRESET]
                    [--resolution RESOLUTION] [--rate RATE]

Batch convert your media library to H264 and AAC.

optional arguments:
  -h, --help            show this help message and exit
  --quality QUALITY     crf quality of libx264 (default: 23)
  --preset PRESET       encoding preset for libx264 (default: veryslow)
  --resolution RESOLUTION
                        maximum resolution in height (default: 1080)
  --rate RATE           maximum framerate (default: 25)
```

**Standalone:**

If you have ffmpeg and python3 installed on your computer, you can use this script directly, but I recommend to use the docker image, because there are already all needed codecs inside.

Install dependencies with `pip install -r requirements.txt`.

```
usage: ffprocess.py [-h] [--quality QUALITY] [--preset PRESET]
                    [--resolution RESOLUTION] [--rate RATE]
                    folder

Batch convert your media library to H264 and AAC.

positional arguments:
  folder                folder to scan

optional arguments:
  -h, --help            show this help message and exit
  --quality QUALITY     crf quality of libx264 (default: 23)
  --preset PRESET       encoding preset for libx264 (default: veryslow)
  --resolution RESOLUTION
                        maximum resolution in height (default: 1080)
  --rate RATE           maximum framerate (default: 25)
```

## Development

I'm very happy about every filed issue or pull-request.

If you create a pull-request, please compare it against the "develop" branch.

## Todo's

 * how to for unraid
 * template for Unraid
 * run as service(???) 

## Warranty

This software is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. It could even start a nuclear war or kill your kittens. ;)

## Donate

If you want to donate for this project, do it by [rootlogin/ffprocess](https://github.com/rootlogin/ffprocess)

## License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.