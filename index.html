-- Xeno Uyumlu - Estetik Troll Menü v3 (Fotolu)
-- Kullanım: BACKGROUND_IMAGE_ID satırına kendi rbxassetid'ni yaz.

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local LocalPlayer = Players.LocalPlayer
local Camera = workspace.CurrentCamera

-- ==== AYARLAR ====
local BACKGROUND_IMAGE_ID = "rbxassetid://0" -- BURAYA KENDİ RESİM ID'Nİ YAZ

local flyEnabled = false
local flySpeed = 50
local walkSpeedEnabled = false
local walkSpeedValue = 30
local noclipEnabled = false
local spinEnabled = false
local spinSpeed = 20
local infiniteJumpEnabled = false
local rgbEnabled = true
local rgbHue = 0

local flyBV, flyBG, flyConn, noclipConn, spinBV

-- ==== RGB ====
local function getRGBColor()
    rgbHue = (rgbHue + 0.005) % 1
    return Color3.fromHSV(rgbHue, 0.85, 1)
end

-- ==== FLY ====
local function startFly()
    flyEnabled = true
    local char = LocalPlayer.Character
    if not char then return end
    local hrp = char:FindFirstChild("HumanoidRootPart")
    if not hrp then return end

    if flyBV then flyBV:Destroy() end
    if flyBG then flyBG:Destroy() end
    if flyConn then flyConn:Disconnect() end

    flyBV = Instance.new("BodyVelocity")
    flyBV.MaxForce = Vector3.new(1e6, 1e6, 1e6)
    flyBV.Velocity = Vector3.zero
    flyBV.Parent = hrp

    flyBG = Instance.new("BodyGyro")
    flyBG.MaxTorque = Vector3.new(1e6, 1e6, 1e6)
    flyBG.P = 10000
    flyBG.D = 50
    flyBG.Parent = hrp

    flyConn = RunService.RenderStepped:Connect(function()
        if not flyEnabled then return end
        local c = LocalPlayer.Character
        if not c then return end
        local root = c:FindFirstChild("HumanoidRootPart")
        if not root then return end

        local moveDir = Vector3.zero
        if UserInputService:IsKeyDown(Enum.KeyCode.W) then moveDir += Camera.CFrame.LookVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.S) then moveDir -= Camera.CFrame.LookVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.A) then moveDir -= Camera.CFrame.RightVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.D) then moveDir += Camera.CFrame.RightVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.E) then moveDir += Vector3.new(0, 1, 0) end
        if UserInputService:IsKeyDown(Enum.KeyCode.Q) then moveDir -= Vector3.new(0, 1, 0) end

        if moveDir.Magnitude > 0 then
            flyBV.Velocity = moveDir.Unit * flySpeed
        else
            flyBV.Velocity = Vector3.zero
        end

        local look = Camera.CFrame.LookVector
        flyBG.CFrame = CFrame.new(root.Position, root.Position + look) * CFrame.Angles(math.rad(-15), 0, 0)
    end)
end

local function stopFly()
    flyEnabled = false
    if flyConn then flyConn:Disconnect() flyConn = nil end
    if flyBV then flyBV:Destroy() flyBV = nil end
    if flyBG then flyBG:Destroy() flyBG = nil end
end

-- ==== WALKSPEED ====
local function applyWalkSpeed()
    local char = LocalPlayer.Character
    if char and char:FindFirstChild("Humanoid") then
        char.Humanoid.WalkSpeed = walkSpeedEnabled and walkSpeedValue or 16
    end
end

-- ==== NOCLIP ====
local function toggleNoclip(state)
    noclipEnabled = state
    if noclipConn then noclipConn:Disconnect() noclipConn = nil end
    if noclipEnabled then
        noclipConn = RunService.Stepped:Connect(function()
            local char = LocalPlayer.Character
            if char then
                for _, v in pairs(char:GetDescendants()) do
                    if v:IsA("BasePart") then v.CanCollide = false end
                end
            end
        end)
    end
end

