# Spec
Specifiation for Eduvid Format - All work in progress - nothing is released yet. We only have some demos working.

# Purpose 
Eduvid meta format is a wrapper format. It will be mainly useful for presentation purpose. 

Consider a video. Video contains audio stream and a video stream. both steams are synced.
Eduvid may contains multiple streams. types of streams are different. Following type are streams are consider for first version for spec

* Audio (.wav, .ogg)
* Video (.ogv, .webm)
* Slides (.pdf, .odp, .html, .png, .jpg)
* Whiteboard Scribble (.svg)

# Format 

eduvid files are .zip file. everything is zipped. Entry file is index.json. Index.json file contains various informations related to format, media and timings.

# Initial attempt

```json
{
  "format": {
      "type": "eduvid",
      "version":"1.0.0"
  },

  "type" : {
      "seekBarType" : "video / audio / slideshow /  scrollbar",
      "seekBarMedia": "media[2]",
      "length / steps": "230000"
  },

  "media" :[
    {
          "type":"pdf",
          "src": "./myslide.pdf"
    },{
          "type":"image",
          "src": "./img/1.png"
    },{
      "type":"audio",
      "src" : "voice1.ogg"
    },{
      "type":"video",
      "src" : "lecture2.ogv"
    },{
      "type":"html",
      "src":"#slide2"
    },{
      "type":"iframe",
      "src": "./html/1.html"
    },{
      "type":"svg",
      "src": "./svg/1.svg"
    }],
"layout": {},
"transition": {
    "0": {
        "show": "media[0]#1"
    },
    "20000": {
        "show": "media[0]#2"
    },
    "50000": {
        "show": "media[0]#3",
        "effect" : {
            "in": "fadeIn",
            "inDuration": "100ms",
            "out": "fadeOut",
            "outDuration": "200ms"    
        }
    },
    "80000": {
        "show": "media[1]"
    },
    "120000": {
        "show": "media[0]#5"
    }
  }
}
```

