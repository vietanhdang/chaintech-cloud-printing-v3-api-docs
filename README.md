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
    

26/11/2025

- Thêm mô tả tham số urlFileExt
# 📁 Collection: Bước 1 - Lấy thông tin máy in. 
undefined 


## End-point: 01-Lấy danh sách máy in của thiết bị.
Giao diện này trả về danh sách thông tin máy in; theo mặc định, danh sách này là thông tin thời gian thực của Cloud Box. Nếu thông tin máy in không được làm mới sau khi thay đổi, vui lòng **nâng cấp phần mềm**.

Mô tả các tham số trả về:

| Tham số | Mô tả |
|---|---|
| driver_type | 0 => Đang chờ hỗ trợ, 1 => Đã hỗ trợ, 2 => Không hỗ trợ |
| printer_name | Tên kiểu máy in |
| driver_name | Tương ứng với tham số printerModel của giao diện gửi |
| isPrinter | Cho biết đây có phải là máy in hay không, ý nghĩa cụ thể của tham số được trình bày trong bảng dưới đây |
| port | Tương ứng với devicePort, đại diện cho cổng USB thứ mấy; máy in mạng sẽ trả về 631, lúc này có thể điền 1 vào devicePort |
| support_status | Hỗ trợ các lệnh truy vấn trạng thái máy in bổ sung, cho biết có thể gọi [Giao diện truy vấn trạng thái máy in](https://documenter.getpostman.com/view/1758872/SWE83H6u?version=latest#9966c8c3-3c94-4436-be1b-81f8e10939f4) |
| printer_species | Loại máy in, tham khảo bảng để biết ý nghĩa |

Tham số máy in mạng:

- ip_addr: Địa chỉ IP của máy in mạng
- markers: Thông tin hộp mực, chỉ có ở máy in mạng
- printer_state: Trạng thái máy in mạng, idle là trạng thái sẵn sàng, printing là đang in, stopped là máy in gặp sự cố

##### Tham số isPrinter:

| Giá trị | Mô tả |
|---|---|
| 1 | Máy in |
| 0 | Không phải máy in (hoặc trong một số trường hợp, khi máy in ở trạng thái in, giá trị này sẽ được trả về) |

---

##### Tham số printer_species:

| Giá trị | Mô tả |
|---|---|
| 0 | Không xác định |
| 1 | Máy in kim |
| 2 | Máy in hóa đơn |
| 3 | Máy in nhãn |
| 4 | Máy in laser |
| 5 | Máy in phun mực |
| 6 | Máy in nhiệt |
| 7 | Máy in thẻ |
### Method: GET
>```
>{{url}}/api/external_api/printer_list?deviceId={{deviceId}}&deviceKey={{deviceKey}}&printerType=1
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|deviceId|{{deviceId}}|
|deviceKey|{{deviceKey}}|
|printerType|1|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "data": {
        "row": [
            {
                "MDL": "MA2000w",
                "device": null,
                "drivce_name": "Kyocera MA2000w GX",
                "driver_name": "Kyocera MA2000w GX",
                "driver_type": 1,
                "id": 611757,
                "idProduct": null,
                "idVendor": null,
                "isPrinter": 1,
                "port": 1,
                "printer_name": "Kyocera MA2000w GX",
                "printer_state": "outOfPaper",
                "product": "MA2000w",
                "species": 4,
                "support_status": true,
                "vendor": null
            },
            {
                "MDL": "",
                "device": null,
                "drivce_name": "ESC/POS通用驱动(203dpi) 模式2",
                "driver_name": "ESC/POS通用驱动(203dpi) 模式2",
                "driver_type": 1,
                "id": 611809,
                "idProduct": null,
                "idVendor": null,
                "isPrinter": 1,
                "port": 2,
                "printer_name": "ESC/POS通用驱动(203dpi) 模式2",
                "printer_state": "idle",
                "product": "BAR PRINTER",
                "species": 0,
                "support_status": false,
                "vendor": null
            },
            {
                "MDL": "e-STUDIO2323AM Printer",
                "device": null,
                "drivce_name": "TOSHIBA e-STUDIO2323AMSeries GDI",
                "driver_name": "TOSHIBA e-STUDIO2323AMSeries GDI",
                "driver_type": 1,
                "id": 612554,
                "idProduct": null,
                "idVendor": null,
                "isPrinter": 1,
                "port": 3,
                "printer_name": "TOSHIBA e-STUDIO2323AMSeries GDI",
                "printer_state": "outOfPaper",
                "product": "TOSHIBA e-STUDIO2323AM Scanner",
                "species": 4,
                "support_status": false,
                "vendor": null
            }
        ],
        "total": 3
    }
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: 02-Lấy thông số máy in [Vui lòng lưu dữ liệu vào bộ nhớ cache sau khi gọi hàm].
Lấy các tham số của thiết bị máy in đích:

*   `printerModel`: Tên kiểu máy in, tương ứng với `driver_name` trong `printer_list`.

Các giá trị tham số lấy được sẽ được điền vào giao diện API `api/print/job`.
### Method: GET
>```
>{{url}}/api/print/printer_params?printerModel={{printerModel}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|printerModel|{{printerModel}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "Capabilities": {
            "Bins": {
                "在纸盘 1 中手动进纸": 4,
                "纸盘 1": 1,
                "自动选择": 7
            },
            "Color": {
                "黑白": 1
            },
            "Copies": 999,
            "Duplex": {
                "关闭": 1,
                "短边": 3,
                "长边": 2
            },
            "MediaTypes": {
                "默认": 0
            },
            "Orientation": {
                "横向": 2,
                "竖向": 1
            },
            "Papers": {
                "10 号信封": 20,
                "16 开 184x260 毫米": 263,
                "16 开 195x270 毫米": 264,
                "16 开 197x273 毫米": 265,
                "8.5x13（自定义）": 258,
                "A4": 9,
                "A5": 11,
                "A6": 70,
                "B5 (JIS)": 13,
                "B5 信封": 34,
                "C5 信封": 28,
                "DL 信封": 27,
                "Double Japan Postcard Rotated": 82,
                "Executive": 7,
                "Japanese Postcard": 43,
                "Legal": 5,
                "Letter": 1,
                "Monarch 信封": 37,
                "A4连续纸(22.86x27.96)\r\n": 512,
                "A4连续纸(24.1x27.96)\r\n": 513,
                "A4连续纸(21x27.96)": 514,
                "A4连续纸(21.6x27.9)": 515,
                "A4连续纸二等分(22.86x13.98)": 516,
                "A4连续纸二等分(24.1x14)": 517,
                "A4连续纸二等分(21x13.98)": 518,
                "A4连续纸二等分(21.6x13.95)": 519,
                "A4连续纸三等分(22.86x9.32)": 520,
                "A4连续纸三等分(24.1x9.32)": 521,
                "A4连续纸三等分(21x9.32)": 522,
                "A4连续纸三等分(21.6x9.3)": 523,
                "A4连续纸不分页(22.86x500)": 524,
                "A4连续纸不分页(24.1x500)": 525,
                "A4连续纸不分页(21x500)": 526,
                "A4连续纸不分页(21.6x500)": 527,
                "标签纸（80x200mm）": 528,
                "标签纸（80x100mm）": 529,
                "A4连续纸(24.10x27.90)": 530
            },
            "Resolutions": null
        },
        "DevMode": {
            "BitsPerPel": 0,
            "Collate": 0,
            "Color": 1,
            "Copies": 1,
            "DefaultSource": 7,
            "DeviceName": [
                72,
                80,
                32,
                76,
                97,
                115,
                101,
                114,
                74,
                101,
                116,
                32,
                80,
                49,
                48,
                48,
                55,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0
            ],
            "DisplayFlags": 0,
            "DisplayFrequency": 0,
            "DitherType": 0,
            "DriverExtra": 821,
            "DriverVersion": 3,
            "Duplex": 1,
            "Fields": 40719,
            "FormName": [
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0
            ],
            "ICMIntent": 0,
            "ICMMethod": 0,
            "LogPixels": 0,
            "MediaType": 0,
            "Orientation": 1,
            "PanningHeight": 0,
            "PanningWidth": 0,
            "PaperLength": 2970,
            "PaperSize": 9,
            "PaperWidth": 2100,
            "PelsHeight": 0,
            "PelsWidth": 0,
            "PrintQuality": 600,
            "Reserved1": 0,
            "Reserved2": 0,
            "Scale": 0,
            "Size": 220,
            "SpecVersion": 1025,
            "TTOption": 0,
            "YResolution": 0
        },
        "DeviceContext": {
            "BitsPixel": 8,
            "HorzRes": 4736,
            "HorzSize": 200,
            "LogPixelsX": 600,
            "LogPixelsY": 600,
            "NumColors": 256,
            "PhysicalHeight": 7016,
            "PhysicalOffsetX": 94,
            "PhysicalOffsetY": 94,
            "PhysicalWidth": 4961,
            "VertRes": 6824,
            "VertSize": 289
        },
        "Name": "HP LaserJet P1007"
    }
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Bước 2 - Gửi công việc in. 
undefined 


## End-point: Gửi yêu cầu in (cách sử dụng cơ bản)
Gửi yêu cầu in

Định dạng `form-data`, không phải JSON.
Loại tham số đầu vào `content-type` là `form-data`.

Đây là một API không đồng bộ, việc gọi API sẽ không bị chặn và sẽ trả về kết quả ngay lập tức. Kết quả trả về lúc này chỉ cho biết yêu cầu đã được chấp nhận thành công, chứ không phải là quá trình in đã hoàn tất.

Khi API này gửi yêu cầu thành công, nó sẽ trả về `task_id` do hệ thống tạo ra, đây là ID duy nhất của nhiệm vụ, có thể được sử dụng để truy vấn trạng thái nhiệm vụ hoặc hủy nhiệm vụ sau này.
### Method: POST
>```
>{{url}}/api/print/job
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body formdata

|Param|value|Type|
|---|---|---|
|deviceId|{{deviceId}}|text|
|deviceKey|{{deviceKey}}|text|
|devicePort|{{devicePort}}|text|
|jobFile|WechatIMG8442.jpg|file|
|dmPaperSize|9|text|
|jpAutoScale|4|text|
|jpScale|fit|text|
|dmOrientation|1|text|
|dmCopies|1|text|
|dmColor|1|text|
|urlFileExt|.pdf|text|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "task_id": "581decf2-c6f6-4163-8646-5dcc0c3c1c05"
    }
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Gửi công việc in (các tùy chọn nâng cao)
Dưới đây là một số tham số bổ sung khi gửi yêu cầu.

Định dạng `form-data`, không phải JSON.
Loại tham số đầu vào `content-type` là `form-data`.

API này là API không đồng bộ, việc gọi không chặn, sẽ trả về kết quả ngay lập tức. Kết quả trả về lúc này chỉ cho biết yêu cầu đã được chấp nhận thành công, **chứ không phải là quá trình in đã hoàn tất.**

Khi API này gửi yêu cầu thành công, nó sẽ trả về `task_id` do hệ thống tạo ra làm ID duy nhất cho yêu cầu. ID này có thể được sử dụng để truy vấn trạng thái yêu cầu hoặc hủy yêu cầu sau này.

---

Giải thích về chức năng gọi lại `callbackUrl`:

- Yêu cầu gọi lại là yêu cầu POST, URL gọi lại có thể chứa các tham số. Dữ liệu POST có định dạng JSON, ví dụ như sau:

```json
{'device_id': 'lk112312312312', 'task_id': 'bd85931c-38fa-4891-b1fa-5e1cf160ec12', 'task_state': 'SUCCESS', 'create_time': '2022-03-01 17:15:02', 'finish_time': '2022-03-01 17:30:58', 'task_result': {'code': 503, 'msg': 'Thiết bị kết nối không ổn định, vui lòng kiểm tra kết nối mạng của thiết bị'}}
```

Giải thích về `errLimitNum`:

Giá trị này đại diện cho số lượng tối đa các yêu cầu liên tiếp bị lỗi được phép, mặc định là 30. Sau khi đạt đến giới hạn này, giá trị trả về sẽ là:

```json
{"code": 11203, "msg": "Số lượng yêu cầu liên tiếp bị lỗi vượt quá %d lần, thiết bị này đã bị tạm dừng sử dụng, vui lòng thử lại sau 30 phút hoặc liên hệ với bộ phận hỗ trợ khách hàng để gỡ bỏ"}
```

Sau khi đạt đến giới hạn, bạn có thể gọi API để gỡ bỏ giới hạn, bằng cách nhấp vào: [API gỡ bỏ giới hạn do số lượng yêu cầu in thất bại quá nhiều](https://documenter.getpostman.com/view/1758872/SWE83H6u#cf31c2a9-716f-4db0-801b-a3b816de4fb7)
### Method: POST
>```
>{{url}}/api/print/job
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body formdata

|Param|value|Type|
|---|---|---|
|deviceId|{{deviceId}}|text|
|deviceKey|{{deviceKey}}|text|
|devicePort|{{devicePort}}|text|
|printerModel|{{printerModel}}|text|
|jobFile|/D:/Stocks/Messy/5270.png|file|
|dmPaperSize|9|text|
|dmOrientation|1|text|
|dmCopies|1|text|
|dmDefaultSource|1|text|
|dmColor|1|text|
|dmDuplex|1|text|
|dmMediaType|256|text|
|dmPaperLength|300|text|
|dmPaperWidth|200|text|
|dmPrintQuality||text|
|isPreview|1|text|
|htmlKernel|wkhtml|text|
|targetIp|192.168.1.1|text|
|jpPageRange||text|
|jpAutoScale|4|text|
|jpScale|fit|text|
|jpAutoAlign|z5|text|
|reportDeviceStatus|1|text|
|reportPrinterStatus|1|text|
|callbackUrl|https://xxx.com/xxxxx|text|
|taskTicket|xxxx|text|
|errLimitNum|30|text|
|pdfRev|0|text|
|jpAutoRotate|0|text|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "task_id": "581decf2-c6f6-4163-8646-5dcc0c3c1c05"
    }
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Bước 3 - Kiểm tra trạng thái in. 
undefined 


## End-point: Lấy thông tin về công việc in.
```json
{
  "translation": "Trong hầu hết các trường hợp, nên sử dụng chức năng gọi lại (callback) của giao diện `POST api/print/job` thay vì giao diện này.\n\nKhi gửi yêu cầu in, hãy sử dụng ID nhiệm vụ (`task_id`) được trả về để truy vấn trạng thái nhiệm vụ in. Nếu là bản xem trước, giao diện sẽ trả về hình ảnh xem trước.\n\n_**Đề xuất khoảng thời gian kiểm tra lại là 10 giây**_\n\n---\n\nTrong kết quả trả về, `task_state` thể hiện trạng thái của hàng đợi, trong đó:\n\n- `READY`: Đang chờ xử lý\n- `PARSING`: Đang phân tích\n- `SENDING`: Đang gửi\n- `SUCCESS`: Thành công\n- `FAILURE`: Thất bại\n- `SET_REVOKE`: Đã đánh dấu để hủy\n- `REVOKED`: Hủy thành công\n\nKhi trạng thái hàng đợi là thành công, **giá trị trả về sẽ bao gồm** `task_result`, **thể hiện kết quả in**. Nếu mã là 200, nghĩa là in thành công; nếu không phải 200, nghĩa là in thất bại. Thông tin chi tiết xem ở `msg`."
}
```
### Method: GET
>```
>{{url}}/api/print/job?deviceId={{deviceId}}&deviceKey={{deviceKey}}&devicePort={{devicePort}}&task_id={{task_id}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|deviceId|{{deviceId}}|
|deviceKey|{{deviceKey}}|
|devicePort|{{devicePort}}|
|task_id|{{task_id}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "data": {
        "task_done_time": "Wed, 06 Dec 2023 02:06:12 GMT",
        "task_done_timestamp": 1701828372789,
        "task_result": {
            "code": 200,
            "data": {
                "file_total": 108499,
                "send_total": 108499,
                "total_page": 2
            },
            "msg": "success"
        },
        "task_state": "SUCCESS"
    },
    "msg": "success"
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Khác (lấy thông tin máy chủ, hủy tác vụ, v.v.) 
undefined 


## End-point: Lấy thông tin thiết bị (trạng thái trực tuyến, kiểu máy, phiên bản phần mềm, thông tin mạng).
Lấy thông tin thiết bị

Bao gồm trạng thái trực tuyến, số lượng cổng USB, thời gian hết hạn, phiên bản phần cứng và phần mềm của thiết bị, thông tin mạng của thiết bị.

#### Tham số "online":
| Giá trị | Mô tả |
|---------|---------------|
| null | Chưa từng khởi động |
| 1 | Trực tuyến |
| 0 | Ngoại tuyến |
### Method: GET
>```
>{{url}}/api/device/device_info?deviceId={{deviceId}}&deviceKey={{deviceKey}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|deviceId|{{deviceId}}|
|deviceKey|{{deviceKey}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "data": {
        "info": {
            "api_support": 1,
            "device_type": 2,
            "expire_date": "2024年8月25日",
            "is_expire": false,
            "mobile_support": 1,
            "online": 1,
            "remote_support": 1,
            "usb_port_num": 3
        },
        "network": {
            "lan": {
                "dns": "",
                "gateway": "",
                "ipaddr": "169.254.1.188",
                "link": [
                    false
                ],
                "macaddr": "",
                "netmask": "255.255.0.0",
                "proto": "dhcp"
            },
            "wwan": {
                "dns": [
                    "192.168.5.29"
                ],
                "gateway": "192.168.5.29",
                "ipaddr": "192.168.7.156",
                "macaddr": "",
                "netmask": "255.255.252.0",
                "proto": "dhcp"
            }
        },
        "version": {
            "hardware": "LK300EW_D2",
            "software": "2.1.113"
        }
    },
    "msg": "success"
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Hủy tác vụ in.
### Method: DELETE
>```
>{{url}}/api/print/job?deviceId={{deviceId}}&deviceKey={{deviceKey}}&devicePort={{devicePort}}&task_id={{task_id}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|deviceId|{{deviceId}}|
|deviceKey|{{deviceKey}}|
|devicePort|{{devicePort}}|
|task_id|{{task_id}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success"
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Lấy danh sách các kiểu máy in được hỗ trợ.
Lấy danh sách tất cả các kiểu máy in được hỗ trợ cho máy in trên máy chủ đám mây.<br>
_(Nếu kiểu máy in của bạn không có trong danh sách, vui lòng phản hồi cho chúng tôi và chúng tôi sẽ cập nhật trong thời gian sớm nhất)_
### Method: GET
>```
>{{url}}/api/print/printer_enum
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "data": [
        "DASCOM DS-660",
        "XP-80",
        "QR-588 LABEL",
        "Microsoft XPS Document Writer",
        "KM-300S",
        "KM-300BU",
        "KM-218PRE",
        "KM-218BT",
        "KM-218",
        "KM-200SP",
        "KM-200",
        "KM-118S",
        "KM-118HD",
        "KM-118C",
        "KM-118BT",
        "KM-118",
        "KM-1100",
        "KM-108",
        "KM-100S",
        "KM-100HD",
        "KM-100",
        "HP LaserJet P1007",
        "EPSON L310 Series",
        "Deli DL-735K",
        "Deli DL-730K",
        "Deli DL-690K",
        "Deli DL-635K",
        "Deli DL-630K",
        "Deli DL-590K",
        "Deli DE-730K",
        "Deli DE-690K",
        "Deli DE-630K",
        "Deli DE-590K",
        "Canon MP280 series Printer",
        "Brother MFC-7880DN Printer"
    ],
    "msg": "success"
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Tìm kiếm các kiểu máy in được hỗ trợ.
Hỗ trợ tìm kiếm mờ dựa trên các kiểu máy in từ danh sách `printer_enum`.
### Method: POST
>```
>{{url}}/api/print/printer_enum
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body (**raw**)

```json
{
    "query": "HP 1020"
}
```

### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success",
    "data": [
        "HP LaserJet 1020",
        "HP Laser NS 1020 PCLmS",
        "HP LaserJet Professional CP1020 Series",
        "Canon iR1020/1024/1025 UFRII LT",
        "JIAPUWEI JPW1020",
        "Kyocera Mita FS-1020D KX",
        "Biaotop TP-1020",
        "TEJIEYIDE TJYD1020",
        "Kyocera FS-1020MFP GX"
    ]
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Truy vấn thông tin về các công việc in của một thiết bị cụ thể trong vòng một ngày.
Truy vấn thông tin về các công việc in của một thiết bị cụ thể trong vòng một ngày.
### Method: POST
>```
>{{url}}/api/print/query_device_task
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body (**raw**)

```json
{
	"deviceId": "{{deviceId}}",
	"deviceKey": "{{deviceKey}}"
}
```

### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "task_list": [
            {
                "task_id": "0241a927-a218-4ff6-894d-8fe427da794c",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-02 11:02:36",
                "updated_at": "2020-09-02 11:02:39"
            },
            {
                "task_id": "69599185-cb22-4a11-8af0-65756911f5d8",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-02 11:00:33",
                "updated_at": "2020-09-02 11:00:38"
            },
            {
                "task_id": "91d6d3d4-8281-4d12-b37c-5b949ea8dd70",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-02 10:55:32",
                "updated_at": "2020-09-02 10:55:39"
            },
            {
                "task_id": "b98a3a4d-efe9-4195-a105-64617edd4036",
                "result": {
                    "code": 500,
                    "msg": "设备连接异常，请检查设备网络: 错误详情：server id not found"
                },
                "job_id": "",
                "job_status": 0,
                "status": "SUCCESS",
                "create_at": "2020-09-02 10:54:41",
                "updated_at": "2020-09-02 10:55:26"
            },
            {
                "task_id": "91f501f8-68b7-4645-ad61-d276afa51a9f",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-02 10:52:38",
                "updated_at": "2020-09-02 10:52:45"
            },
            {
                "task_id": "91df13b5-cc8e-4eb5-b1c9-cd7069fae7e7",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-02 10:52:30",
                "updated_at": "2020-09-02 10:52:35"
            },
            {
                "task_id": "8dbc4f98-0165-4809-b5b5-c81db3a5a784",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-02 10:42:09",
                "updated_at": "2020-09-02 10:45:32"
            },
            {
                "task_id": "76a1e3af-5daa-4507-8ebc-99c3cb4ad096",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 21:48:06",
                "updated_at": "2020-09-01 21:48:11"
            },
            {
                "task_id": "d1202e2e-17ba-41e7-b5c6-00083916b4b8",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 21:47:41",
                "updated_at": "2020-09-01 21:47:45"
            },
            {
                "task_id": "b35dc664-b6ad-47f2-b56e-61f7918c6eb4",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 21:47:29",
                "updated_at": "2020-09-01 21:47:33"
            },
            {
                "task_id": "d910af11-f161-40cf-b5bd-2c91e75a10b9",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 21:47:20",
                "updated_at": "2020-09-01 21:47:24"
            },
            {
                "task_id": "1dc3638e-18d9-4c77-ba8b-bf38e5c5329d",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 21:47:08",
                "updated_at": "2020-09-01 21:47:13"
            },
            {
                "task_id": "87df59f8-d617-4307-8a08-4bc8b08388ac",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 21:46:22",
                "updated_at": "2020-09-01 21:46:26"
            },
            {
                "task_id": "dd998193-f7af-4b85-8075-45a1305dadf6",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 21:44:34",
                "updated_at": "2020-09-01 21:44:38"
            },
            {
                "task_id": "fa166254-d302-48d7-9e84-5311fe41c6ac",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 18:08:51",
                "updated_at": "2020-09-01 18:08:56"
            },
            {
                "task_id": "8524ddea-16ca-4e8e-8fbe-3ba354a63058",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 18:08:41",
                "updated_at": "2020-09-01 18:08:46"
            },
            {
                "task_id": "e3047717-475a-45c8-903a-640c84ef3ae2",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 18:07:29",
                "updated_at": "2020-09-01 18:07:37"
            },
            {
                "task_id": "b20839b8-8cc5-4d9c-9753-ce1543d43f25",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 18:05:57",
                "updated_at": "2020-09-01 18:06:01"
            },
            {
                "task_id": "91289972-b04c-4892-b25e-e38afe14a51f",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 18:05:37",
                "updated_at": "2020-09-01 18:05:41"
            },
            {
                "task_id": "7adbc4c1-c007-4312-81c4-fc3bb9bd01da",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 18:05:22",
                "updated_at": "2020-09-01 18:05:28"
            },
            {
                "task_id": "686a947b-e4e2-4178-8315-543dea680b93",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 18:05:11",
                "updated_at": "2020-09-01 18:05:16"
            },
            {
                "task_id": "48a4469b-3b40-47dd-ab2d-52d991651661",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:32:18",
                "updated_at": "2020-09-01 17:32:39"
            },
            {
                "task_id": "a0214c1b-a9da-4fd7-bde8-8871195623ea",
                "result": {
                    "code": 502,
                    "msg": "转换文件格式失败: 无法旋转文件方向，请检查纸张横竖向是否设置错误"
                },
                "job_id": "",
                "job_status": 0,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:30:18",
                "updated_at": "2020-09-01 17:30:36"
            },
            {
                "task_id": "2e60ff43-7ec0-4f18-96e9-e85cd5cfcc30",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:30:02",
                "updated_at": "2020-09-01 17:30:12"
            },
            {
                "task_id": "d2ed94eb-240a-4071-bef7-3df1f76fc480",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:29:22",
                "updated_at": "2020-09-01 17:29:32"
            },
            {
                "task_id": "7b47f626-af74-4f3f-9677-c04e75ebc781",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:28:46",
                "updated_at": "2020-09-01 17:28:54"
            },
            {
                "task_id": "0e7991cb-5999-41b2-b79a-91425c4170e7",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:28:03",
                "updated_at": "2020-09-01 17:28:19"
            },
            {
                "task_id": "2bbfe936-79f8-4abd-9f4b-121fd8c4e7f3",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:27:19",
                "updated_at": "2020-09-01 17:27:31"
            },
            {
                "task_id": "19c7824e-f442-410f-90f8-7e8da73ea611",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:26:39",
                "updated_at": "2020-09-01 17:26:55"
            },
            {
                "task_id": "964017df-11b6-4a84-b40d-0f44fc5407b6",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:26:18",
                "updated_at": "2020-09-01 17:26:32"
            },
            {
                "task_id": "31fc44d2-5ad0-4563-80bf-34159f29f541",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:25:41",
                "updated_at": "2020-09-01 17:25:51"
            },
            {
                "task_id": "eea34278-2a00-4c5f-b917-ccf13c3c2321",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:24:24",
                "updated_at": "2020-09-01 17:24:40"
            },
            {
                "task_id": "754403c5-ae33-4310-a04a-f77fd8444f4c",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:23:00",
                "updated_at": "2020-09-01 17:23:10"
            },
            {
                "task_id": "4375eb0d-57a9-4abb-a0c8-bed4f23ea346",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:22:45",
                "updated_at": "2020-09-01 17:22:57"
            },
            {
                "task_id": "5362b09a-ffcc-484d-b8d3-db62e6774f48",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:20:09",
                "updated_at": "2020-09-01 17:20:28"
            },
            {
                "task_id": "a914ac53-6f20-42b9-b559-da691fc2ee05",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:17:48",
                "updated_at": "2020-09-01 17:17:56"
            },
            {
                "task_id": "38c6d0d2-c6fd-4e1f-b715-79cf00fae765",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:12:49",
                "updated_at": "2020-09-01 17:13:08"
            },
            {
                "task_id": "f25d3dd4-1351-4ade-be41-b27a271d2206",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 17:12:10",
                "updated_at": "2020-09-01 17:12:27"
            },
            {
                "task_id": "f808e90d-785c-472e-b227-95da770dddd0",
                "result": {
                    "code": 200,
                    "msg": "success"
                },
                "job_id": "",
                "job_status": 1,
                "status": "SUCCESS",
                "create_at": "2020-09-01 16:21:22",
                "updated_at": "2020-09-01 16:21:30"
            }
        ]
    }
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Gửi yêu cầu cấp bộ điều hợp máy in chưa được nhận dạng.
Chỉ dùng để thông báo về việc điều chỉnh cho các dòng máy chưa được hỗ trợ. Sau khi gửi yêu cầu điều chỉnh, chúng tôi sẽ thực hiện điều chỉnh trong vòng 72 giờ. Thông báo hoàn tất điều chỉnh sẽ được gửi đến số điện thoại đã cung cấp.

- "printerId": `ID tương ứng trong danh sách printer_list`
- "phone": `Số điện thoại để nhận thông báo khi cài đặt thành công`
### Method: POST
>```
>{{url}}/api/driver/uninstall_driver_event
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body (**raw**)

```json
{
	"deviceId": "{{deviceId}}",
	"deviceKey": "{{deviceKey}}",
	"printerId": "1",
	"phone": "13512345678"
}
```

### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
```json
{
    "code": 403,
    "msg": "Số điện thoại không hợp lệ"
}
```
```
</details>

### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success"
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Làm mới thông tin thiết bị theo thời gian thực.
**Khi phiên bản phần mềm là 2.1.112 trở lên, thao tác làm mới sẽ do Linker xử lý nội bộ, không cần gọi giao diện này.**

Giao diện này dùng để làm mới trạng thái trực tuyến của máy chủ in. Sau khi gọi giao diện này, hệ thống sẽ trả về kết quả ngay lập tức, và thao tác làm mới sẽ được thực hiện trong hàng đợi nền. Giao diện này tương tự như giao diện đồng bộ, đồng bộ thông tin thiết bị giữa máy chủ và máy chủ in, cũng như thông tin thời gian thực của cổng USB, để đảm bảo máy in không gặp phải tình trạng hiển thị ký tự lạ.

_**Thay vì sử dụng giao diện này để kiểm tra trạng thái trực tuyến, hãy sử dụng giao diện**_[*device_info*](https://documenter.getpostman.com/view/1758872/SWE83H6u#5c1d412a-d0db-4a88-8cdb-7891fea21cc2)_**hoặc kích hoạt tùy chọn `reportDeviceStatus` trong `add_job`.**_

Trong kết quả trả về, `code` đại diện cho trạng thái của thiết bị, trong đó:

- `200`: Yêu cầu thành công
- `401`: Đang thực hiện làm mới
- `404`: ID hoặc mật khẩu thiết bị không chính xác
- `10009`: Yêu cầu quá thường xuyên, chỉ cho phép gọi một lần cho mỗi thiết bị.
### Method: GET
>```
>{{url}}/api/device/async_refresh_device_info?deviceId={{deviceId}}&deviceKey={{deviceKey}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|deviceId|{{deviceId}}|
|deviceKey|{{deviceKey}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success"
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Nhận thông tin trạng thái máy in theo thời gian thực.
Làm mới thông tin trạng thái in, chẳng hạn như nắp mở, hết giấy, hết băng mực, v.v.

Lưu ý:

1. Hiện tại chỉ hỗ trợ một số loại máy in nhất định. Trước khi sử dụng giao diện này, vui lòng đảm bảo rằng trường `support_status` trả về trong danh sách máy in là `true`.

2. **Chức năng này đồng bộ dữ liệu máy in theo thời gian thực. Thời gian trả về của giao diện có thể chậm hơn (các yếu tố ảnh hưởng bao gồm trạng thái mạng của khách hàng và tốc độ phản hồi của máy in). Vui lòng chỉ gọi khi cần thiết. Giao diện này giới hạn số lượng yêu cầu đồng thời từ cùng một thiết bị là 1. Nếu thiết bị gửi nhiều yêu cầu đến cùng một cổng USB trong một khoảng thời gian ngắn, hệ thống sẽ trả về thông báo "yêu cầu quá tải".**

3. Nên sử dụng chức năng này với phiên bản phần mềm cố định cao hơn 2.1.60.

Kết quả trả về:

- `headOpened`: Nắp đã mở.
- `paperJam`: Kẹt giấy.
- `outOfPaper`: Hết giấy.
- `outOfRibbon`: Hết băng mực (chỉ áp dụng cho các loại máy in nhãn có chức năng sử dụng băng mực).
- `outOfInk`: Mực/bột in thấp (chỉ áp dụng cho một số loại máy in laser và máy in phun).
- `pause`: Máy in đang tạm dừng.
- `printing`: Đang in.
- `msg`: Thông báo.

Một số loại máy có thể trả về các trường sau:

- `statusCode`: Mã trạng thái.
- `errCode`: Mã lỗi.
### Method: GET
>```
>{{url}}/api/device/printer_status?deviceId={{deviceId}}&deviceKey={{deviceKey}}&usbPort={{devicePort}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|deviceId|{{deviceId}}|
|deviceKey|{{deviceKey}}|
|usbPort|{{devicePort}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "data": {
        "errCode": null,
        "headOpened": false,
        "msg": "Cannot feed paper.",
        "outOfInk": false,
        "outOfPaper": true,
        "paperJam": false,
        "pause": true,
        "printing": false,
        "statusCode": "41208"
    },
    "msg": "success"
}
```
</details>

### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
```json
{
    "code": 497,
    "msg": "Không tìm thấy máy in, vui lòng kết nối máy in và thử lại."
}
```
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: 【Tùy chọn | Máy in mạng】Tìm kiếm máy in mạng trong mạng cục bộ.
*** Giao diện này chỉ dành cho máy in mạng, không hỗ trợ máy in kết nối qua USB. ***

Giao diện này sẽ tìm kiếm các máy in mạng được hỗ trợ trong mạng cục bộ của thiết bị và trả về tổng số máy in được tìm thấy.

Theo mặc định, thiết bị sẽ tự động gọi giao diện này một lần khi khởi động và chỉ gọi một lần nữa trong vòng 12 giờ, ngay cả khi thiết bị được khởi động lại nhiều lần.
### Method: GET
>```
>{{url}}/api/printer/refresh_network_printer?deviceId={{deviceId}}&deviceKey={{deviceKey}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Query Params

|Param|value|
|---|---|
|deviceId|{{deviceId}}|
|||
|deviceKey|{{deviceKey}}|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: 【Ưu đãi có thời hạn】Nhận số trang của tài liệu/PDF.
**Giao diện này đang trong giai đoạn thử nghiệm, được cung cấp miễn phí trong thời gian giới hạn. Dịch vụ miễn phí này không có cam kết về mức độ dịch vụ (SLA). Sau này, giá sẽ được tính dựa trên mức độ sử dụng thực tế.**

Nếu giao diện này không đáp ứng được yêu cầu của bạn, Alibaba Cloud có các dịch vụ tương tự, bạn có thể sử dụng giao diện của Alibaba Cloud để thay thế chức năng này.

Lưu ý:

1. Mỗi lần chỉ hỗ trợ một tệp duy nhất.

2. Giao diện này có thời gian xử lý yêu cầu khá lâu, vì vậy khi sử dụng URL, việc tải xuống tệp phải hoàn thành trong vòng 5 giây.

3. Tệp tải lên không được lớn hơn 20MB.

4. Không được phép thử lại liên tục với cùng một tệp bị lỗi. Nếu số lần thử vượt quá một giới hạn nhất định, yêu cầu sẽ bị tạm thời chặn.
### Method: POST
>```
>{{url}}/api/print/file_pages
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body formdata

|Param|value|Type|
|---|---|---|
|deviceId|{{deviceId}}|text|
|deviceKey|{{deviceKey}}|text|
|devicePort|{{devicePort}}|text|
|printerModel|{{printerModel}}|text|
|dmPaperSize|9|text|
|jobFile|Hollow-Clock-4.pdf|file|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Gỡ bỏ giới hạn do số lần in bị lỗi quá nhiều.
Trong một số trường hợp, một thiết bị đơn lẻ gặp sự cố, nhưng vẫn tiếp tục khởi tạo in. Sau khi in thất bại liên tục 30 lần, hệ thống sẽ kích hoạt cơ chế hạn chế. Lúc này, có thể thông báo cho người dùng để kiểm tra và khắc phục sự cố của máy in hoặc thiết bị. Sau khi hoàn tất, có thể sử dụng giao diện này để hủy bỏ cơ chế hạn chế. Giao diện này có thể được gọi tối đa 10 lần mỗi ngày cho mỗi thiết bị, vui lòng sử dụng hợp lý.

Giá trị trả về

| **code** | **msg** | **Ý nghĩa** |
|---|---|---|
| 200 | success | Xóa lỗi tác vụ thành công |
| 10009 | 请求频繁 | Chỉ cho phép một yêu cầu cho mỗi thiết bị trong một khoảng thời gian nhất định |
| 11200 | 重置打印失败限制失败，当天重置次数超过限制 | Đã đạt đến giới hạn số lần đặt lại tối đa mỗi ngày |
| 11201 | 暂无打印失败记录，无法重置 | Không có bản ghi lỗi in, không thể đặt lại |
### Method: POST
>```
>{{url}}/api/print/reset_printing_error_limit
>```
### Body (**raw**)

```json
{
    "deviceId": "{{deviceId}}",
    "deviceKey": "{{deviceKey}}",
    "devicePort": "{{devicePort}}"
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Khởi động lại giao diện thiết bị.
Sau khi khởi động lại thiết bị, thiết bị sẽ không thể in trong quá trình khởi động lại, vui lòng thực hiện thao tác cẩn thận; giao diện này không hỗ trợ thực hiện đồng thời, sau khi khởi tạo, quá trình khởi động lại sẽ được thực hiện không đồng bộ.

Giá trị trả về

| **code** | **msg** | **Ý nghĩa** |
| --- | --- | --- |
| 200 | success | Khởi động lại thành công |
| 401 | 正在重启中 | Trả về khi đang thực hiện thao tác khởi động lại sau khi nhận yêu cầu |
| 5002 | 设备已离线，请检查云指示灯 | Khởi động lại yêu cầu thiết bị phải ở trạng thái trực tuyến |
### Method: POST
>```
>{{url}}/api/device/async_device_reboot
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body (**raw**)

```json
{
    "deviceId": "{{deviceId}}",
    "deviceKey": "{{deviceKey}}"
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Lấy danh sách các khổ giấy mà máy in hỗ trợ.
Lấy các tham số của máy in đích:

- `printerModel`: Tên kiểu máy in, tương ứng với `driver_name` trong `printer_list`.

Giá trị trả về:

- `physical_height`: Chiều cao vật lý của giấy, đơn vị là 0,1 mm.
- `physical_width`: Chiều rộng vật lý của giấy, đơn vị là 0,1 mm.
- `printable_height`: Chiều cao của vùng có thể in, đơn vị là 0,1 mm.
- `printable_width`: Chiều rộng của vùng có thể in, đơn vị là 0,1 mm.
- `paper_id`: ID của loại giấy, tương ứng với `dmPaperSize`.
### Method: GET
>```
>{{url}}/api/print/paper_dimension_list?printerModel={{printerModel}}
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body formdata

|Param|value|Type|
|---|---|---|


### Query Params

|Param|value|
|---|---|
|printerModel|{{printerModel}}|


### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "16K": {
            "paper_id": 257,
            "physical_height": 2730,
            "physical_width": 1968,
            "printable_height": 2650,
            "printable_width": 1840
        },
        "8.5x13": {
            "paper_id": 258,
            "physical_height": 3302,
            "physical_width": 2159,
            "printable_height": 3220,
            "printable_width": 2060
        },
        "明信片": {
            "paper_id": 260,
            "physical_height": 1480,
            "physical_width": 1000,
            "printable_height": 1400,
            "printable_width": 870
        },
        "双面明信片": {
            "paper_id": 261,
            "physical_height": 2000,
            "physical_width": 1480,
            "printable_height": 1920,
            "printable_width": 1350
        },
        "A6": {
            "paper_id": 262,
            "physical_height": 1480,
            "physical_width": 1050,
            "printable_height": 1400,
            "printable_width": 920
        },
        "B5 (ISO)": {
            "paper_id": 259,
            "physical_height": 2500,
            "physical_width": 1760,
            "printable_height": 2420,
            "printable_width": 1680
        },
        "B5 (JIS)": {
            "paper_id": 13,
            "physical_height": 2570,
            "physical_width": 1820,
            "printable_height": 2490,
            "printable_width": 1730
        },
        "Monarch 信封": {
            "paper_id": 37,
            "physical_height": 1905,
            "physical_width": 983,
            "printable_height": 1820,
            "printable_width": 870
        },
        "B5 信封": {
            "paper_id": 34,
            "physical_height": 2500,
            "physical_width": 1760,
            "printable_height": 2420,
            "printable_width": 1680
        },
        "C5 信封": {
            "paper_id": 28,
            "physical_height": 2290,
            "physical_width": 1620,
            "printable_height": 2210,
            "printable_width": 1520
        },
        "DL 信封": {
            "paper_id": 27,
            "physical_height": 2200,
            "physical_width": 1100,
            "printable_height": 2120,
            "printable_width": 980
        },
        "10 号信封": {
            "paper_id": 20,
            "physical_height": 2413,
            "physical_width": 1046,
            "printable_height": 2330,
            "printable_width": 920
        },
        "A5": {
            "paper_id": 11,
            "physical_height": 2100,
            "physical_width": 1480,
            "printable_height": 2020,
            "printable_width": 1350
        },
        "A4": {
            "paper_id": 9,
            "physical_height": 2970,
            "physical_width": 2100,
            "printable_height": 2890,
            "printable_width": 2000
        },
        "Executive": {
            "paper_id": 7,
            "physical_height": 2667,
            "physical_width": 1842,
            "printable_height": 2580,
            "printable_width": 1730
        },
        "Legal": {
            "paper_id": 5,
            "physical_height": 3556,
            "physical_width": 2159,
            "printable_height": 3470,
            "printable_width": 2060
        },
        "Letter": {
            "paper_id": 1,
            "physical_height": 2794,
            "physical_width": 2159,
            "printable_height": 2710,
            "printable_width": 2060
        }
    }
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Xóa tất cả các tác vụ đang chờ xử lý.
Sau khi gọi giao diện này, hàng đợi chờ in sẽ bị xóa, nhưng các tác vụ đang in sẽ không bị hủy.
### Method: POST
>```
>{{url}}/api/print/flush_jobs
>```
### Headers

|Content-Type|Value|
|---|---|
|ApiKey|{{ApiKey}}|


### Body (**raw**)

```json
{
    "deviceId": "{{deviceId}}",
    "deviceKey": "{{deviceKey}}",
    "devicePort": {{devicePort}}
}
```

### Response: 200
<details open style="width: fit-content; max-height: 600px; overflow: auto">
<summary>Response example:</summary>

```json
{
    "code": 200,
    "data": {
        "queue_num": 3
    },
    "msg": "success"
}
```
</details>


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
_________________________________________________
Powered By: [postman-to-markdown](https://github.com/bautistaj/postman-to-markdown/)
