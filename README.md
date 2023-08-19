# Screen

Screen is a theme for Hugo that has the look and feel of the Linux shell/vi.

![Top](https://github.com/idofront/hugo-theme-screen/blob/main/images/top.png?raw=true)

![Posts](https://github.com/idofront/hugo-theme-screen/blob/main/images/Posts.png?raw=true)

## Get the theme

Import as hugo module in config.toml:

```toml
[module]
[[module.imports]]
    path = 'github.com/idofront/hugo-theme-theme'
```

OR

Import manually:

1. `git clone https://github.com/idofront/hugo-theme-screen themes/screen`
2. Add `theme = "screen"` in your config.toml.


## Configuration

### Menu

Specific settings for this theme are described in `params.screen`.

| parameter | description                                    |
|-----------|------------------------------------------------|
| user      | Displayed as the username when showing a path. |
| owner     | Displayed as the user for each item.           |
| group     | Displayed as the group for each item.          |

For each Page, specific settings related to this theme should be written in `params.screen.menu`.

| parameter  | description |
|------------|-------------|
| name       | The string to be displayed. Omission is not allowed. |
| path       | The path to which the link leads. If omitted, `name` will be used as a substitute. |
| onHeader   | Specify `true` to display on the header, `false` otherwise. Defaults to `true` if omitted. |
| onTop      | Specify `true` to display on the homepage, `false` otherwise. Defaults to `true` if omitted. |
| type       | Designates the type of the item[^params.screen.menu.type]. Defaults to `"directory"` if omitted. |
| permission | Set using a 3-digit integer, similar to common Linux permission settings. If not specified, it will be automatically set based on `type`. |
| owner      | Designate the user. If omitted, it refers to `params.screen.owner`, then `params.author`, and finally defaults to `"root"`. |
| group      | Designate the group. If omitted, it refers to `params.screen.group`, then `params.author`, and finally defaults to `"root"`. |
| year       | The year of the update. Defaults to `1970` if omitted. |
| month      | The month of the update. Defaults to `"Jan"` if omitted. |
| day        | The day of the update. Defaults to `1` if omitted. |

[^params.screen.menu.type]: Types of `type`
    | type      | default permission | description                   |
    |-----------|--------------------|-------------------------------|
    | directory | 775                | Displayed as a directory. |
    | symlink   | 777                | Displayed as a symbolic link |
    | file      | 664                | Displayed as a file. |

#### Examples

```toml
[[params.screen.menu]]
  name = "posts"
  path = "/posts"
  onHeader = true
  onTop = true
  type = "directory"
  permission = "755"
  owner = "root"
  group = "root"
```

## Demo

- [idofront.com](https://www.idofront.com/blog/)