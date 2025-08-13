print("AntiAfk Activated")
local VirtualUser=game:service'VirtualUser'
repeat
wait()
until game:GetService("Players").LocalPlayer ~= nil and game:GetService("Players").LocalPlayer.Idled ~= nil
game:GetService("Players").LocalPlayer.Idled:connect(function()
VirtualUser:CaptureController()
VirtualUser:ClickButton2(Vector2.new())
end)
_G.WhiteListed = true
if _G.WhiteListed then
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("IREN HUB | MADE BY IRENKISS", "DarkTheme", colors)

local Tab = Window:NewTab("Underrated Farm")
local Tab2 = Window:NewTab("Teleport/Server")
local Tab3 = Window:NewTab("Players/Kill")
local Tab4 = Window:NewTab("Weapon Spams")
local Tab5 = Window:NewTab("Fruit Farming")
local Tab6 = Window:NewTab("Auto Skill")
local Tab7 = Window:NewTab("Sam/Fruit")
local Tab8 = Window:NewTab("Drinks/Farming Stats")
local Tab9 = Window:NewTab("Misc")



local SkillSection = Tab6:NewSection("Auto Skill Devil Fruit 1")
local SkillSection2 = Tab6:NewSection("Auto SKill Devil Fruit 2")
local HakiSection = Tab:NewSection("Haki Farming")
local HakiSection2 = Tab:NewSection("Chest Farming")
local HakiSection3 = Tab:NewSection("Auto Farm Alt")
local WeaponSection3 = Tab4:NewSection("Get Fake Weapon")
local TPSection = Tab2:NewSection("Teleports/Check")
local SamSection = Tab7:NewSection("Sam Quests/Fruit and Compass Stealing")
local DrinkingSection = Tab8:NewSection("Drinks/Farming Stats")
local FFarmingSection = Tab5:NewSection("Light Fruit")
local FFarmingSection2 = Tab5:NewSection("Quake Fruit")
local FFarmingSection3 = Tab5:NewSection("Mob Bring")
local KPSection = Tab3:NewSection("Players")
local KPSection2 = Tab3:NewSection("Quake Fruit")
local KPSection3 = Tab3:NewSection("Light Fruit")
local MiscSection = Tab9:NewSection("Random Stuff")
local WeaponSection1 = Tab4:NewSection("Yoru")
local WeaponSection2 = Tab4:NewSection("Seastone Cestus")
local TPSection2 = Tab2:NewSection("Server")

local Settings = Window:NewTab("Settings")
local SettingsSection = Settings:NewSection("Settings")
local ColorSection = Settings:NewSection("Ui Color")
local PLRS = {}
for i,v in pairs(game:GetService("Players"):GetChildren()) do
table.insert(PLRS,v.Name)
end

----------------------------------- Weapon Spams
WeaponSection1:NewSlider("Yoru Speed", "Increase/Decrease", 200, 1, function(s) -- 200 (MaxValue) | 0 (MinValue)
Speed = s
end)

WeaponSection1:NewToggle("Yoru Spam", "Spams Yoru m1", function(state)
if state then
    _G.Yoru = true
    local Players = game:GetService("Players")
    local Plr = Players.LocalPlayer
    local Character = Plr.Character
    local Yoru = Character:FindFirstChild("Yoru")
    local Environment
while _G.Yoru do
wait()
pcall(function()
for i,v in pairs(getconnections(Yoru["RequestAnimation"].OnClientEvent)) do 
    Environment = getsenv(Yoru["AnimationController"])
end
    wait()
for i = 1, Speed do
Yoru["RequestAnimation"]:FireServer(Environment.PlaceId)
end
end)
wait()
end
else
    _G.Yoru = false
end
end)

WeaponSection2:NewSlider("Seastone Speed", "Increase/Decrease", 200, 1, function(ss) -- 200 (MaxValue) | 0 (MinValue)
Speed2 = ss
end)

WeaponSection2:NewToggle("Seastone Spam", "Spams Seastone Cestus", function(state)
if state then
    _G.Cestus = true
    local Players = game:GetService("Players")
    local Plr = Players.LocalPlayer
    local Character = Plr.Character
    local Cestus = Character:FindFirstChild("Seastone Cestus")
    local Environment
while _G.Cestus do
wait()
pcall(function()
for i,v in pairs(getconnections(Cestus["RequestAnimation"].OnClientEvent)) do 
    Environment = getsenv(Cestus["AnimationController"])
end
    wait()
for i = 1, Speed2 do
Cestus["RequestAnimation"]:FireServer(Environment.PlaceId)
end
end)
end
else
    _G.Cestus = false
end
end)
----------------------------------- Misc

MiscSection:NewToggle("Anti Stun", "Remove Disable,Heart,Hobby,Chilly,Candy,Hollow,Ope,Snow,Rumble,Gra", false, function(bool)
        getgenv().antistun = bool
        while getgenv().antistun do wait()
            pcall(function()
                local hoangashdeptrai = game.Players.LocalPlayer.Character
    repeat
    hoangashdeptrai["DF_Disabled"].Value = false
    hoangashdeptrai.HeartStolen.Value = true
    hoangashdeptrai.Returned.Value = false
    hoangashdeptrai.Hobbied.Value = false
    hoangashdeptrai.HMS.Value = false
    hoangashdeptrai.ChillyPunched.Value = false
    hoangashdeptrai.CandyTouched.Value = false
    hoangashdeptrai.Negative.Value = false
    hoangashdeptrai.OpeSevered.Value = false
    hoangashdeptrai.SnowTouched.Value = false
    hoangashdeptrai.RumbleStun.Value = false
    hoangashdeptrai.GravityCrushed.Value = false
    wait(0.06)
    until hoangashdeptrai.Humanoid.Health == 0
    end)
    end
    end)

