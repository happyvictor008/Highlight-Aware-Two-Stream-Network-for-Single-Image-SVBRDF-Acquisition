# Highlight-Aware-Two-Stream-Network-for-Single-Image-SVBRDF-Acquisition
The code is an unofficial impementation of Highlight-Aware Two-Stream Network for Single-Image SVBRDF Acquisition.
## Software requirements
This code relies on Tensorflow 1.X but can be adapted to TF 2.X with the following compatibility code:

    Replace tensorflow import everywhere by:
    import tensorflow.compat.v1 as tf
    tf.disable_v2_behavior()

It is based on python 3.X, numpy, imageio and opencv for python.
## /!\Highlight Aware Two Stream Network
This network is trained to use 256x256 linear input pictures (please use ---correctGamma if your input still has gamma correction, this option assumes gamma 2.2) and output linear parameters. 
## Training the network
To train the network using adversial loss discribed in the paper, using: 
```
python HATW_net.py --mode train --output_dir $outputDir --input_dir $inputDir/trainBlended --batch_size 1 --loss adv --useLog
```
You can find the training data (85GB) here: https://repo-sam.inria.fr/fungraph/deep-materials/DeepMaterialsData.zip
## Testing the network
To test the network, using:
```
python HATW_net.py --input_dir $INPUT_DIR --mode eval --output_dir $OUTPUT_DIR --checkpoint $CHECKPOINT_LOCATION --imageFormat $YOURIMAGEFORMAT --scale_size $SIZEOFIMAGESIDE
```