-- ==== SPIN ====
local function toggleSpin(state)
    spinEnabled = state
    local char = LocalPlayer.Character
    if not char then return end
    local hrp = char:FindFirstChild("HumanoidRootPart")
    if not hrp then return end
    if spinEnabled then
        if spinBV then spinBV:Destroy() end
        spinBV = Instance.new("BodyAngularVelocity")
        spinBV.MaxTorque = Vector3.new(0, math.huge, 0)
        spinBV.AngularVelocity = Vector3.new(0, spinSpeed, 0)
        spinBV.Parent = hrp
    else
        if spinBV then spinBV:Destroy() spinBV = nil end
    end
end

-- ==== INFINITE JUMP ====
UserInputService.JumpRequest:Connect(function()
    if infiniteJumpEnabled then
        local char = LocalPlayer.Character
        if char and char:FindFirstChild("Humanoid") then
            char.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
        end
    end
end)

-- ==== EMOJI ====
local function playEmoji(text)
    local char = LocalPlayer.Character
    if not char then return end
    local head = char:FindFirstChild("Head")
    if not head then return end
    local bill = Instance.new("BillboardGui")
    bill.Size = UDim2.new(0, 100, 0, 100)
    bill.StudsOffset = Vector3.new(0, 3, 0)
    bill.Adornee = head
    bill.AlwaysOnTop = true
    bill.Parent = head
    local lbl = Instance.new("TextLabel")
    lbl.Size = UDim2.new(1, 0, 1, 0)
    lbl.BackgroundTransparency = 1
    lbl.Text = text
    lbl.TextScaled = true
    lbl.Font = Enum.Font.FredokaOne
    lbl.Parent = bill
    task.delay(2, function() bill:Destroy() end)
end

-- ==== UI ====
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "TrollMenu"
ScreenGui.Parent = game.CoreGui
ScreenGui.ResetOnSpawn = false
ScreenGui.Enabled = false

local MainFrame = Instance.new("Frame")
MainFrame.Parent = ScreenGui
MainFrame.Size = UDim2.new(0, 500, 0, 400)
MainFrame.Position = UDim2.new(0.5, -250, 0.5, -200)
MainFrame.BackgroundColor3 = Color3.fromRGB(18, 18, 22)
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.ClipsDescendants = true
local mc = Instance.new("UICorner") mc.CornerRadius = UDim.new(0, 12) mc.Parent = MainFrame

local bgImage = Instance.new("ImageLabel")
bgImage.Parent = MainFrame
bgImage.Size = UDim2.new(1, 0, 1, 0)
bgImage.BackgroundTransparency = 1
bgImage.Image = BACKGROUND_IMAGE_ID
bgImage.ImageTransparency = 0.55
bgImage.ScaleType = Enum.ScaleType.Crop
bgImage.ZIndex = 0
local bic = Instance.new("UICorner") bic.CornerRadius = UDim.new(0, 12) bic.Parent = bgImage

local Title = Instance.new("TextLabel")
Title.Parent = MainFrame
Title.Size = UDim2.new(1, 0, 0, 42)
Title.BackgroundColor3 = Color3.fromRGB(255, 140, 0)
Title.BorderSizePixel = 0
Title.Text = "TROLL MENU  |  Insert = Aç/Kapat"
Title.TextColor3 = Color3.fromRGB(255,255,255)
Title.Font = Enum.Font.GothamBold
Title.TextSize = 16
Title.ZIndex = 2
local tc = Instance.new("UICorner") tc.CornerRadius = UDim.new(0, 12) tc.Parent = Title

local tabNames = {"Player", "Troll", "Emoji", "Ayarlar"}
local tabs = {}
local tabHolder = Instance.new("Frame")
tabHolder.Parent = MainFrame
tabHolder.Size = UDim2.new(1, -30, 0, 30)
tabHolder.Position = UDim2.new(0, 15, 0, 50)
tabHolder.BackgroundTransparency = 1
tabHolder.ZIndex = 2
local tabLayout = Instance.new("UIListLayout")
tabLayout.Parent = tabHolder
tabLayout.FillDirection = Enum.FillDirection.Horizontal
tabLayout.Padding = UDim.new(0, 8)

