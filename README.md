このプロジェクトは自分の勉強用です。  
* Slack Apps
* Google Apps Script
* node-google-apps-script
* ... and GitHub

---

## Slackコマンドの追加（GASで実装)：連携確認まで

### GASの作成と公開

1. GAS新規作成  
  Google Driveから[New]>..※..>[Google Apps Script]  
  ※Google Apps Scriptがない場合は、追加する。  
  ※Spreadsheetのマクロ（Container-bound Script）で作成する場合は、
  [Tools]>[Script editor...]から作成。以下の手順は同様。

2. デフォルトで作成されるmyFunction()をdoPost()にして、動作確認用のコードを編集  
  例：  
  ```
  function doPost() {  
      return ContentService.createTextOutput("Hello, world!");  
  } 
  ```

3. 適当な名前で保存

4. 公開  
  [Publish]>[Deploy as web app...]
    * Project Version: New
    * Who has access to the app: Anyone, even anonymous ※  
      ※TODO:この辺要確認。

5. Current web app URLをコピー
    * Current web app URL: https://script.google.com/macros/s/.../exec  
      以降このURLは[Deploy as web app...]から確認できる。


### Slackに新規アプリの追加

1. アプリ新規作成  
  Teamのメニューから、[Apps&integrations]>[Build]>[Your Apps]>[Create New App]選択  
  ※または、Channel画面の[Channel Settings]から[Add an app or integrations]>[Build]>...
    * App Name: 適当に
    * Development Slack Team: Teamを選択
    - [Create App]

1. コマンド新規作成  
  左メニューの[Features]-[Slash Commands]>[Create New Command]
    * Command: 作成したいコマンド
    * Request URL: GASのCurrent web app URL
    * Short Description: 適当に
    * Usage Hint: （オプション）適当に  
    - [Save]

1. Teamに本アプリをインストール
  左メニューの[Settings]-[Install App]>[Install App to Team]
    - [Authorize]



### コマンド確認

1. Slackで作成したコマンドを[Send]  
    上記例の場合、「Hello, World!」が返ってくればOK。

---

## GASファイルをGit/GitHubで管理
以下のページ等を参考にさせてもらいました。
* [Google Apps Scriptの開発をモダンに行う方法](http://tech.speee.jp/entry/2016/04/28/190236)
* [http://qiita.com/zaki-yama/items/9a301542137febd8876c](http://qiita.com/zaki-yama/items/9a301542137febd8876c)






