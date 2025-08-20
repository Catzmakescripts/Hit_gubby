getgenv().LoopFistDamage = true -- set to false to stop

task.spawn(function()
    while getgenv().LoopFistDamage do
        local args = {
            Vector3.new(-6.839175224304199, 3.5018556118011475, 0.0006368431495502591),
            1132.7974974908502
        }
        
        game:GetService("ReplicatedStorage")
            :WaitForChild("Networking")
            :WaitForChild("Server")
            :WaitForChild("RemoteEvents")
            :WaitForChild("DamageEvents")
            :WaitForChild("FistDamage")
            :FireServer(unpack(args))

        task.wait(0.01) -- adjust delay to avoid flooding
    end
end)
