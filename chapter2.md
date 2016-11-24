# chapter定義ファイルの作成
このチャプターではチャプター定義ファイルの作成方法を説明します。

## チャプター定義ファイルとは
Bookの各Chapterの内容を記述したファイルです。

CodeprepのBookでは1Chapterが１ファイルに対応し、そのフォーマットはMardown形式です。

### main(chapter1.md)

```
Q. What is the chapter definition file format?
A. ${/markdown/i}
```

### hint
[Markdown](https://ja.wikipedia.org/wiki/Markdown)は文書を記述するための軽量マークアップ言語です。

## チャプター定義ファイルの構成
チャプター定義ファイルの内容はMarkdownの見出し(#)によって区切られます。

### main(chapter1.md)

```
${#} This is chapter title

This is chapter description

${##} This is secion1 title

This is section1 description

${###} main(index.html)

...

${###} hint

...

${##} This is section2 title

...

```

### hint
チャプター定義内での各見出しは以下の意味を持ちます。

- \# チャプターのタイトル
- \## セクションのタイトル(各セクションの区切り)
- \### セクション内の各サブセクション

## チャプターのタイトルを記述する
見出し1(#)を使用してチャプターのタイトルを記述します。

### main(chapter1.md)

```
${#} Chapter1
```

### hint
各チャプターの先頭にはチャプタータイトルが必ず一つだけ必要です。

存在しなかったり、複数ある場合はコンパイルエラーになります。

## チャプターの説明を記述する
見出し1(#)の下にチャプターの説明を記述します。

マークダウンが使用可能です。

### main(chapter1.md)

```
${#} Chapter1

This is chapter1.

!!! Currently chapter description is not used anywhere.

```

### hint
現在チャプターの説明はどこにも表示されていません。

## セクションのタイトルを記述する
見出し2(#)を使用してセクションのタイトルを記述します。

### main(chapter1.md)

```
# Chapter1

This is chapter1.

${##} Section1

```

### hint
チャプタータイトルの次に来る見出しは必ずセクションタイトルになります。

## セクションの説明を記述する
見出し2(#)の下にセクションの説明を記述します。

この文章は各セクションの表示時に画面左に表示されます。

Markdownが使用可能です。

### main(chapter1.md)

```
# Chapter1

This is chapter1.

${##} Section1

This is section1.
```

## コメントを挿入する
チャプター定義ファイル中の「//」で始まる行はコメントとして扱われ、コンパイル時に無視されます。

コメントはコードブロック(\`\`\`で括られた箇所)以外のどこにでも記述可能です。

### main(chapter1.md)

```
# Chapter1

This is chapter1.

## Section1

${\//} This line is comment.

This is section1.
```

### hint
Markdownには標準のコメント形式 `<!-- -->`がありますが、これはBookのコメントとは異なります。

- `//`
  - Book定義上のコメントであり、コンパイル時に削除される
  - GitHub上などでHTML変換されて表示される場合、そのまま表示される
- `<!-- -->`
  - Book定義上は**文章の一部としてそのまま扱われる**
  - GitHub上などでHTML変換されて表示される場合、表示されない
