# Prism.jsの使い方

[Prism.jsの公式サイト](https://prismjs.com/download.html#themes=prism-okaidia&languages=markup+css+clike+javascript+scss&plugins=line-highlight+line-numbers)

1. Minified versionを選択して、必要な言語とプラグインだけダウンロードする
- 上記のリンクに飛べば前回選択した分が参照できる。
- PluginはLine HighlightとLine Numbersがとりあえずおすすめ。

2. 一番下のボタンをクリックしてJSとCSS両方ダウンロード。

3. 自分のコードにそれらのファイルを取り込む。

例：<br>
```html
<head>
    <title>Document</title>
    <link rel="stylesheet" href="../prism.css">
</head>
<body>
    //..
    <script src="../prism.js"></script>
    <script src="../prism-normalize-whitespace.js"></script>
    <script type="text/javascript">
        // Optional
        Prism.plugins.NormalizeWhitespace.setDefaults({
            'remove-trailing': true,
            'remove-indent': true,
            'left-trim': true,
            'right-trim': true,
        });
    </script>
</body>
```

### CF.
`script`の部分で先ほどダウンロードしてきた`prism.js`の他にJSファイルを追加している。<br>
詳しくはこちらの公式ページを参考[Normalize Whitespace](https://prismjs.com/plugins/normalize-whitespace/)<br>
簡単にいうと、ノーマルだと、
例えば以下のように書いた時、１行目に改行が入ってしまう。なのでわざわざ１行目を`<code>`タグの直後に改行せずくっつけなければいけない(見た目が悪い)。だがscriptを書き足すことによって、それを解決できる。<br>
```html
 <pre class="line-numbers"><code class="language-html">
            &lt;h1&gt;ここから離れたところに適用させる&lt;/h1&gt;
                &lt;h2&gt;ここは適用なし&lt;/h2&gt;
                &lt;p&gt;ここに適用!!&lt;/p&gt;
                &lt;h3&gt;ここは適用なし&lt;/h3&gt;
                &lt;p&gt;ここにも適用!!&lt;/p&gt;
        </code></pre>
```

[normalize-whitespace](https://unpkg.com/browse/prismjs@1.6.0/plugins/normalize-whitespace/)

