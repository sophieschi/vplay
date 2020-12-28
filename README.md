# C3VOC A/V Technician Helper
Python script to make the life an A/V technician at c3voc easier.
It can play individual outputs of voctomix, as well as the final transcoded streams from the VOC CDN.

Keep in mind, that this tool uses assumptions about the VOC network and might not simply work in other situations.


## Requirements
Python 3, ffmpeg with ffplay and mpv to play the loudness monitor.


## Usage
There are three basic commands with the hall ID as common parameter:
- `./vplay -s $hall $command` with commands:
    - `cam $cam_no`: Play a camera preview from voctomix
        * Positional argument: Camera Number
    - `mix [-l [-t $track_no] ]`: Play the voctomix mix preview
        * Optionally enable a loudness graph (`-l`) and select which audio track (`-t track_num`) to listen to
    - `stream {hls-hd, hls-sd, webm-hd, webm-sd, slides}`: Play the transcoded stream from the CDN
        * Positional argument: Transcoding type (hls, webm, slides)
        * The hall ID (`-s`) can also be an arbitrary slug in this command

Python's help output is split.
`./vplay -h` shows the available commands and `./vplay $command -h` shows the help for the individual command.
