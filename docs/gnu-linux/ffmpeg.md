
# FFMPEG tips and tricks

## Cut a video 

Below we have a command to cut a video. let we suppose that we have a video with 5 minutes,
we going to call that video as `vid.mp4`, and we want to get a part of the video, 1:30min to 3min, so to do that we will write this:

```bash

ffmpeg -ss 00:01:30 -to 00:03:00 -i vid.mp4 -c copy output.mp4

```

> vid.mp4 its our video that we want to cut, and output.mp4 is the name (we are free to put any name) of the video result ou output.

## Cut multiples clips

Now we want to slice all the video, from the beginning to the end, so we will use this command below:

```bash

ffmpeg -i vid.mp4 -acodec copy -f segment -segment_time 180 -vcodec copy -reset_timestamps 1 -map 0 output%d.mp4

```

> Let we suppose that vid.mp4 has 10 minutes. We can see above the number 180, its 180 seconds or in other words, 3 minutes, so we will slice the entire video in 3min each piece.
>> We also can notice that `output%d.mp4` has a % symbol, actually is `%d` this allow us to add automacally the number at the file, for example: output001.mp4, output002.mp4, output003.mp4 and etc, because this command will create one or many archives.
>>> If we want slice 1 minute we need to write in seconds, so we can convert it doing this math -> `1*60`, 2 minutes: `2*60`, 30 min: `3*600`, 2:34min: `(2*60)+34`. 

## Transform video frames to png

To transform the video frames to image we will use this command:

```bash

ffmpeg -i inputvideo.mp4 -vf fps=30 output%d.png

```

> In fps if we want get one frame each 1 minute, we will put `fps=1/60`, 30 seconds `fps=1/30`, 10 minutes ` fps=1/600 ` etc.

