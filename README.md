# ScriptAttachmentsbeta

-- Arquivo: criacao_attachments.lua

-- Tabela com os attachments disponíveis para criação
local attachments = {
    { name = "Silenciador", metalRequired = 40, maxCraftable = 1 },
    { name = "Empunhadura", metalRequired = 70, maxCraftable = 1 },
    -- Adicione mais attachments aqui
}

-- Tabela para rastrear os attachments criados por cada jogador
local craftedAttachments = {}

-- Comando para criar um attachment
RegisterCommand('criarattachment', function(source, args)
    local player = source
    local attachmentIndex = tonumber(args[1])
    local attachment = attachments[attachmentIndex]
    if attachment then
        -- Verificar se o jogador já criou o attachment
        if craftedAttachments[player] and craftedAttachments[player][attachment.name] then
            -- Notificar o jogador de que ele já criou o attachment
        else
            -- Verificar se o jogador possui metal suficiente
            local playerMetal = -- Lógica para obter a quantidade de metal do jogador
            if playerMetal >= attachment.metalRequired then
                -- Lógica para permitir que o jogador crie o attachment
                -- Exemplo: remover a quantidade necessária de metal do jogador
                -- e adicionar o attachment ao inventário do jogador
                -- Atualizar a tabela de rastreamento de attachments criados pelo jogador
                craftedAttachments[player] = craftedAttachments[player] or {}
                craftedAttachments[player][attachment.name] = true
            else
                -- Notificar o jogador de que ele não possui metal suficiente
            end
        end
    end
end, false)

-- Comando para exibir os attachments disponíveis
RegisterCommand('attachments', function(source, args)
    -- Lógica para exibir a lista de attachments disponíveis
end, false)

-- Função para rota de farm de metal
function FarmMetal(player)
    -- Lógica para adicionar metal ao inventário do jogador
end
