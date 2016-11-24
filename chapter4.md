# Previewのサンプル
このチャプターではPreviewの機能を確認します。

## previewを定義する
preview を定義してみましょう

### main(chapter1.md)

```
### ${preview}

- contentType: text/html
- file: preview.html

```

### preview

```
<html>
<head>
  <title>Preview</title>
  <script src="https://code.jquery.com/jquery-3.1.1.min.js"></script>
<script>
$(document).ready(function() {
  var answer = "${a1}";
  if (answer === "preview") {
    $("#preview").show();
  }
});
</script>
</head>
<body>
<p id="preview" style="display:none;">この文章はブランクを正しく埋めると表示されます。</p>
</body>
</html>
```

## previewでmarkdown変換
mainで定義したmarkdownをmarkedで変換してからpreview表示してみます。

### main(chapter1.md)

```
### ${preview}

- contentType: text/html
- file: preview.html

```

### preview

```
<html>
<head>
  <title>Preview</title>
  <script src="https://code.jquery.com/jquery-3.1.1.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/marked/0.3.6/marked.min.js"></script>
<script>
$(document).ready(function() {
  var $markdown = $("#markdown");
  var text = $markdown.text();
  $markdown.html(marked(text)).show();
});
</script>
</head>
<body>
<p id="markdown" style="display:none;">${content}</p>
</body>
</html>
```

