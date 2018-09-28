## 【會員常見問題】 

### 問題1：為什麼需要推動會員級別機制呢？
- 為了在有限的資源下提供穩定的資料服務水準並提升服務品質，同時調配使用者授權可用流量機制及加強資訊安全管理，也期掌握各加值業者於PTX平臺使用狀況，本部於106年11月1日起正式推動會員分級及API管理機制導入。

### 問題2：我要如何判別申請的會員類別呢？ 
- 您可依據以下適用原則申請一般會員、進階會員及專案用戶，請詳以下說明；
  + 一般會員：適用單一運具開發、單一區域範圍之開發者。
  + 進階會員：適用跨運具開發、全臺灣範圍之開發者。
  + 專案用戶：申請資格建議須以能夠以一年內能產出具體成果且呼叫次數能夠確實達到相關上限為主，另本部保留取消會員相關資格機制之權利。

### 問題3：我一開始註冊成為一般會員後，之後可申請進階會員或專案用戶嗎？ 
- 可以。您可至【會員專區/API授權申請】於進階會員/專案用戶頁面提出申請審核資格，本部將於三個工作日核定審核結果並通知申請者。

### 問題4：我一開始就申請進階會員/專案用戶，馬上就可享有會員權益嗎？ 
- 用戶於交通部PTX平臺註冊進階會員/專案用戶後，系統將會寄送一會員帳號啟動信件，在用戶啟動會員帳號後，本部將於三個工作日核定審核結果，審核通過後才可享有各級會員權益中的每日API服務呼叫次數。

### 問題5：要怎麼判別符合專案用戶資格呢？ 
- 為能夠在有限的資源下，提供穩定的資料服務水準，故須對專案用戶有所限制。申請資格建議須以能夠以一年內能產出具體成果且呼叫次數能夠確實達到相關上限為主，另本部保留取消會員相關資格機制之權利。在您提出申請後，本部將於三個工作日核定審核結果。

### 問題6：我忘記APP Key怎麼辦？  
- 您可於【會員專區/API授權申請】按下【忘記Key】按鈕，選擇忘記Key的API服務類型，系統將會寄送更新的APP Key給您，原有的APP Key則會失效。

### 問題7：我要如何修正原本註冊時填寫的「介接固定伺服器ip資料」？  
- 您可至【會員專區/會員資料修改】修改資料即可。

### 問題8：問一般會員及進階會員的基礎資料（L1）API服務APP Key一樣嗎？ 
- 不同，因不同會員級別，其APP Key的每日API服務呼叫次數上限亦不同。

### 問題9：我原本已是交通部PTX平臺會員，需要申請授權嗎？ 
- 需要，本部將會寄出會員分級及API管理機制導入說明信件，請您能於規範時間內依據需求，申請成為「一般會員」、「進階會員」或「專案用戶」。若申請「一般會員」我們將寄送給您一般會員可享有的基礎資料（L1）API服務與基礎資料加值（L2）API服務授權信，但若您需要更大量的授權，在提出申請成為進階會員或專案用戶，本部將於三個工作日核定審核結果。

### 問題10：我如何使用APP ID & APP Key來介接PTX平臺服務？ 
- 在您介接API服務時，須帶入APP ID及APPKey加上當下的時間戳記組成之簽章，始取得服務。您可至Swagger輸入APP ID 及APP Key進行測試。 
說明：APP ID為會員級別申請之API服務類型，系統自動產生之唯一識別身份值。APP Key則為該APP ID對應之加密憑證。

### 問題11：介接PTX平臺資料，該如何顯著聲明呢？ 
- 可顯名聲明：資料介接「交通部PTX平臺」並加入 平臺標章【<a href="https://github.com/ptxmotc/PTX_Web/blob/master/交通部PTX平臺LOGO.zip?raw=true">Logo下載</a>】

### 問題12：為甚麼突然接不到PTX的資料呢？
- PTX平臺從11/1起正式導入API機制，導入該機制後取得資料方式從原有Token改為HMAC機制，後續進行API的存取管控。故所有介接平台資料的使用者皆須修改您取得資料的方式，您可參考【<a href="https://github.com/ptxmotc/Sample-code">範例程式碼</a>】。

### 問題13：一定要加入會員才能獲取資料嗎?
- 不一定。但如未加入會員會有5000次/日的取用限制，並且僅限於Swagger介面中存取，若透過瀏覽器輸入原API網址，則仍會產生{"message":"Unauthorized"}的訊息，故建議可申請成為API一般會員以享有基本上限20,000次/日服務次數。

### 問題14：同一APP ID及Key是否有限制IP數量?
- 沒有限制IP數量。

### 問題15：如果到達使用次數上限(rate limit)會如何?
- 會阻斷服務，訊息顯示http status 403。 說明：403 沒有權限讀取，可能是IP被阻檔或是伺服器限制。

### 問題16：何時會重新計算?
- 採用UTC時間00:00 重新計算。以台灣時區為UTC+8，即為早上8:00更新。

### 問題17：次數不夠怎麼辦?
- 建議可檢查呼叫策略。 
說明：每次僅取公總一條路線資料 http://ptx.transportdata.tw/MOTC/v2/Bus/Route/InterCity/{RouteName}
建議可以採用一次性呼叫，取得所有路線的手法 http://ptx.transportdata.tw/MOTC/v2/Bus/Route/InterCity
另外使用程式(如:C#、Java、JavaScript等)取得資料時，請記得加入HTTP Header設定(Accept-Encoding: gzip, deflate)，可有效減傳輸量，詳細可參閱【<a href="https://github.com/ptxmotc/Sample-code">範例程式碼</a>】。


      
若有任何疑問，歡迎透過以下方式聯絡我們：ptx@motc.gov.tw，（02） 2349-2803。  