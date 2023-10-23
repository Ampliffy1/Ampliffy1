while do true
    wait(5)

function highlightPlayers(esp)
    local players = game:GetService("Players")
    for i, player in ipairs(players:GetPlayers()) do
      local humanoidRootPart = player.Character.HumanoidRootPart
      humanoidRootPart.BrickColor = esp and BrickColor.Red or BrickColor.White
    end
  end
  
  highlightPlayers(true)
  
  game:GetService("UserInputService").InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.Q then
      highlightPlayers(not highlightPlayers())
      print("hi")
    end
  end)

