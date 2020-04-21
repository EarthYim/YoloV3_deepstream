# zeabus_yolo

This is an implementation of YoloV3 with Deepstream.

Deepstream have many APIs which handle every task end-to-end. Details can be found here: https://docs.nvidia.com/metropolis/deepstream/4.0/dev-guide/DeepStream_Development_Guide/baggage/modules.html

Basics APIs can be configured through deepstream_app_config_yoloV3.txt

## Integrating Yolo model into Deepstream

To use a Yolo model, Deepstream will convert a model (consists of .weights and **yolov3.cfg**) into TensorRT engine. This can be specified in config_infer_primary_yoloV3.txt.  On execution, if the engine is not detected, Deepstream will automatically build an engine from weights and cfg, then saved it to the main directory which can be use next time.

## Bounding Box Parser

Nvdsinfer (inferencing API) will output the result of Yolo model as it (1-D array). Predictions and bounding boxes would need to be extract explicitly. https://towardsdatascience.com/how-to-deploy-onnx-models-on-nvidia-jetson-nano-using-deepstream-b2872b99a031
  The scripts can be found in /nvdsinfer_custom_impl_Yolo/nvdsparsebbox_Yolo.cpp 


