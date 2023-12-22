我的名字叫陳有信，年齡 28 歲。住在新北市中和區一帶，未婚。我曾在天堂遊戲上班。每天最晚也是七點前回家。不抽煙，酒也是淺嘗輒止。晚上一點睡，保證六個小時的充足睡眠。睡前，我一定玩幾場遊戲，再做 0 分鐘的柔軟操，上了床，馬上熟睡。一覺到天亮，疲勞和壓力也會留到第二天。醫生都說我很不正常。  
我的意思是我是一個隨時都想追求平靜生活的人，不拘泥於勝負與煩惱，不樹立令我夜不能寐的程式碼，這就是我對於這個社會的生活態度，我也清楚這就是我的幸福。再說，就算是 <font color="#ff0000">DeBug</font> 我也不會輸給任何人。

<div align="center">
<img src=./images/killerQueen.jpg width=200px/>
</div>

```mermaid
gantt
   title  工作歷程

   dateFormat  YYYY-MM
	axisFormat  %Y-%m

      section 亞思博
         Unity: done, 2018-02, 2020-02

      section 天堂遊戲
         nodeJS & Golang: done, 2020-06, 2023-01

      section 祥捷
         typeScript & vue & mongo: done, 2023-02, 2023-06

      section 帆達
         go & mysql: done, 2023-08, 2023-12
```

# 工作經歷

# 亞思博

[google play 上架遊戲](https://play.google.com/store/apps/developer?id=Adtechinno+AppDev+Team "google play")

1.  獨自開發休閒類遊戲，讓遊戲透過廣告獲得收益
1.  串接 FB、AdMob、FireBase SDK

# 天堂遊戲

### nodejs

1. 工作內容:
   1. webSocket server & 前端 SDK
      1. 調整優化架構
      1. 簡易測試，方便使用者迅速測試功能
      1. 解決上版導致 SDK 版本不符合問題
      1. 由於有前端經驗，前端 cocos bug 除錯，除了 cocos 畫面外，都會透過我來定位問題，幫忙處理前後端所有交互問題
   1. 整合、壓力測試，確保品質而模擬前端進行測試
      1. 從前端(除畫面)開始模擬測試，符合玩家操作流程
      1. 報表產生.md
      1. 壓力測試讓公司大約評估在雲端上花費金額
      1. 壓力測試優化百人遊戲下注寫入 DB 過慢，導致下注失敗
         問題
         - 使用壓力測試後(每秒執行千次下注)，發現百家樂下注處理過於緩慢，發現 db 在更新速度太慢導致，後改為使用插入方式才解決。
   1. 好友系統
      1. redis 存取玩家上下線狀態
      1. arango 存取玩家好友資料
      1. 好友邀請功能，讓玩家互相傳遞網址即可進入遊戲

---

### golang

1. 工作內容:

   1. 其牌遊戲開發(百家樂、牛牛)
   1. 優化百人遊戲下注 DB 過慢問題
   1. 重構百人遊戲，耦合問題
      - 公司原架構，只可以 1 個房間只可容納幾百人，後來調整為一個獨立控制遊戲邏輯，跟 N 個房間，讓 N 個房間去監聽遊戲邏輯結果，玩家進入房間分流道不同房間，可優化操作訊息太多導致遊戲邏輯運算太慢問題，因為玩家進出會跟預演算法分散到不同房間，藉此減緩人數過多問題
   1. 單元測試
   1. 開發文件

# 祥捷

1. 工作內容:
   1. vue 後台網頁 前後端
   1. mongoDB 操作

# 帆達

1. 工作內容:

   1. go 遊戲邏輯(龍虎、搶莊牛)，使用 leaf
   1. 由於公司剛進去時只有我一人，把所有會執行的事件寫作文檔，部屬，遊戲架構...等可以讓新同事上手的文件進行補充
   1. <font color="#ff0000">錢包系統</font>
      - 公司有實現"金幣鎖"的功能，讓玩家<font color="#ff0000">只能登入後台、遊戲大廳、遊戲其中一個</font>，因為這個功能導致只要有可以修改金額的地方玩家不能同時登入，公司架構可以動到金額修改的有 5 以上的專案分散開來，又有 go、python 不同語言，導致難以調整與修復，於是有了此服務。
      - 使用 grpc 的微服務，讓所有跟金幣有關的操作都在此，方便以後修改與維護
      - 使用 gorm 來對 DB 進行操作
      - <font color="#ff0000">可以讓玩家同時遊玩多場牌局遊戲</font>
      - 完整壓力&整合測試、操作文檔案
   1. 優化原本架構
      - 登入與加入房間綁定，導致要執行某些操作要一直頻繁的建立刪除 WebSocket 連線，對 server 性能造成壓力，並與前端溝通現在困境與調整方式
   1. 捕魚 bug
      - 捕魚遊戲存在打死道具魚無法派彩問題，都使用人工進行補償派彩，後來整理好文檔&詢問多位僅存的人員，才讓問題定位完成。

## 其他練習

1. [k8s](https://github.com/Chu16537/Notes-k8s):基礎 k8s 架設&yaml 設定練習
1. [grpc](https://github.com/Chu16537/gRPC): 練習
1. [lineBot](https://github.com/Chu16537/lineBot):lineBot + mongo + Go Gin
1. [vue](https://github.com/Chu16537/project_b_clientWeb/tree/member_vue):練習用 vue，創建基礎的模板功能
1. [model](https://github.com/Chu16537/gomodule): 逐步建立自己的工具庫

## 使用工具

1. 語言
   1. golang
   1. nodejs
1. DB:
   1. mongo
   1. arango
   1. redis
   1. mysql
1. MQ：
   1. NATS
1. 容器
   1. docker

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
