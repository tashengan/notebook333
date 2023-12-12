# yolov5将.pt转为.onnx

### 1.报错：Inplace update to inference tensor outside Inference，

```
python export.py --weights runs/train/exp/weights/best.pt --include torchscript
```

解决方法：在终端打开：

```
./utils/torch_utils.py
```

然后修改minmum:后面的torch版本（图中绿色数字），我当前环境的torch是1.9.0版本的，所以修改大于这个版本即可

![img](https://img-blog.csdnimg.cn/direct/c16328cd64494743a6495d5a68a1f0e8.png)