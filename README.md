# Martfury Shop - Workspace

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
   - Mặc định chạy trên cổng 8080.

4. Chạy frontend cửa hàng
   - Từ `Work_Place/Martfury-Shop`:
     npm install
     npm start
   - Mặc định serve trên cổng 4200.

5. Chạy frontend admin
   - Từ `Work_Place/angular-admin`:
     npm install
     npm start
