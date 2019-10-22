# mtcnn-pytorch
  https://blog.csdn.net/On_theway10/article/details/102628169

# results:
![](https://github.com/Ontheway361/mtcnn-pytorch/tree/master/result/r_kobe_self.jpg)
![](https://github.com/Ontheway361/mtcnn-pytorch/tree/master/result/r_messi_self.jpg)
![](https://github.com/Ontheway361/mtcnn-pytorch/tree/master/result/r_two_faces_self.jpg)


# Test an image
  * run > python mtcnn_test.py

# Training data prepraring
  * download [WIDER FACE](https://pan.baidu.com/s/1sJTO7TcQ2576RUqR_IIhbQ) (passcode:lsl3) face detection data then store it into ./data_set/face_detection
    * run > python ./anno_store/tool/format/transform.py change .mat(wider_face_train.mat) into .txt(anno_train.txt)
  * download [CNN_FacePoint](http://mmlab.ie.cuhk.edu.hk/archive/CNN_FacePoint.htm) face detection and landmark data then store it into ./data_set/face_landmark

# Training
  * preparing data for P-Net
    * run > python mtcnn/data_preprocessing/gen_Pnet_train_data.py
    * run > python mtcnn/data_preprocessing/assemble_pnet_imglist.py
  * train P-Net
    * run > python mtcnn/train_net/train_p_net.py

  * preparing data for R-Net
    * run > python mtcnn/data_preprocessing/gen_Rnet_train_data.py (maybe you should change the pnet model path)
    * run > python mtcnn/data_preprocessing/assemble_rnet_imglist.py
  * train R-Net
    * run > python mtcnn/train_net/train_r_net.py

  * preparing data for O-Net
    * run > python mtcnn/data_preprocessing/gen_Onet_train_data.py
    * run > python mtcnn/data_preprocessing/gen_landmark_48.py
    * run > python mtcnn/data_preprocessing/assemble_onet_imglist.py
  * train O-Net
    * run > python mtcnn/train_net/train_o_net.py

 # Citation
   [DFace](https://github.com/kuaikuaikim/DFace)
