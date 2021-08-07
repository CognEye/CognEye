![HTML](https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white)
![Javascript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Ruby](https://img.shields.io/badge/Ruby-CC342D?style=for-the-badge&logo=ruby&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-0095D5?&style=for-the-badge&logo=kotlin&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
![bootstrap](https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=whi)
# CognEye

## Contributors
* [Jaivanti Dhokey](https://github.com/jaivanti)
* [Atharva Alshi](https://github.com/atharva1608)
* [Sanika Gadge](https://github.com/Sanikagadge15)
* [Vriddhi Gupta](https://github.com/Vriddhigupta)
* [Krishna Ashar](https://github.com/Krishna26Ashar)
* [Chanchal Agrawal](https://github.com/chanchal221b)
* [Aishwarya Harkare](https://github.com/Aishwarya856)
* [Purva Anjarlekar](https://github.com/Caddonix)
* [Shreyansh Chordia](https://github.com/shreyanshchordia)

## Description
The cogneye app opens up with a logo screen, which further moves towards a screen which reads out App features. User can either click on any of the feature or speak out the name of the feature. Eventually the feature will activate camera of the smartphone. Once the Phone's camera is moved around an object/Letter/Paragraph, the voice is enabled and it reads out the object/letter/paragraph aloud.
Currently, the app is still in development mode, cogneye team is working efficiently to improve the quality of the app.
> Code snippet for splash screen
```bash
val SPLASH_TIME_OUT = 4000.toLong()
Executors.newSingleThreadExecutor().execute {
       Thread.sleep(SPLASH_TIME_OUT)
       startActivity(Intent(this, MainActivity::class.java))
       finish()
}
```

>Code Snippet for OCR feature.

```bash
SparseArray<TextBlock> sparseArray = detections.getDetectedItems();
StringBuilder stringBuilder = new StringBuilder();

       for (int i = 0; i<sparseArray.size(); i++){
              TextBlock textBlock = sparseArray.valueAt(i);
               if (textBlock != null && textBlock.getValue() !=null){
                     stringBuilder.append(textBlock.getValue() + " ");
                    }
                }

final String stringText = stringBuilder.toString();
```

> Code snippet for Object detection
```bash
private fun bindPreview(cameraProvider: ProcessCameraProvider){
        val preview = Preview.Builder().build()
        val cameraSelector =CameraSelector.Builder()
            .requireLensFacing(CameraSelector.LENS_FACING_BACK)
            .build()
        preview.setSurfaceProvider(binding.previewView.surfaceProvider)
        val imageAnalysis = ImageAnalysis.Builder()
            .setTargetResolution(Size(720,1280))
            .setBackpressureStrategy(ImageAnalysis.STRATEGY_KEEP_ONLY_LATEST)
            .build()
        imageAnalysis.setAnalyzer(ContextCompat.getMainExecutor(this),ImageAnalysis.Analyzer{ imageProxy ->
            val rotationDegrees = imageProxy.imageInfo.rotationDegrees
            val image = imageProxy.image
            if (image != null){
                val processImage= fromMediaImage(image,rotationDegrees)
                objectDetector
                    .process(processImage)
                    .addOnSuccessListener { objects ->
                        for (i in objects){
                            if(binding.parentLayout.childCount >1) binding.parentLayout.removeViewAt(1)
                            val element = Draw(context =this,
                                rect = i.boundingBox,
                                text = i.labels.firstOrNull()?.text ?: "Undefined")
                            binding.parentLayout.addView(element,1)
                            fun processTexttoSpeech() {
                                val objectname = i.labels.firstOrNull()?.text ?: "Undefined"
                                tts!!.speak(objectname, TextToSpeech.QUEUE_FLUSH, null, "")
                            }
                            processTexttoSpeech()
                        }
                        imageProxy.close()
}
```

>Code snippet from android manifest file.
```bash
    <uses-permission android:name="android.permission.CAMERA"></uses-permission>
    <uses-permission android:name="android.permission.RECORD_AUDIO"></uses-permission>
```

<!--Don't forget to replace the link here with **_your own Github repository_** link. -->

## Important Links

* GitHub repo link: [CognEye Repo](https://github.com/CognEye/CognEye)
* Drive link: [CognEye drive link](https://drive.google.com/drive/folders/1pjNYFkQNOuKjL1RA7lDQqLeqY4qTpyS_?usp=sharing)
* Website link: [CognEye Website](https://cogneye.github.io/)

## Technology stack

Tools and technologies that you learnt and used in the project.

1. Java
2. Kotlin
3. HTML/CSS
4. Javascript
5. Python
6. Android Studio

## Applications
1. CognEye will act as bridge for visually impaired people to see the world through the features like object detection, optical character recognition, facial recognition, etc.
2. CognEye will activate camera and voice technologies in smartphones, to identify objects, letters, paragraph, etc around the user.
3. It will also provides a inbuilt voice assitance to help the user with understanding the app features and its use.



## Future scope
1. We will deploy the facial recognition model that is already implemented.
2. Implementation of Voice activation for opening the app and using the apps feature.
3. Testing on the visually impaired people  

## Our First Prototype Screenshots

![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(4).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(3).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(2).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(1).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM.jpeg)
