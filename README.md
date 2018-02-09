# Pill-bottle-detection

Steps to train model:
1. Run "python xml_to_csv.py" to convert annotations into csv format, the default output file is "all_labels.csv".
2. Split data in "all_labels.csv" into train and test sets also in csv format.
3. Generate TFRecords for tensorflow:
    "python generate_tfrecord.py --csv_input=data/train_labels.csv  --output_path=train.record"
    "python generate_tfrecord.py --csv_input=data/test_labels.csv  --output_path=test.record"
4. Create the label map: "data/object_detection.pbtxt"
5. Configure object detection pipeline:
    Use one from here: https://github.com/tensorflow/models/tree/master/research/object_detection/samples/configs
    Be sure to set the path for the model checkpoint, train and test files, and the label map.
6. Start from a pre-trained model:
    Use one from here: https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md
7. Run the training following directions from here: https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/running_locally.md
    
