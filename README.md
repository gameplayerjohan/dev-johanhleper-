resources/[scripts]/ems_script
ems_script
 ├ fxmanifest.lua
 └ client.lua
 fx_version 'cerulean'
game 'gta5'

author 'JouwNaam'
description 'Simple EMS revive script'
version '1.0'

client_script 'client.lua'
RegisterCommand("revive", function()
    local player = PlayerPedId()

    if IsEntityDead(player) then
        local coords = GetEntityCoords(player)

        NetworkResurrectLocalPlayer(coords.x, coords.y, coords.z, true, true, false)
        SetEntityHealth(player, 200)
        ClearPedBloodDamage(player)

        TriggerEvent('chat:addMessage', {
            args = {"EMS", "Je bent gerevived!"}
        })
    end
end)RegisterCommand("revive", function()
    local player = PlayerPedId()

    if IsEntityDead(player) then
        local coords = GetEntityCoords(player)

        NetworkResurrectLocalPlayer(coords.x, coords.y, coords.z, true, true, false)
        SetEntityHealth(player, 200)
        ClearPedBloodDamage(player)

        TriggerEvent('chat:addMessage', {
            args = {"EMS", "Je bent gerevived!"}
        })
    end
end)
/revive