MiscSection:NewButton("Anti-staff", "Kicks if a staff is in server or joins server", function()
local Pedo = {
    1135910299,520944,43247021,2350183594
}

for _, v in pairs(game:GetService("Players"):GetPlayers()) do
    for _, v1 in pairs(Pedo) do
        if v.UserId == v1 then
            game:GetService("Players").LocalPlayer:Kick("Admin is in the server")
        end
    end
end

game:GetService("Players").PlayerAdded:Connect(function(r)
    for _, v in pairs(Pedo) do
        if r.UserId == v then
            game:GetService("Players").LocalPlayer:Kick("Admin has joined the server")
        end
    end
end)
end)

MiscSection:NewButton("Expertise GUI", "Shows the Expertise GUI", function()
for i,v in pairs(game:GetService("Workspace").Merchants.ExpertiseMerchant:GetDescendants()) do
if v:IsA("ClickDetector") then
fireclickdetector(v)
end
end
end)

MiscSection:NewButton("Affinity Gui", "Shows the affinity diviners gui so u can spin", function()
for i,v in pairs(game:GetService("Workspace").Merchants.AffinityMerchant:GetDescendants()) do
if v:IsA("ClickDetector") then
fireclickdetector(v)
end
end
end)

MiscSection:NewDropdown("Present", "Collect Chosen presents", {"Hourly Presents", "Daily Presents"}, function(AnF)
ChosenOne = AnF
end)

MiscSection:NewTextBox("Present Amount", "Collects presents", function(text)
local plrid = tostring(game.Players.LocalPlayer.UserId)
for i = 1,(text) do
if ChosenOne == "Hourly Presents" then
wait()
workspace.UserData["User_"..plrid].ClaimRewardHourly:FireServer("RewardMark")
end
if ChosenOne == "Daily Presents" then
    workspace.UserData["User_"..plrid].ClaimRewardDaily:FireServer("RewardMark")
end
end
end)

MiscSection:NewButton("PlayerMenu", "Turn on emotes tab to see", function()
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Visible = true
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.BanId.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.OfflineBan.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Ban.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.JoinId.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec["OfflineBan_Text"].Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec["Ban_Text"].Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec["BanId_Text"].Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec["Join_Text"].Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Join.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec["JoinId_Text"].Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Template.Frame.E.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Template.Frame.A.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Template.Frame.B.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Template.Frame.D.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Template.Frame.C.Visible = false
game:GetService("Players").LocalPlayer.PlayerGui.Emotes.Frame.Spec.Template.Frame.E2.Visible = false
end)

MiscSection:NewButton("Emotes", "Gives emotes you also have to press it in each server", function()
local plrid = tostring(game.Players.LocalPlayer.UserId)
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark1.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark2.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark3.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark4.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark5.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark6.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark7.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark8.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark9.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark10.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark11.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark12.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark13.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark14.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark15.Value = true
Game.Workspace.UserData["User_"..plrid].Data.CB_Mark16.Value = true
end)

----------------------------------- Kill Players
local dropdown =  KPSection:NewDropdown("Select Player", "", PLRS, function(f)
Choose = f
Choose2 = f
end)

KPSection:NewButton("Refresh PLR List", "Refreshes Dropdown", function(aa)
local PLRS = {}
for i,v in pairs(game:GetService("Players"):GetChildren()) do
table.insert(PLRS,v.Name)
end
dropdown:Refresh(PLRS)
end)

KPSection:NewButton("View Player", "Views selected player", function()
for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
if v.Name == Choose then
game.Workspace.Camera.CameraSubject = v.Humanoid
end
end
end)

KPSection:NewButton("Teleport", "Teleports you to selected player", function()
for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
if v.Name == Choose then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
end
end
end)

