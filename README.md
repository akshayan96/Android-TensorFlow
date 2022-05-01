# Android-TensorFlow
Android app implementing TensorFlow ML for classification using TensorFlowlite
We have implemented TensorFlow CNN Model as an android mobile application. The CNN here consists of MobileVNet and dense layer with finetuning.

After the model is created we have uploaded the same using TensorFlowlite. We then download this for further use.
Download Android Studio 4.2 or greater version to create the mobile app.
Start Android Studio and select new project while selecting the version of which the app is intended. Remember the SDK needs to be more than 22.0 version for things to work.
## First Step, Import our Model:
* Go to the main folder -> Right-Click-> New -> Other -> Add tensorflowlite -> Select our downloaded model
* This will automatically include the things needed to use tensorflow model in our app
* Since this is a image classification, Go to AndroidManifests->Add camera permission
## Use our Model:
* After the same, we go to app layout xml file. Make a basic layout app to take a picture and place holders to show the results.
* Then move to the main java/Kotlin file where we start to edit for input and output.
* First We get the bitmap image and the dimensions to further crop and center it.
* We Resize image as 224x224x3 as that is size of training image we have used.
* After that in our class classifyimages we create a instance of our model and then. Iterate through pixels normalizing and adding it to a array.
* This then is passed to the tensorflow model to get output which is probability.
* We use this probability to identify the class

One thing to note here is that the model's accuracy is pretty low and hence sometimes the prediction becomes wrong(only by a small percentage).
In the folder we have scrrenshots in which dandelion is identified as rose but by a minor difference.
Our app is as strong as our model.
