-- Configurações

local itensParaColetar = {

    ["Espada do Zoro"] = true,
    ["Espada do Shanks"] = true,
    ["Espada do Mihawk"] = true,
    ["Skull Guitar"] = true,
    ["Chalice"] = true,
    ["Mystic Droplet"] = true,
    ["Fool's Relic"] = true

}

local estilosDeLutaParaColetar = {

    ["Dark Step"] = true,
    ["Electric"] = true,
    ["Water Kung Fu"] = true,
    ["Death Step"] = true,
    ["Electric Claw"] = true,
    ["Sharkman Karate"] = true,
    ["Superhuman"] = true,
    ["Godhuman"] = true,
    ["Sanguine Art"] = true

}

local agilidadesParaComprar = {

    ["Air Jump"] = true,
    ["Flash Step"] = true,
    ["Aura"] = true

}

local precoHakiDaVisao = 750000
local velocidadeVoo = 100
local coletarTodosItens = true
local ilhas = {

    -- ... (lista de ilhas)

}

local ilhaAtual = 1
local nivelMaximo = 2600
local autoExecutar = false
local abaAtual = "Level"



-- Detecta o tipo de dispositivo

local dispositivo = if game:GetService("UserInputService").TouchEnabled then "Celular" else "PC"



-- Criação do HUD (adaptado para diferentes dispositivos)

local screenGui = Instance.new("ScreenGui")

screenGui.Parent = game.Players.LocalPlayer.PlayerGui



local frame = Instance.new("Frame")

-- ... (configurações do frame adaptadas para dispositivos)



local titulo = Instance.new("Max HUB")
-- ... (configurações do título adaptadas para dispositivos)



-- Abas (adaptadas para diferentes dispositivos)
local statusAba = Instance.new("Server Stats")
-- ... (configurações do botão Status adaptadas para dispositivos)



local levelAba = Instance.new("Auto Farm Level")
-- ... (configurações do botão Level adaptadas para dispositivos)



local itensAba = Instance.new("Itens Farm")
-- ... (configurações do botão Itens adaptadas para dispositivos)



-- Frames das abas (adaptadas para diferentes dispositivos)
local statusFrame = Instance.new("Status")
-- ... (configurações do frame Status adaptadas para dispositivos)



local levelFrame = Instance.new("Auto Level")
-- ... (configurações do frame Level adaptadas para dispositivos)



local itensFrame = Instance.new("Itens")
-- ... (configurações do frame Itens adaptadas para dispositivos)



-- Conteúdo das abas (adaptado para diferentes dispositivos)
local miragemLabel = Instance.new("Mirage")
-- ... (configurações do label miragem adaptadas para dispositivos)



local preHistoricaLabel = Instance.new("Preysthoric")
-- ... (configurações do label pré-histórica adaptadas para dispositivos)



local kitsuneLabel = Instance.new("Kitsune")
-- ... (configurações do label kitsune adaptadas para dispositivos)



local nivelLabel = Instance.new("Nivel")
-- ... (configurações do label nível adaptadas para dispositivos)



local coletarTodosCheckbox = Instance.new("CheckBox")
-- ... (configurações do checkbox coletar todos adaptadas para dispositivos)



local coletarTodosLabel = Instance.new("Auto All Itens")
-- ... (configurações do label coletar todos adaptadas para dispositivos)



local comprarAgilidadesCheckbox = Instance.new("Buy all Abilites")
-- ... (configurações do checkbox comprar agilidades adaptadas para dispositivos)



local comprarAgilidadesLabel = Instance.new("Buy all Abilites")
-- ... (configurações do label comprar agilidades adaptadas para dispositivos)



local comprarHakiDaVisaoCheckbox = Instance.new("Auto Obiservation Buy")
-- ... (configurações do checkbox comprar Haki da Visão adaptadas para dispositivos)



local comprarHakiDaVisaoLabel = Instance.new("Auto Obiservation Buy")
-- ... (configurações do label comprar Haki da Visão adaptadas para dispositivos)



-- Funções auxiliares (adaptadas para diferentes dispositivos e coleta de itens/estilos de luta/compra de agilidades/Haki da Visão)

local function encontrarItemMaisProximo(nomeItem)

    local itemMaisProximo = nil

    local distanciaMinima = math.huge



    for _, item in pairs(workspace:GetDescendants()) do

        if item:IsA("BasePart") and item.Name == nomeItem then

            local distancia = (item.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude

            if distancia < distanciaMinima then

                distanciaMinima = distancia

                itemMaisProximo = item

            end

        end

    end



    return itemMaisProximo

end



local function moverParaItem(item)

    -- ... (lógica para mover para o item)

end



local function voar()

    -- ... (lógica para voar)

end



local function encontrarNPCMaisProximo()

    -- ... (lógica para encontrar o NPC mais próximo)

end



local function atacarNPC(npc)

    -- ... (lógica para atacar o NPC)

end



local function moverParaIlha(nomeIlha)

    -- ... (lógica para mover para a ilha)

end



local function atualizarStatus()

    -- Lógica para detectar a presença das ilhas (requer conhecimento avançado do jogo)

    -- Atualizar os labels com as informações detectadas

end



local function atualizarAba(aba)

    abaAtual = aba

    statusFrame.Visible = aba == "Status"

    levelFrame.Visible = aba == "Level"

    itensFrame.Visible = aba == "Itens"

end



local function comprarAgilidade(nomeAgilidade)

    -- Lógica para comprar a agilidade (requer conhecimento avançado do jogo)

end



local function comprarHakiDaVisao()

    -- Lógica para comprar o Haki da Visão (requer conhecimento avançado do jogo)

end



-- Eventos das abas (adaptados para diferentes dispositivos)

mainAba.MouseButton1Click:Connect(function()

    atualizarAba("Main")

end)



itensAba.MouseButton1Click:Connect(function()

    atualizarAba("Itens")

end)



statusAba.MouseButton1Click:Connect(function()

    atualizarAba("Status")

    atualizarStatus()

end)



levelAba.MouseButton1Click:Connect(function()

    atualizarAba("Level")

end)



-- Loop principal (adaptado para diferentes dispositivos e coleta de itens/estilos de luta/compra de agilidades/Haki da Visão)

while true do

    if autoExecutar then

        voar()



        if abaAtual == "Level" then

            -- Lógica para farmar level

        elseif abaAtual == "Itens" then

            if coletarTodosItens then

                for nomeItem, _ in pairs(itensParaColetar) do

                    local itemParaColetar = encontrarItemMaisProximo(nomeItem)



                    if itemParaColetar then

                        moverParaItem(itemParaColetar)

                    end

                end



                for nomeItem, _ in pairs(estilosDeLutaParaColetar) do

                    local itemParaColetar = encontrarItemMaisProximo(nomeItem)



                    if itemParaColetar then

                        moverParaItem(itemParaColetar)

                    end

                end

            end



            if comprarAgilidadesCheckbox.Value then

                for nomeAgilidade, _ in pairs(agilidadesParaComprar) do

                    comprarAgilidade(nomeAgilidade)

                end

            end



            if comprarHakiDaVisaoCheckbox.Value then

                if game.Players.LocalPlayer.leaderstats.Beli.Value >= precoHakiDaVisao then

                    comprarHakiDaVisao()

                end

            end

        end

    end



    wait(0.1)

end                    Noclip.Par…
