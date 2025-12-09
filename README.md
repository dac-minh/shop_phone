# Martfury Shop - Workspace

Tổng quan ngắn: workspace chứa backend Spring Boot (MartfuryShop), hai frontend Angular (Martfury-Shop và angular-admin) và bản dump database MySQL.

Cấu trúc chính
- Backend: MartfuryShop/ — project Spring Boot (Xem [pom.xml](Work_Place/MartfuryShop/pom.xml))
  - Cấu hình: [src/main/resources/application.properties](Work_Place/MartfuryShop/src/main/resources/application.properties) (chứa `bezkoder.app.jwtSecret` và thông tin DB)
- Frontend cửa hàng: Martfury-Shop/ — Angular app (khởi động bằng npm, Xem [package.json](Work_Place/Martfury-Shop/package.json), [angular.json](Work_Place/Martfury-Shop/angular.json))
- Frontend admin: angular-admin/ — Angular admin panel (Xem [package.json](Work_Place/angular-admin/package.json))
- Database dump: [martfury_shop.sql](Work_Place/martfury_shop.sql)

Yêu cầu
- Node.js + npm (phiên bản tương thích với Angular 12)
- Java 11+
- Maven
- MySQL server

Cài đặt & chạy (một lần)
1. Import database
   - Tạo database và import:
     mysql -u root -p < Work_Place/martfury_shop.sql
   - Hoặc tạo DB `martfury_shop` rồi import file trên.

2. Cấu hình backend
   - Chỉnh [Work_Place/MartfuryShop/src/main/resources/application.properties](Work_Place/MartfuryShop/src/main/resources/application.properties) nếu cần thay đổi `spring.datasource.*` hoặc `bezkoder.app.jwtSecret`.

3. Chạy backend
   - Từ thư mục `Work_Place/MartfuryShop`:
     mvn spring-boot:run
   - Mặc định chạy trên cổng 8080 (nếu không cấu hình khác).

4. Chạy frontend cửa hàng
   - Từ `Work_Place/Martfury-Shop`:
     npm install
     npm start
   - Mặc định serve trên cổng 4200.

5. Chạy frontend admin
   - Từ `Work_Place/angular-admin`:
     npm install
     npm start

Ghi chú
- Nếu backend và frontend chạy trên máy khác cổng/host, cập nhật URL API trong code frontend (tìm cấu hình base API trong mã nguồn).
- Kiểm tra mail config trong [application.properties](Work_Place/MartfuryShop/src/main/resources/application.properties) nếu cần gửi mail từ app.
- Các chi tiết cụ thể về API nằm trong mã nguồn backend (xem `src/main/java` trong `MartfuryShop`).

Liên hệ nhanh tới file cấu hình chính:
- Database dump: [Work_Place/martfury_shop.sql](Work_Place/martfury_shop.sql)  
- Backend config: [Work_Place/MartfuryShop/src/main/resources/application.properties](Work_Place/MartfuryShop/src/main/resources/application.properties)  
- Frontend (shop): [Work_Place/Martfury-Shop/package.json](Work_Place/Martfury-Shop/package.json)  
- Frontend (admin): [Work_Place/angular-admin/package.json](Work_Place/angular-admin/package.json)
