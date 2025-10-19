+++
date = '2025-10-19T15:14:05+07:00'
draft = false
title = 'Bài 01: Tổng Quan Về Lập Trình Mạng'
+++
Lập trình mạng là nền tảng cốt lõi của mọi ứng dụng hiện đại, cho phép các thiết bị giao tiếp và trao đổi dữ liệu với nhau qua Internet.

# I. Khái niệm và Vai trò

## Lập trình mạng là gì?
Đây là quá trình xây dựng các ứng dụng có thể truyền và nhận dữ liệu giữa các máy tính thông qua một mạng lưới, sử dụng các giao thức chuẩn. Nó giúp kiến tạo các mô hình quan trọng như **Client-Server**.

# II. Mô hình TCP/IP (Mô hình 4 tầng)

Mô hình **TCP/IP** là xương sống của Internet, chia quá trình giao tiếp thành các tầng độc lập để dễ dàng quản lý và phát triển.

**Sơ đồ 4 tầng của Mô hình TCP/IP:**

![Sơ đồ mô hình TCP/IP](/images/bai1.png)

## 1. Tầng Ứng dụng (Application)
Đây là tầng gần người dùng nhất. Nó bao gồm các giao thức mà ứng dụng sử dụng để trao đổi dữ liệu (ví dụ: HTTP cho Web, SMTP cho Email).

## 2. Tầng Giao vận (Transport)
Tầng này chịu trách nhiệm truyền dữ liệu giữa các tiến trình (Process-to-Process) của hai máy chủ. Hai giao thức chính là:
* **TCP (Transmission Control Protocol):** Đảm bảo dữ liệu đến nơi đầy đủ, đúng thứ tự (Định hướng kết nối/Reliable).
* **UDP (User Datagram Protocol):** Truyền dữ liệu nhanh, không đảm bảo độ tin cậy (Không định hướng kết nối/Unreliable).

## 3. Tầng Mạng (Internet)
Tầng này quản lý địa chỉ $IP$ và tìm đường đi (routing) cho dữ liệu qua mạng lưới, đảm bảo gói tin đến đúng máy chủ đích.

# III. Vai trò của Socket

Socket là **"điểm cuối"** của một kênh giao tiếp hai chiều, cho phép một chương trình gửi và nhận dữ liệu qua mạng.

Trong lập trình $Java$, $Socket$ được sử dụng thông qua các lớp như `java.net.Socket` (cho phía $Client$) và `java.net.ServerSocket` (cho phía $Server$) để thiết lập kết nối $TCP$.