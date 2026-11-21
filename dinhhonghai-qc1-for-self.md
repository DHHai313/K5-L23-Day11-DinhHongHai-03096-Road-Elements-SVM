# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Đinh Hồng Hải (03096)        Người kiểm (học viên): Đinh Hồng Hải (tự kiểm — chưa ghép cặp)  
Ngày: 2026-11-21                          Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): `dinhhonghai-front.zip`, `dinhhonghai-fisheye.zip` (`revision: 1`, `dinhhonghai-manifest.json`)  
Số ảnh kiểm: 6 (`A01`, `A06`, `A08`, `B03`, `B04`, `B06`) (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 65 (41 shape + 24 tag)  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 3 | nhẹ *(thiếu 3 tag phụ ở B03; tag camera đúng đủ 6/6 ảnh)* |
| QC1-02 đủ L1, R1 | bỏ sót | 7 | 0 | nặng *(A06 thiếu R1 đưa vào Ca mơ hồ chờ coach xác nhận miễn)* |
| QC1-03 position | sai thuộc tính / thừa | 13 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 13 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 13 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 13 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 14 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 8 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 14 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 6 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 12 | 1 | chính |
| QC1-12 file | lỗi file | 65 | 0 | nhẹ / nặng |

*(Ảnh mẫu không ghi nhận lỗi: `A01`, `A08`, `B06`).*

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-01 | `B03_04267_RV.png` | `tag:timeofday` | nhẹ | Thiếu tag ảnh `timeofday` trên ảnh fisheye sau `B03`. |
| 2 | QC1-01 | `B03_04267_RV.png` | `tag:weather` | nhẹ | Thiếu tag ảnh `weather` trên ảnh fisheye sau `B03`. |
| 3 | QC1-01 | `B03_04267_RV.png` | `tag:source` | nhẹ | Thiếu tag ảnh `source` trên ảnh fisheye sau `B03`. |
| 4 | QC1-11 | `B04_05535_RV.png` | `traffic_sign#1@(1059,159)` | chính | Chưa bật `edge_zone` dù tâm box nằm ngoài 80 % bán kính vòng ảnh fisheye. |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| `A06_b8c66e31-37045eec.jpg` *(và ngoài mẫu 6 ảnh: `A05`, `A07`, `A09`)* | `road_check lint` báo cảnh báo `QC1-02` thiếu vạch `R1` ở `A06` (và thiếu `L1`/`R1` ở `A05`, `A07`, `A09`). Các ảnh này thực tế không thấy rõ vạch sơn tương ứng — xin coach/lead xác nhận miễn lỗi `QC1-02` theo quy tắc không vẽ bịa vạch. | *(Chờ coach/lead xác nhận)* |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 1 / 65 nhãn = 1,54 %   Lỗi nhẹ: 3   Ca chờ lead: 1  
Quyết định (Release / Hold / Rework): **Hold**  
Lý do (theo luật của phiếu): Không có lỗi nặng đã xác nhận và tỉ lệ lỗi chính là `1,54 %` (≤ 5 % số nhãn đã kiểm), nhưng còn 1 ca mơ hồ (`A06` cảnh báo `QC1-02` thiếu `R1`) cần coach/lead xác nhận miễn trước khi `Release` (nếu coach xác nhận ảnh có thấy vạch `R1` thì chuyển sang `Rework`).  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](docs/qc_severity_road_v1.0.md).