for i, name in ipairs(tabNames) do
    local btn = Instance.new("TextButton")
    btn.Parent = tabHolder
    btn.Size = UDim2.new(0, 100, 1, 0)
    btn.BackgroundColor3 = i == 1 and Color3.fromRGB(255, 140, 0) or Color3.fromRGB(45, 45, 50)
    btn.Text = name
    btn.TextColor3 = Color3.fromRGB(255,255,255)
    btn.Font = Enum.Font.GothamBold
    btn.TextSize = 13
    btn.ZIndex = 2
    local bc = Instance.new("UICorner") bc.CornerRadius = UDim.new(0, 6) bc.Parent = btn
    tabs[name] = btn
end

local content = Instance.new("Frame")
content.Parent = MainFrame
content.Size = UDim2.new(1, -30, 0, 280)
content.Position = UDim2.new(0, 15, 0, 90)
content.BackgroundTransparency = 1
content.ZIndex = 2

-- ==== SLIDER ====
local function makeSlider(parent, labelText, minVal, maxVal, default, y, onChanged)
    local holder = Instance.new("Frame")
    holder.Parent = parent
    holder.Size = UDim2.new(0, 220, 0, 50)
    holder.Position = UDim2.new(0, 0, 0, y)
    holder.BackgroundColor3 = Color3.fromRGB(30, 30, 35)
    holder.ZIndex = 2
    local hc = Instance.new("UICorner") hc.CornerRadius = UDim.new(0, 6) hc.Parent = holder

    local lbl = Instance.new("TextLabel")
    lbl.Parent = holder
    lbl.Size = UDim2.new(1, -10, 0, 18)
    lbl.Position = UDim2.new(0, 8, 0, 4)
    lbl.BackgroundTransparency = 1
    lbl.Text = labelText .. ": " .. default
    lbl.TextColor3 = Color3.fromRGB(255,255,255)
    lbl.Font = Enum.Font.Gotham
    lbl.TextSize = 12
    lbl.TextXAlignment = Enum.TextXAlignment.Left
    lbl.ZIndex = 2

    local barBg = Instance.new("Frame")
    barBg.Parent = holder
    barBg.Size = UDim2.new(1, -20, 0, 8)
    barBg.Position = UDim2.new(0, 10, 1, -14)
    barBg.BackgroundColor3 = Color3.fromRGB(60, 60, 70)
    barBg.BorderSizePixel = 0
    barBg.ZIndex = 2
    local bbc = Instance.new("UICorner") bbc.CornerRadius = UDim.new(1, 0) bbc.Parent = barBg

    local fill = Instance.new("Frame")
    fill.Parent = barBg
    fill.Size = UDim2.new((default - minVal)/(maxVal-minVal), 0, 1, 0)
    fill.BackgroundColor3 = Color3.fromRGB(255, 140, 0)
    fill.BorderSizePixel = 0
    fill.ZIndex = 2
    local fc = Instance.new("UICorner") fc.CornerRadius = UDim.new(1, 0) fc.Parent = fill

    local knob = Instance.new("Frame")
    knob.Parent = barBg
    knob.Size = UDim2.new(0, 14, 0, 14)
    knob.Position = UDim2.new((default - minVal)/(maxVal-minVal), -7, 0.5, -7)
    knob.BackgroundColor3 = Color3.fromRGB(255,255,255)
    knob.BorderSizePixel = 0
    knob.ZIndex = 2
    local kc = Instance.new("UICorner") kc.CornerRadius = UDim.new(1, 0) kc.Parent = knob

    local dragging = false
    local function updateFromX(x)
        local rel = (x - barBg.AbsolutePosition.X) / barBg.AbsoluteSize.X
        rel = math.clamp(rel, 0, 1)
        local val = math.floor(minVal + rel * (maxVal - minVal))
        fill.Size = UDim2.new(rel, 0, 1, 0)
        knob.Position = UDim2.new(rel, -7, 0.5, -7)
        lbl.Text = labelText .. ": " .. val
        onChanged(val)
    end

    barBg.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
            dragging = true
            updateFromX(input.Position.X)
        end
    end)
    UserInputService.InputChanged:Connect(function(input)
        if dragging and (input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch) then
            updateFromX(input.Position.X)
        end
    end)
    UserInputService.InputEnded:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
            dragging = false
        end
    end)
