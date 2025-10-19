+++
date = '2025-10-19T15:15:17+07:00'
draft = false
title = 'Bài 06: Đa Tiến Trình Và Tuần Tự Hóa Đối Tượng Mạng'
+++
Bài viết này đi sâu vào các lớp trong gói `java.net` để quản lý tài nguyên mạng, đặc biệt là `URL`, `URLConnection` và `URI`.

# I. Lớp java.net.URI
Lớp `URI` đại diện cho một **định danh tài nguyên chung** và chủ yếu dùng để phân tích cú pháp (parsing), xây dựng, và so sánh các định danh theo tiêu chuẩn.

**So sánh các lớp URL và URI trong Java:**

Trong Java, URI (Uniform Resource Identifier) và URL (Uniform Resource Locator) đều được dùng để tham chiếu đến tài nguyên, nhưng chúng có phạm vi và mục đích khác nhau.

URI là một chuỗi ký tự xác định duy nhất một tài nguyên trên Internet hoặc trong hệ thống, mà không nhất thiết phải chỉ ra cách truy cập tài nguyên đó. Nó là khái niệm tổng quát bao trùm cả URL và URN (Uniform Resource Name). Trong Java, lớp java.net.URI dùng để biểu diễn URI. Nó chỉ tập trung vào cú pháp và cấu trúc, không liên quan đến việc truy cập dữ liệu. Ví dụ: URI uri = new URI("https://example.com/index.html");

URL là một dạng cụ thể của URI, dùng để xác định vị trí tài nguyên và chỉ ra cách truy cập tài nguyên đó (thông qua giao thức). Nó chứa thông tin như giao thức (http, ftp...), tên miền, cổng, đường dẫn và có thể kèm theo query. Trong Java, lớp java.net.URL được dùng để làm việc với URL, và nó có thể mở kết nối đến tài nguyên thật sự. Ví dụ: URL url = new URL("https://example.com/index.html");

Tóm lại, mọi URL đều là URI, nhưng không phải URI nào cũng là URL. URI chỉ mang tính định danh, còn URL bao gồm cả cách truy cập tài nguyên. Trong Java, URI phù hợp cho việc xử lý cú pháp và phân tích địa chỉ, còn URL dùng khi bạn cần truy cập hoặc tải nội dung từ địa chỉ đó.

## Đặc điểm
* Là một đối tượng **bất biến (immutable)**.
* Không thực hiện kiểm tra giao thức mạng.

```java
// Ví dụ về việc tạo và phân tích URI
URI uri = new URI("[https://example.com/path?query=test#frag](https://example.com/path?query=test#frag)");
System.out.println("Path: " + uri.getPath()); 
// Kết quả: /path