KPSection:NewToggle("Esp Player",false,function(ESP)
        
            ESPPlayer = ESP
            while ESPPlayer do wait()
                UpdatePlayerChams()
            end
        
        end)
            spawn(function()
            while wait() do
                if KillPlayer then
                    game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.CFrame * CFrame.new(0,0,distance)
                    game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Size = Vector3.new(60,60,60)
                    game:GetService'VirtualUser':CaptureController()
                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                end
            end
        end)
        spawn(function()
            while wait() do
                if _G.BringPlayer then
                    pcall(function()
                        game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-3)
                    end)
                end
            end
        end)
        function isnil(thing)
            return (thing == nil)
        end
        local function round(n)
            return math.floor(tonumber(n) + 0.5)
        end
        Number = math.random(1, 1000000)
        function UpdatePlayerChams()
            for i,v in pairs(game:GetService'Players':GetChildren()) do
                pcall(function()
                    if not isnil(v.Character) then
                        if ESPPlayer then
                            if not isnil(v.Character.Head) and not v.Character.Head:FindFirstChild('NameEsp'..Number) then
                                local bill = Instance.new('BillboardGui',v.Character.Head)
                                bill.Name = 'NameEsp'..Number
                                bill.ExtentsOffset = Vector3.new(0, 1, 0)
                                bill.Size = UDim2.new(1,200,1,30)
                                bill.Adornee = v.Character.Head
                                bill.AlwaysOnTop = true
                                local name = Instance.new('TextLabel',bill)
                                name.Font = "SourceSansBold"
                                name.FontSize = "Size14"
                                name.TextWrapped = true
                                name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
                                name.Size = UDim2.new(1,0,1,0)
                                name.TextYAlignment = 'Top'
                                name.BackgroundTransparency = 1
                                name.TextStrokeTransparency = 0.5
                                if v.Team == game.Players.LocalPlayer.Team then
                                    name.TextColor3 = Color3.new(0, 254, 252)
                                else
                                    name.TextColor3 = Color3.new(0, 254, 252)
                                end
                            else
                                v.Character.Head['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
                            end
                        else
                            if v.Character.Head:FindFirstChild('NameEsp'..Number) then
                                v.Character.Head:FindFirstChild('NameEsp'..Number):Destroy()
                            end
                        end
                    end
                end)
            end
        end
KPSection3:NewToggle("Light Camp" , "Kills Player", function(state)
if state then
_G.AutoLight = true
local x = getsenv(game:GetService("Players").LocalPlayer.Character.Powers.Light)
local vp = x.VTCrv
while _G.AutoLight do
    wait(0.00000001)
    for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
        if v.Name == Choose2 then
            game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(vp,"LightPower2", "StopCharging",v.HumanoidRootPart.CFrame,workspace.IslandCaver.Stones.Stone, 100)
        end
        end
 end
else
    _G.AutoLight = false
 end
end)

KPSection2:NewToggle("Quake Camp" , "Kills Player", function(state)
if state then
_G.AutoQuake = true
local x = getsenv(game:GetService("Players").LocalPlayer.Character.Powers.Quake)
local vp = x.VTCebvc
while _G.AutoQuake do
    wait(0.00000001)
    pcall(function()
    for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
        if v.Name == Choose2 then
            game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(vp,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,v.HumanoidRootPart.CFrame,100,Vector3.new(-290.4129333496094, 266.8401794433594, -103.8988037109375))
        end
    end
    end)
    end
else
    _G.AutoQuake = false
end
end)
----------------------------------- FruitFarming
FFarmingSection2:NewToggle("Quake Farm" , "Kills every NPCS", function(state)  --Quake
if state then
_G.AutoQuake = true
local x = getsenv(game:GetService("Players").LocalPlayer.Character.Powers.Quake)
local v = x.VTCebvc
while _G.AutoQuake do
wait(0)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1848.4346923828125, 222, -450.0833740234375), Vector3.new(-0.5347824096679688, -0.43560168147087097, -0.7240573167800903)),100,Vector3.new(-1848.4346923828125, 222, -450.0833740234375), Vector3.new(-0.5347824096679688, -0.43560168147087097, -0.7240573167800903))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1898.96728515625, 225.03367614746094, -200.6829071044922), Vector3.new(-0.9484627842903137, -0.18392488360404968, 0.25805023312568665)),100,Vector3.new(-1898.96728515625, 225.03367614746094, -200.6829071044922), Vector3.new(-0.9484627842903137, -0.18392488360404968, 0.25805023312568665))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1749.58203125, 224.88922119140625, -134.49240112304688), Vector3.new(-0.6882264614105225, -0.40487319231033325, 0.6020150184631348)),100,Vector3.new(-1749.58203125, 224.88922119140625, -134.49240112304688), Vector3.new(-0.6882264614105225, -0.40487319231033325, 0.6020150184631348))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1622.5482177734375, 225.85337829589844, -200.26828002929688), Vector3.new(-0.3189719319343567, -0.7127735018730164, 0.6246685981750488)),100,Vector3.new(-1622.5482177734375, 225.85337829589844, -200.26828002929688), Vector3.new(-0.3189719319343567, -0.7127735018730164, 0.6246685981750488))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(1002.1565551757812, 214, 3349.3857421875), Vector3.new(-0.2978745698928833, -0.6442758440971375, 0.7044001221656799)),100,Vector3.new(1002.1565551757812, 214, 3349.3857421875), Vector3.new(-0.2978745698928833, -0.6442758440971375, 0.7044001221656799))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(2167.46923828125, 213, -631.9636840820312), Vector3.new(0.6589730978012085, -0.6376858949661255, -0.3988874852657318)),100,Vector3.new(2167.46923828125, 213, -631.9636840820312), Vector3.new(0.6589730978012085, -0.6376858949661255, -0.3988874852657318))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(1178.6993408203125, 212.26193237304688, -263.04681396484375), Vector3.new(0.04516664147377014, -0.9571055173873901, 0.28619781136512756)),100,Vector3.new(1178.6993408203125, 212.26193237304688, -263.04681396484375), Vector3.new(0.04516664147377014, -0.9571055173873901, 0.28619781136512756))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1040.117919921875, 215, 1662.1202392578125), Vector3.new(0.9582481980323792, -0.13812202215194702, 0.2503652274608612)), 100,Vector3.new(-1040.117919921875, 215, 1662.1202392578125), Vector3.new(0.9582481980323792, -0.13812202215194702, 0.2503652274608612))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-988.4560546875, 283, 1616.5068359375), Vector3.new(-0.44781866669654846, -0.36267393827438354, 0.8172675371170044)), 100,Vector3.new(-988.4560546875, 283, 1616.5068359375), Vector3.new(-0.44781866669654846, -0.36267393827438354, 0.8172675371170044))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1037.58544921875, 215.7229461669922, 1508.449951171875), Vector3.new(-0.7139230966567993, -0.5779988169670105, 0.39526084065437317)),100,Vector3.new(-1037.58544921875, 215.7229461669922, 1508.449951171875), Vector3.new(-0.7139230966567993, -0.5779988169670105, 0.39526084065437317))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-908.2176513671875, 214, 1621.364990234375), Vector3.new(-0.21460314095020294, -0.40479180216789246, 0.88886958360672)),100,Vector3.new(-908.2176513671875, 214, 1621.364990234375), Vector3.new(-0.21460314095020294, -0.40479180216789246, 0.88886958360672))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-248.8604736328125, 273.4266052246094, 355.64453125), Vector3.new(0.6645273566246033, -0.5016912817955017, -0.5538134574890137)),100,Vector3.new(-248.8604736328125, 273.4266052246094, 355.64453125), Vector3.new(0.6645273566246033, -0.5016912817955017, -0.5538134574890137))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-319.3795471191406, 272.3931884765625, 388.7362060546875), Vector3.new(0.5347911715507507, -0.7442643046379089, -0.40008631348609924)),100,Vector3.new(-319.3795471191406, 272.3931884765625, 388.7362060546875), Vector3.new(0.5347911715507507, -0.7442643046379089, -0.40008631348609924))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-315.74334716796875, 270.4518737792969, 307.21185302734375), Vector3.new(0.4924789369106293, -0.6783868670463562, -0.5452118515968323)),100,Vector3.new(-315.74334716796875, 270.4518737792969, 307.21185302734375), Vector3.new(0.4924789369106293, -0.6783868670463562, -0.5452118515968323))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-178.00997924804688, 272.4919128417969, 390.1238708496094), Vector3.new(0.6851771473884583, -0.678036093711853, -0.26608139276504517)),100,Vector3.new(-178.00997924804688, 272.4919128417969, 390.1238708496094), Vector3.new(0.6851771473884583, -0.678036093711853, -0.26608139276504517))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-159.9521026611328, 269.81768798828125, 312.1455993652344), Vector3.new(0.6065837144851685, -0.7200759649276733, -0.33696722984313965)),100,Vector3.new(-159.9521026611328, 269.81768798828125, 312.1455993652344), Vector3.new(0.6065837144851685, -0.7200759649276733, -0.33696722984313965))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(89.97474670410156, 299.3000183105469, -936.1035766601562), Vector3.new(0.2870140075683594, -0.6174480319023132, -0.7323803305625916)),100,Vector3.new(89.97474670410156, 299.3000183105469, -936.1035766601562), Vector3.new(0.2870140075683594, -0.6174480319023132, -0.7323803305625916))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1169.5670166015625, 219.90908813476562, -1588.0274658203125), Vector3.new(0.015137090347707272, -0.6970996260643005, -0.7168144583702087)),100,Vector3.new(-1169.5670166015625, 219.90908813476562, -1588.0274658203125), Vector3.new(0.015137090347707272, -0.6970996260643005, -0.7168144583702087))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1201.4923095703125, 254.11367797851562, -1660.2674560546875), Vector3.new(0.04675392061471939, -0.6955714225769043, -0.7169341444969177)),100,Vector3.new(-1201.4923095703125, 254.11367797851562, -1660.2674560546875), Vector3.new(0.04675392061471939, -0.6955714225769043, -0.7169341444969177))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1288.0887451171875, 245.90695190429688, -1653.00537109375), Vector3.new(0.025024037808179855, -0.7537118196487427, -0.6567284464836121)),100,Vector3.new(-1288.0887451171875, 245.90695190429688, -1653.00537109375))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1339.789306640625, 245.81817626953125, -1634.641845703125), Vector3.new(0.07458476722240448, -0.6587507128715515, -0.7486552596092224)),100,Vector3.new(-1339.789306640625, 245.81817626953125, -1634.641845703125), Vector3.new(0.07458476722240448, -0.6587507128715515, -0.7486552596092224))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1432.3958740234375, 256.3514709472656, -1652.33984375), Vector3.new(0.007446270436048508, -0.6148971319198608, -0.7885722517967224)),100,Vector3.new(-1432.3958740234375, 256.3514709472656, -1652.33984375), Vector3.new(0.007446270436048508, -0.6148971319198608, -0.7885722517967224))
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Quake.RemoteEvent:FireServer(v,"QuakePower4", "StopCharging",workspace.IslandCaver.Stones.Stone,CFrame.new(Vector3.new(-1270.039794921875, 263.09088134765625, -1793.016357421875), Vector3.new(0.32165566086769104, -0.4306340515613556, -0.8432627320289612)),100,Vector3.new(-1270.039794921875, 263.09088134765625, -1793.016357421875), Vector3.new(0.32165566086769104, -0.4306340515613556, -0.8432627320289612))
wait(0.1)
end
else
_G.AutoQuake = false
end
end)

