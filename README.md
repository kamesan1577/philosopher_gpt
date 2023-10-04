# philosopher_gpt
Excelファイルを読み込み、入力された文字があなたの考えにあっているかを判定するPythonスクリプトです
# 使い方 Windows11環境 Excel365 Python3.10系を想定
## 事前準備
### OpenAI APIキーの取得
以下を参考に行ってください <br>
https://book.st-hakky.com/docs/open-ai-create-api-key/
### 環境変数の設定
OPENAI_API_KEYに上記で取得したキーを入れる <br>
以下を参考 <br>
https://atmarkit.itmedia.co.jp/ait/articles/1805/11/news035.html
### Pythonのインストール
以下を参考 <br>
https://www.python.jp/install/windows/install.html
### PowerShellでプログラムがあるフォルダを開く
ダウンロードしたリポジトリのフォルダをエクスプローラーで開く
何もないところにカーソルを合わせ Shift + 右クリック した後に"PowerShellウィンドウをここで開く"をクリック
表示されたパスがダウンロードしたフォルダと同じであることを確認
### Pythonパッケージのインストール
PowerShell上で以下のコマンドを入力
```powershell
pip install  -r .\requirements.txt
```
## 使い方
### 初回実行時
```powershell
//現在のフォルダにテンプレ用Excelファイル{example.xlsx}を作成
python .\main.py
```
### Excelファイルに調査したい値を入力する(以下サンプル)
- text: 検証したい文
- similarity(入力不要): textのguidelineに対する一致度
- is_match(入力不要): similarityがthresholdを上回っているかどうか
- guideline: 判定の基準となる文
- threshold: similarityがこの値を上回るとis_matchになる(0~1.0の少数を入れる)

| text                           | similarity | is_match | guideline              | 
| ------------------------------ | ---------- | -------- | ---------------------- | 
| りんごは糖分が多く含まれている |            |          | りんごは甘くて美味しい | 
| バナナはおいしい               |            |          | threshold              | 
| 大学いくのだるい               | 　　　　　　|　　　　　　|0.7                       |

### 入力した文字列に対する一致度の判定
```powershell
//デフォルトのパスは.\examlpe.xlsx
python .\main.py {判定したいExcelファイルのパス}
```
### 出力結果のイメージ
![image](https://github.com/kamesan1577/philosopher_gpt/assets/47214420/45bc5059-874d-4ae5-a06c-44d9642acc85)


