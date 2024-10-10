-- Load Orion Library
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

-- Create a window
local Window = OrionLib:MakeWindow({
    Name = "Fraise's Hub",
    HidePremium = false,
    IntroText = "Made by Fraise LE BG and Neyrozz",
    SaveConfig = true,
    ConfigFolder = "FraiseHubConfig"
})

-- Variables to control hitboxes
_G.HeadSize = 30
_G.Transparency = 0.7
_G.ShowHitboxes = false
_G.Disabled = true

-- Function to apply hitbox changes
local function applyHitboxChanges()
    game:GetService('RunService').RenderStepped:Connect(function()
        if not _G.Disabled then
            for i,v in next, game:GetService('Players'):GetPlayers() do
                if v.Name ~= game:GetService('Players').LocalPlayer.Name and v.Character and v.Character:FindFirstChild("HumanoidRootPart") then
                    pcall(function()
                        v.Character.HumanoidRootPart.Size = Vector3.new(_G.HeadSize, _G.HeadSize, _G.HeadSize)
                        v.Character.HumanoidRootPart.Transparency = _G.Transparency
                        v.Character.HumanoidRootPart.BrickColor = BrickColor.new("Really blue")
                        v.Character.HumanoidRootPart.Material = "Neon"
                        v.Character.HumanoidRootPart.CanCollide = false
                    end)
                end
            end
        end
    end)
end

