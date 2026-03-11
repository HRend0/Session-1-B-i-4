# Session-1-B-i-4
[Bài tập] Hệ thống Quản lý Lớp học Trực tuyến
Bài 1:
- Các thực thể: Người dùng (NguoiDung), Khóa học (KhoaHoc), Danh mục khóa học (DanhMucKhoaHoc), Giảng viên (GiangVien), Học viên (HocVien), Bài học (BaiHoc), Bài kiểm tra (BaiKiemTra), Kết quả (KetQua), Đăng ký học (DangKyHoc) - Thực thể yếu.
- Thuộc tính:
  + NguoiDung: mã người dùng, họ tên, email, mật khẩu, vai trò (student/instructor/admin).
  + KhoaHoc: mã khóa, tên, mô tả, cấp độ, giá, ngày phát hành.
  + DanhMucKhoaHoc: mã danh mục, tên danh mục.
  + GiangVien: học vị, chuyên môn.
  + BaiHoc: mã bài học, tiêu đề, nội dung, thời lượng, thuộc khóa học.
  + BaiKiemTra: mã quiz, tiêu đề, số câu hỏi, thuộc bài học nào.
  + KetQua: mã kết quả, điểm, ngày làm, thuộc về học viên nào và quiz nào.
  + DangKyHoc: ngày đăng ký, trạng thái (đang học, hoàn thành, hủy).
- Khóa chính:
  + NguoiDung: Mã người dùng.
  + KhoaHoc: Mã khóa.
  + DanhMucKhoaHoc: mã danh mục.
  + GiangVien: mã người dùng - mã giảng viên.
  + BaiHoc: mã bài học.
  + BaiKiemTra: mã quiz.
  + KetQua: mã kết quả.
  + HocVien: mã người dùng - mã học viên.
- Khóa ngoại:
  + GiangVien: mã khóa
  + KhoaHoc: mã giảng viên, mã danh mục, mã học viên
  + BaiHoc: mã khóa
  + HocVien: mã khóa, mã quiz
  + BaiKiemTra: mã học viên
Bài 2:
- Mối quan hệ chính:
  + [GiangVien] (N) ---<dạy>--- (N) [KhoaHoc]: 1 giảng viên có thể dạy nhiều khóa học và 1 khóa học có thể có nhiều giảng viên cùng tham gia giảng dạy
  + [KhoaHoc] (N) ---<trong>--- (1) [DanhMucKhoaHoc]: 1 danh mục khóa học có thể có nhiều khóa học nhưng 1 khóa học chỉ thuộc về duy nhất 1 danh mục khóa học
  + [KhoaHoc] (1) ---<có>--- (N) [BaiHoc]: 1 khóa học gồm nhiều bài học khác nhau nhưng 1 bài học chỉ thuộc khóa học chứa nó
  + [BaiHoc] (1) ---<có>--- (1) [BaiKiemTra]: 1 bài học chỉ có 1 bài kiểm tra, 1 bài kiểm tra chỉ dành cho 1 bài học
  + [HocVien] (N) ---<học>--- (N) [KhoaHoc]: 1 học viên có thể đăng ký nhiều khóa học, 1 khóa học có thể có nhiều học viên đăng ký
  + [HocVien] (N) ---<làm>--- (N) [BaiKiemTra]: 1 học viên có thể làm nhiều bài kiểm tra, 1 bài kiểm tra có thể cho nhiều học viên làm
