# HTML/CSS基礎解説書：画像とリンクの配置

## 1. CSSとは何か？

CSS（Cascading Style Sheets）は、HTMLで作った構造に「見た目」を与える言語です。

### HTMLとCSSの役割分担
- **HTML**：文書の構造（骨組み）を作る
- **CSS**：見た目やレイアウトを決める

例えば：
- HTML：「ここは見出し」「ここは段落」と定義
- CSS：「見出しは赤色で大きく」「段落は黒色で小さく」と装飾

## 2. CSSの基本的な書き方

### CSSを適用する3つの方法

#### 1. インラインスタイル（タグに直接書く）
```html
<p style="color: red;">赤い文字</p>
```

#### 2. 内部スタイルシート（HTMLファイル内に書く）
```html
<head>
  <style>
    p {
      color: red;
    }
  </style>
</head>
```

#### 3. 外部スタイルシート（別ファイルに書く）※推奨
```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

### CSSの基本構文
```css
セレクタ {
  プロパティ: 値;
}
```

例：
```css
p {
  color: blue;        /* 文字色を青に */
  font-size: 16px;    /* 文字サイズを16ピクセルに */
}
```

## 3. 重要なCSSプロパティ

### 色に関するプロパティ
- `color`: 文字の色
- `background-color`: 背景色

```css
.example {
  color: #333333;              /* 文字色（16進数） */
  background-color: lightblue; /* 背景色（色名） */
}
```

### 余白に関するプロパティ
- `margin`: 要素の外側の余白
- `padding`: 要素の内側の余白

```css
.box {
  margin: 10px;    /* 外側の余白を10px */
  padding: 20px;   /* 内側の余白を20px */
}
```

### サイズに関するプロパティ
- `width`: 幅
- `height`: 高さ

```css
img {
  width: 200px;    /* 幅を200pxに */
  height: 150px;   /* 高さを150pxに */
}
```

## 4. 演習課題の解説

### 課題1：画像3枚を並べる

#### HTMLの基本構造
```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>画像とリンクの練習</title>
  <style>
    /* ここにCSSを書きます */
  </style>
</head>
<body>
  <h1>画像ギャラリー</h1>
  
  <!-- 画像を3枚並べる -->
  <img src="image1.jpg" alt="画像1">
  <img src="image2.jpg" alt="画像2">
  <img src="image3.jpg" alt="画像3">
</body>
</html>
```

#### CSSで画像を整える
```css
img {
  width: 200px;      /* 画像の幅を統一 */
  height: 150px;     /* 画像の高さを統一 */
  margin: 10px;      /* 画像間に余白を作る */
}
```

#### なぜこのCSSが必要か？
1. **width/height**: 画像サイズがバラバラだと見栄えが悪いため統一
2. **margin**: 画像同士がくっつくと見づらいため余白を追加

### 課題2：Twitterリンクをボタン風にする

#### HTMLの基本構造
```html
<a href="https://twitter.com/your_account" class="twitter-button">
  Twitterでフォロー
</a>
```

#### CSSでボタン風にする
```css
.twitter-button {
  /* 背景と文字の色 */
  background-color: #1DA1F2;  /* Twitter青 */
  color: white;               /* 白文字 */
  
  /* 余白でボタンらしく */
  padding: 10px 20px;         /* 上下10px、左右20px */
  
  /* その他の装飾 */
  text-decoration: none;      /* 下線を消す */
  display: inline-block;      /* paddingを効かせる */
  border-radius: 5px;         /* 角を丸くする */
}

/* マウスを乗せた時の効果 */
.twitter-button:hover {
  background-color: #0d8bd9;  /* 少し暗い青 */
}
```

#### なぜこれらのプロパティが必要か？

1. **background-color**: ボタンには背景色が必要
2. **color**: 背景色に合わせて文字色を変更
3. **padding**: クリックしやすいサイズにするため内側余白を追加
4. **text-decoration: none**: リンクのデフォルトの下線を消す
5. **display: inline-block**: `<a>`タグはインライン要素なので、paddingを正しく効かせるため
6. **border-radius**: 角を丸くしてモダンなボタンに
7. **:hover**: マウスを乗せた時に色が変わることで「クリックできる」ことを示す

## 5. 完成形のサンプルコード

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>画像とリンクの練習</title>
  <style>
    /* ページ全体の設定 */
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    
    /* 見出しのスタイル */
    h1 {
      color: #333;
      border-bottom: 2px solid #ddd;
      padding-bottom: 10px;
    }
    
    /* 画像のスタイル */
    img {
      width: 200px;
      height: 150px;
      margin: 10px;
      border: 2px solid #ddd;
    }
    
    /* Twitterボタンのスタイル */
    .twitter-button {
      background-color: #1DA1F2;
      color: white;
      padding: 10px 20px;
      text-decoration: none;
      display: inline-block;
      border-radius: 5px;
      margin-top: 20px;
      font-weight: bold;
    }
    
    .twitter-button:hover {
      background-color: #0d8bd9;
    }
  </style>
</head>
<body>
  <h1>私の画像ギャラリー</h1>
  
  <!-- 画像3枚 -->
  <img src="https://via.placeholder.com/200x150/ff0000" alt="赤い画像">
  <img src="https://via.placeholder.com/200x150/00ff00" alt="緑の画像">
  <img src="https://via.placeholder.com/200x150/0000ff" alt="青い画像">
  
  <!-- Twitterリンク -->
  <p>
    <a href="https://twitter.com" class="twitter-button">
      Twitterでフォロー
    </a>
  </p>
</body>
</html>
```

## 6. 学習のポイント

### CSSを理解するコツ

1. **ボックスモデルを理解する**
   - すべての要素は「箱」として扱われる
   - margin（外側余白）→ border（境界線）→ padding（内側余白）→ content（内容）

2. **セレクタの種類を覚える**
   - 要素セレクタ：`p`、`img`、`a`
   - クラスセレクタ：`.twitter-button`
   - IDセレクタ：`#header`

3. **よく使うプロパティから覚える**
   - 色：`color`、`background-color`
   - サイズ：`width`、`height`
   - 余白：`margin`、`padding`
   - 文字：`font-size`、`font-weight`

### 次のステップ

1. **Flexboxを学ぶ**：要素を横並びにする現代的な方法
2. **レスポンシブデザイン**：画面サイズに応じてレイアウトを変える
3. **CSSアニメーション**：動きのあるWebページを作る

## 7. 練習問題

以下を試してみましょう：

1. 画像に影をつけてみる（`box-shadow`プロパティ）
2. ボタンを複数作って色違いにしてみる
3. 画像にマウスを乗せた時に大きくなる効果をつける（`transform: scale()`）

これらの基礎を理解すれば、より複雑なレイアウトも作れるようになります！