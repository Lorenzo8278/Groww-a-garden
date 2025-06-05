-- StarterGui > LoadingUI (ScreenGui)
-- Com um Frame, Label escrito "Carregando..."

local loadingGui = Instance.new("ScreenGui")
loadingGui.Name = "LoadingUI"

local frame = Instance.new("Frame", loadingGui)
frame.Size = UDim2.new(0.3, 0, 0.2, 0)
frame.Position = UDim2.new(0.35, 0, 0.4, 0)
frame.BackgroundColor3 = Color3.fromRGB(34, 139, 34)
frame.BorderSizePixel = 0

local text = Instance.new("TextLabel", frame)
text.Text = "Carregando jardim..."
text.Size = UDim2.new(1, 0, 1, 0)
text.BackgroundTransparency = 1
text.Font = Enum.Font.SourceSansBold
text.TextScaled = true
text.TextColor3 = Color3.new(1, 1, 1)

loadingGui.ResetOnSpawn = false
loadingGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")-- StarterPlayerScripts > GrowAGardenClient.lua

local player = game.Players.LocalPlayer
local gui = player:WaitForChild("PlayerGui")

local loading = gui:WaitForChild("LoadingUI")
local main = gui:WaitForChild("MainUI")

-- Simula carregamento (pode ser ajustado)
task.wait(3)

-- Troca interfaces
loading:Destroy()
main.Enabled = true
local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local loadingUI = playerGui:WaitForChild("LoadingUI")
local mainUI = playerGui:WaitForChild("MainUI")

-- Aguarda tudo carregar corretamente
task.wait(3)  -- tempo de carregamento

-- Troca as interfaces
loadingUI.Enabled = false
mainUI.Enabled = true
