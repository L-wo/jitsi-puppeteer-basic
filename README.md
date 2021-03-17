# jitsi-puppeteer-basic
A basic version of my Jitsi Puppeteer implementation

*THIS CODE IS UNTESTED AND HAS BEEN PRODUCED FOR DEMO PURPOSES ONLY. IT PROBABLY WILL NOT WORK STRAIGHT OUT OF THE BOX*

## Installation

These are the things I installed on my server to make it work. You probably dont need all these:

    sudo apt update
    sudo apt install npm chromium-browser ffmpeg -y

    sudo apt install gconf-service libasound2 libatk1.0-0 libatk-bridge2.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils libnss3-dev libgdk-pixbuf2.0-dev libgtk-3-dev libxss-dev libgconf-2-4 libatk1.0-0 libatk-bridge2.0-0 libgdk-pixbuf2.0-0 libgtk-3-0 libgbm-dev libnss3-dev libxss-dev


Then, run this within the directory of the package:

    npm install

## Usage

To run the code, fill in the blanks within app.js and then use

    npm run start

You will not be able to use the bots on a secure domain server, or to join a server that uses waiting rooms or has a password on a room. I have found ways to enable these behaviours but that is beyond the scope of this demonstration.

## Video Conversion

To convert videos in MP4 format to Y4M and WAV:
  
    ffmpeg -i "test.mp4" -pix_fmt yuv420p -vf scale=320:180 -r 15 -map "0:v" "test.y4m"
    ffmpeg -i "test.mp4" -af asetrate=48000,aresample=48000 "test.wav"

Results varied depending on input MP4, but these parameters will convert anything downloaded from Vimeo nicely.

===========

Copyright 2021 L-Wo 

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.