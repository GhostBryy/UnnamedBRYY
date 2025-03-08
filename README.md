while true do 
local validCodes = {
    FROGMAN = function(player)
        -- Grant the Frogman Corps cosmetic items
        player.Character:FindFirstChild("FrogmanCosmetics"):Clone().Parent = player.Character
        -- You can add additional actions like notifications here
        game.ReplicatedStorage:WaitForChild("Notify"):Fire(player, "Frogman Corps unlocked!")
    end
}

local function handleCodeEntry(player, code)
    if validCodes[code] then
        validCodes[code](player)
    else
        game.ReplicatedStorage:WaitForChild("Notify"):Fire(player, "Invalid code!")
    end
end
