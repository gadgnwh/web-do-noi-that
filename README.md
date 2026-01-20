CREATE TABLE about_us (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(255) NOT NULL,          -- Tiêu đề (VD: Về chúng tôi)
    content TEXT NOT NULL,                -- Nội dung chi tiết
    image_url VARCHAR(255),               -- Hình ảnh minh họa xưởng sản xuất
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
<section class="about-section py-5">
    <div class="container">
        <div class="row align-items-center">
            <div class="col-md-6">
                <img src="https://images.unsplash.com/photo-1595428774223-ef52624120d2?auto=format&fit=crop&q=80&w=600" 
                     alt="Xưởng sản xuất tủ quần áo" class="img-fluid rounded shadow">
            </div>
            
            <div class="col-md-6">
                <h2 class="fw-bold mb-4">Chào mừng đến với Wardrobe Luxury</h2>
                <p class="text-muted">
                    Với hơn 10 năm kinh nghiệm trong ngành nội thất, chúng tôi chuyên cung cấp các giải pháp 
                    tối ưu cho không gian lưu trữ của bạn. Từ tủ gỗ tự nhiên đến tủ công nghiệp hiện đại.
                </p>
                <ul class="list-unstyled">
                    <li><i class="bi bi-check-circle-fill text-success"></i> Chất liệu gỗ cao cấp, chống ẩm mốc.</li>
                    <li><i class="bi bi-check-circle-fill text-success"></i> Thiết kế thông minh, đa dạng kích thước.</li>
                    <li><i class="bi bi-check-circle-fill text-success"></i> Bảo hành lên đến 5 năm.</li>
                </ul>
                <a href="#contact" class="btn btn-primary mt-3">Liên hệ tư vấn ngay</a>
            </div>
        </div>
    </div>
</section>
// Controller xử lý trang chủ
public function index() {
    // Lấy thông tin giới thiệu đầu tiên trong bảng
    $about = AboutUs::first(); 
    
    // Trả về view kèm dữ liệu
    return view('client.home', compact('about'));
}
<form action="/admin/about/update" method="POST" enctype="multipart/form-data">
    <div class="form-group mb-3">
        <label>Tiêu đề giới thiệu</label>
        <input type="text" name="title" class="form-control" value="Về chúng tôi">
    </div>
    <div class="form-group mb-3">
        <label>Nội dung chi tiết</label>
        <textarea name="content" class="form-control" rows="5">Nội dung bài viết giới thiệu...</textarea>
    </div>
    <div class="form-group mb-3">
        <label>Hình ảnh minh họa</label>
        <input type="file" name="image" class="form-control-file">
    </div>
    <button type="submit" class="btn btn-success">Cập nhật trang giới thiệu</button>
</form>
