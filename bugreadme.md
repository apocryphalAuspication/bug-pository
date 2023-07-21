## Bugs...?
It's just a bug identification model. There aren't many specific species it can identify, but there are a few. It was really a matter of the time I had and the images I could find and add. Originally, I had planned to write some quick facts about each bug species in the database that it would spit out along with the identification of whatever bug was in the image it was analysing, but I'm just... too tired. It would require some extra coding and stuff, too, so scratch that.

## The Algorithm
The algorithm, as far as I understand it, works by first becoming familiar with all the images it's been "trained" on, learning what kinds of patterns to look for, what kinds of colour palettes, creating an "idea" of what the object it is meant to identify is in terms of shape, tone and consistent features between images. To identify an image, it compares it to its "idea" of the object and looks for similarities, dividing it up into smaller sections to be thorough (if I remember correctly, this also helps prevent false identification by ensuring the *entire* subject in the image is similar to the object it is searching for, and not just pieces of it. Kind of how like if you ordered a pizza with mushrooms on it, you probably wouldn't want one that's also got anchovies on half of it, unless you ordered that).

## Running this project

1. You would obviously need (preferably an expanded version of) my dataset to train the model off of.
2. Also, import the model, duh.
3. Make sure the dataset is in the right directory and you know how to access it.
4. Run the train.py file on the dataset to train the model.
5. Wait for a very long time and ensure that nothing frustrating, confusing, annoying or otherwise inconvenient happens while the model is training.
6. Import your images (the bugs you want to identify).
7. Run these two commands: NET=models/bugsmodel and DATASET=data/bugsdata
8. Run this command: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/IMAGENAME.EXT (replace IMAGENAME.EXT with the name of the image you want to model to classify).
