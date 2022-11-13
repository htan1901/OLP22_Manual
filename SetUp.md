# **Hướng dẫn thiết lập môi trường thi OLP mã nguồn mở**

## **1. Tổng quan về môi trường cài đặt**

**Hệ điều hành:** Ubuntu

**Công cụ:**

- Vmware Workstation
- Docker
- Ngnix
- PHP
- MariaDB
- NukeViet CMS
- Git
- Vim/Nvim/Nano/Visual Studio Code

## **2 Cài đặt máy ảo Vmware Worksation và hệ điều hành Linux**

Tải và cài đặt Vmware Workstation [tại đây](https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html)

Tải image của hệ điều hành Ubuntu tại [tại đây](https://ubuntu.com/download#download)

Thiết lập cấu hình cài đặt Ubuntu trên Vmware Wokstation [tham khảo tại đây](https://www.thegioididong.com/game-app/cach-cai-dat-ubuntu-tren-vmware-chi-tiet-day-du-nhat-1423306)

## **3. Cài đặt các công cụ cần thiết**

Mở terminal trên Ubuntu bằng cách ấn tổ hợp phím `CTRL` + `ALT` + `T`

Cập nhật lại các package và repositiry:

```bash
sudo apt update && sudo apt upgrade
```

![Cập nhật lại các package và repositiry](res/pic_sudo_update.png 'Cập nhật lại các package và repositiry')

### **Cài đặt Git**

Gói cài đặt Git được bao gồm trong kho lưu trữ mặc định repository của Ubuntu và có thể được cài đặt bằng trình quản lý gói apt. Để cài đặt Git trên Ubuntu 22.04, bạn hãy chạy câu lệnh bên dưới với người dùng root hoặc người dùng có quyền sudo trên máy chủ.

```bash
sudo apt install git
```

Kiểm tra phiên bản Git vừa cài đặt bằng câu lệnh sau:

```bash
git --version
```

![Kiểm tra phiên bản Git](res/pic_git_check.png 'Kiểm tra phiên bản Git')

Việc đầu tiên khi cấu hình Git là chỉ định tên tài khoản và địa chỉ e-mail. Điều này rất quan trọng vì mỗi Git sẽ sử dụng chúng cho mỗi lần commit, những thông tin này được gắn bất di bất dịch vào các commit:

```bash
git config --global user.name "Nguyen Dinh Anh"
git config --global user.email nd.anh@hutech.edu.vn
```

Ta có thể lựa chọn trình soạn thảo mặc định sử dụng để soạn thảo các dòng lệnh. Mặc định, Git sử dụng trình soạn thảo mặc địch của hệ điều hành, thường là Vi hoặc Vim.

```bash
git config --global core.editor nvim
```

Một lựa chọn hữu ích khác mà có thể muốn thay đổi đó là chương trình so sánh sự thay đổi để giải quyết các trường hợp xung đột nội dung. Ví dụ vimdiff:

```bash
git config --global merge.tool vimdiff
```

Kiểm tra cấu hình:

```bash
git config --list
```

![Kiểm tra cấu hình](res/pic_list_git.png 'Kiểm tra cấu hình')

### **Cài đặt Docker**

Sử dụng snap để cài đặt docker

```bash
sudo snap install docker
```

kiểm tra phiên bản docker:

```bash
docker version
```

![Kiểm tra cấu hình](res/pic_docker_version.png 'Kiểm tra cấu hình')
