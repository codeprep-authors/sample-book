# book.ymlの作成
このチャプターではbook.ymlの役割とその作成方法について解説します。

## book.ymlとははgdh
book.ymlとはbook全体の情報を定義したファイルです。  

codeprepのbookではルートディレクトリに必ずbook.ymlが存在しなければなりません。

### hint
book.ymlのファイル形式は[YAML](https://ja.wikipedia.org/wiki/YAML)です。

### main(readme.md)

```
book.yml is a file which defined basic book informations.

book.yml must be in root directory of book.

Q. What is the file format of book.yml?
A. ${yaml}
```

## book.ymlの中身
book.ymlでは

- title
- detail
- chapters

という3つの必須項目と、オプションとして

- image
- files

という2つの項目が定義できます。

### main(book.yml)

```
# Try to define yaml keys.

## These are required keys

${title}:
${detail}:
${chapters}:

## These are option keys

${image}:
${files}:
```

### hint
yamlのキーを定義してみましょう。

## titleの定義
titleにはBookのタイトルを定義します。

### main(book.yml)

```
${title}: My first HTML
detail:
chapters:
```

## detailの定義
detailにはBookの詳細説明を定義します。

### main(book.yml)

```
title: My first HTML
${detail}: This book explains about HTML.
chapters:
```

## 複数行のdetail
detailが複数行に渡る場合は「|」を使うことで複数行の文字列を定義できます。

### main(book.yml)

```
title: My first HTML
detail: ${|}
  This book explains about HTML.
  It is very easy.
chapters:
```

### hint
「|>」などの別の複数行オプションを使用することも可能です。

## chaptersの定義
chaptersにはリスト形式で各chapterの定義ファイルを相対パスで指定します。

ここで指定したファイルはそのパスに存在しなければなりません。

### main(book.yml)

```
title: My first HTML
detail: |
  This book explains about HTML.
  It is very easy.
chapters:
  ${-} chapter1.md
  ${-} chapter2.md
  ${-} chapter3.md
```

### hint
yamlでリストを示す記号は「-」です。

## imageの定義
imageにはBookのカバーイメージファイルを相対パスで指定します。

ここで指定したファイルはそのパスに存在しなければなりません。

### main(book.yml)

```
${codeprep:section(prev)}
${image}: cover.png
```

### hint
サポートされているイメージフォーマットはgif, png, jpeg, svgです。

## filesの定義
filesにはBook内で横断的に使用するstaticなファイルをリスト形式で相対パスで指定します。

ここで指定したファイルはそのパスに存在しなければなりません。

### main(book.yml)

```
title: My first HTML
${codeprep:section(prev)}
${files}:
  ${-} image1.png
  ${-} index.html
```

### hint
例えばbook内で横断的に使用する画像ファイルや、CSSのbookでindex.htmlは一切編集しない場合などにここでfilesを指定できます。

横断的にindex.htmlを使用する場合でも途中で内容が変わる場合にはここではなく各セクションのfilesで指定します。

