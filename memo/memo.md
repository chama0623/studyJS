# JavScript勉強メモ

## ドキュメント
- HTML : https://developer.mozilla.org/ja/docs/Web/HTML
- CSS : https://developer.mozilla.org/ja/docs/Web/CSS
- JavaScript : https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference

便利ツール
- Nu Html Checker : https://validator.w3.org/nu/

## 基礎知識
### HTML
#### タグと要素
- タグ: `<開始タグ>`と`</終了タグ>`の`<>`で囲まれたもの
- 要素(element): 開始タグ, コンテンツ, 終了タグをまとめたもの
- void要素: contentを持たない要素. void要素は開始タグのみで構成され，コンテンツや終了タグを記述できない.
```html
<タグ名 属性1="属性値1" 属性2="属性値2" ...>content</タグ名>
```

#### インライン要素とブロック要素
- インライン要素 : 文章の一部として扱われる要素. 要素の後で改行は行われない.
- ブロック要素 : 行全体をまとまりとして扱う要素. 要素の後で改行される.

インライン要素とブロック要素の違い
1. width/heightの指定 : インライン要素はwidth, heightの指定が適用されないが, ブロック要素はwidth, heightの指定が適用される.
2. marginとpaddingの指定 : インライン要素はmargin指定が水平方向にのみ適用され, padding指定は水平・垂直方向の両方に適用されるが他の要素と重なることがある. ブロック要素ではmargin/paddingともに想定通りに指定でき, 他の要素と重ならない.

#### spanとdiv
- `span`タグ: インライン要素としてまとまりを作るためのタグ 
- `div`タグ: ブロック要素としてまとまりを作るためのタグ

divタグとpタグの違い  
divタグはブロック要素のまとまりを作るため, pタグは段落を作るときに使う.

#### idとclass

idとclassは属性の1つで, タグに対して名前を設定できるものである. idやclassを設定することで, 特定のclassを持っているものにまとめてCSSで装飾したり, JSで操作することができる.

- `id` : ページ内で一意な名前を持たせるときに使用する.
- `class` : ページ内で一意ではない名前を持たせるときに使用する.

1つの要素に複数のclassを持たせたり, 1つの要素にidとclassを同時に設定することも可能.
```html
<p id="hoge">content</p>
<p class="huga">content</p>
<p class="huga1 huga2"> <!-- huga1とhuga2の2つのclassに設定-->
<P class="hogehoge" class="huga"> <!-- idとしてhogehoge, classとしてhugaを設定 -->
```

### CSS
#### 基本構文
- セレクタ: 装飾する要素
- プロパティ: 装飾内容

```
セレクタ{
    プロパティ1: 値1;
    プロパティ2: 値2;
    ...
}
```

```css
p{
    background-color: red;
    border-radius: 3px;
}
```

#### 複数の要素にまとめて装飾する
h1タグとpタグの要素に同じ装飾をする.
```html
<h1>This is page title!</h1>
<p>content</p>
```
```css
h1, p{
    color: red;
}
```

#### ネストされた要素を指定して装飾する
divタグの中にあるpタグの要素にのみ装飾をする.
```html
<div><p>p content in div</p></div>
```

```css
div p{
    color: yellow;
}
```

#### id, classを指定して装飾する
idは`#ID名`, classは`.class名`で指定する.
```html
<p id="hoge">hoge content</p>
<p class="huga">huga content</p>
```
```css
#hoge{
    color: blue;
}

.huga{
    color: green;
}
```

#### 基本構文