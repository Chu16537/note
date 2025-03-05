我的名字叫陳有信，年齡 29 歲。住在新北市中和區一帶，未婚。我曾在天堂遊戲上班。每天最晚也是七點前回家。不抽煙，也不喝酒。晚上一點睡，保證六個小時的充足睡眠。睡前，我一定玩幾場遊戲，再做 0 分鐘的柔軟操，上了床，馬上熟睡。一覺到天亮，疲勞和壓力也會留到第二天。醫生都說我很不正常。  
我的意思是我是一個隨時都想追求平靜生活的人，不拘泥於勝負與煩惱，不樹立令我夜不能寐的程式碼，這就是我對於這個社會的生活態度，我也清楚這就是我的幸福。再說，就算是 <font color="#ff0000">DeBug</font> 我也不會輸給任何人。

```mermaid
pie title 工作經驗比例圖
    "遊戲開發" : 3
    "系統重構" : 2
    "系統測試" : 3
    "文件撰寫" : 3
```

## 技術專長

- **程式語言**：Golang、Node.js、TypeScript、JavaScript
- **資料庫**：MySQL、MongoDB、Redis、ArangoDB
- **訊息佇列**：NATS、Redis
- **容器技術**：Docker、Kubernetes
- **框架與工具**：Gin、GORM、Leaf、gRPC、WebSocket、Vue.js、
- **版本控制**：Git

## 專案經驗

<span style="font-size:24px;"><font color="#9C27B0">Live Slot </font> </span>

#### 專案簡介

