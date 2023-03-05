# wezterm.bar

A [WezTerm](https://wezfurlong.org/wezterm/) [plugin](https://github.com/wez/wezterm/commit/e4ae8a844d8feaa43e1de34c5cc8b4f07ce525dd)
that makes your retro bar look nice.

```lua
local wezterm = require("wezterm")
local c = wezterm.config_builder()

-- build your config according to
-- https://wezfurlong.org/wezterm/config/lua/wezterm/config_builder.html
-- then finally apply the plugin

-- these are currently the defaults:
wezterm.plugin.require("https://github.com/nekowinston/wezterm.bar").apply_to_config(c, {
  dividers = "slant_right", -- or "slant_left", "arrows", "rounded", false
  indicator = {
    leader = {
      enabled = true,
      off = " ",
      on = " ",
    },
    mode = {
      enabled = true,
      names = {
        resize_mode = "RESIZE",
        copy_mode = "VISUAL",
        search_mode = "SEARCH",
      },
    },
  },
  tabs = {
    numerals = "arabic", -- or "roman"
    pane_count = "superscript", -- or "subscript", false
    brackets = {
      active = { "", ":" },
      inactive = { "", ":" },
    },
  },
  clock = { -- note that this overrides the whole set_right_status
    enabled = true,
    format = "%H:%M", -- use https://wezfurlong.org/wezterm/config/lua/wezterm.time/Time/format.html
  },
})

return c
```
