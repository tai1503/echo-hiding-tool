***Nội dung và hướng dẫn thực hiện bài lab***

**Giấu tin trong âm thanh sử dụng tool** 

**(thuật toán echo hiding single kernel)**

**1\. Chuẩn bị môi trường**

* Máy ảo Ubuntu có cài đặt labtainer  
* File imodule của labtainer echo-hiding-tool

**2\. Các bước thực hiện**

**2.1. Chuẩn bị bài lab**

* Tải bài lab:

*imodule [https://github.com/tai1503/echo-hiding-tool/raw/refs/heads/main/imodule.tar](https://github.com/tai1503/echo-hiding-tool/raw/refs/heads/main/imodule.tar?fbclid=IwZXh0bgNhZW0CMTAAYnJpZBExNkY1QVF3aEM2OVVjaXJodwEep1wjxJKiT_WZlx7dXi_38S2uVyf3bU4HIa-PbClmYkyZ4RyCpo9TvjH2pkc_aem_yqdLFGGzccuJkbY3BOQ6zA)*

* Khởi động bài lab:  
  *labtainer \-r echo-hiding-tool*

**2.2 Thực hiện bài lab**

Cài đặt các thư viện cần thiết cho bài lab:

     pip3 install numpy
     
     pip3 install scipy
     
     pip3 install matplotlib
     
     pip3 install scikit-learn
     
     sudo apt update
     
     sudo apt install python3-tk

Xem nội dung file thông điệp:

     cat message.txt

Thực hiện giấu nội dung thông điệp vào file âm thanh .wav theo thuật toán echo hiding single kernel:

     python3 echo\_single\_tool.py encode \-i input.wav \-o sg\_out.wav \-m message.txt \--algo single

Thực hiện tách nội dung thông điệp từ file âm thanh *sg\_out.wav*:

     python3 echo\_single\_tool.py decode \-i sg\_out.wav \--algo single

Thực hiện giấu nội dung thông điệp vào file âm thanh .wav theo thuật toán echo hidng backward and forward:

     python3 echo\_single\_tool.py encode \-i input.wav \-o bf\_out.wav \-m message.txt \--algo bf

Thực hiện tách nội dung thông điệp từ file âm thanh *bf\_out.wav*:

     python3 echo\_single\_tool.py decode \-i bf\_out.wav \--algo bf

* MSE (Mean Squared Error): Là sai số bình phương trung bình giữa tín hiệu gốc và tín hiệu đã biến đổi. MSE càng nhỏ ⇒ tín hiệu càng giống gốc**.**

* SNR (Signal-to-Noise Ratio): Là tỉ lệ giữa năng lượng tín hiệu và nhiễu, đo bằng dB. SNR càng lớn ⇒ tín hiệu càng ít nhiễu, chất lượng càng cao.

Thực hiện so sánh giữa hai file đã giấu tin với file ban đầu và xem thuật toán nào có hiệu suất tốt hơn:

      python3 echo\_single\_tool.py compare \-i input.wav \-o sg\_out.wav
      
      python3 echo\_single\_tool.py compare \-i input.wav \-o bf\_out.wav

Trên terminal đầu tiên:

* Kiểm tra kết quả bài lab:

     checkwork

* Kết thúc bài lab:

     stoplab

* Khởi động lại bài lab:

     labtainer \-r echo-hiding-tool

