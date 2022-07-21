---
title: PROGRESSBAR
author: bytesizd
date: 2022-07-21 02:24:00 +0800
categories: [Documentation Lua, PROGRESSBAR]
tags: [Lua, UI]
math: true
mermaid: true
---

# ***VORP ProgressBar***

> A `client` side UI progressbar that allows you to display brogress bars/circles within your scripts!

## **How to use**
---

Can only be used from `client side `

### Initiate the progress bar globally
---
```lua
    progressbar = exports.vorp_progressbar:initiate()
```
 
### Start your progress UI
---

```lua
    progressbar.start(message, time, callback, theme)
```

**Input Parameters**
| Input | Info |
|--|--|
| message | What you want the progress to display |
| time | how long the progress should display (in milliseconds) |
| callback | function that will get called when the progress is done |
| theme | What you want the progress bar/circle to look like |

**Theme Options**
| Option | Info |
|--|--|
| linear | Shows a linear progress flat bar |
| circle | Shows a circle progress bar |
| innercircle | Shows a circle progress bar with a seconds countdown in the middle |

_**Example:**_
```lua
    progressbar.start('Loading Example", 20000, function ()
        print('DONE!!!!')
    end, 'linear')
```