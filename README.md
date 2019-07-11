# Google® Coral USB Accelerator
 

### Software Requirements
Any Linux computer with a USB port:
* Ubuntu 18.04
* [`Python 3.6`](https://www.python.org/downloads/)
* System architecture of either x86-64 or ARM32/64 with ARMv8 instruction set

### Clone Repository and Install
```bash
cd ~
git clone https://github.com/constandinos/Coral.git
cd Coral/edgetpu_api
bash ./install.sh
```

Caution: During installation, you'll be asked, "Would you like to enable the maximum operating frequency?" Enabling this option improves the the inferencing speed but it also causes the USB Accelerator to become very hot to the touch during operation and might cause burn injuries. If you're not sure you need the increased performance, type N and press Enter to use the default operating frequency. (You can change this later by simply re-running the install script.)

### Run models on the Edge TPU (Image Classifiacation):

Now Plug in the Accelerator using the provided USB 3.0 cable

```bash
# Demo No1 (Parrot)

cd /usr/local/lib/python3.6/dist-packages/edgetpu/demo

python3 classify_image.py \
--model ~/Coral/models/mobilenet_v2_1.0_224_inat_bird_quant_edgetpu.tflite \
--label ~/Coral/labels/inat_bird_labels.txt \
--image ~/Coral/images/parrot.jpg
```

```bash

# Demo No2 (Face)

cd /usr/local/lib/python3.6/dist-packages/edgetpu/demo

python3 object_detection.py \
--model ~/Coral/models/mobilenet_ssd_v2_face_quant_postprocess_edgetpu.tflite \
--input ~/Coral/images/face.jpg \
--output ~/Coral/results/detection_results.jpg
```

### References
* **https:dasd//coral.withgoogle.com/docs/accelerator/get-started/**
* **https://coral.withgoogle.com/docs/edgetpu/api-intro/**


