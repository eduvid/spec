# Spec
Specifiation for Eduvid Format - All work in progress - nothing is released yet. We only have some demos working.

# Purpose 
The purpose of Project Eduvid is to create a “eco-system” where student/learner will be able to
create and share “Home lectures, Classroom lectures, Seminars lectures via Slidecasting and
other technique”. Something similar to Wikipedia. Wikipedia do it for text/articles, Eduvid aims
for digital contents with text, images, audio and video and animation. 

# Goals

The goal is to re-form education in third world countries and developing nations which still do
not have proper education.
The goal is to take benefit from tremendous “creativity and knowledge” of students/teachers
and share among other students. We need not to find good teacher to educate students. All we
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



