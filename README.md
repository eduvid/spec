# Spec
Specifiation for Eduvid Format - All work in progress - nothing is released yet. We only have some demos working.

# Purpose 
The purpose of Project Eduvid is to create a “eco-system” where student/learner will be able to
create and share “Home lectures, Classroom lectures, Seminars lectures via Slidecasting and
other technique”. Something similar to Wikipedia. Wikipedia do it for text/articles, Eduvid aims
for digital contents with text, images, audio and video and animation. 

# Goals

The goal is to re-form education using digital content. mainling slicecasting.
The goal is to take benefit from tremendous "creativity and knowledge" of students and 
share this knowledge among other students. We need not to find good teacher to educate students. All we
need to find good students and empower them with “Eduvid Platform” so that they can
“easily” create and share and modify “educational contents”
The Goal is to remove/reduce barriers in “creating and sharing and modifying educational
contents”

# Format 

Eduvid meta format is a wrapper format. It will be mainly useful for presentation purpose.

Consider a video. Video contains audio stream and a video stream. both steams are synced.
Eduvid may contains multiple streams. types of streams are different. Following type are streams are consider for first version for spec

* Audio (.wav, .ogg)
* Video (.ogv, .webm)
* Slides (.pdf, .odp, .html, .png, .jpg)
* Whiteboard Scribble (.svg)

Eduvid files are .zip file. everything is zipped. Entry file is index.json. Index.json file contains various informations related to format, media and timings.

# Initial attempt
```json
{
    "format": {
        "type": "eduvid",
        "version": "1.0.1"
    },
    "type": {
        "seekBarType": "video / audio / slideshow /  scrollbar",
        "seekBarMediaIndex": 2,
        "length": "0:0:60:0"
    },
    "media": [
        {
            "type": "pdf",
            "src": "myslide.pdf"
        },
        {
            "type": "imageDir",
            "src": "img"
        },
        {
            "type": "audio",
            "src": "voice1.ogg"
        },
        {
            "type": "video",
            "src": "lecture2.ogv"
        },
        {
            "type": "html",
            "src": "#slide2"
        },
        {
            "type": "iframe",
            "src": "./html/1.html"
        },
        {
            "type": "svg",
            "src": "./svg/1.svg"
        }
    ],
    "layout": {},
    "events": [
        {
            "time": "0:0:0:0",
            "show": "0#1"
        },
        {
            "time": "0:0:3:0",
            "show": "0#2"
        },
        {
            "time": "0:0:5:0",
            "show": "0#3",
            "effect": {
                "in": "fadeIn",
                "inDuration": "100ms",
                "out": "fadeOut",
                "outDuration": "-200ms"
            }
        },
        {
            "time": "0:0:10:0",
            "show": "1#nature.png"
        },
        {
            "time": "0: 0: 12: 0",
            "show": "0#5"
        }
    ]
}
```

# Convension

* Q - What is ```1#nature.png``` ?
* A - media Array's second index ([1]) is type imageDir, so it is basically "./img/nature.png"
* Q - What is ```{"time": "0:0:3:0", "show": "0#2"}```
* A - 0 index represent pdf file. So ```0#2``` basically means, ```Show Page number 2 of myslide.pdf at Time equal to 3 second```
* Q - ```0:0:60:0``` format ?
* A - Hour:Minute:Second:Millisecond

# Todo
* How to specify z index ? There can be multiple media on screen at the same time.
* SVG scribble to be included inside format.
* Add S5 or html5rocks slides in the format.