end

-- ==== TOGGLE ====
local function makeToggle(parent, text, y, callback)
    local f = Instance.new("Frame")
    f.Parent = parent
    f.Size = UDim2.new(0, 210, 0, 34)
    f.Position = UDim2.new(0, 0, 0, y)
    f.BackgroundColor3 = Color3.fromRGB(30, 30, 35)
    f.ZIndex = 2
    local c = Instance.new("UICorner") c.CornerRadius = UDim.new(0, 6) c.Parent = f

    local lbl = Instance.new("TextLabel")
    lbl.Parent = f
    lbl.Size = UDim2.new(0.7, 0, 1, 0)
    lbl.Position = UDim2.new(0, 10, 0, 0)
    lbl.BackgroundTransparency = 1
    lbl.Text = text
    lbl.TextColor3 = Color3.fromRGB(255,255,255)
    lbl.Font = Enum.Font.Gotham
    lbl.TextSize = 13
    lbl.TextXAlignment = Enum.TextXAlignment.Left
    lbl.ZIndex = 2

    local btn = Instance.new("TextButton")
    btn.Parent = f
    btn.Size = UDim2.new(0, 44, 0, 22)
    btn.Position = UDim2.new(1, -54, 0.5, -11)
    btn.BackgroundColor3 = Color3.fromRGB(255, 140, 0)
    btn.Text = "OFF"
    btn.TextColor3 = Color3.fromRGB(255,255,255)
    btn.Font = Enum.Font.GothamBold
    btn.TextSize = 11
    btn.ZIndex = 2
    local bc = Instance.new("UICorner") bc.CornerRadius = UDim.new(0, 5) bc.Parent = btn

    local on = false
    btn.MouseButton1Click:Connect(function()
        on = not on
        btn.Text = on and "ON" or "OFF"
        btn.BackgroundColor3 = on and Color3.fromRGB(0, 200, 0) or Color3.fromRGB(255, 140, 0)
        callback(on)
    end)
end

-- ==== SAYFALAR ====
local playerPage = Instance.new("Frame")
playerPage.Parent = content
playerPage.Size = UDim2.new(1, 0, 1, 0)
playerPage.BackgroundTransparency = 1
playerPage.ZIndex = 2

local trollPage = Instance.new("Frame")
trollPage.Parent = content
trollPage.Size = UDim2.new(1, 0, 1, 0)
trollPage.BackgroundTransparency = 1
trollPage.Visible = false
trollPage.ZIndex = 2

local emojiPage = Instance.new("Frame")
emojiPage.Parent = content
emojiPage.Size = UDim2.new(1, 0, 1, 0)
emojiPage.BackgroundTransparency = 1
emojiPage.Visible = false
emojiPage.ZIndex = 2

local settingsPage = Instance.new("Frame")
settingsPage.Parent = content
settingsPage.Size = UDim2.new(1, 0, 1, 0)
settingsPage.BackgroundTransparency = 1
settingsPage.Visible = false
settingsPage.ZIndex = 2

-- PLAYER
makeToggle(playerPage, "Fly (E/Q Yukarı/Aşağı)", 0, function(s) if s then startFly() else stopFly() end end)
makeSlider(playerPage, "Fly Speed", 1, 1000, flySpeed, 42, function(v) flySpeed = v end)
makeToggle(playerPage, "WalkSpeed", 98, function(s) walkSpeedEnabled = s; applyWalkSpeed() end)
makeSlider(playerPage, "WalkSpeed", 1, 1000, walkSpeedValue, 140, function(v) walkSpeedValue = v; applyWalkSpeed() end)
makeToggle(playerPage, "Noclip", 196, function(s) toggleNoclip(s) end)
makeToggle(playerPage, "Infinite Jump", 236, function(s) infiniteJumpEnabled = s end)