FFarmingSection:NewToggle("Light Farm" , "Kills a few NPCS", function(state)  --Light
if state then
local x = getsenv(game:GetService("Players").LocalPlayer.Character.Powers.Light)
local v = x.VTCrv
_G.Light = true
while _G.Light do 
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-988.4560546875, 283, 1616.5068359375), Vector3.new(-0.44781866669654846, -0.36267393827438354, 0.8172675371170044)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-1037.58544921875, 215.7229461669922, 1508.449951171875), Vector3.new(-0.7139230966567993, -0.5779988169670105, 0.39526084065437317)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-908.2176513671875, 214, 1621.364990234375), Vector3.new(-0.21460314095020294, -0.40479180216789246, 0.88886958360672)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-248.8604736328125, 273.4266052246094, 355.64453125), Vector3.new(0.6645273566246033, -0.5016912817955017, -0.5538134574890137)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-319.3795471191406, 272.3931884765625, 388.7362060546875), Vector3.new(0.5347911715507507, -0.7442643046379089, -0.40008631348609924)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-315.74334716796875, 270.4518737792969, 307.21185302734375), Vector3.new(0.4924789369106293, -0.6783868670463562, -0.5452118515968323)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-178.00997924804688, 272.4919128417969, 390.1238708496094), Vector3.new(0.6851771473884583, -0.678036093711853, -0.26608139276504517)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-159.9521026611328, 269.81768798828125, 312.1455993652344), Vector3.new(0.6065837144851685, -0.7200759649276733, -0.33696722984313965)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(89.97474670410156, 299.3000183105469, -936.1035766601562), Vector3.new(0.2870140075683594, -0.6174480319023132, -0.7323803305625916)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-1169.5670166015625, 219.90908813476562, -1588.0274658203125), Vector3.new(0.015137090347707272, -0.6970996260643005, -0.7168144583702087)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-1201.4923095703125, 254.11367797851562, -1660.2674560546875), Vector3.new(0.04675392061471939, -0.6955714225769043, -0.7169341444969177)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-1288.0887451171875, 245.90695190429688, -1653.00537109375), Vector3.new(0.025024037808179855, -0.7537118196487427, -0.6567284464836121)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-1339.789306640625, 245.81817626953125, -1634.641845703125), Vector3.new(0.07458476722240448, -0.6587507128715515, -0.7486552596092224)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-1432.3958740234375, 256.3514709472656, -1652.33984375), Vector3.new(0.007446270436048508, -0.6148971319198608, -0.7885722517967224)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Powers.Light.RemoteEvent:FireServer(v,"LightPower2", "StopCharging",CFrame.new(Vector3.new(-1270.039794921875, 263.09088134765625, -1793.016357421875), Vector3.new(0.32165566086769104, -0.4306340515613556, -0.8432627320289612)),workspace.IslandCaver.Stones.Stone, 100)
wait(0.1)
end
else
_G.Light = false
end
end)
FFarmingSection:NewToggle("Tp To Afk LightFarm" , "Teleport You To Light Farm Spot", function(state)
if state then
_G.TeleLight = true
while _G.TeleLight do
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(100, 3000, 800)
wait(0.1)
end
else
_G.TeleLight = false
end
end)

