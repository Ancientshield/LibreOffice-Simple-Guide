# LibreOffice 架構介紹


### 超過兩百個模組

### 其中

### 較重要的有：

Module
sal/    系統抽象層(System abstraction layer)rtl, osl and sal
tools/
vcl/
framework/
sfx2/

### 應用程式相關

desktop/ LibreOffice installarion interface
sw/    Writer
sc/    Calc
sd/    Draw/Impress


### 圖形相關

basegfx/ canvas演算法
canvas/    基於UNO的圖形後端渲染
cppcanvas/ 使用UNO canvas 的 C++ helper
drawinglayer/ 繪圖層

### Online架構

wsd/ 網頁伺服器服務(The Web Services Daemon)
kit/ 在chroot的客戶端。渲染文件
common/ 共用程式
loleaflet/ 客戶端的JavaScript元件
test/ C++單元測試
cypress_test/ JavaScript集成測試


### LibreOffice Online WebSocket server(伺服器端)
online/wsd 需要libpng、Poco library、libcap-progs
loolwsd = Libre Office On Line Web Socket Daemon
API的提供端


### Leaflet platform for LibreOffice Online(客戶端)
online/loleaflet/
API的呼叫端
由 npm 安裝 nodejs

### 





