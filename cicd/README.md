## GitHub cicd 範例


### 每次新增tag 就會執行

1. 到 gcp 創建 服務帳戶
    1. 服務帳戶詳細資料 自行填寫
    2. 將專案存取權授予這個服務帳戶 (選用)
       * 把所有  Artifact Registry 相關聯的權限都給予
    3. 將這個服務帳戶的存取權授予使用者 (選用)
       * 選擇要給的帳號 

2. 選擇帳號 > 金鑰
    1. 新增鍵
    2. 選擇 json
    3. 下載 json 檔案

3. 將 json 檔案放到 github secret
    1. 去到指定的專案 > setting > Secrets and variables(左邊欄位) > Action
    2. 將 json 內容複製到 secret
    3. 名稱填寫 GCR_JSON_KEY(在yml這裡會使用到 Configure GCR Credentials)

4. 新增 .github/workflows 資料夾
   1. 到專案底下新增 .github/workflows
   2. 並產生 [push_image.yml](./push_image.yml)
   3. 上傳到github

5. 在專案根目錄新增 Dockerfile,用於打包 image

6. 新增 tag
7. 到 github actions 看看有沒有執行