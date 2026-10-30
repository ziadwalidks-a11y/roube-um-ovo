
-- SISTEMA DE MINIMIZAR PRIME HUB

local BotaoP = Instance.new("TextButton")
BotaoP.Name = "PrimeButton"
BotaoP.Size = UDim2.new(0, 55, 0, 55)
BotaoP.Position = UDim2.new(0.5, -27, 0.5, -27)
BotaoP.BackgroundColor3 = Color3.fromRGB(100, 30, 180)
BotaoP.Text = "P"
BotaoP.TextColor3 = Color3.new(1, 1, 1)
BotaoP.TextSize = 28
BotaoP.Font = Enum.Font.GothamBold
BotaoP.Visible = false
BotaoP.Parent = GUI

local Canto = Instance.new("UICorner")
Canto.CornerRadius = UDim.new(1, 0)
Canto.Parent = BotaoP

local Borda = Instance.new("UIStroke")
Borda.Color = Color3.fromRGB(190, 80, 255)
Borda.Thickness = 2
Borda.Parent = BotaoP

-- Minimizar
local function Minimizar()
    Main.Visible = false
    BotaoP.Visible = true
end

-- Restaurar
BotaoP.MouseButton1Click:Connect(function()
    Main.Visible = true
    BotaoP.Visible = false
end)

-- Arrastar bolinha
local arrastando = false
local inicio
local posicao

BotaoP.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        arrastando = true
        inicio = input.Position
        posicao = BotaoP.Position
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if arrastando and input.UserInputType == Enum.UserInputType.MouseMovement then
        local delta = input.Position - inicio
        BotaoP.Position = UDim2.new(
            posicao.X.Scale,
            posicao.X.Offset + delta.X,
            posicao.Y.Scale,
            posicao.Y.Offset + delta.Y
        )
    end
end)

UserInputService.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        arrastando = false
    end
end)

