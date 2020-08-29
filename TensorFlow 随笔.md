GPU 支持

软件要求

目前 tensorflow 2.3.0，如果不是从源代码构建请使用下列版本，**不要过高或过低，否则运行代码会出现错误**

- **CUDA 10.1**
- **cuDNN v7.6.x**

必须在系统中安装以下 NVIDIA® 软件：

- NVIDIA® GPU 驱动程序：**CUDA 10.1** 需要 **418.x** 或更高版本。
- CUDA® 工具包：TensorFlow 支持 **CUDA 10.1**（TensorFlow 2.1.0 及更高版本）
- CUDA 工具包附带的 CUPTI。
- cuDNN SDK（**7.6** 及更高版本）
- （可选）TensorRT 6.0，可缩短用某些模型进行推断的延迟时间并提高吞吐量。

1. 设置 > 应用和功能

搜索 NVIDIA 全部卸载，删除 C:\ProgramData、C:\Program Files (x86)、C:\Program Files NVIDIA 相关目录，重启系统

2. 下载显卡对应的驱动程序

https://www.nvidia.com/download/index.aspx?lang=en-us

3. 下载 CUDA Toolkit

https://developer.nvidia.com/cuda-toolkit-archive

4. 下载 cuDNN SDK（需 NVIDIA 注册帐号）

https://developer.nvidia.com/cudnn

下载完成后解压 `cudnn-10.1-windows10-x64-v8.0.2.39.zip`（复制 bin、include、lib 文件夹粘贴） 到 CUDA Toolkit 安装目录 `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1`（目录下同样有三个文件夹 bin、include、lib）

CUDA　统一计算设备架构


5. 此时安装 TensorFlow 的必要软件已满足


    pip install tensorflow
    
测试代码，注意加载的动态库，所有都为 Successfully，安装成功

    import tensorflow as tf
    
    print(tf.__version__)
    print("Num GPUs Available: ",
          len(tf.config.experimental.list_physical_devices('GPU')))

