## Sử dụng `postgresql` để save dữ liệu trong trường hợp bất khả kháng, không thể dùng `mysql` or `sql Server`.
Một tình huống đặt ra thế này!

Khi chúng ta làm việc ở công ty, việc cài đặt một phần mềm hay chương trình nào đó không còn là tự do nhưng máy tính cá nhân nữa. Điều này cũng dễ hiểu vì lý do bảo mật cũng như rất nhiều vấn đề gì gì đấy. Đại loại là khi muốn cài một phần mềm nào đấy, thuộc loại phần mềm cần biến môi trường, phần lớn cần phải thông qua bộ phận IT để mở quyền cài đặt phần mềm. 

Chính vì sự bất tiện này, việc sử dụng `Command Line (CMD)` là một kỹ năng cần có. Và việc cấu hình server `postgresql` là một trường hợp như vậy. 

Dưới đây là phần cấu hình server `postgresql` và sử dụng `DBeaver` (GUI) để view dữ liệu ở góc nhìn giao diện.

## Cấu hình server `postgresql`
>1. Download file .zip từ trang chủ postgresql rồi sau đó giải nén, rồi đặt ở đâu đó tại ở C nhé (đặt ở đâu cũng được nhưng thường thì là ổ C nè). 

>2. Chắc mọi người đã biết cấu hình biến java để build chương trình rồi chứ nhỉ, đối với postgres  cũng làm tương tự. Vào lấy đường dẫn `C:/..../bin` rồi  đặt chúng vào mục `path` dành cho `user environment variables` nhé!

>3. Mở CMD trên windows rồi tiến hành tạo user, database nè!

### Trước tiên, ta tạo một thư mục có tên là `data` ở thư mục chính của postgres, rồi copy đường dẫn, `save in cache (path_in_cache)` nhé và mở `cmd` của windows ra nè!
- DO FOLLOWING THE INSTRUCTIONS BELOW!

    - `create databast server`
        ```
        initdb -E UTF8 -U postgres -W 'path_in_cache'
        ```

    - `start server to create user and database`
        ```
        pg_ctl start -D 'path_in_cache'
        ```
    - `access postgres`
        ```
        psql -U postgres
        ```
    - `create user`
        ```
        create user nqvuong99qn password 'ahihi'
        ```
    - `create database`
        ```
        create database postgresDB
        ```
    - `allow permission`
        ```
        grant all privileges on database postgresDB to nqvuong99qn
        ```
    - `exit` 
        ```
        exit
        ```


### DONE. 
> ## Như vậy là ta đã cấu hình xong server postgres using CMD rồi đấy. Hi vọng hướng dẫn này có ích cho mọi người. 









