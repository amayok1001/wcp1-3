# wcp1-3
## HTMLの概念＝左上に重力のある入れ子(多重構造)型の箱の集まりで出来ている
	・ヘッダー部分
	・メインビジュアル部分(top画像のようなもの)
	・メイン部分
	・フッター部分
	箱：<div>タグ＝何にでも使える（特に意味をもたないがひとかたまりとしてとらえることができる）

## リセットCSS
	ブラウザの持っているデフォルトのCSSを消す

## 要素の余白設定：margin(内側) / padding(外側)
   box-sizing: border-box;　と指定するとmargin/paddingトータルのサイズ
   ＊contents box;とした場合、margin/paddingだけのサイズが変化

## width / height
### width
	auto：初期値(自動)　基本的に横いっぱいにひろがる
	⚪︎⚪︎px：絶対値
	⚪︎⚪︎%：可変値　上の箱の大きさによって幅が変わる
### height
	auto：要素の中身の分だけの高さ
	⚪︎⚪︎px：
	⚪︎⚪︎%：使わない

## 子要素
### 幅と高さの基本
	width：子要素は親要素の幅が最大値
	height：指定しなければ子要素の高さ合計がそのままの高さとなる
### floatプロパティ(left/right/none＝解除)
	要素を右に寄せたり左に寄せたりする（横並びにできる）
	横並びにしたい要素にいれる
	＊親要素が０になる/レイアウト崩れが起きてしまう
	　親要素の高さは子要素の高さによって変わるのでfloat(=浮いた)　状態では、子要素としてみなされないため、親要素の高さがなくなる
	　加えて、floatを指定すると後の要素の下に潜り込んでしまう
	　⇨解消方法『Clearfix』
#### Clearfix
	 ・擬似要素
	   ::after セレクタ要素の直後
	   ::before セレクタ要素の直前
#### display：ブロック要素に指定し横幅を100%にする
#### clear：floatによる回り込みを解除するためのプロパティ
	  both:左及び右寄せの両方に対する回り込みを解除する設定

## 中央寄せ
	余白＋CSSで指定(margin:0 auto;)
	＊この場合のauto:width指定していないとき0と同じ意味をもつ
	　横幅を指定した状態でmarginの左右にauto値を指定すると左右等分のmarginが　算出される

## borderプロパティ＝枠線を指定
	border(-top/right/left/bottom): 太さ 種類(solid/double/dashed:破線/dotted:点線) 枠線の色;

## ボックスモデルの考え方
	margin:borderより外側の余白
	　borderの外側に余白/余白に背景色をいれたくないとき
	padding:borderより内側の余白
	　borderの内側に余白/余白に背景色を適用させたいとき
	borderと要素の四辺は同一のものではない
### 数値指定
	margin(padding):上下左右; 値1つ
	margin(padding):上下 左右; 値2つ
	margin(padding):上 左右 下; 値3つ
	margin(padding):上 右 下 左; 値4つ

# 確認問題
問1: 3.
問2: 2.
問3: 4. 6.
問4: <div><div></div></div>
問5: メリット 2.
	 デメリット 4.
問6: 3.
問7:
- HTML
<div class="boxes">
	<div class="box1"></div>
	<div class="box2"></div>
- CSS
.clearfix::after {
	content: "";
	display: block;
	clear: both;
}

.boxes {
	width: 600px;
	background-color: yellow;
	margin: 0 auto;
}

.box1 {
	width: 150px;
	height: 400px;
	background-color: orange;
	float: left;
}
.box2 {
	width: 250px;
	height: 400px
	background-color: red;
	float: right;
}