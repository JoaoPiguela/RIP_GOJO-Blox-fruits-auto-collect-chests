# RIP_GOJO-Blox-fruits-auto-collect-chests


<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Entrar no Discord</Join>
    <style>
        .discord-button {
            background-color: #7289DA;
            color: white;
            padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            border-radius: 5px;
            border: none;
            cursor: pointer;
        }
        .discord-button:hover {
            background-color: #5b6eae;
        }
    </style>
</head>
<body>
    <a href="https://discord.gg/tpGkscTC" class="discord-button">Entrar no meu servidor do Discord</a>
</body>
</html>

local widget = require("widget")

-- Função para alternar a visibilidade do elemento "main"
local function toggleMain()
    local main = display.newGroup() -- Supondo que "main" seja um grupo de display
    if main.isVisible then
        main.isVisible = false
    else
        main.isVisible = true
    end
end

-- Criar o botão com a imagem
local button = widget.newButton({
    width = 100,
    height = 100,
    defaultFile = "1727889340066.png", -- Substitua pelo caminho da sua imagem
    onRelease = toggleMain
})

-- Posicionar o botão na tela
button.x = display.contentCenterX
button.y = display.contentCenterY


---Script

local worlds = {"Primeiro Mundo", "Segundo Mundo", "Terceiro Mundo"}
local chests = {
    {type = "Bronze", id = 1},
    {type = "Ouro", id = 2},
    {type = "Diamante", id = 3}
}

function teleportToChest(chest)
    -- Função para teleportar para o baú
    print("Teleportando para o baú de " .. chest.type)
    -- Código de teleporte aqui
end

function collectChest(chest)
    -- Função para coletar o baú
    print("Coletando baú de " .. chest.type)
    -- Código de coleta aqui
end

function checkAllChestsCollected()
    -- Função para verificar se todos os baús foram coletados
    print("Verificando se todos os baús foram coletados")
    -- Código de verificação aqui
    return true -- Retornar verdadeiro se todos os baús foram coletados
end

function switchServer()
    -- Função para trocar de servidor
    print("Trocando de servidor")
    -- Código para trocar de servidor aqui
end

function collectAllChests()
    for _, world in ipairs(worlds) do
        print("Verificando baús no " .. world)
        for _, chest in ipairs(chests) do
            teleportToChest(chest)
            collectChest(chest)
        end
    end
    if checkAllChestsCollected() then
        switchServer()
    end
end

collectAllChests()
