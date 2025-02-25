local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
 
 
local Window = Rayfield:CreateWindow({
    Name = "Slap Battles But Bad",
    Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
    LoadingTitle = "Loading...",
    LoadingSubtitle = "by isssacque1234",
    Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes
 
    DisableRayfieldPrompts = false,
    DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface
 
    ConfigurationSaving = {
       Enabled = true,
       FolderName = skibidi, -- Create a custom folder for your hub/game
       FileName = "skibidi script"
    },
 
 
    KeySystem = true, -- Set this to true to use our key system
    KeySettings = {
       Title = "Key",
       Subtitle = "Key System",
       Note = "Dm for key (Tiktok: Mega_cat_studios)", -- Use this to tell the user how to get a key
       FileName = "skibidi key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"Key_9120"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
    }
 }) 
 
 
 local Aimbot = loadstring(game:HttpGet("https://raw.githubusercontent.com/Exunys/Aimbot-V3/main/src/Aimbot.lua"))()
 local chams = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Roblox-Chams-Highlight/refs/heads/main/Highlight.lua"))()
 local targethud = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Lua-TargetHud/refs/heads/main/targethud.lua"))()
 local speed = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Lua-Speed/refs/heads/main/speed.lua"))()
 
 
 
 
 local aimbotTab = Window:CreateTab("Main", "crosshair")
 
 local Section = aimbotTab:CreateSection("Main")
 
 
 
 
 local Button = aimbotTab:CreateButton({
   Name = "Anti-Void",
   Callback = function()
       local part = Instance.new("Part")
       part.Size = Vector3.new(2048, 2, 2048)
       part.Position = Vector3.new(5.28387451, 189.407303, -188.988602)
       part.Transparency = 0.35
       part.Anchored = true
       part.CanCollide = true
       part.Parent = workspace
   end,
})


 local Button = aimbotTab:CreateButton({
   Name = "Safe zone for badges",
   Callback = function()
       local part = Instance.new("Part")
       part.Size = Vector3.new(30, 2, 30)
       part.Position = Vector3.new(5912.072265625, 705.3837280273438, -8280.7998046875)
       part.Anchored = true
       part.CanCollide = true
       part.Parent = workspace

       local player = game.Players.LocalPlayer
       if player then
           player.Character:SetPrimaryPartCFrame(CFrame.new(5911.400390625, 716.906982421875, -8279.2646484375))
       end
   end,
})


local Button = aimbotTab:CreateButton({
   Name = "Slap aura (bugged)",
   Callback = function()
       for _, player in ipairs(game.Players:GetPlayers()) do
           if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
               local humanoidRootPart = player.Character.HumanoidRootPart
               humanoidRootPart.Size = Vector3.new(45, 45, 45)
           end
       end
   end,
})

 local Button = aimbotTab:CreateButton({
   Name = "TP to lobby",
   Callback = function()
       local player = game.Players.LocalPlayer
       if player then
           player.Character:SetPrimaryPartCFrame(CFrame.new(-41.980438232421875, 644.3502807617188, -285.6496887207031))
       end
   end,
})


 local Button = aimbotTab:CreateButton({
   Name = "TP to cannon island",
   Callback = function()
       local player = game.Players.LocalPlayer
       if player then
           player.Character:SetPrimaryPartCFrame(CFrame.new(313.801605, 212.306824, 83.6384201, 0.551201403, 0, 0.834372222, -0, 1, -0, -0.834372222, 0, 0.551201403))
       end
   end,
})


 local Button = aimbotTab:CreateButton({
   Name = "TP to Area",
   Callback = function()
       local player = game.Players.LocalPlayer
       if player then
           player.Character:SetPrimaryPartCFrame(CFrame.new(24.730520248413086, 200.04953002929688, -218.87469482421875))
       end
   end,
})


local Button = aimbotTab:CreateButton({
   Name = "Slap all (click on the screen)",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

       local humanoidRootPart = player.Character.HumanoidRootPart
       local playersTeleported = {}

       task.spawn(function()
           for _, targetPlayer in ipairs(game.Players:GetPlayers()) do
               if game.Players:FindFirstChild(targetPlayer.Name) and 
                  targetPlayer ~= player and 
                  targetPlayer.Character and 
                  targetPlayer.Character:FindFirstChild("HumanoidRootPart") and 
                  not playersTeleported[targetPlayer.Name] then

                   humanoidRootPart.CFrame = targetPlayer.Character.HumanoidRootPart.CFrame
                   playersTeleported[targetPlayer.Name] = true
                   task.wait(0.75)
               end
           end
       end)
   end,
})


