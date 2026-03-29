# Project: Tài liệu hướng dẫn sử dụng API v3 của Chainko Cloud Printing.
## Quy trình thao tác cơ bản:

**Điều kiện tiên quyết:** Trước khi kết nối API, vui lòng đảm bảo đã liên kết thiết bị trên nền tảng mở ([https://open.liankenet.com/](https://open.liankenet.com/#/device/detail?device_id=lc27cs03124305)), xem chi tiết tại [《Thông báo quan trọng: Nâng cấp bảo mật thiết bị Lianke Cloud》](https://lianke.yuque.com/vgtche/ng6y25/gylb4owfwsn4che4?singleDoc#%E3%80%8A%E9%87%8D%E8%A6%81%E9%80%9A%E7%9F%A5%EF%BC%9A%E9%93%BE%E7%A7%91%E4%BA%91%E8%AE%BE%E5%A4%87%E5%AE%89%E5%85%A8%E6%80%A7%E5%8D%87%E7%BA%A7%E3%80%8B)

1. **Bước 1 - Lấy thông tin máy in**

    - Mua Cloud Box, khuyến nghị sử dụng Lianke Cloud Box, [nhấn vào đây để đặt hàng](https://shop167081082.m.youzan.com/v2/showcase/homepage?alias=W79JHvloAF)
        
    - Lấy `deviceId` (tài khoản đám mây) và `deviceKey` (mật khẩu đám mây) từ mã QR
        
2. **Bước 2 - Gửi tác vụ in**

    - Thiết lập các tham số máy in và gửi tác vụ in
        
3. **Bước 3 - Truy vấn trạng thái in**

    - Truy vấn kết quả in (có thể sử dụng callback thay thế)
        

Địa chỉ máy chủ API: `cloud.liankenet.com`

---

`cloud.wisiyilink.com` **tên miền đã ngừng hoạt động, vui lòng thay đổi kịp thời, tên miền này có thể ngừng hoạt động bất cứ lúc nào** [nhấn vào đây để xem chi tiết thông báo cập nhật](https://lianke.yuque.com/vgtche/ng6y25/vywmdxu20ghmysle?singleDoc=)

## Thỏa thuận API

- Mỗi yêu cầu phải điền ApiKey trong phần headers _**(quan trọng, nếu không có ApiKey, Lianke sẽ không chịu trách nhiệm về việc gián đoạn dịch vụ)**_
    
- Vui lòng đăng ký trên nền tảng để lấy ApiKey [nhấn vào đây](https://open.liankenet.com)
    

## Cách lấy deviceId và deviceKey từ mã QR

- Phân tích mã QR để lấy liên kết trang web, phân tích liên kết trang web để lấy tham số token
    
- Lấy giá trị token và giải mã base64, thu được chuỗi phân tách bằng dấu ":"
    
- Phần trước của chuỗi là deviceId, phần sau là deviceKey
    

## SDK (cập nhật liên tục)

php sdk: [https://github.com/liankenet/cloud_printer_demo](https://github.com/liankenet/cloud_printer_demo)

Plugin cấu hình mạng cho ứng dụng nhỏ:

[https://mp.weixin.qq.com/wxopen/plugindevdoc?appid=wxa2a39810c572b508&token=1709758749&lang=zh_CN](https://mp.weixin.qq.com/wxopen/plugindevdoc?appid=wxa2a39810c572b508&token=1709758749&lang=zh_CN)

## Bản demo thử nghiệm API

[https://open.liankenet.com/api_demo/](https://open.liankenet.com/api_demo/#/home)

## Lưu ý (quan trọng)

- Vui lòng sử dụng [https://docs.liankenet.com/api_doc/](https://docs.liankenet.com/api_doc/) để lấy tài liệu mới nhất, tránh gặp sự cố do cập nhật phiên bản
    
- Vui lòng thông báo trước nếu có thời điểm lưu lượng truy cập cao để đảm bảo tính ổn định của dịch vụ
    
- Đây là dịch vụ chính thức, nghiêm cấm thực hiện kiểm tra tải trên API này, nếu có hành vi kiểm tra tải, sẽ bị coi là tấn công, Lianke có quyền vô hiệu hóa ApiKey và địa chỉ IP máy chủ, các hành vi tấn công gây ảnh hưởng nghiêm trọng đến hoạt động kinh doanh sẽ bị xử lý theo pháp luật
    

## Nhật ký cập nhật
01/03/2022
- Thêm các tham số `reportDeviceStatus`, `reportPrinterStatus` và `callbackUrl` vào giao diện in
01/02/2023
- Thêm chức năng đẩy thông báo, có thể đẩy thông báo về trạng thái thiết bị ngoại tuyến, máy in cắm/rút, v.v. kịp thời, nếu muốn sử dụng chức năng này, vui lòng thiết lập địa chỉ callback trong trang quản trị
07/02/2023
- Thêm API để đặt lại lỗi in liên tục
30/11/2023
- Thêm API để xóa các tác vụ đang chờ trong hàng đợi
- Thay đổi tên miền
11/01/2024
- Tối ưu hóa mô tả tham số jobFile khi gửi tác vụ
21/02/2024
- Thêm mô tả tham số jpScale
27/09/2024
- Tối ưu hóa mô tả tham số jobFile khi gửi tác vụ
08/10/2024
- Tối ưu hóa mô tả tham số jobFile khi gửi tác vụ
28/10/2024
- Thêm lời nhắc liên kết thiết bị trước khi kết nối
- Sửa đổi địa chỉ liên kết tài liệu
03/07/2025
- Giao diện refresh_device_info đã ngừng hoạt động

---

## 👤 Author

* Vietnamese Translation & Documentation: **Viet Anh Dang**

---

## 📄 License

This project is for internal use and documentation purposes only.
