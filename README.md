# tensorflow_maksrcnn_opencv
A Train Test  demo of maskrcnn_opencv

#### depandend
- python3
- opencv (>3.4.3)
- tensorflow_gpu (12.0)
- cuda9.0 cudnn7.0

#### 数据生成

- install labelme
```
sudo  pip3 install labelme
```

- generate tf.record

```
python3 create_tf_record.py \
    --images_dir=path_to_images_dir \   
    --annotations_json_dir=path_to_train_annotations_json_dir \ 
    --label_map_path=path_to_label_map.pbtxt \
    --output_path=path_to_train.record
```
#### download pretrain model 

[下载inception预训练模型](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md/)

#### download tensorflow models
```
git clone https://github.com/tensorflow/models.git
```

#### traing
在models/research/object_detection目录下执行
```
python model_main.py \
    --model_dir=path/to/save/directory \
    --pipeline_config_path=path/to/mask_rcnn_inception_v2_xxx.config
```

#### pb2graph

get model graph txt
```
python tf_text_graph_rcnn.py  
```

![Image text](https://github.com/mahxn0/tensorflow_maksrcnn_opencv/blob/master/data/1.jpg)

![Image text](https://github.com/mahxn0/tensorflow_maksrcnn_opencv/blob/master/data/2.jpg)


![Image text](https://github.com/mahxn0/tensorflow_maksrcnn_opencv/blob/master/data/3.jpg)
