# demo配置文档
## 项目说明
### demo中集成了卡号定位、卡号识别模块，受文件大小所限不另再单独提供具体模块实现
## 项目环境
- Ubuntu16
- Cuda10.0.130
- Tensorflow1.13.1
- Python3
## 配置过程
1. 由于模型大小超过上传上限，需从百度网盘或git上下载模型
   - 百度云链接
   - GitHub链接
2. 安装第三方库
    `cython`
    `opencv-python`
    `easydict`
    `breaker`
    `bottle`
    `numpy`
    `matplotlib`
3. 将setup.py中的-arch更改到适应GPU
  ```Shell
  cd faster_rcnn/lib
  # Change the GPU architecture (-arch) if necessary
  vim setup.py
  ```

  | GPU model  | Architecture |
  | ------------- | ------------- |
  | TitanX (Maxwell/Pascal) | sm_52 |
  | GTX 960M | sm_50 |
  | GTX 1080 (Ti) | sm_61 |
  | Grid K520 (AWS g2.2xlarge) | sm_30 |
  | Tesla K80 (AWS p2.xlarge) | sm_37 |

4. Build the Cython modules
  ```Shell
  make clean
  make
  cd ..
  ```
