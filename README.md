local UserInputService = game:GetService("UserInputService")

local function handleFlyInput(input, gamepad)
    if input.KeyCode == Enum.KeyCode.Space then
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")

        if humanoid.FloorMaterial == Enum.Material.Air then
            character.PrimaryPart.Velocity = Vector3.new(0, 50, 0)
        end
    end
end

UserInputService.InputBegan:Connect(handleFlyInput)
