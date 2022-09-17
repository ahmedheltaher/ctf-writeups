# Lesson 17: Meta data

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/17-meta-data](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/17-meta-data)*

## Introduction

Metadata is data that describes other data. It is data about data. Metadata is used to organize and describe data in a way that makes it easier to find, access, and use. Metadata is often used to describe the contents of a file, such as the title, author, and subject of a document. Metadata can also be used to describe the structure and format of a file, such as the number of pages, the font used, and the size of the file.

## Challenge

> Name:\
> *Keep it Simple*

---

> Description:\
> *The answer is simple.*

## Solution

If open the website, we will find it a super simple website, with image, text, and button for hint. the hint is image that says `KEEP CALM AND FOCUS ON THE BASICS`.

So, Lets open the page source, and we will find that it is not just a single image, but there is a hidden image. so lets Download both images, and compare them.

They are the same, but the hidden image has some metadata, so lets open it with `exiftool`, and we will find the flag.

if we open the first image with `exiftool`, we will get this output:

```bash
$ exiftool the_eye.jpeg 
ExifTool Version Number         : 12.23
File Name                       : the_eye.jpeg
Directory                       : .
File Size                       : 71 KiB
File Modification Date/Time     : 2021:04:16 04:03:50+01:00
File Access Date/Time           : 2021:04:16 04:03:50+01:00
File Inode Change Date/Time     : 2021:04:16 04:03:50+01:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
Image Width                     : 640
Image Height                    : 371
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 640x371
Megapixels                      : 0.237
```

and if we open the second image with `exiftool`, we will get this output:

```bash
$ exiftool index.jpeg 
ExifTool Version Number         : 12.23
File Name                       : index.jpeg
Directory                       : .
File Size                       : 73 KiB
File Modification Date/Time     : 2021:04:16 04:08:56+01:00
File Access Date/Time           : 2021:04:16 03:33:13+01:00
File Inode Change Date/Time     : 2021:04:16 04:08:56+01:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
Exif Byte Order                 : Big-endian (Motorola, MM)
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Y Cb Cr Positioning             : Centered
GPS Version ID                  : 2.3.0.0
GPS Latitude Ref                : North
GPS Longitude                   : 0 deg 0 0.00
GPS Altitude                    : 0 m
XMP Toolkit                     : XMP Core 5.6.0
Rights                          : {S1mpl3sty_i$_th_@nswer}
Current IPTC Digest             : 5e3e91b2890a2a0c1f69d828fd37bc26
Coded Character Set             : UTF8
Copyright Notice                : {S1mpl3sty_i$_th_@nswer}
Image Width                     : 640
Image Height                    : 371
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 640x371
Megapixels                      : 0.237
GPS Latitude                    : 0 deg 0 0.00 N
GPS Position                    : 0 deg 0 0.00 N, 0 deg 0 0.00
```

As we can see, the second image has some metadata, and the flag is in the `Rights` field.

## Flag

> S1mpl3sty_i$_th_@nswer

## Resources

- [https://en.wikipedia.org/wiki/Metadata](https://en.wikipedia.org/wiki/Metadata)\

- [https://exiftool.org/](https://exiftool.org/)

- [https://www.exiftool.org/TagNames/EXIF.html](https://www.exiftool.org/TagNames/EXIF.html)