- [範例遊戲](https://www.youtube.com/watch?v=TsjkEVsPSIM)
- **遊戲玩法**：主播下注時，其他玩家可以同步下注，並透過直播平台進行即時互動，提升遊戲參與度與娛樂性。

### 技術運用

#### WebSocket：即時通信

- 確保遊戲狀態能即時同步給所有玩家，提升即時互動體驗。

#### Gin + GORM：後端 API

- 使用 **Gin 框架** 提供 **RESTful API**，支援遊戲管理與數據查詢。
- **GORM** 操作 **MySQL**，實作後台需求，報表查詢...等功能。

#### Redis

- **Stream** 通知所有服務，確保水平擴展的服務統一資訊，以及高並發環境下的通知穩定性。

#### 第三方 API 串接

- 串接 **直播平台 API**，允許主播開啟 Live 直播，並將遊戲數據即時更新至直播畫面。
- 串接 **第三方平台遊戲**，提供跨平台遊戲體驗。

---

<span style="font-size:22px; color:#9C27B0;">錢包系統開發</span>

### 專案簡介

- **系統目標**：讓玩家可同時參與多場遊戲，並確保錢包金額異動的正確性與高效性。
- 開發高可用性、高併發的錢包系統。
- 採用微服務架構，提升系統的可擴展性和可維護性。
- 支援玩家**同時參與多局遊戲**，確保金額異動的準確性和一致性。

### **技術運用**

#### Redis

- 使用 **分布式鎖** 保證錢包金額異動的**原子性**，避免玩家多線程請求時發生資金錯誤。
- **異步解鎖機制**，防止鎖失效時造成交易異常。
-

#### GORM + MySQL

- 使用 **GORM** 操作 **MySQL**，確保交易日誌完整記錄，支持**事務回滾**，避免異常交易導致的金額錯誤。
- **索引優化**：對玩家錢包表加上 **索引（INDEX）**，加速高併發時的查詢效率。

#### gRPC 通訊：高效跨遊戲錢包管理

- **gRPC** 作為錢包與遊戲伺服器的溝通方式，確保**低延遲、高吞吐量**的交易處理。
- **雙向串流模式**（Bidirectional Streaming），讓遊戲與錢包系統可**即時溝通**，減少 API Call 延遲。
-

#### 多局遊戲支援

- 允許玩家在 **多個遊戲中同時下注**，透過進房前預先扣款機制，確保錢包互相不影響。

---

## <span style="font-size:22px; color:#9C27B0;">百家樂</span>

### 專案簡介

- 遊戲斷線或伺服器崩潰時，玩家遊戲狀態需能即時恢復。
- 確保多個遊戲服務之間的通訊高效且不耦合。
- 遊戲過程中玩家與伺服器的即時同步，確保低延遲的互動體驗。

### 技術運用

#### Redis

- 使用 **Redis** 作為遊戲狀態緩存，確保伺服器崩潰後可自動恢復玩家遊戲進度。
- 設計 **自動快照機制**，定期將關鍵遊戲資訊儲存至 Redis，減少資料遺失風險。

#### WebSocket

- 建立 **WebSocket 連線**，確保玩家可即時獲取遊戲結果與下注資訊，提供流暢的遊戲體驗。
- **心跳機制（Heartbeat）**，定期確認連線狀態，若玩家斷線則自動重新連線，避免影響遊戲進行。

#### NATS

- 使用 **NATS** 進行 **玩家請求與遊戲伺服器通訊**，避免服務間的直接依賴，提高系統可擴展性。

---

# 艾爾默

1. 開發第三方錢包串接服務，簡化交易流程。
2. 建置第三方平台服務，實現自動化系統測試，縮短開發週期。
3. 開發多款 Slot 遊戲，針對不同遊戲設計。
4. 開發[Live slot 遊戲開發](https://www.youtube.com/watch?v=TsjkEVsPSIM)，實現實時互動並提升用戶參與度。
5. 設計支持水平擴展的 Web Server，實現多節點選領導機制，提升系統高可用性與穩定性。
6. 使用 Gin 框架與 GORM 插件，重構原有架構，提升程式碼可讀性與可維護性。
7. 調整系統架構以支持單元測試，降低日後開發與維護的成本。

# 帆達

遊戲邏輯開發與維護：

1. 開發並優化多款遊戲邏輯（如龍虎、搶莊牛），使用 Leaf 框架提升代碼模組化與可維護性。
1. 編寫詳細的事件操作文檔與遊戲架構說明，為新同事提供快速上手的技術支持。

錢包系統重構與微服務化：

1. 設計並實現"金幣鎖"功能，確保玩家僅能在後台、遊戲大廳或遊戲中之一進行金額操作，解決多專案間金額修改的同步問題。
1. 開發基於 gRPC 的微服務，統一管理所有金幣相關操作，提升系統維護性與可擴展性。
1. 使用 GORM 操作資料庫，確保金額操作的數據一致性與效能最佳化。
1. 支持玩家同時參與多場牌局遊戲，優化原系統限制，提升用戶體驗。

架構優化：

1. 分析並解決登入與加入房間綁定導致的頻繁 WebSocket 建立與銷毀問題，降低伺服器負載並提升穩定性。
2. 與前端團隊合作，提出調整建議，解決跨部門溝通中的技術瓶頸。

遊戲 Bug 定位與修復：

1. 排查捕魚遊戲中道具魚無法派彩的問題，通過文檔分析與溝通協調，成功解決長期以來的技術難題，減少人工補償操作。

壓力測試與整合測試：

1. 完成錢包系統的壓力測試與整合測試，撰寫完整測試報告與操作文檔，確保高併發環境下的穩定性與準確性。

# 祥捷

- 熟悉 Vue.js 框架與前端效能優化技術。
- 深入掌握 MongoDB 資料結構設計與操作，能有效應對大數據量的存取需求。
- 具備全端開發能力，能獨立完成系統設計與功能實現。

# 天堂遊戲

- 精通 WebSocket 協議，熟悉高併發系統的設計與壓力測試。
- 擅長系統性能優化與架構重構，解決高負載環境中的性能瓶頸問題。
- 具備強調用戶體驗的開發能力，結合後端與前端專業知識，快速定位與解決跨領域問題。

### Node.js

WebSocket Server 與前端 SDK 開發：

1. 優化 WebSocket 架構，確保低延遲與高效能。
1. 撰寫簡易測試工具，提升功能測試效率，縮短開發周期。
1. 解決上線導致的 SDK 版本兼容問題，減少使用者端的報錯率。
1. 憑藉前端經驗，協助排除 Cocos 框架的 Bug，快速定位並解決前後端交互問題。

整合與壓力測試：

1. 模擬前端操作流程，執行大規模壓力測試，確保系統穩定性。
1. 優化百人遊戲下注邏輯，解決數據庫更新速度過慢問題（每秒千次下注測試），改用插入操作，成功提升效能。
1. 根據測試結果生成報告，為公司提供雲端資源成本預估數據。

好友系統開發：

1. 利用 Redis 儲存玩家上下線狀態，提升即時互動的響應速度。
1. 使用 ArangoDB 管理好友資料，支持大規模數據存取。
1. 開發好友邀請功能，實現玩家透過專屬網址快速加入遊戲房間的便捷操作。

---

### Golang

棋牌遊戲開發：

1.  棋牌類，單局房間只有 2~5 位遊玩
1.  百人遊戲，百家樂，單局遊戲有數百人同時遊玩
1.  老虎機，數值給輪帶，產生結果與前端對接

系統與測試優化：

1. 優化百人遊戲下注邏輯，解決數據庫性能瓶頸，顯著提升遊戲穩定性。
1. 重構遊戲架構，實現多房間邏輯分流，解決玩家數過多導致的性能問題，提升系統可擴展性。
1. 編寫單元測試，提升代碼覆蓋率與可靠性。
1. 撰寫詳細開發文件，降低團隊接手成本，促進技術知識的傳遞與共享。

# 亞思博

[google play 上架遊戲](https://play.google.com/store/apps/developer?id=Adtechinno+AppDev+Team "google play")

1. 1 年內替公司開發 6 款休閒類遊戲
2. 獨立開發休閒類遊戲，全程負責從概念設計、程式開發到上架的完整流程，確保遊戲在 Google Play 平台成功上架。
3. 透過遊戲內嵌廣告（FB、AdMob 等）實現收益最大化。
4. 第三方 SDK 串接與整合，高效整合 Facebook、AdMob、Firebase 等多項 SDK，實現用戶數據分析、廣告投放與即時通知功能。
5. 具備獨立開發能力，熟悉遊戲效能優化與廣告變現策略，並成功為公司創造穩定收益來源

---

---

---

# 程式碼守護神

```javascript

 . ...  .: rv..::i..   5QQs  :i:iqS7rrissqrriri:::ivj2SKIUbMXqvI127g27gd7YsIXQbbr::iir7sLj12UIsL7YIPqqqRgIJjrr777YJbdEqZZQZ     rQgRD        ..rQEdDEQ
 . ..  .::.:7.::ri:..  rBBZ.i7riXMEYvvY25bv7rrr:::7vIPPPBBQIE25SqIUMDKgQqQBBBZ5Qu:iUbvvj1UqqPPdPXUPbEERQDLLvri7r7vuZgggMQBBPPPZEBQBBB.      .:vPBQBBBB
 .  .. ..:..:..:ii..   :DgPrs7ivZK17rvYIIYir:ri.:.ijKu2qQEYsvvusLSP2JUYKMEq5vvsZqsZBS:iv7sJU121sv7vjjqPSr:.:..::.iiSIX5qSdMBQBBBMMgBs      .YMQdRQQQZB
 .  ..  ....i...i::    7gdPu17LsI77vvJ5X1i:i:ii:gridMIPIgPLL7vvJ5sr7JsYJQjvrvLvuQIUX::i7vYJujv7rr:7vu25Li.........:1js2S5qMDggMgggQQi  S7  2BBBPBPv..L
 .  ..   :v5Z5ri::...ruEqPK2JJY2LvJJsU55r::::iiRXqIEuSqgggjYvv1Pr77jYjru5vrLLLr5UiYr.:i7L1j1v7i:::iYJUvvi.    .. .:vr7jKIEMgDgggDMRgur5BB:.bBQQZJ.   i
 .  .   iXBDBgXv:.ivbZdqKSXIIIqbjuS1U1Ksi:::::LBsvPJvXS5qqB1Jvqsv7LYJL7u7vYL7rPS7i2s::i7JJj7ri:...isJ1vr:         .iir1IKbRDgZgZggMgBRBBB::KBQB7.    J
 .  .  7PMMKDdJLsUKDPP222KqdqEMM2IqXUKS7:::i.:.L1rq2rUKIYsXM7uvvvusY7sUJ7Lv7Lgd7YrMK:irssU7ri:....iujvrri::i::..   :i7u2PdDDdgDgggggMDZQEisXBBd...   B
 .  .  EPqqJPSvvgEPS52U15KDDgMQZKSgKUK5r:.::.7r.bjsg2LUSJ1Y5UsLLZZ1u77PX11IXXjYU2bZ:iirsULri:...  rJIUPZBBBBBQBBRX:.77Y2PKZPbEDdggMZMdggQgSuBQ2 .   .B
 .  . .Z1X1JSIrsPPuujusI5PDRgZEdqEbPSgX7...:.iDJUBY1dESuYds1UjY5U7r7siijKPSJY1PdM1.iir71sv::..   .uMQBBBQQQQQQQBQBB5r7rSPPdqXbqXPgDDgbDMMQUjQQZ:..  .B
 .  . :5L7J7IsrvSUYY1j1IPdMggPggd5UPgQdr:.....IqJUSYY1dUPus75qsJ2i::Yr. ::7i7vKY5S::r7J1Yr:..   iRBBQMRgRgRgRgRgRMBB5i7XbqdIKKSuKEDZMPggRguLRZQSXur  K
 .    .Jrr7rujrrU2Y1J1SgRRDMZgMdYsjSbRIr...:..XQj7UUvUvbRvLL2Y:. ii7rr.r2r.vviU7:77.:ir7::...  IBBMRgMgggggMgRDMDgMQQvrX5KX25KuJ5DDggbDRZP7YbbEKbDgi J
P7  . .:ii7rI2ri52UjuSgRgPPbgRg27rU5bEs7:.:.:.i1SuJrPUsPQSjjIur.2S77rYQPSU2QY77Ji     ..:.::..gBDZgDRgggggMgMEMgMggMBQrrrrL71KIuXgRDRPggqur7q5P1KSDs:I
QB ..  ..i7752r7Xqj1SbXKSPKqZBg27v2XKS77:..::i..rUjLKYJubgXSvEU1Y7gXrrS7sSIQu77XZr     .:::.:MQEPZEDgRgMgRgQgqDRDRgRMBZii::::7vjPBBBBgQgjs:vIUS1SIXKEX
BB ..   .:v7K2YvPXUSSuU2KKddRDEIJ7uSE277i.:.ii::Yj2JSJJU775UJgP57PdU.:7rgKXZgrr:q2:  .:::..:MgEPPdgDggggMDgMgIZgRDDggRB5::::::ii7s5XP2Z57ri72jSJXUSSgu
QB  .  ..rr75q1YKK2UYJsU5dZdXK2UY7rqQqYU7ri::ri7us1URuYbbSssirr:.:i:.vPUL1IEBrrvZjv..i::...ggdqbdDDDDMKMMZdQP1PgRgKQZdQB7::::::riiiii:ii::.rjJULUjuKEY
DQ. .   .r7rXPuvPKj7v7sJPdq11YJYvrLSDb2Usr7iiirY21PSIJZ5BKEgU7::7SSbS...7qPXBUjQ1ii.:...  PQdqbdggDdQPDMRPERZsbPgRPPQdZBQ:::i:i:iiiii:::i:..r75vILuID7
IB2..   .7rr2SYYPU7v7vJPdSju777LvJXPqq2J7i77iiis1XMQ7YEiPQXs:..BRI5BBX:JDgbPBPLI:.      .qMdqPPZDD5DgdQQDgZQgsKbPRZSDQPgBU.::::::i:ii::i::.:::7v2LjqbJ
2QU..   .r7i1UjJPY77u1EEKJusv7JJJUPdg5KL7iLriirvUqS7::JbJMKD5riQB1PPPMEgZIPKB5JPi      .QMdPbPEgP5DQdRBBQgDqqs2EbPQIXDQqBQi:::..::::r:::::..::i:rrKPZ2
1M:.    .7ris5jj51rL2EPq5KIUsj12uI2qgbXJv7vrir7s7i::::.7PEDPMZPgg17iUDDD11SDQSbBR:    iBBbPbPdMDSRQQgB5r:. .KPvEPbZMvXZgPB2i:sYsLuuUr::i::.:::::::JgRq
jb..    .ri:JIjv5uYuEX22qSX2UYJY15uuDPUJI7rrrir:.:::....2rbEP2j1XurrX2uY7XZQRugBB:. .qBBMbdPEgZSMBBZU7.   rKBQuKEPbgMYUbZEXrr7JXPqPEq::::::::::.::isDb
7dr:.  ..r::LULYI1YKqU1Suu2KLrr77IsJqEJjus7r::.:.::... :Y7vqDMr.77rri:..7gQBPZBZ.  SBBQQEEPEbRZRZPUSPMBBu.DgBBgKZZdPgQXjqRdJi7:rsKISPr.:.....:...:i77Z
r1j7:..::ii:LjsvKIKPKJ1ujJU1r:rrrj11KbSLvrr..:::::.... :vi7YMQRv:...:..7RQgPsi:  .BBBDdSRU1EIRgU1XEUsjKMBJ:QQQQgPZZuPgBESZBBgIiri7I25u......... ..:rvU
:vv7:. :.r::JSLJKDdPJ77sU2uILL7rrJrvv7::::.:...:...... .ir71DgBB2XqISDbDQv       :2r7dE717uQ1u1dM2ii::iiUM.XPRgQKZE51dRQSZ1EBBvv:irUUS:... ........iiv
:rY7:....i::5qu2DMbL7rYqgqbZI17::i:::::::.:.    :.....   :Lv:::qMbP25IDRr    ..   XUiPMr::UQIXBZ7:i:iirirS:U5dQgPDgqI1gQSEP5dBgi::iv5I72u.  ... ...:ir
:r77.. ..:.iSK1PMRU77sbBBR57:::i:i:::i:::i:     ......   .:U.   uQ27JDMi     :    LBLEg7i:7BRBIiirii:iir7:vguPQDdMZgZXKBdddEXEBgsvru2XLZBDr:     ..::i
::rr:  ..:.iKq5dgPUvYUPbS7::::::::i:i:::::.     .......   .7..   .:::.      ..    .QSDgrrr.SQs:iriiiii7:.7ggdKRgQMgggDEQqXgZEPggBBQDdSJsQEDQ2.    .::i
:ii7:. ..::rPbSEPbUsUPLJ7i:::::::::i:. . ..      ....... ... ..             .     7QdQEriv. iiii:iiirr..JD2gZgMQdgRDSggQZ7uPEDDEZEKPPd7jXZXDQBU.   ..r
ii7r:. ..:riPdPPd22u277vi:i::::::::.      : . .  ...... ..    .  .  .      ..    :BPKQPr7i  ..i:i:i::. rbMESgZQQbUBMU5ggBXirvJ5dQqSEKKLUUXPPZDBP7.  .r
:777:. ..irrEgKdqX5jr7Yvii::::::::      .::. ..  ........    ..   .        ...  :BgSqRY7r..::..suv.. . :PMEUPZgBgrKBQSPQQBJ::i:YgbPRPqYU5LqZbDgPPSi. i
ivL7r:  .rLYQR5Kd5Lirvu7r::::.:.:.    .:::::. ..  :....      .    .       ..   rQEbPgsrr..i:::iQQSv.. ..dgZvKdZQB.:2BMPPQQB2rri7QgRMQSUuKrvUKdRSXUMD.:
iLL7ii ..v2jQBKPL7r7rY7i::::......   ......:....  .:.....         .            BDUvuR1rr:i:::.YBUj5r... UQE7vEEgR.  7ggKEBBBI7rsBMdgQqu1IY7YL1XSS2PBJ:
i7s7ri...ubjBBS77rrirrr::.......... .......i: ... .::.rrr:...    ..            7LirrEP7vr:::::MXjJIY  . .dg7Y1KEE . .bBZZgRRBI7LBD2XRPUjILsvYYJvj1bBdi
rYvLri..iMM2PS77riiiiri:.... ..... ........i.  ........::i::.:.. .              RMS5PgYuJ:ii.KMJJjj2... :PDKI5uKd.  uBZS5IuqguYIgMKIZB2UIj7LLJsLrLXBEr
YL77r..:rqX71Urii:::i:........... .::.....::. .......          ....      ..     vBQMqDIj2iii7Bg11JU7::i.sQEi:::Yd.::BMv:irKgPPQQBRQQBBXUPJvvsYjL77JMDr
Ys7r:..::7J715ii:i::...............::.....::..:.....                   ...   ... SBRPJju7iir7KZq5IJii:iiuBXi:ruRrriqBuirjRBPQBQQQZPbKbPKbjvvYjJj7vsPvi
svri....:72rJjrir::...............:::....:i..::......                 .... .....  7QZjY7r7rrriivEPs:ii::5Q1iIgB1:i7Qq7XZBBjrji:isvJju2KKbJLvJj2uvJ2Pr:
7vii.:.::v2r77iri:::.:.:...........i::.:..:::::..:....               ......... .   5qY7r77ri::::rR2riii:XQJPgQqii75RbMBBgU:...:r7YL152v7jYvLY2uJrrrr.:
rrri.::::JUr7rii:::::::.. ........::r::::.:::::.:::.:..             ............  .Su7i7r:::iiii:7P7rii:bZDMRPirZQQQMP5sv:r7Lssvvv7JIuYii:::iii:.:i:.:
i7rr.:.::vY77vii::::.... ..........iri:i:..::i:..::::...        ................  .i:::r..::i7i::::L7rirEZPgP7sBBgK17::ri:ir7YLsvLvu2Ssrr:.::::::i:..:
rr7i::.::i7iLr:........ ...........:rr7ri:::iri...:::.. . . ....................      ......r7i::..Lu77DRdb57vQgUri:iiiiiirrrrv777ssXEUrr:::::::::...:
ir7i.:.:.:iii:....     ............:irLsri:iirri.:::::.:::.............. .             .::::r17i:::P1v1Bdgsiiv7::7iiiiirrririr7vrr77vI17i:.::::i:....i
:ri:::.:::rirriii::::...:..........:iivvrii:iirriiir7ri:::............                .::ir7v5bL77rSdvbBE2rrr..  iiiiirirrirrr77rirruXSrr:::::::. ...:
.:.:::.:..::::...::ii::i:i:::::i::::::i7r::::::iirrir7Li::.........:1:iPqUP RBBB.iU....::irL2bSs2Ir1MUXQYv77.  .ivrriiiiirrii77rirr7jP5Li:.::::. ... :
..::::... .:7uL77:..:.:.......::i::::.:iv:..:.:.::irvLvi::.....    .. rujIr DXiB.   ..:::irrjj7rvsrrggL:..7:..:r777iriiiii77riv77i77YI2uJ7:::::.......
:i:.    .rZPRBRBQBbs...........:::::::.:ri........:i::::::..       :. .Y:r: r  :     ..irr7vrr77rii:rR7   iuU1s7irr7ii:iirirv7i7777L7JSYuYr7iii. ..:.:
..   .iujPBPgQbdRQBBQv. .......:i::.:::.ii:.......:.:.:..          .                 .:i77Yrii77i:::.::  .DEPXK5Lriiriri:iiiriiiL7vL7rIUj7rY1YU.....:.
  .:jZuXJXQKPMqbEgDMQBgr     ..:ii::.:...:.........:.:.. .         .                 ..ir7rrii:ri:....   .rUKdXXI27ririiir:irr:r7vYjrrJ1ULrsYus. ..:::
 iq7IqsI1jMIPDqqEEDdDDBBZi     .r::....:rir:. ......      .                         ..::r::::::::.....      .:75XU2jLrrirrriiirii72Yr:ruUY7vsLs......:
2BD7Ug2DSSBEDBDMMQQQQQQBQBBDu7irv7rYKQBBBBBBBPi.     .     . .       ............. ...ii::.:.:.:.:.... .        :LuUSPX2Yv7vv7sJrvK1rriLXU7Uu2Y....:.:



```
