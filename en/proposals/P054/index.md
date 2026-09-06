# 本機桌面 RPA 代理（Mac App）：讓 AI 直接操作沒有 API 的老系統，把 ERP／報稅／後台對帳流程自動化

中小企業最貴的重複人力，全卡在那些沒有 API、也不會有 API 的舊系統上；與其等廠商開接口，不如讓一個本機 AI agent 看著螢幕把流程跑完，帳號密碼與資料完全不離開公司電腦。

**Monetization**：①Mac App 買斷（主力）：單機版一次付清，主打『本機執行、資料零外流、不上雲』，鎖定會計事務所、電商營運、進出口貿易這類每天要在舊後台重複點擊的角色，買斷價位對照一位工讀生一週工資即可成立；②團隊版／自架 SaaS 月費：多台機器排程、流程版本管理、執行稽核日誌與截圖佐證、失敗告警，按『同時運行的流程數』或座席分級收月費，稽核日誌與合規報表列為付費牆功能，因為這正是事務所與需要內控的公司願意付錢的部分；③流程包與導入服務：把常見流程（電商後台每日對帳、金流平台報表匯出、電子發票開立與作廢查核、ERP 進銷存過帳）做成現成流程包，單包販售或訂閱更新，另收一次性導入客製費＋年度維護；④網頁端廣告與聯盟：教學站的『無 API 系統自動化』長尾文章掛 Adsterra／Monetag，文中自然導購自架所需的主機／NAS／備援方案走主機商聯盟連結，開源版本頁面放 Ko-fi 收贊助。全案不涉及任何 VPN 類聯盟。

**How it works**：分四層，關鍵設計是『能走 API 就走 API，能走 DOM 就走 DOM，最後才用像素』。執行層：congchuanling-dot/Cohort 是本機代理執行時，負責螢幕擷取、滑鼠鍵盤操作與視窗切換，把『看螢幕／點這裡／輸入這串』暴露成工具；它是唯一能碰到桌面應用（ERP 用戶端、報稅軟體、老舊 Java/VB 介面）的一層。網頁層：凡是流程跑在瀏覽器裡的環節，一律優先交給 ChromeDevTools/chrome-devtools-mcp，因為它走 DOM 與 CDP 協定，選取元素比對像素座標穩定一個量級，換了螢幕解析度或視窗大小也不會崩；只有網頁層真的抓不到（Canvas 畫的表格、嵌入式舊控件）才退回 Cohort 的像素操作。編排層：HKUDS/nanobot 當工作流引擎，把『登入 → 選日期區間 → 匯出報表 → 下載檔案 → 比對前一日餘額 → 產出差異表』拆成可單獨重跑的步驟，每步定義成功條件與重試策略，失敗時只重跑失敗的那一段而不是整條流程重來。混合接口層：oomol-lab/open-connector 處理有正規 API 的環節（雲端硬碟存放檔案、會計 SaaS 寫入、通知發送與 OAuth 認證保管），讓一條流程可以前半段靠螢幕操作把資料從舊系統挖出來、後半段用乾淨的 API 寫進新系統。封裝層：modelcontextprotocol/python-sdk 把上述全部打包成單一本機 MCP server，Claude Desktop／Cursor 掛上去之後，使用者可以用一句自然語言觸發或編修流程，而不必學任何 RPA 腳本語法。錄製與重播：使用者手動操作一次，系統同步記錄操作序列、視窗標題、元素選擇器與畫面錨點截圖，產出人類可讀的 YAML 流程檔，之後由本機排程器定時執行，每一步都留截圖與時間戳做為稽核佐證。安全設計：所有『不可逆操作』（送出申報、確認付款、刪除資料）預設插入人工確認關卡，agent 只能停在按鈕前面等人點頭。與現有企劃的區隔：P041 解決的是『有 API 的 SaaS 怎麼統一接上 agent』，P031 是瀏覽器端的網站品質走查，兩者都碰不到桌面應用；本案的核心價值正是那批永遠不會開 API 的內部與在地系統。

**Difficulty**：high · **Effort**：估 4–6 週做出能跑版本：單一真實流程的端到端 demo（例如某電商後台每日對帳）約 2 週，錄製轉 YAML 與重播引擎約 1.5 週，排程器＋稽核日誌＋失敗告警約 1 週，MCP 封裝與自然語言編修約 0.5–1 週。難點有四：一是脆弱性——舊系統一改版，畫面錨點就失效，必須做視覺容錯（多重錨點、模糊比對）與『找不到就停下來問人』的自我保護，寧可停也不能點錯；二是憑證與二階段驗證——密碼要進系統鑰匙圈而非明文設定檔，OTP 環節目前只能設計成人工介入或走硬體金鑰，不該硬幹；三是不可逆操作的風險控制——沒有回滾機制的動作（送出申報、轉帳）一律強制人工確認，這條不能為了自動化率讓步；四是 macOS 權限——螢幕錄製與輔助使用權限的引導流程要做得夠傻瓜，否則第一次啟動就會流失大半使用者，另外 App 若要上架需處理沙盒限制，較可行的路線是官網直售並自行公證。

## Open-source parts

- [congchuanling-dot/Cohort](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/congchuanling-dot-cohort/) — Local-first Agent Runtime connecting LLMs to controlled tools, Chrome, desktop automation, MCP, context gover…
- [ChromeDevTools/chrome-devtools-mcp](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/chromedevtools-chrome-devtools-mcp/) — Chrome DevTools for coding agents
- [HKUDS/nanobot](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/hkuds-nanobot/) — Ultra-lightweight, open-source, self-hosted personal AI agent framework in Python with WebUI, tools, memory, …
- [oomol-lab/open-connector](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/oomol-lab-open-connector/) — Open-source auth gateway connecting 1400+ SaaS providers to AI agents through SDK, CLI, MCP, HTTP, and OpenAP…
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
