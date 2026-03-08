## BUỔI 1: TỔNG QUAN EMBEDDED LINUX - CÀI MÔI TRƯỜNG

![alt text](image.png)

### 1.1 Hệ thống nhúng là gì

EX: ASUS ROGSTRIG G512
![alt text](image-1.png)

- CPU (Quan trọng nhất) (Clock)
- Ngoại vi (Monitor, Battery, Fan, USBx,...)

### 1.2 Công việc thường làm Embedded Linux

- Bootloader: Tối ưu time khởi chạy
- Linux Kernel: Viết driver: I2C/SPI/USB/CAN/...
- Rootfs: Phát triển ứng dụng trên tầng user space

EX: Công ty phát triển thiết bị Laptop ABC

```cpp
- Designed (Bỏ những cái không cần thiết)
- Tối ưu lại các thành phần của hệ thống (bootloader, kernel, app)
```

### 1.3 SRC

```cpp
https://elixir.bootlin.com/linux/v6.19.3/source/kernel
```

### 1.4 SSH

Cài packet

```cpp
sudo apt install openssh-server: Cài gói openssh-server
```

sudo: mượn quyền cao nhất (root)
openssh-server: packet -> ssh remote từ device khác

### 1.5 CMD

```
uname -a : ra phiên bản
```

```
pwd : Lấy ra đường dẫn hiện tại
```

```
touch abc.txt : Tạo file abc.txt
```

```
echo "hello hoc cung et" > abc.txt : ghi vô file abc.txt
```

```
cat abc.txt : View file
```

```
cd folderA : Di chuyển vào thư mục A
```

```
cd ../ : Lùi thư mục
```

```
ls : In ra những thứ các file trong folder
```

```
ls -l : Lấy ra nhiều thông tin hơn
```

```
ls -a : lấy ra cả file ẩn
```

```
rm -rf abc.txt : Xóa luôn file (không có trong thùng rác)
```

### 1.6 VIM

```
vim abc.txt - Tạo file abc.txt và mở trình soạn thảo vim
-------------------------------
i: mode insert - sửa đổi file
ESC + :wq - lưu và thoát
ESC + !q - thoát và không lưu
ESC + w - lưu
:set number - hiển thị number
-------------------------------
shift + g: di chuyển về cuối file
g + g: di chuyển về đầu file
d + d: xóa 1 dòng
```

### 1.7 Hello world

```
gcc -o filerun main.c
```

## BUỔI 2: MAKEFILE

Tham khảo seri makeFile
😎 https://www.youtube.com/playlist?list=PLbQ6BBf-QSJwjnLCxxZioumIBd3HKZSXY

Makefile là 1 script bên trong chứa các thông tin như

- cấu trúc dự án
- các cmd để build, clean,...

Ví dụ
script build project

```
gcc -o main main.c
```

Có thể thấy nếu có nhiều file chúng ta sẽ dùng các cmd build rất nhiều -> dùng makefile

```
all
    gcc -c main main.c -I.
clean
    rm -rf main
```
