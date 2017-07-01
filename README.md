# genericTaskPresenter

This is a generic task presenter for PYBOSSA which can handle the following media types -
* Image - png, gif, jpg, jpeg
* Video - mp4, mkv
* Audio - mp3
* Document - pdf

It supports multiple questions of mcq and text type.

## JSON Data formats required -

To work properly, this presenter assumes a particular data format in which tasks and projects are stored. If this format is adhered to, then the presenter is guaranteed to work as required.

### The Project JSON Format -

The JSON of Project in PYBOSSA already has a dictionary `info`. This presenter requires a dictionary `questionSet` inside `project.info`. Here is its structure -

```javascript
"questionSet": {
  "images":[
    {
      "questionString" : "What is this image about?",
      "type" : "normal",
      answers : []
    },
    {
      "questionString" : "Do you like this image?",
      "type" : "mcqs",
      answers : ["Yes","No"]
    }
  ],
  "videos":[
    {
      "questionString" : "What is this video about?",
      "type" : "normal",
      answers : []
    },
    {
      "questionString" : "Do you like this video?",
      "type" : "mcqs",
      answers : ["Yes","No"]
    }
  ],
  "audios":[
    {
      "questionString" : "What is this audio about?",
      "type" : "normal",
      answers : []
    },
    {
      "questionString" : "Do you like this audio?",
      "type" : "mcqs",
      answers : ["Yes","No"]
    }
  ],
  "documents":[
    {
      "questionString" : "What is this document about?",
      "type" : "normal",
      answers : []
    },
    {
      "questionString" : "Do you like this document?",
      "type" : "mcqs",
      answers : ["Yes","No"]
    }
  ]
}
```
