# Angular19-sample-app

本專案是使用 [Angular CLI](https://github.com/angular/angular-cli) 版本 19.2.11 建立。

## 開發伺服器

啟動本地開發伺服器：

```bash
ng serve
```

伺服器啟動後，開啟瀏覽器至 `http://localhost:4200/`。當你修改任何原始碼檔案時，應用程式會自動重新載入。

## 程式碼腳手架

Angular CLI 提供強大的腳手架工具。建立新元件：

```bash
ng generate component component-name
```

查看所有可用的腳手架類型（例如：`components`、`directives`、`pipes`）：

```bash
ng generate --help
```

## 專案建置

建置專案：

```bash
ng build
```

編譯後的成果會放置於 `dist/` 目錄，預設會使用最佳化方式為正式環境進行編譯。

## 單元測試

使用 [Karma](https://karma-runner.github.io) 執行單元測試：

```bash
ng test
```

## 端對端測試

執行端對端（e2e）測試：

```bash
ng e2e
```

Angular CLI 預設不包含 e2e 測試框架，你可以根據需求自行選擇。

## 專案目錄結構說明

以下為推薦的 Angular 專案架構：

```
- 📂 my-angular-app
  - 📂 e2e
  - 📂 node_modules
  - 📂 src
      - 📂 app
          - 📂 core （共用工具模組）
               - 📂 constants：共用常數定義，避免 magic number 或字串
               - 📂 enums：列舉定義，統一管理選項類型
               - 📂 guards：路由守衛，控制路由存取權限
               - 📂 interceptors：HTTP 攔截器，處理請求與回應邏輯
               - 📂 models：通用資料模型，供整體應用共用
               - 📂 services：通用服務，例如本地儲存或 API 共用邏輯
               - 📂 utils：工具方法（如 common.utils.ts 提供共用邏輯）
               - 📂 validators：自訂驗證器，表單驗證邏輯集中管理
          - 📂 features（功能模組）
               - 📂 feature-a
                    - 📄 feature-a.component.html/scss/ts：該功能畫面元件
                    - 📂 models：此功能專屬的資料模型定義
          - 📂 shared（共用模組與元件）
               - 📂 components：可複用元件
               - 📂 directives：自訂指令
               - 📂 layout：畫面排版元件（如 header, footer）
               - 📂 pipes：自訂資料格式轉換器
          - 📄 app.component.*：應用主元件
          - 📄 app.module.ts：根模組（若使用 standalone 可移除）
          - 📄 app.routing-module.ts：路由設定（若使用 standalone 可移除）
      - 📂 assets（靜態資源）
          - 📂 data：假資料或 JSON 檔
          - 📂 icons：SVG 或圖示集
          - 📂 images：圖片資源
          - 📂 scripts：外部 JS 程式碼
      - 📂 environments：環境變數設定
          - 📄 environment.ts：開發環境
          - 📄 environment.prod.ts：正式環境
      - 📂 styles（全域樣式）
          - 📄 _custom.scss：第三方樣式覆寫
          - 📄 styles.scss：全域樣式進入點
      - 📄 index.html：主 HTML 模板
      - 📄 main.ts：應用程式進入點
      - 📄 polyfills.ts：瀏覽器相容補丁
  - 📄 .gitignore
  - 📄 angular.json
  - 📄 package.json
  - 📄 tsconfig.json
  - 📄 README.md
```

建議開發者依照此結構進行模組與元件規劃，可提升專案可維護性與協作效率。
