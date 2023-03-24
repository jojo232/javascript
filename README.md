# javascript
Created with CodeSandbox

# ①明確な定義はないが以下にあたりを指すことが常
・ React vue angular Riot等の仮想DOMを用いるライブラリ/フレームワークを使用<br>
・ npm/yarm等のパッケージマネージャを使用<br>
・ 主にES2015(ES6以降)の記法を使用<br>
・ webpack等のモジュールバンドラーを使用<br>
・ Babel等のトランスパイラを使用<br>

# ②そもそもDOMって？
・ Document Object Modelの略。ドムと読む<br>
・ HTMLなどを解釈し木構造で表現したもの<br>

### これまでのDOMを直接操作していた
・ 素のjavascriptやjquery等<br>
※デメリット：レンダリングコスト高、コードの複雑化<br>

## 仮想DOMとは
### javascriptのオブジェクトで仮想的に作られたDOM
・ いきなりDOMを操作せず、JS上で仮想DOMを操作し差分を出してからDOMに反映<br>

# ③npm/yarm等のパッケージマネージャを使用
### かつてのjavascriptは1つのJSファイルに全ての処理を記述していた
・　処理が複雑になるにつれてコードがカオス化<br>
・　コードの再利用ができない<br>

### ちょっと改善されたjavascript、他のJSファイルを読み込んで使っていた
・　コードの再利用、共通化ができるようになった<br>
・　読み込み順を意識しないとエラーになる(依存関係)<br>
・　何がどこから読み込まれたものかわからない<br>

### 試行錯誤があったモダンJavaScript、npm/yarn等のパッケージマネージャーを使用
・　内部ではNode.js(サーバサイドに実行されるJavaScript)が動いている<br>
・　依存関係を勝手に解決してくれる<br>
・　import先に明示的にわかる<br>
・　世界中で公開されているパッケージをコマンド1つで利用可能<br>
・　チーム内での共有も簡単に<br>
<img width="100" alt="スクリーンショット 2022-08-26 17 33 48" src="https://user-images.githubusercontent.com/65487059/225487898-51973cce-3fb1-4219-a224-3e96c141645d.jpeg">


# ④主にES2015(ES6以降)の記法を使用
・### ECMAScriotとは
・　えくますくりぷと<br>
・　JavaScriptの標準規格(こういうルールで書くぜ！)<br>
・　欧州電子計算機工業会<br>
・　毎年1回発表される<br>
・　ES5=ES2014、ES6=ES2015、<br>
・　ES20XXの呼び方を一般化<br>
・　ES2015で機能追加が多くあり、近代JSの転換期と言える<br>

## ★ES2015で追加された規格
・　let、constを用いた変数宣言<br>
・　アローファンクション<br>
・　Class構文(オブジェクト指向でよくでてくる)<br>
・　分割代入<br>
・　テンプレート文字列<br>
・　スレッド構文<br>
・　Promise<br>

# ⑤Webpack等のモジュールバンドラー、Babel等のトランスパイラを使用
### モジュールバンドラーとは、
・　複数のJS(css/image)ファイルを1つにまとめるためのもの
### トランスパイラとは、(BABEL)
・　新しいJavaScriptの記法を古い記法に変換してくれる

### モジュールバンドラー/トランスパイラまとめ
・　開発は効率よく、本番環境はうまく変換<br>
・　最近はフレームワーク/ライブラリが割と面倒見てくれる<br>
・　まずは概念を押さえておけばOK<br>



# SPAとは、Single Page Application
・　モダンJavaScriptはSPAが基本<br>
・　HTMLは1つのみでJavaScriptで画面を置き換える<br>
※　SPAを使用したWebシステムは、プロフィールを表示するための必要なデータだけを送る(htmlではなくデータのみ)<br>
※　index.htmlを置き換える<br>

### SPAのメリット
・　ページ遷移毎のチラつきがなくなる<br>
・　表示速度のアップによるユーザー体験向上<br>
・　コンポーネント分割が容易になることで開発効率アップ<br>


# Promiseとは(webのクローリング)

# await/async

# 同期処理・非同期処理とは
- 同期処理、処理Aから順番に実行される。次の処理(処理B)は、前の処理(処理A)が終わるまで実行ができない
- 非同期処理、前の処理(処理B)が完了するのを待たずに、次の処理(処理C)を実行できる

## なぜ非同期処理が必要なのか？(同期処理だと困ること)
- 同期処理だと、実行中の処理が終わるまで、次の処理を実行できない。
- 長時間かかるような処理を実行すると、次の処理をすぐ実行したくてもできない
- 処理をブロックせず、次の処理を実行できる。
- 非同期処理を使って効率的に処理を実行できる<br>
・(例),AppサーバーでHTTPリクエストごとにデータベースにアクセスする(I/O処理)し、完了待ちしているときに、　別のHTTPリクエストを捌けない<br>
・(例),ブラウザでAPIアクセスしている間に、ユーザーがボタンをクリックしても反応がしない<br>


# JavaScriptの非同期処理
- JavaScriptはシングルスレッドで実行される<br>
・普通に書いていると、同時に1つのことしか実行できない(同期処理)<br>
※スレッドとは、CPUの実行単位となっている
- 非同期に処理されるAPI(以降、非同期API)を利用することで、非同期処理を実現すできる
## JavaScriptでの非同期APIの例
- タイマー
・setTimeout
・setInterval
- I/O
・fs.readFile
・fetch
=> コールバックを受け取るものや、Promiseを返すものなど違いがあり、たくさんあるが、利用するときはドキュメントをしっかり見るべし

## コールバックの非同期処理
- 非同期APIは、コールバック関数を最後に引数にとり、非同期処理の終了時にコールバックが呼び出される。
・コールバックを登録しておいて、処理完了後に呼び出される(重要)
- 昔は非同期処理といえば、コールバックを使うしかなかった。
- コールバック地獄
・コールバックの結果を使おうとすると、ネストが深くなって読みづらくなる。


# playwrightというライブラリを使用してwebのクローリング(Promise)

# よくあるつまづきポイント
- なぜか処理が呼び出されなかったり、期待する順番に動作させることがでいない
- いつ非同期処理が必要になるかわからない
- いつawaitをつけるべき？

