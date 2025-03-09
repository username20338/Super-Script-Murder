-- Carregando a Kavo UI Library
local Kavo = loadstring(game:HttpGet("https://raw.githubusercontent.com/o7-Fire/Kavo-UI-Script/main/source.lua"))()

-- Criando a Janela Principal
local Window = Kavo.CreateLib("MM2 Script", "DarkTheme")

-- Criando Abas
local ESP_Tab = Window:NewTab("ESP Supremo")
local AutoFarm_Tab = Window:NewTab("Auto Farm Coin")
local GodMode_Tab = Window:NewTab("GodMode Ultra")
local XRay_Tab = Window:NewTab("X-Ray Hacker")
local Antiban_Tab = Window:NewTab("Antiban PRO")
local Extras_Tab = Window:NewTab("Extras")

-- Criando Seções
local ESP_Section = ESP_Tab:NewSection("ESP Supremo")
local AutoFarm_Section = AutoFarm_Tab:NewSection("Auto Farm Coin")
local GodMode_Section = GodMode_Tab:NewSection("GodMode Ultra")
local XRay_Section = XRay_Tab:NewSection("X-Ray Hacker")
local Antiban_Section = Antiban_Tab:NewSection("Antiban PRO")
local Extras_Section = Extras_Tab:NewSection("Extras")

-- Função ESP Supremo
ESP_Section:NewButton("Ativar ESP Supremo", "Ativa o ESP Supremo", function()
    for _, player in pairs(game.Players:GetPlayers()) do
        if player ~= game.Players.LocalPlayer then
            local highlight = Instance.new("Highlight")
            highlight.Parent = player.Character
            highlight.FillColor = Color3.fromRGB(255, 0, 0)
            highlight.FillTransparency = 0.5
            highlight.OutlineColor = Color3.fromRGB(255, 255, 255)
        end
    end
end)

-- Função Auto Farm Coin
AutoFarm_Section:NewButton("Auto Farm Coin", "Coleta moedas automaticamente", function()
    spawn(function()
        while true do
            for _, coin in pairs(game:GetService("Workspace").Coins:GetChildren()) do
                if coin:IsA("Part") then
                    game.Players.LocalPlayer.Character:MoveTo(coin.Position)
                    wait(0.2)
                end
            end
            wait(1)
        end
    end)
end)

-- Função GodMode Ultra
GodMode_Section:NewButton("Ativar GodMode", "Fica invencível", function()
    local character = game.Players.LocalPlayer.Character
    for _, part in pairs(character:GetChildren()) do
        if part:IsA("BasePart") then
            part.CanCollide = false
            part.Anchored = true
        end
    end
end)

-- Função X-Ray Hacker
XRay_Section:NewButton("Ativar X-Ray", "Ativa visão de raio-x", function()
    for _, obj in pairs(game:GetService("Workspace"):GetDescendants()) do
        if obj:IsA("BasePart") then
            obj.Transparency = 0.5
        end
    end
end)

-- Função Antiban PRO
Antiban_Section:NewButton("Ativar Antiban", "Evita bans automáticos", function()
    game.Players.PlayerAdded:Connect(function(player)
        if player:GetRankInGroup(123456) >= 200 then -- Altere para o ID do grupo de admins
            game.Players.LocalPlayer:Kick("Admin detectado!")
        end
    end)
end)

-- Função Detector de Murderer
Extras_Section:NewButton("Ativar Detector de Murderer", "Avisa quem é o Murderer", function()
    spawn(function()
        while true do
            for _, player in pairs(game.Players:GetPlayers()) do
                if player.Backpack:FindFirstChild("Knife") or player.Character:FindFirstChild("Knife") then
                    print("Murderer detectado:", player.Name)
                end
            end
            wait(1)
        end
    end)
end)

-- Função Kill Aura
Extras_Section:NewButton("Ativar Kill Aura", "Ataca jogadores próximos", function()
    while true do
        for _, player in pairs(game.Players:GetPlayers()) do
            if player ~= game.Players.LocalPlayer and player.Character then
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
                wait(0.1)
            end
        end
    end
end)

-- Função Notificação de Arma Solta
Extras_Section:NewButton("Ativar Notificação de Arma", "Avisa quando a arma do Xerife está solta", function()
    game:GetService("Workspace").ChildAdded:Connect(function(child)
        if child:IsA("Tool") and child.Name == "Gun" then
            print("⚠️ Arma do Xerife disponível!")
        end
    end)
end)

-- Função Teleporte Rápido
Extras_Section:NewButton("Teleporte para Jogadores", "Vai até qualquer jogador", function()
    for _, player in pairs(game.Players:GetPlayers()) do
        if player ~= game.Players.LocalPlayer then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
            wait(1)
        end
    end
end)

-- Função NoClip
Extras_Section:NewButton("Ativar NoClip", "Atravessa paredes", function()
    game:GetService("RunService").Stepped:Connect(function()
        for _, part in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
            if part:IsA("BasePart") then
                part.CanCollide = false
            end
        end
    end)
end)

-- Função FPS Booster
Extras_Section:NewButton("Ativar FPS Booster", "Melhora desempenho do jogo", function()
    for _, obj in pairs(game:GetService("Workspace"):GetDescendants()) do
        if obj:IsA("BasePart") then
            obj.Material = Enum.Material.SmoothPlastic
            obj.Reflectance = 0
            obj.Transparency = 0
        end
    end
    game.Lighting.GlobalShadows = false
end)

-- Função Anti Fling
Extras_Section:NewButton("Ativar Anti Fling", "Evita exploits de arremesso", function()
    game:GetService("RunService").Stepped:Connect(function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.Velocity
