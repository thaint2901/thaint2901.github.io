Trong bài viết này, mình sẽ hướng dẫn các bạn làm thế nào để cài setup môi trường ENV cho mục đích học tập cũng như xây dựng Machine Learning và Deep Learning với Python một cách clean và hiệu quả.

# Nội dung
Nội dung bài viết gồm có:

1. Giới thiệu CUDA, CuDnn và Tensorrt
2. Thông số hệ thống và các thư viện cần cấu hình
3. Hướng dẫn cài đặt và cấu hình
4. Tham khảo


# Giới thiệu CUDA, CuDnn và Tensorrt

**CUDA** (Compute Unified Device Architecture - Kiến trúc thiết bị tính toán hợp nhất) là một kiến trúc tính toán song song do NVIDIA phát triển. Nói một cách ngắn gọn, CUDA là động cơ tính toán trong các GPU (Graphics Processing Unit - Đơn vị xử lý đồ họa) của NVIDIA

**cuDNN** - NVidia CUDA® Deep Neural Network: Là một thư viện nền tảng cho các deep neural network được tăng tốc bởi GPU. cuDNN cung cấp các thiết lập được tinh chỉnh cho các thủ tục được chuẩn hóa như forward and backward convolution, pooling, normalization và các lớp kích hoạt. cuDNN là một phần của Deep Learning SDK do NVidia cung cấp.

**TensorRT**: Đây là một SDK do NVIDIA phát triển, phục vụ cho việc infer các model với hiệu năng cao. Nó bao gồm các bộ tối ưu các thuật toán deep learning, cho phép infer các pretrained model với độ trễ nhỏ và tiêu tốn ít memory. Chi tiết về công cụ này sẽ được mình viết trong các bài sau.

# System Requirements

Cấu hình môi trường máy tính cá nhân của mình như sau:

* Ubuntu 18.04
* Nvidia GTX 1650, Capability=7.5
* Python: 3.6

Các công cụ và thư viện chính sẽ được setup:

* Driver: 450 (bản mới nhất nhé).
* CUDA: 10.1
* Cudnn: 7.6.5
* TensorRT: 6.0.1.5

# Hướng dẫn cài đặt và cấu hình

## Cài đặt Driver

Trước tiên hãy update và upgrade hệ thống

```bash
sudo apt-get update
sudo apt-get upgrade
```

Thêm repo và cài đặt

```bash
sudo add-apt-repository ppa:graphics-drivers
sudo apt-get update
sudo apt-get install nvidia-driver-440
```

Cuối cùng là khởi động lại máy

```bash
sudo reboot
```

Sau khi khởi động lại, bạn kiểm tra với lệnh

```bash
nvidia-smi
```

Kết quả sẽ như sau

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/nvidia-smi.png){:.align-center}