local Button = aimbotTab:CreateButton({
   Name = "Get all items",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

       local humanoidRootPart = player.Character.HumanoidRootPart
       local toolsTeleported = {}

       task.spawn(function()
           for _, tool in ipairs(workspace:GetDescendants()) do
               if tool:IsA("Tool") and not tool.Parent:IsA("Player") and not toolsTeleported[tool] then
                   humanoidRootPart.CFrame = tool.Handle.CFrame
                   toolsTeleported[tool] = true
                   task.wait(0.1)
                   
                   local prompt = tool:FindFirstChildOfClass("ProximityPrompt")
                   if prompt then
                       fireproximityprompt(prompt)
                   end
               end
           end
       end)
   end,
})


local Button = aimbotTab:CreateButton({
   Name = "Get all Slapple",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

       local humanoidRootPart = player.Character.HumanoidRootPart

       -- Folder names inside the FruitGloves model
       local fruitGlovesModelName = "FruitGloves" -- The model name
       local applesFolderName = "apples" -- Folder containing Slapple and BigSlapple
       local folderName = "Folder" -- Folder containing greyslapple
       local waterappleFolderName = "waterapple" -- Folder containing water

       -- Allowed item names
       local allowedNames = { "slanana", "BigSlapple", "Slapple", "greyslapple", "water" }
       local teleportedObjects = {}

       -- Save the player's position before teleporting
       local originalPosition = humanoidRootPart.CFrame

       -- Find the FruitGloves model
       local fruitGlovesModel = workspace:FindFirstChild(fruitGlovesModelName)
       local applesFolder = fruitGlovesModel and fruitGlovesModel:FindFirstChild(applesFolderName)
       local folder = fruitGlovesModel and fruitGlovesModel:FindFirstChild(folderName)
       local waterappleFolder = fruitGlovesModel and fruitGlovesModel:FindFirstChild(waterappleFolderName)

       task.spawn(function()
           -- Teleport to items in the apples folder
           if applesFolder then
               for _, item in ipairs(applesFolder:GetDescendants()) do
                   if (item:IsA("Part") or item:IsA("MeshPart") or item:IsA("UnionOperation")) and table.find(allowedNames, item.Name) and not teleportedObjects[item] then
                       humanoidRootPart.CFrame = item.CFrame
                       teleportedObjects[item] = true
                       task.wait(0.75)
                   end
               end
           end

           -- Teleport to items in the Folder
           if folder then
               for _, item in ipairs(folder:GetDescendants()) do
                   if (item:IsA("Part") or item:IsA("MeshPart") or item:IsA("UnionOperation")) and table.find(allowedNames, item.Name) and not teleportedObjects[item] then
                       humanoidRootPart.CFrame = item.CFrame
                       teleportedObjects[item] = true
                       task.wait(0.75)
                   end
               end
           end

           -- Teleport to items in the waterapple folder
           if waterappleFolder then
               for _, item in ipairs(waterappleFolder:GetDescendants()) do
                   if (item:IsA("Part") or item:IsA("MeshPart") or item:IsA("UnionOperation")) and table.find(allowedNames, item.Name) and not teleportedObjects[item] then
                       humanoidRootPart.CFrame = item.CFrame
                       teleportedObjects[item] = true
                       task.wait(0.75)
                   end
               end
           end

           -- After collecting all objects, wait 3 seconds and return to the original position
           task.wait(3)
           humanoidRootPart.CFrame = originalPosition
       end)
   end,
})

 
 local visualsTab = Window:CreateTab("Visuals", "crosshair")
 
 local Section = visualsTab:CreateSection("This is visual, meaning it doesn't appear to the entire server, just you.")
 
 
 local Toggle = visualsTab:CreateToggle({
    Name = "ESP players",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        getgenv().chams.enabled = Value
    end,
 })
 

local playerTab = Window:CreateTab("Player", "crosshair")
 
 local Section = playerTab:CreateSection("I think you already know")


local Toggle = playerTab:CreateToggle({
    Name = "activate Speed",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        getgenv().speed.enabled = Value
    end,
 })
 
 
  local Slider = playerTab:CreateSlider({
    Name = "Speed",
    Range = {0, 1000},
    Increment = 1,
    Suffix = "Speed",
    CurrentValue = 0,
    Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        getgenv().speed.speed = Value
    end,
 })

 
 
 getgenv().speed = {
    enabled = false,       -- Enable or disable the speed boost
    speed = 16,          -- Desired walk speed
    control = false, -- Enable enhanced control
    friction = 2.0,       -- Custom friction factor for more control
    keybind = Enum.KeyCode.KeypadDivide -- yes.. i put it as divide.. on the keypad
}
 
 
 Rayfield:Notify({
    Title = "Ready!",
    Content = "Script loaded.",
    Duration = 6.5,
    Image = 4483362458,
 })
