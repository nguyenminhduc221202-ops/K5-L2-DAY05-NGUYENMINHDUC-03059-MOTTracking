# Báo cáo cá nhân — HoVaTen-MSSV

Đổi tên file theo quy tắc `MSSV_HoTen.md`. Ví dụ: `20241234_NguyenVanAn.md`.

Đoạn video: MOT17-09, 150 frame (frame 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên:NGUYEN MINH DUC
- MSSV:03059
- Mã đề (A/B/C):B
- Email:nguyenminhduc221202@gmail.com
- Link repository:https://github.com/nguyenminhduc221202-ops/K5-L2-DAY05-NGUYENMINHDUC-03059-MOTTracking.git
- Giờ bắt đầu:4:27
- Giờ kết thúc:6:46

## 1. Xem trước đoạn video (CP0)

Ghi **trước khi vẽ**, mỗi người một dòng.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame | Ghi chú |
|---|---|---|---|---|---|
| P1 | 0| | | | |
| P2 | 0| | | | |
| P3 | 2| | | | |
| P4 | 0| | | | |
| P5 | 40| | | | |

## 2. Keyframe và thời gian (CP1, CP4)

Số keyframe lấy từ kết quả `src/check_submission.py`.

| Mã | Số keyframe | Keyframe ở frame | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó |
|---|---|---|---|---|---|---|
| P1 |7|[0, 32, 39, 50, 55, 136, 149]| | | | |
| P2 |33|[3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 20, 21, 22, 24, 26, 28, 29, 31, 33, 34, 37, 38, 42, 109, 137, 141, 145]| | | | |
| P3 |19|[2, 3, 4, 5, 6, 7, 9, 10, 13, 17, 18, 19, 22, 23, 33, 40, 46, 104, 145]| | | | |
| P4 |17|[0, 26, 36, 65, 86, 101, 134, 136, 138, 139, 141, 142, 143, 145, 146, 147, 148]| | | | |
| P5 |12|[40, 49, 75, 86, 90, 93, 96, 108, 122, 125, 140, 149] | | | | |
| **Tổng** |88 |- |705| 12.5| | |

Keyframe / 100 frame của cả bài = tổng keyframe ÷ tổng số frame có mặt × 100 = 88 ÷ 705 × 100 = 12.5

Bạn đặt keyframe nhiều nhất ở người nào? Vì sao (người đó rẽ, dừng, lại gần camera hay bị che)?

3-42 chủ yếu box sát người

## 3. Đoạn bị che (CP2)

Người bị che: `P_`

| Mốc | Frame |
|---|---:|
| Bắt đầu bị che một phần (bật `occluded`) | |
| Mất hẳn (bật `outside`) | |
| Hiện lại (tắt `outside`) | |
| Thấy rõ trở lại (tắt `occluded`) | |

- Thời gian khuất hẳn: ___ frame = ___ giây.
- Quyết định: giữ cùng ID / tạo track mới.
- Lý do (trả lời 3 câu: khuất bao lâu so với 60 frame, ngoại hình có khớp, chỗ hiện lại có đúng hướng và tốc độ):

...

Ảnh chụp màn hình:

![Trước khi che](images/che_1_truoc.png)
![Giữa đoạn che, thấy cờ trên panel object](images/che_2_giua.png)
![Sau khi hiện lại, cùng ID](images/che_3_sau.png)

## 4. Tự review ID (CP3)

Lượt 1 theo người (đi ngược từ frame 149 về 0 trên CVAT), lượt 2 theo cảnh (nhảy 10 frame). Ít nhất 3 dòng; không có lỗi thì ghi một dòng "đã kiểm hai lượt, không lỗi".

Loại lỗi dùng đúng một trong 7 mã: `id_switch`, `fragmentation`, `lost`, `merge`, `false_track`, `drift`, `flag`.

| Frame | Mã người | Loại lỗi | Mô tả một câu | Phát hiện ở lượt | Đã sửa? |
|---:|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

Tổng hợp số lỗi theo loại:

| `id_switch` | `fragmentation` | `lost` | `merge` | `false_track` | `drift` | `flag` |
|---:|---:|---:|---:|---:|---:|---:|
| | | | | | | |

Lỗi nào chỉ lượt 2 (theo cảnh) mới thấy, lượt 1 (theo người) không thấy? Vì sao?

...

## 5. File xuất và kết quả tự kiểm (CP4)

| Kiểm tra | Kết quả |
|---|---|
| Tên file MOT 1.1 | nguyenminhduc_mot.zip|
| Tên file CVAT for video 1.1 | nguyenminhduc_cvat_video.zip|
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5) | 5|
| Frame `outside` không có dòng trong `gt.txt` (đúng / sai) |đúng |
| Job đã completed trên CVAT máy cá nhân |complete |

Dán phần tóm tắt in ra từ `src/check_submission.py`:

```text
Số frame in theo CVAT (bắt đầu từ 0). Trong gt.txt, frame_id = frame CVAT + 1.

=== File MOT 1.1: nguyenminhduc_mot.zip ===
  Số track ID: 5   |   Tổng số box: 705
  [OK]        Đúng 5 track ID.

  Track | Frame có mặt | Số frame | Đoạn vắng (outside)
      1 |   0–149      |      150 | -
      2 |   0–149      |      150 | -
      3 |   2–149      |      148 | -
      4 |   3–149      |      147 | -
      5 |  40–149      |      110 | -


=== File CVAT for video 1.1: nguyenminhduc_cvat_video.zip ===

  Track | Nhãn   | Frame thấy | Keyframe | KF/100 frame | Frame occluded | Lần bật outside
      0 | person |        150 |        7 |          4.7 |             11 |               0
              Track 0: keyframe ở frame [0, 32, 39, 50, 55, 136, 149]
      1 | person |        147 |       33 |         22.4 |             33 |               0
              Track 1: keyframe ở frame [3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 20, 21, 22, 24, 26, 28, 29, 31, 33, 34, 37, 38, 42, 109, 137, 141, 145]
      2 | person |        148 |       19 |         12.8 |             46 |               0
              Track 2: keyframe ở frame [2, 3, 4, 5, 6, 7, 9, 10, 13, 17, 18, 19, 22, 23, 33, 40, 46, 104, 145]
      3 | person |        150 |       17 |         11.3 |              0 |               0
              Track 3: keyframe ở frame [0, 26, 36, 65, 86, 101, 134, 136, 138, 139, 141, 142, 143, 145, 146, 147, 148]
      4 | person |        110 |       12 |         10.9 |              0 |               0
              Track 4: keyframe ở frame [40, 49, 75, 86, 90, 93, 96, 108, 122, 125, 140, 149]

  Tổng: 88 keyframe / 705 frame có mặt = 12.5 keyframe / 100 frame
  [OK]        Đọc được 5 track từ annotations.xml.

=== Tóm tắt ===
  Lỗi: 0   |   Cảnh báo: 0
  Đạt. Dán phần tóm tắt này vào báo cáo mục 5.
```

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   ...

2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

   ...

3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

   ...

## 7. Tài liệu tham khảo và công cụ AI đã dùng

...
