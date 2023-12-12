# yolov5将.pt转为.rknn

### 1.将.pt文件转为onnx(windows系统)

找到yolov5_master（笔记本上）

在终端打开：

```
python export.py --weights weights/best.pt --include onnx
```

##### （1）报错：Inplace update to inference tensor outside Inference，

```
./utils/torch_utils.py
```

然后修改minmum:后面的torch版本（图中绿色数字），我当前环境的torch是1.9.0版本的，所以修改大于这个版本即可

![img](https://img-blog.csdnimg.cn/direct/c16328cd64494743a6495d5a68a1f0e8.png)

##### （2）报错：Yolov5 ONNX: export failure: Unsupported ONNX opset version: 17

在export.py 中的 def parse_opt()函数修改：将--opset的default改为12

![image-20231212204149024](assets/image-20231212204149024.png)

### 2.将.onnx文件转为.rknn文件(ubuntu x64系统)

##### （1）环境配置

直接用系统环境

```
sudo apt-get update
sudo apt-get install -y python3 python3-dev python3-pip gcc

sudo apt-get install -y python3-opencv
sudo apt-get install -y python3-numpy
```

##### （2）安装RKNN Toolkit Lite2

下载链接：

```
https://github.com/rockchip-linux/rknn-toolkit2
```

![img](assets/v2-076dbef54432ba1623b51b1bf4424ee8_720w.webp)

安装PC端的

```
# Python 3.7
pip3 install rknn_toolkit_lite2-1.x.0-cp37-cp37m-linux_aarch64.whl
# Python 3.8
pip3 install rknn_toolkit_lite2-1.x.0-cp38-cp38-linux_aarch64.whl
# Python 3.9
pip3 install rknn_toolkit_lite2-1.x.0-cp39-cp39-linux_aarch64.whl
# Python 3.10
pip3 install rknn_toolkit_lite2-1.x.0-cp310-cp310-linux_aarch64.whl
```

##### （3）下载rknpu2-master

下载链接：

```
https://github.com/rockchip-linux/rknpu2
```

打开

```
rknpu2-master/examples/rknn_yolov5_demo/convert_rknn_demo/yolov5/
```

##### （4）运行onnx2rknn.py

修改onnx2rknn.py中的

```
MODEL_PATH
platform = "rk3588"
exp
```