-- TROLL
makeToggle(trollPage, "Spin (Kendi Karakterin)", 0, function(s) toggleSpin(s) end)
makeSlider(trollPage, "Spin Speed", 1, 1000, spinSpeed, 42, function(v) spinSpeed = v; if spinEnabled and spinBV then spinBV.AngularVelocity = Vector3.new(0, v, 0) end end)

-- EMOJI
local emojiList = {"😂","🤣","💀","🔥","👻","🎃","👿","💩","🍆","🥵","🖕","🤡","😈","🤪","👽","💣","☠️","🎉","🤮","👀"}
local emojiHolder = Instance.new("Frame")
emojiHolder.Parent = emojiPage
emojiHolder.Size = UDim2.new(1, 0, 0, 250)
emojiHolder.BackgroundTransparency = 1
emojiHolder.ZIndex = 2
local emojiGrid = Instance.new("UIGridLayout")
emojiGrid.Parent = emojiHolder
emojiGrid.CellSize = UDim2.new(0, 55, 0, 55)
emojiGrid.CellPadding = UDim2.new(0, 8, 0, 8)

for _, emo in ipairs(emojiList) do
    local b = Instance.new("TextButton")
    b.Parent = emojiHolder
    b.BackgroundColor3 = Color3.fromRGB(30, 30, 35)
    b.Text = emo
    b.TextScaled = true
    b.Font = Enum.Font.FredokaOne
    b.ZIndex = 2
    local bc = Instance.new("UICorner") bc.CornerRadius = UDim.new(0, 8) bc.Parent = b
    b.MouseButton1Click:Connect(function() playEmoji(emo) end)
end

-- AYARLAR
makeToggle(settingsPage, "RGB Renk Modu", 0, function(s) rgbEnabled = s end)

local colorInfo = Instance.new("TextLabel")
colorInfo.Parent = settingsPage
colorInfo.Size = UDim2.new(0, 300, 0, 30)
colorInfo.Position = UDim2.new(0, 0, 0, 50)
colorInfo.BackgroundTransparency = 1
colorInfo.Text = "RGB açıkken menü rengi gökkuşağı olur."
colorInfo.TextColor3 = Color3.fromRGB(200,200,200)
colorInfo.Font = Enum.Font.Gotham
colorInfo.TextSize = 12
colorInfo.TextXAlignment = Enum.TextXAlignment.Left
colorInfo.ZIndex = 2

-- SEKME GEÇİŞ
local pages = {Player = playerPage, Troll = trollPage, Emoji = emojiPage, Ayarlar = settingsPage}
local function showPage(name)
    for n, p in pairs(pages) do p.Visible = (n == name) end
    for n, b in pairs(tabs) do
        b.BackgroundColor3 = (n == name) and Color3.fromRGB(255, 140, 0) or Color3.fromRGB(45, 45, 50)
    end
end
for name, btn in pairs(tabs) do
    btn.MouseButton1Click:Connect(function() showPage(name) end)
end

-- RGB DÖNGÜ
task.spawn(function()
    while true do
        task.wait(0.05)
        if rgbEnabled then
            local col = getRGBColor()
            for _, t in ipairs(tabs) do
                if t.BackgroundColor3 ~= Color3.fromRGB(45,45,50) then
                    t.BackgroundColor3 = col
                end
            end
            Title.BackgroundColor3 = col
        end
    end
end)

-- INSERT
UserInputService.InputBegan:Connect(function(input, gp)
    if gp then return end
    if input.KeyCode == Enum.KeyCode.Insert then
        ScreenGui.Enabled = not ScreenGui.Enabled
    end
end)

-- RESPAWN
LocalPlayer.CharacterAdded:Connect(function()
    task.wait(1)
    applyWalkSpeed()
    if flyEnabled then stopFly() end
    if noclipEnabled then toggleNoclip(true) end
    if spinEnabled then toggleSpin(true) end
end)

print("v3 hazır kanka. Insert = aç/kapat. Resim ID'sini BACKGROUND_IMAGE_ID'ye yaz.")