FFarmingSection3:NewSlider("Distance", "Increase/Decrease", 50, 1, function(to) -- 50 (MaxValue) | 0 (MinValue)
Distance1 = to
end)
FFarmingSection3:NewToggle("Bring All Mob","nil",false,function(state)
if state then
_G.BringMob = true
while _G.BringMob do
    game:GetService("Workspace").Enemies["Lv8000 Gunner Captain"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv500 Bucky"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv440 Buster"].HumanoidRootPart.CFrame= CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv360 Bruno"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv32 Fredric"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv28 Friedrich"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv36 Gunslinger"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv14 Bandit"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv15 Bandit"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv14 Boar"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv29 Frued"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv22 Thug"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv34 Freddi"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv17 Thug"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv24 Gunslinger"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv35 Angry Bobb"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv50 Gunslinger"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv9 Bandit"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv24 Fred"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv4 Freddy"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv11 Boar"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv28 Fredde"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv40 Cave Demon"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv4 Boar"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv24 Thug"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game:GetService("Workspace").Enemies["Lv30 Thug"].HumanoidRootPart.CFrame = CFrame.new(6654, 418, -1468)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(6670, 418, -1468)
    wait(0.1)
    end
    else
    _G.BringMob = false
    end
    end)
    
----------------------------------- Drinks/Barrel Farming
DrinkingSection:NewDropdown("The Drink", "Buys chosen drinks", {"Cider+", "Lemonade+", "Juice+", "Smoothie+"}, function(An)
Choice = An
end)

DrinkingSection:NewTextBox("Drink Amount", "Makes you buy drinks", function(text)
for i = 1,(text) do
    wait(0.1)
    game.Workspace.Merchants.BetterDrinkMerchant.Clickable.Retum:FireServer(Choice)
    end
end)

DrinkingSection:NewToggle("Auto Drink", "Auto Drinks juices", function(state)
if state then
    _G.Using = true
while _G.Using do
wait(0.5)  
pcall(function()
local Players = game:GetService("Players")
local Lp = Players.LocalPlayer
local Character = Lp.Character or Lp.CharacterAdded:Wait()
local Humanoid = Character.Humanoid
local user = tostring(game.Players.LocalPlayer.Name)
for i,v in pairs(Lp.Backpack:GetChildren()) do 
if v:IsA("Tool") and string.find(v.Name, "Juice") or string.find(v.Name, "Cider") or string.find(v.Name, "Milk")  or string.find(v.Name, "+")  or string.find(v.Name, "Smoothie") or string.find(v.Name, "Lemonade") or string.find(v.Name, "Golden") then  
    Humanoid:EquipTool(v)
    v:Activate()
    wait()
end 
end 
end)
end
else
    _G.Using = false
end
end)

DrinkingSection:NewToggle("Auto Barrels", "Auto clicks all barrels", function(state)
if state then
     _G.AutoMixer = true
local user = tostring(game.Players.LocalPlayer.Name)
local StoredLocation = game.workspace[""..user].HumanoidRootPart.CFrame 

spawn(function()
local plrid = tostring(game.Players.LocalPlayer.UserId)
local plr = tostring(game.Players.LocalPlayer)
while _G.AutoMixer do
wait()
pcall(function()
repeat task.wait() until game.Players[""..plr].PlayerGui.Challenges.Frame.Frame.ChallengesFrame.ScrollingFrame["Challenge_13"].Claim.AutoButtonColor == true
workspace.UserData["User_"..plrid].ChallengesRemote:FireServer("Claim","Challenge13")
workspace.UserData["User_"..plrid].ChallengesRemote:FireServer("Claim","Challenge14")
end)
end
end)

function amongus()
for i,v in pairs(game:GetService("Workspace").Barrels:GetDescendants()) do
if v:IsA("ClickDetector") then
fireclickdetector(v)
end
end
for i,v in pairs(game:GetService("Workspace").Island8.Kitchen:GetDescendants()) do
if v:IsA("ClickDetector") then
fireclickdetector(v)
end
end
end

while _G.AutoMixer do
pcall(function()
for i,v in pairs(game:GetService("Workspace").Barrels.Barrels:GetDescendants()) do
if v.Name == "Barrel" then
game.workspace[""..user].HumanoidRootPart.CFrame = v.CFrame + Vector3.new(0, 5, 0)
amongus()
wait(0.1)
end
end
for i,v in pairs(game:GetService("Workspace").Barrels:GetDescendants()) do
if v.Name == "Crate" then
game.workspace[""..user].HumanoidRootPart.CFrame = v.CFrame + Vector3.new(0, 5, 0)
amongus()
wait(0.1)
end
end
game.workspace[""..user].HumanoidRootPart.CFrame = StoredLocation
end)
wait(15)
end
else
   _G.AutoMixer = false
end
end)

----------------------------------- Sam
SamSection:NewButton("Collect all compass's", "Collects all compass's", function()
workspace.Merchants.QuestMerchant.Clickable.Retum:FireServer("Claim10")
end)

SamSection:NewButton("Collect one compass", "Collects single compass", function()
workspace.Merchants.QuestMerchant.Clickable.Retum:FireServer("Claim1")
end)


