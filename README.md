-- Reduzindo as configurações gráficas
local Lighting = game:GetService("Lighting")
Lighting.Brightness = 1
Lighting.ShadowSoftness = 0  -- Desativa sombras suaves
Lighting.GlobalShadows = false  -- Desativa sombras globais
Lighting.Ambient = Color3.fromRGB(180, 180, 180)  -- Iluminação mais suave e simples
Lighting.FogStart = 500  -- Ajusta o início da névoa
Lighting.FogEnd = 1000  -- Ajusta o fim da névoa

-- Ajustando a qualidade dos gráficos para o mais baixo possível
game:GetService("ReplicatedStorage"):SetAttribute("GraphicsLevel", 1)  -- Mínima qualidade gráfica

-- Alterando o material de todas as partes para um estilo mais simples (sem brilho)
game:GetService("Workspace").DescendantAdded:Connect(function(part)
    if part:IsA("Part") then
        part.Material = Enum.Material.SmoothPlastic  -- Material simples
        part.Anchored = true  -- Bloqueia as partes no lugar
    end
end)

-- Função para criar blocos simulando o estilo "Minecraft"
local function createBlock(position)
    local block = Instance.new("Part")
    block.Size = Vector3.new(4, 4, 4)  -- Tamanho de cada bloco
    block.Position = position
    block.Anchored = true  -- Bloqueia o bloco no lugar
    block.Color = Color3.fromRGB(128, 128, 128)  -- Cor padrão (similar ao bloco de pedra do Minecraft)
    block.Material = Enum.Material.SmoothPlastic
    block.Parent = game.Workspace
end

-- Criando alguns blocos de exemplo
createBlock(Vector3.new(0, 10, 0))
createBlock(Vector3.new(5, 10, 0))
createBlock(Vector3.new(10, 10, 0))