-- Self Tab for Hitbox controls
local HitboxTab = Window:MakeTab({
    Name = "Hitbox Controls",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

-- Toggle for enabling/disabling hitboxes
HitboxTab:AddToggle({
    Name = "Enable Hitboxes",
    Default = false,
    Callback = function(Value)
        _G.Disabled = not Value
        if not Value then
            for _,v in next, game:GetService('Players'):GetPlayers() do
                if v.Character and v.Character:FindFirstChild("HumanoidRootPart") then
                    v.Character.HumanoidRootPart.Size = Vector3.new(2, 2, 1) -- Reset to default size
                    v.Character.HumanoidRootPart.Transparency = 1 -- Reset transparency
                end
            end
        end
        print("Hitboxes Enabled:", Value)
        applyHitboxChanges()
    end    
})

-- Slider to change hitbox size (Max extended to 10000)
HitboxTab:AddSlider({
    Name = "Hitbox Size",
    Min = 2,
    Max = 10000,
    Default = 30,
    Color = Color3.fromRGB(255,255,255),
    Increment = 1,
    ValueName = "Size",
    Callback = function(Value)
        _G.HeadSize = Value
        print("Hitbox Size set to:", Value)
    end    
})

-- Slider to change hitbox transparency
HitboxTab:AddSlider({
    Name = "Hitbox Transparency",
    Min = 0,
    Max = 1,
    Default = 0.7,
    Color = Color3.fromRGB(255,255,255),
    Increment = 0.1,
    ValueName = "Transparency",
    Callback = function(Value)
        _G.Transparency = Value
        print("Hitbox Transparency set to:", Value)
    end    
})

-- Toggle to show hitboxes (change color/material)
HitboxTab:AddToggle({
    Name = "Show Hitboxes",
    Default = false,
    Callback = function(Value)
        _G.ShowHitboxes = Value
        print("Show Hitboxes:", Value)
        for i,v in next, game:GetService('Players'):GetPlayers() do
            if v.Name ~= game:GetService('Players').LocalPlayer.Name and v.Character then
                pcall(function()
                    if _G.ShowHitboxes then
                        v.Character.HumanoidRootPart.BrickColor = BrickColor.new("Really blue")
                        v.Character.HumanoidRootPart.Material = "Neon"
                    else
                        v.Character.HumanoidRootPart.BrickColor = BrickColor.new("Institutional white")
                        v.Character.HumanoidRootPart.Material = "Plastic"
                    end
                end)
            end
        end
    end    
})

-- Additional Tab for Extra Scripts
local ScriptsTab = Window:MakeTab({
    Name = "Scripts",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

-- Function to add script buttons
local function addScriptButton(name, url)
    ScriptsTab:AddButton({
        Name = name,
        Callback = function()
            loadstring(game:HttpGet(url))()
            print(name .. " Launched")
        end    
    })
end

-- Adding all the scripts as buttons
addScriptButton("Launch Infinite Yield", 'loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
addScriptButton("Launch airhub", 'loadstring(game:HttpGet("https://raw.githubusercontent.com/Exunys/AirHub-V2/main/src/Main.lua"))()
addScriptButton("Launch arsenal", 'loadstring(game:HttpGet('https://raw.githubusercontent.com/AFGCLIENT/Snyware/main/Loader'))()
addScriptButton("Launch blox fruit", 'loadstring(game:HttpGet(("https://raw.githubusercontent.com/koonpeatch/PeatEX/master/BKHAX/BloxFruits"),true))()
addScriptButton("Launch doors", 'loadstring(game:HttpGet("https://raw.githubusercontent.com/KINGHUB01/BlackKing-obf/main/Doors%20Blackking%20And%20BobHub"))()
addScriptButton("Launch ez hub", 'loadstring(game:HttpGet(('https://raw.githubusercontent.com/debug42O/Ez-Industries-Launcher-Data/master/Launcher.lua'),true))()
addScriptButton("Launch feet simulator", 'loadstring(game:HttpGet("https://pastebin.com/raw/jtLYTQmg"))()
addScriptButton("Launch rivals", 'loadstring(game:HttpGet("https://raw.githubusercontent.com/cracklua/cracks/m/SilentRivals"))()
addScriptButton("Launch prizzlife", 'https://raw.githubusercontent.com/elliexmln/PrizzLife/main/pladmin.lua
addScriptButton("Launch spacehub", 'loadstring(game:HttpGet("https://orbituniverse.com/spacehub"))()
addScriptButton("Launch redz hub mobile (blox fruit)", 'loadstring(game:HttpGet("https://raw.githubusercontent.com/REDzHUB/BloxFruits/main/redz9999"))()


-- Adding a text label for "Made by Fraise LE BG and Neyrozz"
local label = Instance.new("TextLabel")
label.Parent = Window.Main
label.Size = UDim2.new(0, 200, 0, 50)
label.Position = UDim2.new(0.5, -100, 0, 10) -- Centered at the top
label.Text = "Made by Fraise LE BG"
label.TextColor3 = Color3.new(1, 1, 1)
label.BackgroundTransparency = 1
label.Font = Enum.Font.SourceSans
label.TextSize = 18

-- Fraise's Rivals Hub Fly Integration
local FlyEnabled = false
local function Fly()
    local player = game.Players.LocalPlayer
    local mouse = player:GetMouse()
    local HumanoidRootPart = player.Character:FindFirstChild("HumanoidRootPart")

    local flying = false
    local speed = 50
    local bp = Instance.new("BodyPosition")
    local bg = Instance.new("BodyGyro")
    bp.P = 9e4
    bp.maxForce = Vector3.new(9e4, 9e4, 9e4)
    bp.position = HumanoidRootPart.Position
    bg.maxTorque = Vector3.new(9e4, 9e4, 9e4)
    bg.cframe = HumanoidRootPart.CFrame

    bp.Parent = HumanoidRootPart
    bg.Parent = HumanoidRootPart

    flying = true
    game:GetService('RunService').RenderStepped:Connect(function()
        if flying then
            bp.position = HumanoidRootPart.Position + (HumanoidRootPart.CFrame.lookVector * (speed / 5))
            HumanoidRootPart.Velocity = Vector3.new(0, 0, 0)
        end
    end)

    mouse.KeyDown:Connect(function(key)
        if key == "q" then -- toggle fly off
            flying = false
            bp:Destroy()
            bg:Destroy()
        end
    end)
end

-- Add Fly Toggle to Rivals Hub in Self Tab
local FraisesScriptsTab = Window:MakeTab({
    Name = "Fraise's Scripts",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

FraisesScriptsTab:AddButton({
    Name = "Fraise Rivals Hub",
    Callback = function()
        -- Rivals Fly Functionality
        Fly()
        print("Fly function from Rivals Hub activated.")
    end
})

-- Initialize the GUI
OrionLib:Init()