SamSection:NewToggle("Compass Destination", "Tp's you to your compass destination", function(state)
if state then
    _G.Destination = true
while _G.Destination do 
task.wait(0.2)        
local user = tostring(game.Players.LocalPlayer.Name)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(game:GetService("Players")[""..user].Backpack.Compass.Poser.Value)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")[""..user].Compass.Power.Value
 end
else
    _G.Destination = false
end
end)

SamSection:NewToggle("Compass Stealing", "Steals a compass if dropped", function(state)

if state then
_G.CompassSteal = true
local plr=game:GetService'Players'.LocalPlayer              --compass stealing
local find='Compass' 
while _G.Compass do
local char=plr.Character or plr.CharacterAdded:Wait()
local HRP=char:WaitForChild'HumanoidRootPart'
for i,v in next, workspace:GetChildren() do
local Handle=v:FindFirstChild'Handle'
if v:IsA'Tool' and string.find(v.Name:lower(), find:lower()) and Handle then
Handle.CFrame=HRP.CFrame
end
end
wait()
end
else
_G.CompassSteal = false
end
end)
SamSection:NewToggle("TpFruit", "Tps fruits", function(state)
if state then
 _G.Tpfruit = true
while _G.Tpfruit do
 task.wait()
for i,v in pairs(game:GetService("Workspace").Trees.Tree:GetDescendants()) do
if v:IsA("ClickDetector") then
fireclickdetector(v)
end
end
end    
else
    _G.Tpfruit = false
end
end) 

----------------------------------- Haki Scripts
HakiSection2:NewToggle("Collect Chest", "Collect All Chests In Server, Really Lag", function(bool)
            getgenv().autochest = bool
            while getgenv().autochest do wait()
                pcall(function()
    local apis = game.workspace:GetDescendants()
    for i, v in pairs(apis) do
    if v.Name == "Touch" and v.Parent.Name == "TreasureChestPart" then
    v.Parent.CFrame = game.workspace[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame
    end
    end
    end)
    end
    end)
HakiSection:NewToggle("Haki Drain", false, function(bool)
            getgenv().autohaki = bool
    function hakiauto()
       local Players = game:GetService("Players")
    local cache = {}
    function lol(name)
        if cache[name] then return cache[name] end
        local player = Players:FindFirstChild(name)
        if player then
            cache[name] = player.UserId
            return player.UserId
        end 
    
        local id
        pcall(function ()
            id = Players:lol(name)
        end)
        cache[name] = id
        return id
    end
    local ehh = game.Players.LocalPlayer.Name
    local Final = lol(ehh)
    
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "Off",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    local args = {
        [1] = "On",
        [2] = 1
    }
    
    workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    
    
    
    end
    while getgenv().autohaki do wait(0)
        hakiauto()
    end
    end)
HakiSection:NewDropdown("Haki Farm", "1.2.2 then loop (1.1.2.2.2)", {"Haki 1", "Haki 2"}, function(hakiOption)
if hakiOption == "Haki 1" then
for i = 1,5 do
    local Players = game:GetService("Players")
    local cache = {}
    function lol(name)
        if cache[name] then return cache[name] end
        local player = Players:FindFirstChild(name)
        if player then
            cache[name] = player.UserId
            return player.UserId
        end 
    
        local id
        pcall(function ()
            id = Players:lol(name)
        end)
        cache[name] = id
        return id
    end
    local ehh = game.Players.LocalPlayer.Name
    local Final = lol(ehh)
    _G.swim = true
    
    while _G.swim do
    wait(0) do
    local args = {
        [1] = "On",
        [2] = 1
    }
    game.Workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    end
    end
    end
    end
if hakiOption == "Haki 2" then
for i = 1,5 do
    local Players = game:GetService("Players")
    local cache = {}
    function lol(name)
        if cache[name] then return cache[name] end
        local player = Players:FindFirstChild(name)
        if player then
            cache[name] = player.UserId
            return player.UserId
        end 
    
        local id
        pcall(function ()
            id = Players:lol(name)
        end)
        cache[name] = id
        return id
    end
    local ehh = game.Players.LocalPlayer.Name
    local Final = lol(ehh)
    _G.swim = true
    
    while _G.swim do
    wait(0) do
    local args = {
        [1] = "Off",
        [2] = 1
    }
    game.Workspace.UserData["User_"..Final].III:FireServer(unpack(args))
    end
    end
    end
    end
       end
    )
    
    WeaponSection3:NewButton("Seastone Cestus", "Get Seastone Cestus Fake", function()
    local Players = game:GetService("Players")
    local cache = {}
    function lol(name)
        if cache[name] then return cache[name] end
        local player = Players:FindFirstChild(name)
        if player then
            cache[name] = player.UserId
            return player.UserId
        end 
    
        local id
        pcall(function ()
            id = Players:lol(name)
        end)
        cache[name] = id
        return id
    end
    local ehh = game.Players.LocalPlayer.Name
    local Final = lol(ehh)
    local A_1 = "Seastone Cestus"
    local Event = game:GetService("Workspace").UserData["User_"..Final].UpdateMelee
    Event:FireServer(A_1)
    end)
WeaponSection3:NewButton("Aqua Staff", "Get Aqua Staff", function()
   local Players = game:GetService("Players")
    local cache = {}
    function lol(name)
        if cache[name] then return cache[name] end
        local player = Players:FindFirstChild(name)
        if player then
            cache[name] = player.UserId
            return player.UserId
        end 
    
        local id
        pcall(function ()
            id = Players:lol(name)
        end)
        cache[name] = id
        return id
    end
    local ehh = game.Players.LocalPlayer.Name
    local Final = lol(ehh)
    local A_1 = "Aqua Staff"
    local Event = game:GetService("Workspace").UserData["User_"..Final].UpdateMelee
    Event:FireServer(A_1)
    end)
----------------------------------- Teleports
TPSection:NewDropdown("Island Teleports", "Teleports you to chosen island", {"Windmill", "Race Track" , "Bar" ,"Cave", "Marine Fort" ,"Sam", "Krizma", "Cannon Dealer Island" , "Expertise", "Mansion" , "Trees Island" , "Dead Mountain", "Pyramid", "Snow Mountain", "Little Snow Island", "Vokun", "Kaizu", "Purple", "Pursuer", "Safe Place"}, function(currentOption)
if currentOption == "Expertise" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(902.105103, 282.199921, 1219.1825, 0.000111424371, -4.80737405e-08, 1, -5.58505509e-09, 1, 4.80743623e-08, -1, -5.59041169e-09, 0.000111424371)
end

if currentOption == "Krizma" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1074.2793, 360.999908, 1687.67566, 0.998138607, -2.49312624e-08, 0.0609866381, 1.98675316e-08, 1, 8.3636543e-08, -0.0609866381, -8.22692101e-08, 0.998138607)
   end

if currentOption == "Windmill" then
    for i,v in pairs(game.Workspace.IslandWindmill:GetDescendants()) do
        if v.Name == "Part" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
        end
        end    end  

if currentOption == "Cave" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(76.3779144, 299.999908, -916.032043, 0.0174713228, -3.14204591e-08, 0.999847353, 5.21297814e-08, 1, 3.05143395e-08, -0.999847353, 5.15886995e-08, 0.0174713228)
end

if currentOption == "SandCastle" then
    for i,v in pairs(game.Workspace.IslandSandCastle:GetDescendants()) do
        if v.Name == "Part" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
        end
        end    end
  
if currentOption == "Sam" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1298.30603, 217.999954, -1352.47571, 0.017669782, -1.08078257e-08, 0.999843895, -7.31044647e-09, 1, 1.09387068e-08, -0.999843895, -7.50258966e-09, 0.017669782)
end

