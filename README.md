# game
![DEMO image](docs/images/demo.gif)  
Python向けレトロゲームエンジン Pyxel を使用したゲーム作成の情報  
[ブログ記事（Pyxelゲーム作成の記事一覧）](https://kinutani.hateblo.jp/entry/2022/12/15/184811)  
  
## Pyxelゲームの処理の基本
![flow image](docs/images/pyxel_flow.png)  
Pyxelのゲームの処理の流れは基本的に「初期化処理を最初に1回行い，その後は update() と draw() を実行し続ける」になります。この流れを頭に入れてゲーム作成を行いましょう。  

## ブログ記事で紹介したプログラム  
| No. | リンク | 内容 |
|:---:|:---:|:---|
| 1 | [じゃんけんゲーム](pyxel/rps_game/) | クリック位置の取得 |  
| 2 | [アクションゲーム1](pyxel/ninja/) | タイルマップの使用 |  
| 3 | [アクションゲーム2](pyxel/penguinjump/) | 画面スクロール<br>ゲームの進行 |  
| 4 | [三目並べ](pyxel/TicTacToe/) | クラスを使ったプログラム |  
| 5 | [シューティングゲーム](pyxel/shooter_r/) | 公式サンプルを改造 |  
| 6 | [迷路ゲーム1](pyxel/maze/) | 上下左右移動のアニメーション<br>（クラス未使用版） |  
| 7 | [迷路ゲーム2](pyxel/maze_random/) | 迷路の自動生成 |  
| 8 | [日本語表示例](pyxel/bmpfont/) | ビットマップフォントの表示 |  

## ひな形等

### プログラムテンプレート
| No. | リンク | 内容 |
|:---:|:---:|:---|
| 1 | [Appクラスのひな形](template/01_main.py) | Appクラスのコード |  
| 2 | [テストプログラム用](template/01a_simple.py) | クラスなし簡易版 |  
| 3 | [スクリーンショット用](template/02_screenshot.py) | show()で1回だけ表示 |  
| 4 | [イメージバンク画像出力](template/02_screenshot.py) | イメージバンクをPNGファイルで出力 |  
| 5 | [GIFアニメーションファイル用](template/03_animation.py) | flip()で表示ループ |  

  
### コピペ用命令リスト
#### コマンド
| コマンド | 内容 |
|:---|:---|
| `pip install -U pyxel` | Windows Pyxelのインストール（アップデート） |
| `pyxel copy_examples` | サンプルコードコピー |
| `pyxel edit filename` | Pyxel Editor の起動 |
| `pyxel package appdir srcname` | Pyxel アプリケーションファイル (.pyxapp) 作成 |
| `pyxel app2html your_app.pyxapp` | Pyxel アプリを HTML ファイルに変換する |
| `python -m http.server` | PythonのWebサーバー起動<br>http://localhost:8000/test.html のようにアクセス |

#### コード部品
乱数（整数）  
``` python
pyxel.rndi(1,100)
```
マウス位置取得  
``` python
pyxel.mouse(True)
```
``` python
x = pyxel.mouse_x
y = pyxel.mouse_y
```
方向キー入力  
``` python
if pyxel.btn(pyxel.KEY_UP) or pyxel.btn(pyxel.GAMEPAD1_BUTTON_DPAD_UP):

if pyxel.btn(pyxel.KEY_DOWN) or pyxel.btn(pyxel.GAMEPAD1_BUTTON_DPAD_DOWN):

if pyxel.btn(pyxel.KEY_LEFT) or pyxel.btn(pyxel.GAMEPAD1_BUTTON_DPAD_LEFT):

if pyxel.btn(pyxel.KEY_RIGHT) or pyxel.btn(pyxel.GAMEPAD1_BUTTON_DPAD_RIGHT):
```
スペースキー入力  
``` python
if pyxel.btnp(pyxel.KEY_SPACE) or pyxel.btnp(pyxel.GAMEPAD1_BUTTON_A):
```
``` python
if pyxel.btnp(pyxel.KEY_SPACE,15,15) or pyxel.btnp(pyxel.GAMEPAD1_BUTTON_A,15,15):
```
タイルマップ取得，設定  
``` python
xidx = 1 //8
yidx = 1 //8
tile = pyxel.tilemap(0).pget(xidx,yidx)
pyxel.tilemap(0).pset(xidx,yidx, (1,0) )
```
タイルマップ表示  
``` python
pyxel.camera()
pyxel.bltm(0,0, 0, self.scroll_x,self.scroll_y, pyxel.width,pyxel.height, 0)
pyxel.camera(self.scroll_x,self.scroll_y)
```
イメージ表示  
``` python
pyxel.blt(self.x, self.y, 0, u,v, self.w, self.h, 0)
```
効果音再生  
``` python
pyxel.play(ch,sNo)
```
BGM再生・停止  
``` python
pyxel.playm(msc, loop=True)
pyxel.stop(ch)
```
シーン番号  
``` python
SNO_TITLE    = 0
SNO_STAGESET = 10
SNO_PLAY     = 11
SNO_SFINISH  = 12
SNO_GAMEOVER = 13
SNO_END      = 20
```
シーン分岐  
``` python
if SNO_TITLE == self.scene:
    pass
elif SNO_STAGESET == self.scene:
    pass
elif SNO_PLAY == self.scene:
    pass
elif SNO_SFINISH == self.scene:
    pass
elif SNO_GAMEOVER == self.scene:
    pass
elif SNO_END == self.scene:
    pass
else:
    pass
```




# Author
E-mail benkyoubox@gmail.com  

