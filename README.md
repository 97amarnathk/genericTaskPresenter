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
As you can see, `questionSet` contains 4 arrays - `images`, `videos`, `audios` and `documents`. Each of these arrays contain questions. Each question has a `questionString` which is basically what you want to ask. Next there is a variable called `type`, which decides whether the question expects a text type answer or is an mcq. The type `normal` indicates a text based answer. The type `mcqs` indicates an mcq based answer. If the type is `mcqs` then an additional array `answers` is required which has the choices given to the user.

## The task JSON format -

Just like the project, the task JSON in PYBOSSA also contains an `info` field. This field should have 2 sub-fields -

* **url** - The url of the resource which is to be crowdsourced.
* **type** - The data type of the resource. It can be of the type - `images`, `videos`, `audios`, `documents`.
