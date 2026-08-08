- `cd` : Di chuyển đến folder/file
- `grep <string cần tìm> <path>` : Tìm string trong 
- `cat` : Mở file
    + `cat` ko có tham số ở cuối : Hứng toàn bộ dữ liệu input -> in thẳng ra màn hình
    + `cat ./` : Dùng để mở các file có `-` ở đầu (dashed filename)
    + `cat " "` : Dùng để mở file tên có khoảng trắng`
- `diff <path1> <path2>` : so sánh xem chỗ nào khác trong 2 file
- `ls` : Liệt kê trong folder có những folder/file nào
    + `ls -a`: Liệt kê file bị ẩn ( file có dấu . ở đầu )
    + `ls -l`: Cho biết kiểu file(- file thường, d thư mục,...)
- `pwd` : Xem hiện tại ở đâu
- `~` : Thay thế, tương đương /home/...
- `touch <tên file>` : Tạo file
- `rm <tên file>` : Xóa file
- `rm -rf` : Xóa sạch tất cả
- `mv <path1> <path2>` : Di chuyển file 
- `cp <path1> <path2>` : Sao chép và dán
- `mkdir <tên file>`: Tạo folder
- `find <Phạm vi tìm kiếm> -<tiêu chí tìm kiếm>`: Tìm file theo tiêu chí ví dụ : find / -name xyz
- `ln -s <path1> <path2>` : Tạo symlink liên kết mềm, tương tác với path2 -> tương tác với path 1 ( path2 như kiểu con trỏ, mặt nạ và file ở path2 chưa tồn tại)
- `file <tên file>` : Cho biết tên, loại file, có thể nhận ra symlink
- `echo <...> > <file>`: Lấy output echo ghi đè vào file
- `echo <...> >> <file>`: Lấy output echo ghi nối thêm vào file
- `grep <từ/kí tự cần tìm> <tên file>`: Lọc ra các string chứa từ / kí tự cần tìm
- `grep -v <từ/kí tự ko muốn>` : Lọc ra, loại bỏ các string chứa từ / kí tự ko muốn
- `sed "s/<từ muốn bỏ>/<từ thay thế>/g"` : Trong cùng 1 string, thay thế từ này bằng từ khác
- `... | tee <file1> <file2>` : Nhân bản các output đi qua pipe, đồng thời inra output và làm input luôn cho các file
- `export <variable>=<value>` : Khiến nó trở thành biến môi trường
- `env`: in ra các biến môi trường đã được export
- `ps -ef`: Liệt kê tiến trình chạy trong terminal
- `kill <PID>`: Dừng tiến trình
- `su`: Vào quyền root
- `sudo <lệnh>`: Chạy lệnh với quyền root
- `chown <tên user> <file>`:Chuyển đổi quyền sở hữu file sang owner khác (thường thì root mới được sử dụng chown)
- `chgrp <tên user> <file>`:Chuyển đổi quyền sở hữu file sang group khác
- `id` : Thông tin về user như là User ID, thuộc group nào, tên gì
- `chmod u/g/o/a<user/group,other,all> +<thêm quyền> hoặc -<xóa quyền> r/w/x/s(SUID) <tên file>`: Thêm, xóa quyền làm việc với file của u/g/o/a
- `chmod +t ...` : sticky bit, chỉ cho phép những người sở hữu file được quyền đổi tên hoặc xóa các file nằm trong thư mục đó
- `<command1>; <command2>` : Nối chuỗi các lệnh thay vì phải enter từng lệnh
- `<command1> && <command2>` : Chạy lệnh 2 nếu lệnh 1 success
- `<command2> || <command2>` : Chạy lệnh 2 nếu lệnh 1 fail
- `<file.sh>` : Tạo file shell script
- `bash <file.sh>` : Chạy file shell script
- `$1 $2`: Trong script shell là đối số
- `screen`: Mở terminal mới song song hiện tại
     + `Ctrl A + D`: Quay về terminal gốc
     + `screen -r`: Quay lại terminal mới
     + `screen -ls`: Liệt kê các terminal mới
- `tmux`: Mở terminal mới song song
     + `Ctrl B + D`: Quay về terminal gốc
     + `tmux attach`: Quay lại terminal mới
     + `Ctrl B + %`: Chia đôi màn hình
- `PATH`: Là biến môi trường, như một cái bản đồ, nếu set `PATH=" "` rỗng như này thì gần như ko kích hoạt được lệnh nào, như mù đường, ls cũng dựa vào PATH để liệt kê, mỗi đường dẫn cách nhau bằng `:`
- `echo $PATH`: Liệt kê các đường dẫn, trái -> phải là thứ tự ưu tiên tìm kiếm
- `which ...`: In ra đường dẫn đến `...`
- `.bashrc` : Là file cấu hình tự động chạy các lệnh trong nó khi mở terminal
    + Người thường : Cài đặt môi trường, tạo alias(phím tắt)
    + Hacker : Ghi lệnh như `cat /flag`, lệnh gửi mật khẩu về máy hacker
- `ps aux` : Xem toàn bộ processes(tiến trình) và command( có thể nhạy cảm như nhập tk, mk)
- `Fork Bomb` : Làm đứng sập sever bằng cách chạy nhiều tiến trình(attack DoS) bằng cách gửi `:(){ :|:& };: & :(){ :|:& };: & :(){ :|:& };:`
- `yes > file.txt` : Làm đầy ổ đĩa 
- file có `-` ở đầu (dashed filename) : Để mở dùng cat và thêm ./
- Xử lý file có khoảng trắng trong tên, để mở cần cho full name vào dấu `" "`
- `sort` : Sắp xếp
- `uniq -u` : Dòng liền kề nhau nào lặp là bị xoá
- `strings <file>` : In ra tất cả chuỗi có nghĩa trong file nhị phân
- `base64 <file>` : encode nội dung cho trong file
    + `base64 -d <file>` : decode nội dung trong file
- `history` : Xem các lệnh đã gõ
- `wget <link>` : Download
- `ssh <name>@<IP address>`: Kết nối tới máy khác
- `scp <file> <name>@<IP address>:<link>` : copy file từ máy này -> máy khác
- `scp <name>@<IP address>:<link> <file>` : copy file từ máy khác -> máy này
- `python3 -m  http.server` : Biến thư mục hiện tại thành websever tạm thời
    + `wget http://<IP>:<port>/<file>` : Lấy file cần sau khi biến thư mục thành websevẻ
- `systemctl <option> <service>`: Tương tác với tiến trình `systemd`
- `Ctrl Z` or `&` : Đưa command vào chạy nền
- `fg` : Đưa chạy nền ra thẳng màn hình
- `telnet <IP> <Port>` : Giống `ssh` nhưng thường chỉ dùng test nhanh xem cổng mở ko
- `nslookup <link>` : Xem IP của miền
- `whois <link>` : Thông tin người đăng ký miền, thời điểm tạo, ...
- `curl <https://example.com>` : Xem nội dung trang web
- `curl -I <https://example.com>` : Xem thông tin `response header`
