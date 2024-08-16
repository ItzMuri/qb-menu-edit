# qb-menu
Menu System for the QBCore Framework

# My Discord Server
https://discord.gg/AXEVAqH7yX

![image](https://github.com/user-attachments/assets/8ffe3e11-1b05-49ba-bcf9-74982a13f294)
![image](https://github.com/user-attachments/assets/4ee74fc1-8843-4a2f-80b1-078367ed7e6f)


--[[
EXAMPLE MENU
--]]

```
RegisterCommand("qbmenutest", function(source, args, raw)
    openMenu({
        {
            header = "Main Title",
            isMenuHeader = true, -- Set to true to make a nonclickable title
        },
        {
            header = "Sub Menu Button",
            txt = "This goes to a sub menu",
            params = {
                event = "qb-menu:client:testMenu2",
                args = {
                    number = 1,
                }
            }
        },
        {
            header = "Sub Menu Button",
            txt = "This goes to a sub menu",
            disabled = true,
            -- hidden = true, -- doesnt create this at all if set to true
            params = {
                event = "qb-menu:client:testMenu2",
                args = {
                    number = 1,
                }
            }
        },
    })
end)
```
```
RegisterNetEvent('qb-menu:client:testMenu2', function(data)
    local number = data.number
    openMenu({
        {
            header = "< Go Back",
        },
        {
            header = "Number: "..number,
            txt = "Other",
            params = {
                event = "qb-menu:client:testButton",
                args = {
                    message = "This was called by clicking this button"
                }
            }
        },
    })
end)
```
```
RegisterNetEvent('qb-menu:client:testButton', function(data)
    TriggerEvent('QBCore:Notify', data.message)
end)
```