if currentOption == "Mansion" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1818.72119, 218, 881.086304, 0.707021296, 6.48462928e-09, -0.707192302, -5.54870603e-08, 1, -4.63041019e-08, 0.707192302, 7.19780076e-08, 0.707021296)
end

if currentOption == "Dead Mountain" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2053.56348, 491.999908, -603.457642, 0.999845803, -6.42047766e-08, -0.0175616108, 6.59244677e-08, 1, 9.73443264e-08, 0.0175616108, -9.84870496e-08, 0.999845803)
end

if currentOption == "Cannon Dealer Island" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2606.74414, 269.599915, 1098.1311, 0.0525588207, -5.60069324e-09, 0.998617828, -1.80996815e-10, 1, 5.61797142e-09, -0.998617828, -4.76020612e-10, 0.0525588207)
end

if currentOption == "Race Track" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6056.94434, 217.643265, 3332.71924, -0.824234724, -3.06996917e-08, -0.566248238, -9.82805215e-09, 1, -3.991018e-08, 0.566248238, -2.73302394e-08, -0.824234724)
end
  
if currentOption == "Little Snow Island" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1897.03699, 224.999954, 3295.97852, 0.422415107, -1.19760401e-07, -0.906402469, 5.81015094e-08, 1, -1.05049857e-07, 0.906402469, -8.28870661e-09, 0.422415107)
end

if currentOption == "Pyramid" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(117.47625, 277.999908, 4948.05713, -0.688197017, 3.47416451e-09, 0.725523829, -6.7682937e-10, 1, -5.43049916e-09, -0.725523829, -4.22830926e-09, -0.688197017)
end

if currentOption == "Snow Mountain" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(6640.6499, 417.998901, -1478.11169, -0.294113189, 6.32640322e-08, -0.955770612, 2.0722144e-08, 1, 5.98149583e-08, 0.955770612, -2.21324803e-09, -0.294113189)
end

if currentOption == "Marine Fort" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3134.58325, 275.799927, -3652.50513, 0.99999994, -9.04243613e-09, -0.000312123768, 9.0418677e-09, 1, -1.82297777e-09, 0.000312123768, 1.82015547e-09, 0.99999994)
end

if currentOption == "Purple" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5285.72803, 515.999817, -7745.1543, -0.999651134, 6.1504144e-09, 0.0264117159, 3.64631259e-09, 1, -9.48584287e-08, -0.0264117159, -9.47290317e-08, -0.999651134)
end

if currentOption == "Bar" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1521.71997, 260.38623, 2187.73511, 1, 8.61509197e-11, 7.85281545e-16, -8.61509197e-11, 1, -9.82245325e-08, -7.93743669e-16, 9.82245325e-08, 1)
end

if currentOption == "Trees Island" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6032.78955, 401.999908, 4.39634514, -0.999964476, 1.89321381e-09, -0.00843126699, 1.84625704e-09, 1, 5.57713209e-09, 0.00843126699, 5.56136781e-09, -0.999964476)
end

if currentOption == "Vokun" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4572.5, 217.399857, 5094.63428, -0.999854326, 3.65839306e-08, -0.0170693286, 3.71540878e-08, 1, -3.30852146e-08, 0.0170693286, -3.37145885e-08, -0.999854326)
end

if currentOption == "Pursuer" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4846.59082, 569.999817, -7142.89258, 0.996175706, -2.08068229e-09, -0.087372601, 9.85005189e-10, 1, -1.25833957e-08, 0.087372601, 1.24492106e-08, 0.996175706)
end

if currentOption == "Kaizu" then
    game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1589.06714, 215.999954, 9941.59766, -0.0209177006, -8.02182285e-08, -0.999781191, 4.7343427e-08, 1, -8.1226311e-08, 0.999781191, -4.90321348e-08, -0.0209177006)
end

if currentOption == "Safe Place" then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1000, 50000, 8000)
baseplatee = Instance.new("Part", workspace)
baseplatee.Size = Vector3.new(150, 1, 150)
baseplatee.CFrame = game.workspace[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame + Vector3.new(0,-2, 0)
baseplatee.Anchored = true
end
end)
TPSection:NewButton("Rayleigh Check And Teleport", "Check Raileigh and teleport if he spawned", function()
local emoi = game:GetService("Workspace").Merchants.QuestHakiMerchant.Clickable.Available.Value
    if emoi == true
    then 
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Merchants.QuestHakiMerchant.HumanoidRootPart.CFrame
        else
         game.StarterGui:SetCore("SendNotification", {
            Title = "Iren Hub",
            Text = "Rayleigh haven't spawned yet.",
            Duration = 4
          })
    
        end
        end
    )
