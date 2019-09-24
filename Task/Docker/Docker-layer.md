# Docker layer

Có thể xem tất cả các lớp tạo nên image bằng lệnh `docker history <ID-Image>`. Cột hình ảnh trực tuyến (tức là hình ảnh trung gian hoặc lớp) hiển thị UUID được tạo ngẫu nhiên tương quan với lớp đó.

```sh
$ docker history expressweb
IMAGE         CREATED    CREATED BY                       SIZE      
fdd93d9c2c60  2 days ago /bin/sh -c CMD ["npm" "start"]   0 B
e9539311a23e  2 days ago /bin/sh -c EXPOSE 8080/tcp       0 B
995a21532fce  2 days ago /bin/sh -c COPY dir:50ab47bff7   760 B
ecf7275feff3  2 days ago /bin/sh -c npm install           3.439 MB
334d93a151ee  2 days ago /bin/sh -c COPY file:551095e67   265 B
86c81d89b023  2 days ago /bin/sh -c WORKDIR /usr/src/app  0 B
7184cc184ef8  2 days ago /bin/sh -c mkdir -p /usr/src/app 0 B
530c750a346e  2 days ago /bin/sh -c CMD ["node"]          0 B
```

<img src=https://i.imgur.com/EbQj2nv.png>

Dưới đây là sơ đồ của container được tạo từ lệnh run. Các container chứa có một layer có thể ghi được xếp chồng lên trên các layer của image ban đầu. Layer này cho phép bạn thực hiện các thay đổi vì các layer thấp chỉ cho phép đọc.

<img src=https://i.imgur.com/PqStSeT.png>

## Tài liệu tham khảo
- https://medium.com/@jessgreb01/digging-into-docker-layers-c22f948ed612