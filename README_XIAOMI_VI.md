# Xiaomi Wash 12KG – Dashboard Home Assistant

- Trạng thái hoạt động và biểu đồ lịch sử dùng `sensor.mibx5_f91_77fa_washer`.
- Thời gian còn lại dùng `sensor.mibx5_f91_77fa_left_time`.
- Nút chuông trên card gốc điều khiển `switch.mibx5_f91_77fa_alarm` (âm báo của máy).
- Nút ổ cắm trên card gốc điều khiển `switch.mibx5_f91_77fa_switch_status` (bật/tắt máy).
- Không khai báo cảm biến công suất, điện năng hoặc chi phí vì máy không cung cấp các entity này.
- Các entity Cloud Collect/Data Logging được đặt ở phần cuối để tiện kiểm tra; một số có thể đang `unknown`.

Cài resource `washing-machine-card.js` dưới dạng JavaScript Module, sau đó thêm `examples/xiaomi_wash_12kg.yaml` vào Manual card.
