# Private AI – các gói tải thêm

Kho này chỉ chứa **các gói tải thêm** mà phần mềm Private AI tự tải về khi người dùng chọn (trang "Tải thêm").
Phần mềm kiểm từng tệp bằng kích thước và mã SHA-256 trước khi dùng. Không tải tay các tệp ở đây.

Private AI được xây dựng trên [Open WebUI](https://github.com/open-webui/open-webui).

## Bản phát hành `goi-1`

| Tệp | Nội dung | Giấy phép |
|---|---|---|
| `giong_doc.000` | Giọng đọc: VieNeu (25 giọng tiếng Việt), Kokoro-82M (6 giọng tiếng Anh), ONNX Runtime, máy chủ giọng đọc của Private AI | VieNeu: Apache-2.0 · Kokoro-82M: Apache-2.0 · ONNX Runtime: MIT · thư viện kèm theo: giấy phép trong từng thư mục `*.dist-info` |
| `tach_nguoi.000` | Nhận ra người nói: phân đoạn pyannote 3.0 (bản ONNX của sherpa-onnx) và nhận dạng giọng CAM++ (3D-Speaker) | pyannote segmentation 3.0: MIT · 3D-Speaker CAM++: Apache-2.0 |
| `video_goc.000`, `video_goc.001` | Chương trình làm video của Giảng viên ảo: mã Private AI (avatar_worker, body_motion…), MuseTalk, EchoMimicV3, Python 3.11 nhúng với PyTorch, Diffusers, Transformers, OpenCV…, kho ảnh trang phục mẫu | MuseTalk: MIT (`MuseTalk/LICENSE`) · EchoMimicV3: Apache-2.0 · Python: PSF · PyTorch: BSD-3-Clause, kèm thư viện CUDA của NVIDIA theo giấy phép phân phối lại của NVIDIA · các gói Python khác: giấy phép trong từng thư mục `python/Lib/site-packages/*.dist-info` · **FFmpeg: GPL-3.0 (xem dưới)** |

Mỗi tệp `.000`, `.001` là các tệp gốc nối liền nhau theo thứ tự ghi trong danh sách của phần mềm (`danh_sach_tai.json`).

## FFmpeg (GPL-3.0)

Gói `video_goc` có kèm chương trình **FFmpeg** (qua thư viện imageio-ffmpeg 0.6.0):

- Tệp: `python/Lib/site-packages/imageio_ffmpeg/binaries/ffmpeg-win-x86_64-v7.1.exe`
- SHA-256: `2ce797a0f88d7f067180338fb227f7b1928ea727bd9a4d7a1d022f7c52af71a3`
- Bản dựng: `ffmpeg version 7.1-essentials_build-www.gyan.dev` (cấu hình `--enable-gpl --enable-version3`, có libx264, libx265…)
- Giấy phép: **GNU General Public License phiên bản 3 hoặc mới hơn** – toàn văn trong [`LICENSES/GPL-3.0.txt`](LICENSES/GPL-3.0.txt).
  FFmpeg được phân phối **không kèm bất kỳ bảo đảm nào**.

**Mã nguồn tương ứng:**
- FFmpeg 7.1: https://ffmpeg.org/releases/ffmpeg-7.1.tar.xz (kho mã: https://git.ffmpeg.org/ffmpeg.git, nhãn `n7.1`)
- Bản dựng của gyan.dev (cấu hình và các thư viện đi kèm): https://www.gyan.dev/ffmpeg/builds/
- Theo yêu cầu, trong thời hạn ít nhất ba năm kể từ ngày phát hành, chúng tôi cung cấp bản sao đầy đủ mã nguồn tương ứng của bản FFmpeg này (kể cả mã nguồn các thư viện được liên kết vào) với chi phí không quá chi phí sao chép: hãy mở một mục [Issues](../../issues) tại kho này.

Private AI chỉ gọi FFmpeg như một chương trình riêng để ghép âm thanh và hình ảnh, không sửa đổi FFmpeg.
