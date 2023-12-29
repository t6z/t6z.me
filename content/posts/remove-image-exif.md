---
title: "Removing personal information from images"
date: 2023-12-29T14:15:35-06:00
draft: false
tags:
    - privacy
---

The internet is a big place with a lot of people (and bots) meddling around. Digital images can sometimes contain metadata that can reveal personal information.

When you upload images to social media sites suchas X (Twitter), Facebook, Instagram, etc., the personal metadata (GPS location, Camera ID, etc.) is removed during the upload process.

If you're a small blogger who is uploading images directly to your server, you may be leaking your location without realizing it.

## Exif data

Wikipedia has a good article on what data is stored as part of the [Exif format](https://en.wikipedia.org/wiki/Exif) within common image formats.

Information like GPS location, Camera type / ID, etc. is the information that can reveal where you are located and what type of device you're using.

## Solving the problem

Phil Harvey has created a robust tool, [exiftool](https://exiftool.org/), to read and write Exif data.

The [application documentation](https://exiftool.org/exiftool_pod.html) provides examples that have the reading and writing commands we need.

To read all metadata:

```
exiftool -a -u -g1 <image/directory/regex>
```

To remove all metadata:

```
exiftool -all= <image/directory/regex>
```

