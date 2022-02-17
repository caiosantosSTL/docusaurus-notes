# Using feh

Feh commad is a image viewer and work with pictures

## Basic commands

```
feh image.png
```
> we use this command to see a picture

```
feh .
```
> this command to see all images available in a current directory

To exit from the image window, just click `q` from your keyboard

## Create a slideshow

To create a slideshow we will use this command:

```
feh -r -F -D2 -. dir/
```

Above we have:

* `-r` recursive
* `-F` screen presentation
* `-D2` change to the next picture for each 2 sec
* `-.` picture in big screen
* `dir/` go to the directory