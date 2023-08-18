# Screen

Screen is a aaaaaaaaa

## Get the theme

Import as hugo module in config.toml:

```toml
[module]
[[module.imports]]
    path = 'github.com/idofront/hugo-theme-theme'
```

OR

Import manually:

1. git clone https://github.com/idofront/hugo-theme-screen themes/screen
2. Add `theme = "screen"`` in your config.toml:


## Configuration

このテーマ固有の設定は `params.screen.menu` に記述します．

| parameter  | description |
|------------|-------------|
| name       | 表示する際の文字列である．省略は許容されない． |
| path       | リンク先のパスである．省略した場合は name で代替する． |
| onHeader   | ヘッダに表示する場合は true，それ以外の場合は false を指定する．省略した場合は true として扱う． |
| onTop      | トップページに表示する場合は true，それ以外の場合は false を指定する．省略した場合は true として扱う． |
| type       | 項目の種別を指定する[^params.screen.menu.type]．省略した場合は directory として扱う． |
| permission | Linux における一般的な permission 設定と同じ 3 桁の整数で指定する．指定しなかった場合は type によって |

[^params.screen.menu.type]: type 種別
    | type      | description |
    |-----------|-------------|
    | directory | directory のように表示する．
    | symlink   | symbolic link のように表示する． |
    | file      | file のように表示する．

### Examples

```toml
[[params.screen.menu]]
  name = "posts"
  path = "/posts"
  onHeader = true
  onTop = true
  type = "list"
  permission: 755
```