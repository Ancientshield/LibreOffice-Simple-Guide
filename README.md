# LibreOffice 架構介紹


### 超過兩百個模組

### 其中

### 較重要的有：

Module
sal/    系統抽象層(System abstraction layer)rtl, osl and sal
tools/    提供基本內部型(三角形、多邊形、顏色)
vcl/    Visual Class Library 提供widgets小零件 (windowing, buttons, controls, file-pickers etc.)工具包

framework/ UNO Stuff, Toolbars, menus, 包含加速器和交互作用
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


# Online架構

### 基本目錄
wsd/ 網頁伺服器服務(The Web Services Daemon)
kit/ 在chroot的客戶端。渲染文件
common/ 共用程式
loleaflet/ 客戶端的JavaScript元件
test/ C++單元測試
cypress_test/ JavaScript集成測試


### LibreOffice Online WebSocket server(伺服器端)
https://github.com/LibreOffice/online/blob/master/wsd/README
online/wsd (需要libpng、Poco library、libcap-progs)
API的提供端
loolwsd = Libre Office On Line Web Socket Daemon


### Leaflet platform for LibreOffice Online(客戶端)
https://github.com/LibreOffice/online/blob/master/loleaflet/README
online/loleaflet/
API的呼叫端
~/.npmrc prefix=/opt/npm
開發CSS可以藉由安裝browser-sync自動Reload
```
npm install -g browser-sync
./configure --enable-browsersync
```
delete `dist` directory

LOOL_SERVE_FROM_FS=1 make run

make sync-[writer|calc|impress]

To run another document use:
```
browser-sync start --config browsersync-config.js --startPath "loleaflet/96c23f663/loleaflet.html?file_path=file:///path/to/the/file.ods"
```

open dist/loleaflet.html through loolwsd's fileserver

https://localhost:9980/loleaflet/dist/loleaflet.html?file_path=file:///PATH/TO_DOC&host=wss://localhost:9980


## API & 事件

### LOLeaflet API 文件

https://github.com/LibreOffice/online/blob/master/loleaflet/reference.html

或參考 

### Collabora Online editor API reference

https://www.collaboraoffice.com/collabora-online-editor-api-reference/

### Leaflet 官方文件

https://leafletjs.com/reference-1.6.0.html


Collabora文件、Leaflet官方文件，基本上差異不大


### LibreOffice Online API (HTTP API 文件) (server端)

https://github.com/LibreOffice/online/blob/master/wsd/reference.md




### WOPI Extensions

LibreOffice Online 使用「類WOPI」傳輸協定與host Online主機互動
![https://i.imgur.com/m3qFGWK.png](https://i.imgur.com/m3qFGWK.png)

##### 什麼是WOPI

Web application Open Platform Interface protocol (WOPI) 
網頁應用程式公開平台介面協定

REST-based protocol
符合REST基礎的協定

##### WOPI官網
https://wopi.readthedocs.io/projects/wopirest/en/latest/index.html