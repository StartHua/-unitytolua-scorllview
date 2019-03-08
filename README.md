# -unitytolua-scorllview
基于unitytolua无线scorllview



    --滚动条 + item实例
     local Scroll_View = GameObject.Find("Scroll_View").transform
     local item = GameObject.Find("ListItem").transform
    --
     local scroll = require("Core.UIComponents.UIScrollView.UScrollView").new(Scroll_View,item)
    --
    scroll:SetOnItemLoadedHandler(function (item)
         --print(item.Index..","..ta[item.Index])
         local data = ta[item.Index]

         --item.gameObject:Find("Text"):GetComponent("Text").text = data

         item.gameObject:GetComponent("Button").onClick:RemoveAllListeners()
         item.gameObject:GetComponent("Button").onClick:AddListener(function()
             print(ta[item.Index])
         end)

    end)
    scroll:Create(#ta,2)
    --scroll:JumpByOffset(1334)
    scroll:JumpToItem(10)
    --scroll:Ref()
