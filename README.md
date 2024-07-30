# Rabbit Stream HLS API by WaffleHacker

This is a NodeJS/ExpressJS script that will use decode Rabbit Stream's WASM and output the HLS file (m3u8) as well as captions for a Rabbitstream Video ID. 

## Installation

- Clone this repo by running

```bash
git clone https://github.com/joshholly/rabbitstream_api.git
```

- Install the dependencies 
```bash
npm install
```

- Install ts-node globally to run typescript

```bash
npm install ts-node -g
```

## Usage

First, start up the API server

```bash
ts-node rabbit.ts
```

Then go to http://localhost:3002/api/[RabbitstreamVideoID]

## Get Rabbitstream Video ID

The rabbitstream URL will look like this: 

https://rabbitstream.net/v2/embed-4/KDeBr6IDhIk4?z=

This part of the URL is your video ID
```
KDeBr6IDhIk4
```

So when you go to

http://localhost:3002/api/KDeBr6IDhIk4

It will return a json response with the decoded m3u8 URL and captions in json format like this:

```json
{
  "decoded": [
    {
      "file": "https://ag.bigtimedelivery.net/_v13/cbb6fc56c9495f26646f9463df825f1e35b1f885a9c5affc5c62dc768f3eb536d7a851dba5284435e5f5174eae5087552b31069346ae87c39f8936973b9e40df0665256671730a5982327f928a0927a5aad0b3fd1010b9e73de6c1c52de1f71d9437ac209cae48ea1d06bdfb9bfc69fe5230e3db24259771e35833d4e5dbad17/playlist.m3u8",
      "type": "hls"
    }
  ],
  "captions": [
    {
      "file": "https://cc.2cdns.com/7e/5f/7e5fc1bd26be2175e035a44444b8b13e/eng-2.vtt",
      "label": "English",
      "kind": "captions",
      "default": true
    }
  ]
}
````