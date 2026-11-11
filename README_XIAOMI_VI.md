# Xiaomi Wash 12KG – cấu hình Home Assistant

Cấu hình `examples/xiaomi_wash_12kg.yaml` dành cho máy giặt Xiaomi Wash 12KG dùng các entity Miot Auto có tiền tố `mibx5_f91_77fa`.

## Lưu ý về cảm biến điện năng

Máy giặt này không có sensor công suất/điện năng. Cấu hình đã **không khai báo** các tùy chọn:
- `power_entity`
- `energy_entity`
- `cost_entity`
- `power_threshold`

Đây đều là tùy chọn của card, không cần tạo entity giả. Khu vực công suất và thống kê năng lượng/chi phí chu kỳ sẽ không được hiển thị.

## Cài đặt

1. Cài `washing-machine-card.js` vào `/config/www/` (hoặc cài qua HACS theo README chính).
2. Thêm resource `/local/washing-machine-card.js?v=7` với loại `JavaScript Module`.
3. Mở `examples/xiaomi_wash_12kg.yaml`, sao chép cấu hình vào một Manual card trên dashboard.
4. Các entity `unknown` được giữ ở phần Cloud Collect/Data Logging để tiện kiểm tra; trạng thái unknown không có nghĩa là card bị lỗi.

## Trạng thái máy

Card hoạt hình đọc trạng thái từ `sensor.mibx5_f91_77fa_run_status`, thời gian còn lại từ `sensor.mibx5_f91_77fa_left_time`. Danh sách `running_states` được khai báo để nhận diện các trạng thái giặt/xả/vắt/sấy thường gặp. Khi máy trả về `not run`, card sẽ coi là không chạy.
