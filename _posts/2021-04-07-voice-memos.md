---
layout: post
title: Voice Memos
---

I received great suggestions for taking voice memos and turning them into text. The two solutions:

## Otter.ai Approach

Sign up for http://otter.ai/ - you get 600 minutes free. It's really high quality voice->text conversion.

## gCloud Approach 

1. SETUP:
- Enable Google Cloud Speech-to-Text API (think you have to set up billing)
- Enable Google Cloud storage and create a bucket 
- Install gcloud command line tool

2. Process the files

    `for file in *.WMA; do ffmpeg -i "${file}"  -c:a flac "${file/.WMA/.flac}"; done`
    `sox *.flac [file_name].flac`

3. Load into gcloud

    `gsutil cp ./[file_name].flac gs://[bucket-name]/[file_name].flac`

4. Convert using API

    `gcloud ml speech recognize-long-running gs://[bucket-name]/[file_name].flac --language-code="en-US" > [notes].txt`

More involved then the otter approach, but if you have a lot of voice notes, over the free tier, might be cheaper.