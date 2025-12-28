# Ghostty設定ディレクトリ

このディレクトリはGhosttyの設定ファイルを管理しています。

## Ghosttyとは

Ghosttyは、GPU加速とプラットフォームネイティブなUIを活用した、高速で機能豊富なクロスプラットフォームターミナルエミュレータです。

公式ドキュメント: https://ghostty.org/docs

## 設定ファイル

### 場所

- `~/.config/ghostty/config` (XDG標準、このディレクトリ)
- `~/Library/Application Support/com.mitchellh.ghostty/config` (macOS専用)

両方存在する場合、後者が前者を上書きします。

### 形式

`key = value` 形式のシンプルな構文:

```ini
# コメントは # で始める
background = 282c34
foreground = ffffff
font-family = JetBrains Mono
font-size = 14
```

- 大文字小文字を区別する
- クォートは任意（スペースを含む値でも省略可能）
- 空の値でデフォルトにリセット: `font-family =`

### 設定の再読み込み

- macOS: `cmd+shift+,`
- Linux: `ctrl+shift+,`

## 主要な設定オプション

### フォント

```ini
font-family = JetBrains Mono
font-family-bold = JetBrains Mono Bold
font-size = 14
font-feature = liga  # 合字の有効化
```

### カラー

```ini
background = 1e1e2e
foreground = cdd6f4
cursor-color = f5e0dc
selection-background = 45475a
selection-foreground = cdd6f4
palette = 0=#45475a  # ANSI色のカスタマイズ
```

### ウィンドウ

```ini
window-width = 120
window-height = 40
window-padding-x = 10
window-padding-y = 10
window-decoration = auto
```

### キーバインド

```ini
keybind = ctrl+shift+c=copy_to_clipboard
keybind = ctrl+shift+v=paste_from_clipboard
keybind = ctrl+d=new_split:right
keybind = ctrl+z=close_surface
```

### 設定ファイルの分割

```ini
# 別ファイルを読み込む
config-file = themes/catppuccin.conf

# オプショナル（存在しなくてもエラーにならない）
config-file = ?local.conf
```

## 参考リンク

- 設定リファレンス: https://ghostty.org/docs/config/reference
- キーバインド: https://ghostty.org/docs/config/keybind
- テーマ: https://ghostty.org/docs/config/themes
