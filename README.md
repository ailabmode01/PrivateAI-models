# Private AI – các gói tải thêm

Kho này chỉ chứa **các gói tải thêm** mà phần mềm Private AI tự tải về khi người dùng chọn (trang "Tải thêm").
Phần mềm kiểm từng tệp bằng kích thước và mã SHA-256 trước khi dùng. Không tải tay các tệp ở đây.

Private AI được xây dựng trên [Open WebUI](https://github.com/open-webui/open-webui).

## Bản phát hành `goi-1`

| Tệp | Nội dung | Giấy phép |
|---|---|---|
| `giong_doc.000` | Giọng đọc: VieNeu (25 giọng tiếng Việt), Kokoro-82M (6 giọng tiếng Anh), ONNX Runtime, máy chủ giọng đọc của Private AI | VieNeu: Apache-2.0 · Kokoro-82M: Apache-2.0 · ONNX Runtime: MIT · thư viện kèm theo: giấy phép trong từng thư mục `*.dist-info` |
| `tach_nguoi.000` | Nhận ra người nói: phân đoạn pyannote 3.0 (bản ONNX của sherpa-onnx) và nhận dạng giọng CAM++ (3D-Speaker) | pyannote segmentation 3.0: MIT · 3D-Speaker CAM++: Apache-2.0 |

Mỗi tệp `.000` là các tệp gốc nối liền nhau theo thứ tự ghi trong danh sách của phần mềm (`danh_sach_tai.json`).
