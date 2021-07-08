# deepDR
## paper "deepDR: A network-based deep learning approach to in silico drug repositioning"

### 1. tạo PPMI matrix
 Chạy dataprocess.m với các network mới để tạo 10 PPMI.

### 2. tạo 2 thư mục "test_models" và "test_results" trong project
### 2. trong với file example_params, sửa lại tham số select_nets là các PPMI matrix phù hợp
### 2. training MDA
  run: python getFeatures.py example_params.txt
### 3. training VAE
  - pretraining with features: python cvae.py --dir dataset -a 6 -b 0.1 -m 300 --save --layer 1000 100
  -  refine training with rating: python cvae.py --dir dataset --rating -a 15 -b 3 -m 500 --load 1 --layer 1000 100

### Requirements
deepDR được test trên python 3.7
thư viện sử dụng  Keras, PyTorch, TensorFlow, numpy, scipy, and scikit-learn.

