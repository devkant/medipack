# MEDIPACK

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.ocm/srbcheema1/medipack/issues)
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)](https://github.com/srbcheema1/medipack)
[![HitCount](http://hits.dwyl.io/srbcheema1/medipack.svg)](http://hits.dwyl.io/srbcheema1/medipack)

Medipack is `Media + Package`, A command-line tool used to `trim`, `crop`, `resize` media files.
It can also be used to `extract` out `audio` or `video` from a media file.

[![Medipack](https://raw.githubusercontent.com/srbcheema1/medipack/master/extra/medipack-52x90.png)](https://pypi.org/project/medipack/)


### Installation

#### Build from Source

- `git clone https://github.com/srbcheema1/medipack`
- `cd medipack`
- `sudo python3 setup.py install`

#### Install using pip

```
sudo python3 -m pip install medipack
```
you may use `--user` option to install locally for user only in `~/.local/bin`
for this don't forget `~/.local/bin` should be in your `PATH`

### Usage

```
srb@srb-pc:$ medipack --help
usage: medipack [-h] {trim,crop,resize,extract} ...

positional arguments:
  {trim,crop,resize,extract}
```

```
suboptions are:
    trim        trim a video/audio file from given starting point to given ending point.
    crop        crop frame window of video.
    resize      resize the file by reducing video quality. to make small size video files.
    extract     extract audio-only or video-only file from media file
```

```
For more help regarding suboptions run:

medipack trim -h
medipack crop -h
medipack resize -h
medipack extract -h
```


### Supported formats

- mp4
- mp3

### supported actions

- trim
- crop
- resize
- extract

### Examples

#### trim

```
srb@srb-pc:$ medipack trim -h
usage: medipack trim [-h] [-s START] [-e END | -t TIME] [-o OUTPUT] [inp]

positional arguments:
  inp                   input video file ex: input.mp4

optional arguments:
  -h, --help            show this help message and exit
  -s START, --start START
                        start time for cuting in format hh:mm:ss or mm:ss
  -e END, --end END     end time for cuting in format hh:mm:ss or mm:ss
  -t TIME, --time TIME  clip duration in format hh:mm:ss or mm:ss
  -o OUTPUT, --output OUTPUT
```

- trimming a video from 01:04 to 14:08
```
medipack trim input.mp4 -s 01:04 -e 14:08 -o output.mp4
medipack trim input.mp4 -s 01:04 -t 13:04 -o output.mp4
medipack trim input.mp4 -s 01:04 -e 14:08
medipack trim input.mp4 -s 01:04 -t 13:04
medipack trim input.mp4
medipack trim
```
- trimming an audio from 01:04 to 14:08
```
medipack trim input.mp3 -s 01:04 -e 14:08 -o output.mp3
```

#### crop

```
srb@srb-pc:$ medipack crop -h
usage: medipack crop [-h] [-t TOP] [-b BOTTOM] [-l LEFT] [-r RIGHT]
                     [-o OUTPUT]
                     [inp]

positional arguments:
  inp                   input video file ex: input.mp4 (default: None)

optional arguments:
  -h, --help            show this help message and exit
  -t TOP, --top TOP     percentage of screen to be chopped from top (default: 0)
  -b BOTTOM, --bottom BOTTOM
                        percentage of screen to be chopped from bottom (default: 0)
  -l LEFT, --left LEFT  percentage of screen to be chopped from left (default: 0)
  -r RIGHT, --right RIGHT
                        percentage of screen to be chopped from right (default: 0)
  -o OUTPUT, --output OUTPUT
                        output file name, ex: output.mp4 (default: None)
```

- To crop the bottom right quarter of a video window
```
medipack crop input.mp4 -t 50 -l 50 -o output.mp4
medipack crop input.mp4 -t 50 -l 50
```

- To crop away top 10% of area
```
medipack crop input.mp4 -t 10 -o output.mp4
```

- To crop away right 20% of the area
```
medipack crop input.mp4 -r 20 -o output.mp4
```

- To crop away top 10% of area and right 20% of the area
```
medipack crop input.mp4 -t 10 -r 20 -o output.mp4
```

#### resize
```
srb@srb-pc:$ medipack resize -h
usage: medipack resize [-h] [-q QUALITY] [-o OUTPUT] [inp]

positional arguments:
  inp                   input video file ex: input.mp4

optional arguments:
  -h, --help            show this help message and exit
  -q QUALITY, --quality QUALITY
                        output video quality (on scale of 100) (default: 50)
  -o OUTPUT, --output OUTPUT
                        output file name, ex: output.mp4
```

- To resize a video to reduce its size
```
medipack resize input.mp4 -q 40 -o output.mp4
medipack resize input.mp4 -q 40
```

#### extract
```
srb@srb-pc:$ medipack extract -h
usage: medipack extract [-h] (-v | -a) [-o OUTPUT] [inp]

positional arguments:
  inp                   input video file ex: input.mp4

optional arguments:
  -h, --help            show this help message and exit
  -v, --video
  -a, --audio
  -o OUTPUT, --output OUTPUT
                        output file name

```
- To extract audio from media file
```
medipack extract --audio input.mp4 -o output.mp3
medipack extract --audio input.mp4
```

- To extract video from media file
```
medipack extract input.mp4 --video -o output.mp4
medipack extract input.mp4 --video
```


### Note

- For audio-input files only trim action is supported.
- If you dont provide output file then the outputfile will be names as <base>_output.<extension> for base.extension file. [except `extract` option in this output file will get name .mp3 by default]
- You may skip options, medikit is smart enough to detect or ask you the required options as per requirement
- In case of any bug/issue, Please report this to srbcheema2@gmail.com. Or, even better, submit a PR to fix it!


### Contact / Social Media

[![Github](https://raw.githubusercontent.com/srbcheema1/medipack/master/extra/github.png)](https://github.com/srbcheema1/)
[![LinkedIn](https://raw.githubusercontent.com/srbcheema1/medipack/master/extra/linkedin-48x48.png)](https://www.linkedin.com/in/srbcheema1/)
[![Facebook](https://raw.githubusercontent.com/srbcheema1/medipack/master/extra/fb.png)](https://www.facebook.com/srbcheema/)

### Development by

Developer / Author: [Srb Cheema](https://github.com/srbcheema1/)
