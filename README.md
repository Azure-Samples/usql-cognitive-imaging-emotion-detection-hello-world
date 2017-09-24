---
services: data-lake-analytics
platforms: dotnet
author: saveenr
---

# USQL/Cognitive Imaging Emotion Detection Hello World

## Load the assemblies

```
REFERENCE ASSEMBLY ImageCommon;
REFERENCE ASSEMBLY FaceSdk;
REFERENCE ASSEMBLY ImageEmotion;
REFERENCE ASSEMBLY ImageTagging;
REFERENCE ASSEMBLY ImageOcr;

@emotions_from_extractor =
    EXTRACT FileName string, 
        NumFaces int, 
        FaceIndex int, 
        RectX float, 
        RectY float, 
        Width float, 
        Height float, 
        Emotion string, 
        Confidence float
    FROM @"/usqlext/samples/cognition/{FileName}.jpg"
    USING new Cognition.Vision.EmotionExtractor();
```

