---
title: VORP INPUTS
author: outsider
date: 2022-05-08 14:10:00 +0800
categories: [Documentation Lua, INPUTS]
tags: [Lua]
render_with_liquid: false
---

### VORP inputs is a tool that is mandatory within the vorp framework. 

[`VORP INPUTS LUA`][inputs] **download**

# **How to use**


Can only be used from `client side `


### ***Single input***

```lua
local button = "Confirm" --label
local placeholder = "Insert player ID" --label

    TriggerEvent("vorpinputs:getInput", button, placeholder, function(result)

        if result ~= "" or result then -- making sure its not empty or nil
            print(result) -- returs a string
        else
            print("its empty?") -- notify
        end
    end)

```

![image](/assets/img/sample/inputs2.jpg)


### ***With input Type***

```lua
    local button = "Confirm"
    local placeholder = "Test Here"
    local inputType = "input" -- number ,textarea , date, etc.
    TriggerEvent("vorpinputs:getInput", button, placeholder,inputType, function(result)

        if result ~= "" or result then -- making sure its not empty or nil
            print(result) -- returs a string
        else
            print("its empty?") -- notify
        end
    end)
```

### ***Advanced inputs***   `NEW`

```lua

local myInput = {
    type = "enableinput", -- don't touch
    inputType = "input", -- input type
    button = "Confirm", -- button name
    placeholder = "NAME QUANTITY", -- placeholder name
    style = "block", -- don't touch
    attributes = {
        inputHeader = "GIVE ITEM", -- header
        type = "text", -- inputype text, number,date,textarea ETC
        pattern = "[0-9]", --  only numbers "[0-9]" | for letters only "[A-Za-z]+" 
        title = "numbers only", -- if input doesnt match show this message
        style = "border-radius: 10px; background-color: ; border:none;"-- style 
    }
}

TriggerEvent("vorpinputs:advancedInput", json.encode(myInput), function(result)
    
    if result ~= "" and result then -- make sure its not empty or nil
        print(result) --returns string
    else
        print("it's empty?") --notify
    end
end)

```

![image](/assets/img/sample/inputs.jpg)

-------
# ***Devtips***

 **split a string into more than one separated by a space**

 ```lua

local result = yourvariable
local splitString = {}
      for i in string.gmatch(result, "%S+") do
         splitString[#splitString + 1] = i
       end
local data1, data2 = splitString[1],splitString[2]

print(data1,data2)

 ```

 ```lua 

 -- use can use these to make sure what you want the input to be.
 tostring(data1) -- returns string
 tonumber(data2) -- returns number

 ```
------

[inputs]:https://github.com/VORPCORE/vorp_inputs-lua


