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
 
 
    KeySystem = false, -- Set this to true to use our key system
    KeySettings = {
       Title = "Key",
       Subtitle = "Key System",
       Note = "Dm for key (Tiktok: Mega_cat_studios)", -- Use this to tell the user how to get a key
       FileName = "skibidi key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"Key_9120", "Key_4045"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
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
       part.Position = Vector3.new(5911.56787, 701.383789, -8281.13477)
       part.Anchored = true
       part.CanCollide = true
       part.Parent = workspace

       local player = game.Players.LocalPlayer
       if player then
           player.Character:SetPrimaryPartCFrame(CFrame.new(5911.56787, 701.383789, -8281.13477))
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
