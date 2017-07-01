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

```json
"questionSet": {
  "images":[
    {
      "questionString" : "What is this image about?"
      "type" : "normal"
      answers : []
    },
    {
    
    }
  ]
}
```
