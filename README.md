# fish-jis
JISキーボードでは動かないデフォルトキーバインドをJISキーボードに合わせて再定義するプラグイン  
(環境依存が強いため、記述内容・動作は保証しない)

## アプリケーションによる違い

iTermでは、AltをMeta as Escに設定できるため本プラグインは必要ない。  
(Preference > Profiles > Keys　画面下部チェックボックス)


HyperやVSCodeのTerminalでは役に立つ可能性あり。  
(VSCodeでのMeta使用は `"terminal.integrated.macOptionIsMeta": true`)

## 仕様

JISキーボードでは動かないデフォルトキーバインドをJISキーボードに合わせて再定義する

| Label    | function                      | Default   | Patch     |
| -------- | ----------------------------- | --------- | --------- |
| Alt-up   | history-token-search-backward | \e\[1\;3A | \e\[1\;5A |
| Alt-down | history-token-search-forward  | \e\[1\;3B | \e\[1\;5B |

## その他のJISキーボード注意点

`Command-left`, `Command-right`  はそれぞれ `\eOF`, `\eOH`として扱われる。  
[jethrokuan/fzf](https://github.com/jethrokuan/fzf)など、`\eO`をbindする場合は注意が必要。(\eOFで上書きすればとりあえず動く)
