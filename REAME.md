lỗi: if (updatedData.isActive) và if (updatedData.powerWatts)
khi truyền isActive: false hoặc powerWatts: 0 thì cả 2 đều bị coi là sai => bỏ qua toàn bộ khối code 
thay bằng: if (updatedData.isActive !== undefined) và if (updatedData.powerWatts !== undefined) nó sẽ kiểm tra xem thuộc tính có tồn tại trong dữ liệu truyền vào hay không, giúp nhận và cập nhật chính xác cả giá trị false và 0

Trường hợp kiểm thử: Tắt điều hòa phòng khách
Dữ liệu đầu vào:     targetId = 1
updatedData = { isActive: false }
(thiết bị ban đầu: { id: 1, name: "Điều hòa", isActive: true })
Kết quả sai thực tế:    isActive: true 
Kết quả đúng mong đợi:  isActive: false

Trường hợp kiểm thử: Hạ công suất đèn ngủ về 0W
Dữ liệu đầu vào:     targetId = 2
updatedData = { powerWatts: 0 }
(thiết bị ban đầu: { id: 2, name: "Đèn ngủ", powerWatts: 25 })
Kết quả sai thực tế:    powerWatts: 25 
Kết quả đúng mong đợi:  powerWatts: 0