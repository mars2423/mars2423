local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
    Name = "tappin.cc",
    Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
    LoadingTitle = "join dc serv comning soon..",
    LoadingSubtitle = "by mars",
    Theme = "Serenity", -- Check https://docs.sirius.menu/rayfield/configuration/themes
 
    DisableRayfieldPrompts = false,
    DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface
 
    ConfigurationSaving = {
       Enabled = true,
       FolderName = nil, -- Create a custom folder for your hub/game
       FileName = "nice"
    },
 
    Discord = {
       Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
       Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
       RememberJoins = true -- Set this to false to make them join the discord every time they load it up
    },
 
    KeySystem = false, -- Set this to true to use our key system
    KeySettings = {
       Title = "Untitled",
       Subtitle = "Key System",
       Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
       FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
    }
 })

 local MainTab = Window:CreateTab("main", 4483362458) -- Title, Image
 local MainSection = MainTab:CreateSection("main tab")

 local Button = MainTab:CreateButton({
    Name = "silent aim streamable rejoin to turn off",
    Callback = function()
        getgenv().SilentAim = {
            Settings = {
                Enabled = true,
                AimPart = "UpperTorso",
                Prediction = 0.165,
                WallCheck = true
            },
            FOV = {
                Enabled = true,
                Size = 75,
                Filled = false,
                Thickness = 0.66,
                Transparency = 0.0,
                Color = Color3.fromHSV(tick() % 5 / 5, 1, 1)
            }
        }
        local lp = game:GetService("Players").LocalPlayer
        local cc = game:GetService("Workspace").CurrentCamera
        local mouse = lp:GetMouse()
        getgenv().PredictionBackUp = getgenv().SilentAim.Settings.Prediction
        local cc = game:GetService("Workspace").CurrentCamera
        local mouse = lp:GetMouse()
        
        local Utility = {
            Invite = "camlock",
            BackupInvite = "closetcheating",
            Version = "1.0.0a",
            Method = "UpdateMousePos",
            AllowedPlaceIDs = {
                2788229376, -- Da Hood
                7213786345, -- Da Hood VC
                9825515356, -- Hood Customs
                5602055394, -- Hood Modded
                7951883376, -- Hood Modded VC
                12927359803, -- Dah Aim Trainer
                12867571492, -- KatanaHood
                7242996350, -- Da Hood Aim Trainer
                12884917481, -- Da Hood Aim Trainer VC
                11867820563, -- Dae Hood
                12618586930, -- Dat Hood
            }
        }
        
        if game.PlaceId == 2788229376 or game.PlaceId == 7213786345 then -- // Da Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 5602055394 or game.PlaceId == 7951883376 then -- // Hood Modded
            Utility.Method = "MousePos"
                MainRemote = game:GetService("ReplicatedStorage").Bullets 
        elseif game.PlaceId == 12927359803 then -- // Dah Aim Trainer
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 7242996350 or game.PlaceId == 12884917481 then -- // Da Hood Aim Trainer
            Utility.Method = "UpdateMousePos" 
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 12867571492 then -- // Katana Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 11867820563 then -- // Dae Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 12618586930 then -- // Dat Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        end
        
        WTS = (function(Object)
            local ObjectVector = cc:WorldToScreenPoint(Object.Position)
            return Vector2.new(ObjectVector.X, ObjectVector.Y)
        end)
        
        Filter = (function(obj)
            if (obj:IsA('BasePart')) then
                return true
            end
        end)
        
        mousePosVector2 = (function()
            return Vector2.new(mouse.X, mouse.Y) 
        end)
        
        getClosestBodyPart = (function()
            local shortestDistance = math.huge
            local bodyPart = nil
            for _, v in next, game.Players:GetPlayers() do
                if (v ~= lp and v.Character and v.Character:FindFirstChild("Humanoid")) then
                    for k, x in next, v.Character:GetChildren() do
                        if (Filter(x)) then
                            local Distance = (WTS(x) - mousePosVector2()).magnitude
                            if (Distance < shortestDistance) then
                                shortestDistance = Distance
                                bodyPart = x
                            end
                        end
                    end
                end
            end
            return bodyPart
        end)
        local FOVCircle = Drawing.new("Circle")
        function updateFOV()
            FOVCircle.Radius = SilentAim.FOV.Size * 3
            FOVCircle.Visible = SilentAim.FOV.Enabled
            FOVCircle.Transparency = SilentAim.FOV.Transparency
            FOVCircle.Filled = SilentAim.FOV.Filled
            FOVCircle.Color = SilentAim.FOV.Color
            FOVCircle.Thickness = SilentAim.FOV.Thickness
            FOVCircle.Position = Vector2.new(game:GetService("UserInputService"):GetMouseLocation().X, game:GetService("UserInputService"):GetMouseLocation().Y)
            return FOVCircle
        end
        
        local plrService = game:GetService("Players")
        local localPlr = plrService.LocalPlayer
        local mouseLocal = localPlr:GetMouse()
        local Players, Client, Mouse, Camera =
            game:GetService("Players"),
            game:GetService("Players").LocalPlayer,
            game:GetService("Players").LocalPlayer:GetMouse(),
            game:GetService("Workspace").CurrentCamera
        
        
        function wallCheck(destination, ignore)
            if (getgenv().SilentAim.Settings.WallCheck) then
                local Origin = Camera.CFrame.p
                local CheckRay = Ray.new(Origin, destination - Origin)
                local Hit = game:GetService("Workspace"):FindPartOnRayWithIgnoreList(CheckRay, ignore)
                return Hit == nil
            else
                return true
            end
        end
        
        function getClosestPlayerToCursor()
            closestDist = SilentAim.FOV.Size * 3.47
            closestPlr = nil;
            for i, v in next, plrService:GetPlayers() do
                pcall(function()
                    local notKO = v.Character:WaitForChild("BodyEffects")["K.O"].Value ~= true;
                    local notGrabbed = v.Character:FindFirstChild("GRABBING_COINSTRAINT") == nil
                    if v ~= localPlr and v.Character and v.Character.Humanoid.Health > 0 and notKO and notGrabbed then
                        local screenPos, cameraVisible = Camera:WorldToViewportPoint(v.Character.HumanoidRootPart.Position)
                        if cameraVisible then
                            local distToMouse = (Vector2.new(mouseLocal.X, mouseLocal.Y) - Vector2.new(screenPos.X, screenPos.Y)).Magnitude
                            if distToMouse < closestDist and wallCheck(v.Character.Head.Position, {
                                game:GetService("Players").LocalPlayer,
                                v.Character
                            }) then
                                closestPlr = v
                                closestDist = distToMouse
                            end
                        end
                    end
                end)
            end
            return closestPlr, closestDist
        end
        
        spawn(function()
            while wait() do
                Plr = getClosestPlayerToCursor()
            end
        end)
        
        spawn(function()
            while wait() do
                if Plr ~= nil and Plr.Character.Humanoid.FloorMaterial ~= Enum.Material.Air then
                    local Ping = math.floor(game.Stats.Network.ServerStatsItem["Data Ping"]:GetValue())
                    getgenv().SilentAim.Settings.Prediction = Ping / 1000 + 0.07
                end
            end
        end)
        
        game:GetService("RunService").Heartbeat:connect(function()
            updateFOV()
        end)
        
        game.Players.LocalPlayer.Character.ChildAdded:Connect(function(tool)
            if tool:IsA("Tool") then -- add a better check for if the tool is a weapon 
                tool.Activated:Connect(function() -- fuck a :Disconnect lol
                    if Plr ~= nil then
                        game:GetService("ReplicatedStorage").MainEvent:FireServer(Utility.Method, Plr.Character[SilentAim.Settings.AimPart].Position + (Plr.Character[SilentAim.Settings.AimPart].Velocity * SilentAim.Settings.Prediction))
                    end
                end)
            end
        end)
    end,
 })

 local Button = MainTab:CreateButton({
    Name = "silent aim unstreamble rejoin to turn off",
    Callback = function()
        getgenv().SilentAim = {
            Settings = {
                Enabled = true,
                AimPart = "UpperTorso",
                Prediction = 0.165,
                WallCheck = true
            },
            FOV = {
                Enabled = true,
                Size = 90,
                Filled = false,
                Thickness = 0.66,
                Transparency = 10,
                Color = Color3.fromHSV(tick() % 5 / 5, 1, 1)
            }
        }
        local lp = game:GetService("Players").LocalPlayer
        local cc = game:GetService("Workspace").CurrentCamera
        local mouse = lp:GetMouse()
        getgenv().PredictionBackUp = getgenv().SilentAim.Settings.Prediction
        local cc = game:GetService("Workspace").CurrentCamera
        local mouse = lp:GetMouse()
        
        local Utility = {
            Invite = "camlock",
            BackupInvite = "closetcheating",
            Version = "1.0.0a",
            Method = "UpdateMousePos",
            AllowedPlaceIDs = {
                2788229376, -- Da Hood
                7213786345, -- Da Hood VC
                9825515356, -- Hood Customs
                5602055394, -- Hood Modded
                7951883376, -- Hood Modded VC
                12927359803, -- Dah Aim Trainer
                12867571492, -- KatanaHood
                7242996350, -- Da Hood Aim Trainer
                12884917481, -- Da Hood Aim Trainer VC
                11867820563, -- Dae Hood
                12618586930, -- Dat Hood
            }
        }
        
        if game.PlaceId == 2788229376 or game.PlaceId == 7213786345 then -- // Da Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 5602055394 or game.PlaceId == 7951883376 then -- // Hood Modded
            Utility.Method = "MousePos"
                MainRemote = game:GetService("ReplicatedStorage").Bullets 
        elseif game.PlaceId == 12927359803 then -- // Dah Aim Trainer
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 7242996350 or game.PlaceId == 12884917481 then -- // Da Hood Aim Trainer
            Utility.Method = "UpdateMousePos" 
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 12867571492 then -- // Katana Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 11867820563 then -- // Dae Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        elseif game.PlaceId == 12618586930 then -- // Dat Hood
            Utility.Method = "UpdateMousePos"
                MainRemote = game:GetService("ReplicatedStorage").MainEvent
        end
        
        WTS = (function(Object)
            local ObjectVector = cc:WorldToScreenPoint(Object.Position)
            return Vector2.new(ObjectVector.X, ObjectVector.Y)
        end)
        
        Filter = (function(obj)
            if (obj:IsA('BasePart')) then
                return true
            end
        end)
        
        mousePosVector2 = (function()
            return Vector2.new(mouse.X, mouse.Y) 
        end)
        
        getClosestBodyPart = (function()
            local shortestDistance = math.huge
            local bodyPart = nil
            for _, v in next, game.Players:GetPlayers() do
                if (v ~= lp and v.Character and v.Character:FindFirstChild("Humanoid")) then
                    for k, x in next, v.Character:GetChildren() do
                        if (Filter(x)) then
                            local Distance = (WTS(x) - mousePosVector2()).magnitude
                            if (Distance < shortestDistance) then
                                shortestDistance = Distance
                                bodyPart = x
                            end
                        end
                    end
                end
            end
            return bodyPart
        end)
        local FOVCircle = Drawing.new("Circle")
        function updateFOV()
            FOVCircle.Radius = SilentAim.FOV.Size * 3
            FOVCircle.Visible = SilentAim.FOV.Enabled
            FOVCircle.Transparency = SilentAim.FOV.Transparency
            FOVCircle.Filled = SilentAim.FOV.Filled
            FOVCircle.Color = SilentAim.FOV.Color
            FOVCircle.Thickness = SilentAim.FOV.Thickness
            FOVCircle.Position = Vector2.new(game:GetService("UserInputService"):GetMouseLocation().X, game:GetService("UserInputService"):GetMouseLocation().Y)
            return FOVCircle
        end
        
        local plrService = game:GetService("Players")
        local localPlr = plrService.LocalPlayer
        local mouseLocal = localPlr:GetMouse()
        local Players, Client, Mouse, Camera =
            game:GetService("Players"),
            game:GetService("Players").LocalPlayer,
            game:GetService("Players").LocalPlayer:GetMouse(),
            game:GetService("Workspace").CurrentCamera
        
        
        function wallCheck(destination, ignore)
            if (getgenv().SilentAim.Settings.WallCheck) then
                local Origin = Camera.CFrame.p
                local CheckRay = Ray.new(Origin, destination - Origin)
                local Hit = game:GetService("Workspace"):FindPartOnRayWithIgnoreList(CheckRay, ignore)
                return Hit == nil
            else
                return true
            end
        end
        
        function getClosestPlayerToCursor()
            closestDist = SilentAim.FOV.Size * 3.47
            closestPlr = nil;
            for i, v in next, plrService:GetPlayers() do
                pcall(function()
                    local notKO = v.Character:WaitForChild("BodyEffects")["K.O"].Value ~= true;
                    local notGrabbed = v.Character:FindFirstChild("GRABBING_COINSTRAINT") == nil
                    if v ~= localPlr and v.Character and v.Character.Humanoid.Health > 0 and notKO and notGrabbed then
                        local screenPos, cameraVisible = Camera:WorldToViewportPoint(v.Character.HumanoidRootPart.Position)
                        if cameraVisible then
                            local distToMouse = (Vector2.new(mouseLocal.X, mouseLocal.Y) - Vector2.new(screenPos.X, screenPos.Y)).Magnitude
                            if distToMouse < closestDist and wallCheck(v.Character.Head.Position, {
                                game:GetService("Players").LocalPlayer,
                                v.Character
                            }) then
                                closestPlr = v
                                closestDist = distToMouse
                            end
                        end
                    end
                end)
            end
            return closestPlr, closestDist
        end
        
        spawn(function()
            while wait() do
                Plr = getClosestPlayerToCursor()
            end
        end)
        
        spawn(function()
            while wait() do
                if Plr ~= nil and Plr.Character.Humanoid.FloorMaterial ~= Enum.Material.Air then
                    local Ping = math.floor(game.Stats.Network.ServerStatsItem["Data Ping"]:GetValue())
                    getgenv().SilentAim.Settings.Prediction = Ping / 1000 + 0.07
                end
            end
        end)
        
        game:GetService("RunService").Heartbeat:connect(function()
            updateFOV()
        end)
        
        game.Players.LocalPlayer.Character.ChildAdded:Connect(function(tool)
            if tool:IsA("Tool") then -- add a better check for if the tool is a weapon 
                tool.Activated:Connect(function() -- fuck a :Disconnect lol
                    if Plr ~= nil then
                        game:GetService("ReplicatedStorage").MainEvent:FireServer(Utility.Method, Plr.Character[SilentAim.Settings.AimPart].Position + (Plr.Character[SilentAim.Settings.AimPart].Velocity * SilentAim.Settings.Prediction))
                    end
                end)
            end
        end)
    end,
 })

 local Toggle = MainTab:CreateButton({
    Name = "aim assist for silent aim (e)",
    CurrentValue = false,
    Flag = "Toggle ON AND OFF", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        getgenv().RecurringPoint = "UpperTorso"
        getgenv().Hitbox = "UpperTorso"
        getgenv().Keybind = "e"
        getgenv().AimbotStrengthAmount = 0.0335
        getgenv().PredictionAmount = 10
        getgenv().Radius = 25
        getgenv().UsePrediction = true
        getgenv().AimbotStrength = true
        getgenv().FirstPerson = true
        getgenv().ThirdPerson = true
        getgenv().TeamCheck = false
        getgenv().Enabled = true
        
        
        -- // main script use with silent aim / / -- 
        
        loadstring(game:HttpGet("https://raw.githubusercontent.com/tenaaki/GenericAimbot/main/v1.0.0"))()
    end,
 })

 local Button = MainTab:CreateButton({
    Name = "camlock1 moblie/pc keybind (q) and p to diable",
    Callback = function()
        getgenv().Prediction = 0.1248710929171	
getgenv().AimPart = "UpperTorso"	
getgenv().Key = "q"	
getgenv().DisableKey = "P"	
	
getgenv().FOV = true	
getgenv().ShowFOV = false	
getgenv().FOVSize = 55	
	
--// Variables (Service)	
	
local Players = game:GetService("Players")	
local RS = game:GetService("RunService")	
local WS = game:GetService("Workspace")	
local GS = game:GetService("GuiService")	
local SG = game:GetService("StarterGui")	
	
--// Variables (regular)	
	
local LP = Players.LocalPlayer	
local Mouse = LP:GetMouse()	
local Camera = WS.CurrentCamera	
local GetGuiInset = GS.GetGuiInset	
	
local AimlockState = true	
local Locked	
local Victim	
	
local SelectedKey = getgenv().Key	
local SelectedDisableKey = getgenv().DisableKey	
	
--// Notification function	
	
function Notify(tx)	
    SG:SetCore("SendNotification", {	
        Title = "Midnight v2",	
        Text = tx,	
Duration = 5	
    })	
end	
	
--// Check if aimlock is loaded	
	
if getgenv().Loaded == true then	
    Notify("Camlock is already loaded!")	
    return	
end	
	
getgenv().Loaded = true	
	
--// FOV Circle	
	
local fov = Drawing.new("Circle")	
fov.Filled = false	
fov.Transparency = 1	
fov.Thickness = 1	
fov.Color = Color3.fromRGB(255, 255, 0)	
fov.NumSides = 1000	
	
--// Functions	
	
function update()	
    if getgenv().FOV == true then	
        if fov then	
fov.Radius = getgenv().FOVSize * 2	
            fov.Visible = getgenv().ShowFOV	
fov.Position = Vector2.new(Mouse.X, Mouse.Y + GetGuiInset(GS).Y)	
	
            return fov	
        end	
    end	
end	
	
function WTVP(arg)	
    return Camera:WorldToViewportPoint(arg)	
end	
	
function WTSP(arg)	
    return Camera.WorldToScreenPoint(Camera, arg)	
end	
	
function getClosest()	
    local closestPlayer	
    local shortestDistance = math.huge	
	
    for i, v in pairs(game.Players:GetPlayers()) do	
        local notKO = v.Character:WaitForChild("BodyEffects")["K.O"].Value ~= true	
        local notGrabbed = v.Character:FindFirstChild("GRABBING_COINSTRAINT") == nil	
        	
if v ~= game.Players.LocalPlayer and v.Character and v.Character:FindFirstChild("Humanoid") and v.Character.Humanoid.Health ~= 0 and v.Character:FindFirstChild(getgenv().AimPart) and notKO and notGrabbed then	
            local pos = Camera:WorldToViewportPoint(v.Character.PrimaryPart.Position)	
local magnitude = (Vector2.new(pos.X, pos.Y) - Vector2.new(Mouse.X, Mouse.Y)).magnitude	
            	
            if (getgenv().FOV) then	
                if (fov.Radius > magnitude and magnitude < shortestDistance) then	
                    closestPlayer = v	
                    shortestDistance = magnitude	
                end	
            else	
                if (magnitude < shortestDistance) then	
                    closestPlayer = v	
                    shortestDistance = magnitude	
                end	
            end	
        end	
    end	
    return closestPlayer	
end	
	
--// Checks if key is down	
	
Mouse.KeyDown:Connect(function(k)	
    SelectedKey = SelectedKey:lower()	
    SelectedDisableKey = SelectedDisableKey:lower()	
    if k == SelectedKey then	
        if AimlockState == true then	
            Locked = not Locked	
            if Locked then	
                Victim = getClosest()	
	
                Notify("Locked onto: "..tostring(Victim.Character.Humanoid.DisplayName))	
            else	
                if Victim ~= nil then	
                    Victim = nil	
	
                    Notify("Unlocked!")	
                end	
            end	
        else	
            Notify("Aimlock is not enabled!")	
        end	
    end	
    if k == SelectedDisableKey then	
        AimlockState = not AimlockState	
    end	
end)	
	
--// Loop update FOV and loop camera lock onto target	
	
RS.RenderStepped:Connect(function()	
    update()	
    if AimlockState == true then	
        if Victim ~= nil then	
            Camera.CFrame = CFrame.new(Camera.CFrame.p, Victim.Character[getgenv().AimPart].Position + Victim.Character[getgenv().AimPart].Velocity*getgenv().Prediction)	
        end	
    end	
end)	
	while wait() do
        if getgenv().AutoPrediction == true then	
        local pingvalue = game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValueString()	
        local split = string.split(pingvalue,'(')	
local ping = tonumber(split[1])	
if ping < 225 then	
getgenv().Prediction = 1.4	
elseif ping < 215 then	
getgenv().Prediction = 1.2	
	elseif ping < 205 then
getgenv().Prediction = 1.0	
	elseif ping < 190 then
getgenv().Prediction = 0.10	
elseif ping < 180 then	
getgenv().Prediction = 0.12	
	elseif ping < 170 then
getgenv().Prediction = 0.15	
	elseif ping < 160 then
getgenv().Prediction = 0.18	
	elseif ping < 150 then
getgenv().Prediction = 0.110	
elseif ping < 140 then	
getgenv().Prediction = 0.113	
elseif ping < 130 then	
getgenv().Prediction = 0.116	
elseif ping < 120 then	
getgenv().Prediction = 0.120	
elseif ping < 110 then	
getgenv().Prediction = 0.124	
elseif ping < 105 then	
getgenv().Prediction = 0.127	
elseif ping < 90 then	
getgenv().Prediction = 0.130	
elseif ping < 80 then	
getgenv().Prediction = 0.133	
elseif ping < 70 then	
getgenv().Prediction = 0.136	
elseif ping < 60 then	
getgenv().Prediction = 0.140	
elseif ping < 50 then	
getgenv().Prediction = 0.143	
elseif ping < 40 then	
getgenv().Prediction = 0.145	
elseif ping < 30 then	
getgenv().Prediction = 0.155	
elseif ping < 20 then	
getgenv().Prediction = 0.157	
        end	
        end	
	end
    end,
 })

 local Button = MainTab:CreateButton({
    Name = "camlock2 (Q)",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Camlock-da-hood-mobile-20398"))()
    end,
 })

 local PlayerTab = Window:CreateTab("player🕵️‍♀️", 4483362458) -- Title, Image
 local PlayerSection = PlayerTab:CreateSection("player options")

 local Toggle = PlayerTab:CreateButton({
    Name = "fly (f)-to increase (e) to decrease (t) click when u reset or stomped",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
    -- Services
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

-- Variables
local player = Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

local flying = false
local speed = 50 -- Initial flying speed
local moveDirection = Vector3.zero
local bodyVelocity = nil
local bodyGyro = nil

-- Toggle fly mode
local function toggleFly()
    flying = not flying

    if flying then
        -- Enable fly mode
        bodyVelocity = Instance.new("BodyVelocity", humanoidRootPart)
        bodyVelocity.MaxForce = Vector3.new(1e6, 1e6, 1e6) -- Allow movement in all directions
        bodyVelocity.Velocity = Vector3.zero

        bodyGyro = Instance.new("BodyGyro", humanoidRootPart)
        bodyGyro.MaxTorque = Vector3.new(1e6, 1e6, 1e6) -- Stabilize rotation
        bodyGyro.CFrame = humanoidRootPart.CFrame

        print("Fly mode enabled")
    else
        -- Disable fly mode
        if bodyVelocity then bodyVelocity:Destroy() end
        if bodyGyro then bodyGyro:Destroy() end

        print("Fly mode disabled")
    end
end

-- Update movement based on input
local function updateDirection()
    moveDirection = Vector3.zero

    if UserInputService:IsKeyDown(Enum.KeyCode.W) then
        moveDirection = moveDirection + workspace.CurrentCamera.CFrame.LookVector
    end
    if UserInputService:IsKeyDown(Enum.KeyCode.S) then
        moveDirection = moveDirection - workspace.CurrentCamera.CFrame.LookVector
    end
    if UserInputService:IsKeyDown(Enum.KeyCode.A) then
        moveDirection = moveDirection - workspace.CurrentCamera.CFrame.RightVector
    end
    if UserInputService:IsKeyDown(Enum.KeyCode.D) then
        moveDirection = moveDirection + workspace.CurrentCamera.CFrame.RightVector
    end
    if UserInputService:IsKeyDown(Enum.KeyCode.Space) then
        moveDirection = moveDirection + Vector3.new(0, 1, 0)
    end
    if UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
        moveDirection = moveDirection - Vector3.new(0, 1, 0)
    end
end

-- Apply fly physics
RunService.RenderStepped:Connect(function()
    if flying and bodyVelocity and bodyGyro then
        updateDirection()
        if moveDirection.Magnitude > 0 then
            bodyVelocity.Velocity = moveDirection.Unit * speed
        else
            bodyVelocity.Velocity = Vector3.zero
        end
        bodyGyro.CFrame = workspace.CurrentCamera.CFrame
    end
end)

-- Adjust speed in-game
UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end

    -- Toggle fly mode
    if input.KeyCode == Enum.KeyCode.F then
        toggleFly()
    end

    -- Increase speed
    if input.KeyCode == Enum.KeyCode.E then
        speed = speed + 50
        print("Speed increased to: " .. speed)
    end

    -- Decrease speed
    if input.KeyCode == Enum.KeyCode.T then
        speed = math.max(50, speed - 50) -- Ensure speed doesn't go below 50
        print("Speed decreased to: " .. speed)
    end
end)

    end,
 })

 local Button = MainTab:CreateButton({
    Name = "target starfe (z)",
    Callback = function()
    --[[
    === Config Section ===
    Adjust these values to customize the script.
--]]

local CONFIG = {
    ToggleKey = Enum.KeyCode.Z,      -- Key to toggle strafing (now set to Z)
    TargetPart = "UpperTorso",       -- Part to strafe around ("Head", "UpperTorso", etc.)
    StrafeRadius = 10,               -- Distance to maintain from the target
    StrafeSpeed = 10,                -- Speed of strafing
    EnableNotifications = true       -- Show notifications in the output
}

--[[
    === Script Start ===
--]]

-- Services
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")

-- Variables
local player = Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
local target = nil
local isStrafing = false
local currentAngle = 0

-- Notify function
local function notify(message)
    if CONFIG.EnableNotifications then
        print(message)
    end
end

-- Find the closest target
local function findClosestTarget()
    local closestPlayer = nil
    local closestDistance = math.huge

    for _, otherPlayer in pairs(Players:GetPlayers()) do
        if otherPlayer ~= player and otherPlayer.Character and otherPlayer.Character:FindFirstChild(CONFIG.TargetPart) then
            local targetPart = otherPlayer.Character[CONFIG.TargetPart]
            local distance = (targetPart.Position - humanoidRootPart.Position).Magnitude

            if distance < closestDistance then
                closestDistance = distance
                closestPlayer = otherPlayer
            end
        end
    end

    return closestPlayer
end

-- Toggle strafing
local function toggleStrafing()
    isStrafing = not isStrafing

    if isStrafing then
        -- Find a target to strafe around
        local closestPlayer = findClosestTarget()

        if closestPlayer and closestPlayer.Character then
            target = closestPlayer.Character:FindFirstChild(CONFIG.TargetPart)
            notify("Target Strafe: Enabled on " .. closestPlayer.Name)
        else
            notify("Target Strafe: No valid target found.")
            isStrafing = false
        end
    else
        notify("Target Strafe: Disabled.")
        target = nil
    end
end

-- Update strafing motion
RunService.RenderStepped:Connect(function(deltaTime)
    if isStrafing and target and humanoidRootPart then
        -- Calculate new position based on circular motion
        currentAngle = currentAngle + CONFIG.StrafeSpeed * deltaTime
        local offsetX = math.cos(currentAngle) * CONFIG.StrafeRadius
        local offsetZ = math.sin(currentAngle) * CONFIG.StrafeRadius
        local targetPosition = target.Position + Vector3.new(offsetX, 0, offsetZ)

        -- Move character to calculated position
        humanoidRootPart.CFrame = CFrame.new(targetPosition, target.Position)
    end
end)

-- Keybind to toggle strafing
UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end

    if input.KeyCode == CONFIG.ToggleKey then
        toggleStrafing()
    end
end)

    end,
 })

 local Button = MainTab:CreateButton({
    Name = "camlock3",
    Callback = function()
    --[[
    === Config Section ===
    Adjust these values to customize the script.
--]]

local CONFIG = {
    ToggleKey = Enum.KeyCode.Q,      -- Key to toggle camlock
    TargetPart = "UpperTorso",       -- The part of the target to lock onto ("UpperTorso", "Head", etc.)
    SearchRadius = math.huge,        -- Maximum distance to search for a target
    FOV = 30,                        -- Field of View for targeting (degrees)
    PredictionFactor = 0.15,         -- Predictive aiming factor (adjust based on average ping)
    EnableNotifications = true       -- Show notifications in the output
}

--[[
    === Script Start ===
--]]

-- Services
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

-- Variables
local player = Players.LocalPlayer
local camera = workspace.CurrentCamera
local target = nil
local isCamLocked = false

-- Notify function
local function notify(message)
    if CONFIG.EnableNotifications then
        print(message)
    end
end

-- Function to toggle camlock
local function toggleCamlock()
    isCamLocked = not isCamLocked

    if isCamLocked then
        -- Find the closest player within the FOV
        local closestPlayer = nil
        local closestDistance = CONFIG.SearchRadius
        local smallestAngle = CONFIG.FOV

        for _, otherPlayer in pairs(Players:GetPlayers()) do
            if otherPlayer ~= player and otherPlayer.Character and otherPlayer.Character:FindFirstChild(CONFIG.TargetPart) then
                local part = otherPlayer.Character[CONFIG.TargetPart]
                local screenPoint, onScreen = camera:WorldToViewportPoint(part.Position)

                if onScreen then
                    local cameraDirection = camera.CFrame.LookVector
                    local targetDirection = (part.Position - camera.CFrame.Position).Unit
                    local angle = math.deg(math.acos(cameraDirection:Dot(targetDirection)))

                    if angle < smallestAngle then
                        local distance = (part.Position - player.Character.HumanoidRootPart.Position).Magnitude
                        if distance < closestDistance then
                            smallestAngle = angle
                            closestDistance = distance
                            closestPlayer = otherPlayer
                        end
                    end
                end
            end
        end

        -- Lock onto the closest player within the FOV
        if closestPlayer and closestPlayer.Character then
            target = closestPlayer.Character:FindFirstChild(CONFIG.TargetPart)
            notify("Camlock by Mars: Enabled on " .. closestPlayer.Name)
        else
            notify("Camlock by Mars: No valid target found within FOV.")
            isCamLocked = false
        end
    else
        -- Disable camlock
        target = nil
        notify("Camlock by Mars: Disabled.")
    end
end

-- Predictive aiming function
local function getPredictedPosition(part)
    if not part or not part.Parent then return part.Position end

    local humanoidRootPart = part.Parent:FindFirstChild("HumanoidRootPart")
    if humanoidRootPart and humanoidRootPart.Velocity then
        return part.Position + humanoidRootPart.Velocity * CONFIG.PredictionFactor
    else
        return part.Position
    end
end

-- Update camera position
RunService.RenderStepped:Connect(function()
    if isCamLocked and target then
        -- Predict the target's position based on their velocity
        local predictedPosition = getPredictedPosition(target)
        camera.CFrame = CFrame.new(camera.CFrame.Position, predictedPosition)
    end
end)

-- Keybind to toggle camlock
UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end

    if input.KeyCode == CONFIG.ToggleKey then
        toggleCamlock()
    end
end)

    end,
 })

 local Toggle = PlayerTab:CreateToggle({
    Name = "esp donsent follow very well sorry",
    CurrentValue = true,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
    --[[
    === Enhanced Smooth ESP Script ===
    Tracks players more accurately while retaining smooth visuals.
--]]

local CONFIG = {
    ESPColor = Color3.fromRGB(255, 0, 0), -- Color of the ESP box
    ESPThickness = 1,                    -- Thickness of the ESP box
    HighlightFriends = false,            -- Highlight friends differently
    FriendColor = Color3.fromRGB(0, 255, 0), -- Color for friends' ESP
    MaxDistance = 1000,                  -- Maximum distance for ESP visibility
    NameColor = Color3.fromRGB(255, 255, 255), -- Color of the player names
    NameSize = 16,                       -- Font size for player names
    UpdateInterval = 0.05,               -- Time (in seconds) between updates
    SmoothingFactor = 0.5,               -- Smoothing factor for interpolation (higher = slower)
    SnapThreshold = 5                    -- Threshold (in pixels) for snapping to precise position
}

-- Services
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local Camera = workspace.CurrentCamera
local LocalPlayer = Players.LocalPlayer

-- Variables
local ESPObjects = {}
local lastUpdate = 0

-- Create ESP objects (box and name)
local function createESP(player)
    local box = Drawing.new("Square")
    box.Visible = false
    box.Color = CONFIG.ESPColor
    box.Thickness = CONFIG.ESPThickness
    box.Filled = false

    local name = Drawing.new("Text")
    name.Visible = false
    name.Color = CONFIG.NameColor
    name.Size = CONFIG.NameSize
    name.Center = true
    name.Outline = true
    name.Text = player.Name

    ESPObjects[player] = {
        Box = box,
        Name = name,
        TargetPosition = nil, -- Target position for smooth movement
        CurrentPosition = nil -- Current position for interpolation
    }
end

-- Remove ESP objects
local function removeESP(player)
    if ESPObjects[player] then
        ESPObjects[player].Box:Remove()
        ESPObjects[player].Name:Remove()
        ESPObjects[player] = nil
    end
end

-- Interpolation function for smooth movement
local function lerp(current, target, alpha)
    return current + (target - current) * alpha
end

-- Update ESP objects
local function updateESP()
    local currentTime = tick()
    if currentTime - lastUpdate < CONFIG.UpdateInterval then
        return
    end
    lastUpdate = currentTime

    for player, objects in pairs(ESPObjects) do
        local character = player.Character
        local rootPart = character and character:FindFirstChild("HumanoidRootPart")
        local humanoid = character and character:FindFirstChildOfClass("Humanoid")

        if rootPart and humanoid and humanoid.Health > 0 then
            local distance = (LocalPlayer.Character.HumanoidRootPart.Position - rootPart.Position).Magnitude

            if distance <= CONFIG.MaxDistance then
                local screenPos, onScreen = Camera:WorldToViewportPoint(rootPart.Position)

                if onScreen then
                    local head = character:FindFirstChild("Head")
                    local leg = character:FindFirstChild("HumanoidRootPart")
                    if head and leg then
                        local headPos = Camera:WorldToViewportPoint(head.Position + Vector3.new(0, 0.5, 0))
                        local legPos = Camera:WorldToViewportPoint(leg.Position - Vector3.new(0, 2, 0))
                        local targetSize = Vector2.new(math.abs(headPos.X - legPos.X), math.abs(headPos.Y - legPos.Y))
                        local targetPosition = Vector2.new(headPos.X - targetSize.X / 2, headPos.Y)

                        -- Initialize current position
                        if not objects.CurrentPosition then
                            objects.CurrentPosition = targetPosition
                        end

                        -- Check if the difference is below the snap threshold
                        if (targetPosition - objects.CurrentPosition).Magnitude < CONFIG.SnapThreshold then
                            objects.CurrentPosition = targetPosition
                        else
                            -- Interpolate position for smoother following
                            objects.CurrentPosition = lerp(objects.CurrentPosition, targetPosition, CONFIG.SmoothingFactor)
                        end

                        -- Update box position and size
                        objects.Box.Size = targetSize
                        objects.Box.Position = objects.CurrentPosition
                        objects.Box.Visible = true

                        -- Update name position
                        local namePosition = Vector2.new(objects.CurrentPosition.X + targetSize.X / 2, objects.CurrentPosition.Y - 15)
                        objects.Name.Position = namePosition
                        objects.Name.Visible = true

                        -- Highlight friends if enabled
                        if CONFIG.HighlightFriends and Players:GetPlayerFromCharacter(character) then
                            objects.Box.Color = CONFIG.FriendColor
                            objects.Name.Color = CONFIG.FriendColor
                        else
                            objects.Box.Color = CONFIG.ESPColor
                            objects.Name.Color = CONFIG.NameColor
                        end
                    end
                else
                    objects.Box.Visible = false
                    objects.Name.Visible = false
                end
            else
                objects.Box.Visible = false
                objects.Name.Visible = false
            end
        else
            objects.Box.Visible = false
            objects.Name.Visible = false
        end
    end
end

-- Setup ESP for all players
local function setupESP()
    for _, player in ipairs(Players:GetPlayers()) do
        if player ~= LocalPlayer then
            createESP(player)
        end
    end
end

-- Clean up ESP on player removal
Players.PlayerRemoving:Connect(function(player)
    removeESP(player)
end)

-- Add ESP for new players
Players.PlayerAdded:Connect(function(player)
    if player ~= LocalPlayer then
        createESP(player)
    end
end)

-- Initialize
setupESP()

-- Update ESP with an interval
RunService.Heartbeat:Connect(updateESP)

    end,
 })

 