TPSection:NewButton("Dark Atlar", "Teleport To Dark Atlar", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Altar.RecepticalEffect.CFrame * CFrame.new(0, 0, 0)
        end
    )
    
TPSection2:NewButton("Server Hop","Teleport To Low Server", function()
    wait ()
local Servers = game.HttpService:JSONDecode(game:HttpGet("https://games.roblox.com/v1/games/3237168/servers/Public?sortOrder=Asc&limit=100"))
for i,v in pairs(Servers.data) do
  if v.playing ~= v.maxPlayers then
      game:GetService('TeleportService'):TeleportToPlaceInstance(game.PlaceId, v.id)
  end
end
end)
TPSection2:NewButton("Server Rejoin","Rejoin To Current Server", function()
local TeleportService = game:GetService("TeleportService")
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local Rejoin = coroutine.create(function()
    local Success, ErrorMessage = pcall(function()
        TeleportService:Teleport(game.PlaceId, LocalPlayer)
    end)

    if ErrorMessage and not Success then
        warn(ErrorMessage)
    end
end)

coroutine.resume(Rejoin)  

end)

------------------ AUTO SKILL
SkillSection:NewToggle("Auto Skill Z" , "nil", function(state) 
if state then
_G.SkillZ = true
while _G.SkillZ do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillZ = false
end
end)

SkillSection:NewToggle("Auto Skill X" , "nil", function(state) 
if state then
_G.SkillX = true
while _G.SkillX do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillX = false
end
end)

SkillSection:NewToggle("Auto Skill C" , "nil", function(state)
if state then
_G.SkillC = true
while _G.SkillC do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillC = false
end
end)

SkillSection:NewToggle("Auto Skill V" , "nil", function(state)
if state then
_G.SkillV = true
while _G.SkillV do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillV = false
end
end)

SkillSection:NewToggle("Auto Skill B" , "nil", function(state)
if state then
_G.SkillB = true
while _G.SkillB do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"B",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"B",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillB = false
end
end)

SkillSection:NewToggle("Auto Skill N" , "nil", function(state)
if state then
_G.SkillN = true
while _G.SkillN do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"N",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"N",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillN = false
end
end)

SkillSection2:NewToggle("Auto Skill F" , "nil", function(state)
if state then
_G.SkillF = true
while _G.SkillF do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"F",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"F",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillF = false
end
end)

SkillSection2:NewToggle("Auto Skill G" , "nil", function(state)
if state then
_G.SkillG = true
while _G.SkillG do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"G",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"G",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillG = false
end
end)   

SkillSection2:NewToggle("Auto Skill H" , "nil", function(state)
if state then
_G.SkillH = true
while _G.SkillH do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"H",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"H",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillH = false
end
end)   

SkillSection2:NewToggle("Auto Skill J" , "nil", function(state)
if state then
_G.SkillJ = true
while _G.SkillJ do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"J",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"J",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillJ = false
end
end)

SkillSection2:NewToggle("Auto Skill K" , "nil", function(state)
if state then
_G.SkillK = true
while _G.SkillK do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"K",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"K",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillK = false
end
end)

SkillSection2:NewToggle("Auto Skill L" , "nil", function(state)
if state then
_G.SkillL = true
while _G.SkillL do
game:GetService("VirtualInputManager"):SendKeyEvent(true,"L",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
game:GetService("VirtualInputManager"):SendKeyEvent(false,"L",false,game.Players.LocalPlayer.Character.HumanoidRootPart)
wait(0.1)
end
else
_G.SkillL = false
end
end)

HakiSection3:NewToggle("Auto Die","Auto Drown You To Dead", function(qwe)
if qwe then
_G.AutoDie = true
while _G.AutoDie do
pcall(function()
                    game.Players.LocalPlayer.Character.Humanoid.Health = 0
                    game:GetService("Workspace").LocalPlayer.CharacterTrait.Health = 0
                    end)
wait(0.1) 
end
else
_G.AutoDie = false

end
    end)
    HakiSection3:NewToggle("Auto Spawn At Spawn Spot", "Automatic Spawn You To Spawn Pot With PlateForm", function(ty)
    if ty then
    _G.AutoSpawnFarm = true
    while _G.AutoSpawnFarm do
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1000, 50000, 7990)
wait(0.1)
    end
    else
    _G.AutoSpawnFarm = false
    end
    end)
    
    HakiSection3:NewButton("Create Farm Spot", "Teleport And Creat Place For You To Farm", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1000, 50000, 8000)
baseplatee = Instance.new("Part", workspace)
baseplatee.Size = Vector3.new(150, 1, 150)
baseplatee.CFrame = game.workspace[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame + Vector3.new(0,-2, 0)
baseplatee.Anchored = true
        end)
        
HakiSection3:NewButton("Teleport To Farm Spot", "Teleport To Farm Spot", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1000, 50000, 8000)
end)
        
---------------------------------- Settings section

SettingsSection:NewKeybind("Toggle Ui", "Toggles the ui on and off when key is pressed", Enum.KeyCode.M, function()
Library:ToggleUI()
end)

local colors = {
SchemeColor = Color3.fromRGB(0,255,255),
Background = Color3.fromRGB(0, 0, 0),
Header = Color3.fromRGB(0, 0, 0),
TextColor = Color3.fromRGB(255,255,255),
ElementColor = Color3.fromRGB(20, 20, 20)
}

for theme, color in pairs(colors) do
ColorSection:NewColorPicker(theme, "Change your "..theme, color, function(color3)
Library:ChangeColor(theme, color3)
end)
end
end   
