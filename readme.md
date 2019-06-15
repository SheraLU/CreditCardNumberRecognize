# demo配置文档
---
## 项目环境
- Ubuntu16
- Cuda10.0.130
- Tensorflow1.13.1
- Python3
## 配置过程
1. 安装第三方库
    `cython`
    `opencv-python`
    `easydict`
    `breaker`
    `bottle`
    `numpy`
    `matplotlib`
2. 将setup.py中的-arch更改到适应GPU
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

3. Build the Cython modules
  ```Shell
  make clean
  make
  cd ..
  ```
