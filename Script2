-- BY:Arthurzin2600
-- KEY:2025ROUBEUMBRAINROT
local P=game:GetService("Players");local R=game:GetService("RunService");local pl=P.LocalPlayer;local T=game:GetService("TweenService");local KEY="2025ROUBEUMBRAINROT"

-- Menu Key
local G=Instance.new("ScreenGui",pl:WaitForChild("PlayerGui"))
local F=Instance.new("Frame",G)
F.Size=UDim2.new(0,300,0,150);F.Position=UDim2.new(0.5,-150,0.5,-75);F.BackgroundColor3=Color3.fromRGB(50,50,50)
local TB=Instance.new("TextBox",F)
TB.Size=UDim2.new(0,280,0,50);TB.Position=UDim2.new(0,10,0,50);TB.PlaceholderText="Digite a KEY aqui";TB.TextScaled=true
local B=Instance.new("TextButton",F)
B.Size=UDim2.new(0,280,0,50);B.Position=UDim2.new(0,10,0,110);B.Text="Confirmar";B.TextScaled=true;B.BackgroundColor3=Color3.fromRGB(0,170,0)

local function iniciar()
    local BC,BS,CT,DV=Vector3.new(0,5,0),Vector3.new(20,1,20),0.5,0.1
    local C=Instance.new("Part",workspace)
    C.Name="Chao";C.Size=BS;C.Position=BC+Vector3.new(0,5,0);C.Anchored=true;C.Transparency=CT;C.CanCollide=true
    local chaoAtivo=true
    R.Heartbeat:Connect(function() if chaoAtivo and C.Position.Y>BC.Y then C.Position=C.Position-Vector3.new(0,DV,0) end end)

    local function atualizarESP()
        for _,plr in pairs(P:GetPlayers()) do
            local char=plr.Character
            if char and char:FindFirstChild("HumanoidRootPart") then
                local hrp=char.HumanoidRootPart
                local esp=hrp:FindFirstChild("ESP")
                if not esp then
                    esp=Instance.new("BillboardGui",hrp);esp.Name="ESP";esp.Size=UDim2.new(0,50,0,50);esp.AlwaysOnTop=true
                    local f=Instance.new("Frame",esp);f.Size=UDim2.new(1,0,1,0);f.BackgroundTransparency=0.5
                end
                local p=hrp.Position
                local dx=math.abs(p.X-BC.X)<=BS.X/2
                local dz=math.abs(p.Z-BC.Z)<=BS.Z/2
                esp.Frame.BackgroundColor3=dx and dz and Color3.fromRGB(0,255,0) or Color3.fromRGB(255,0,0)
            end
        end
    end
    R.Heartbeat:Connect(atualizarESP)

    local GUI=Instance.new("ScreenGui",pl:WaitForChild("PlayerGui"))
    local btn=Instance.new("TextButton",GUI)
    btn.Size=UDim2.new(0,50,0,50);btn.Position=UDim2.new(0.9,0,0.05,0);btn.Text="-";btn.TextScaled=true;btn.BackgroundColor3=Color3.fromRGB(255,0,0);btn.AutoButtonColor=false;btn.ClipsDescendants=true
    local cores={Color3.fromRGB(255,0,0),Color3.fromRGB(0,255,0),Color3.fromRGB(0,0,255),Color3.fromRGB(255,255,0)}
    local i=0
    R.Heartbeat:Connect(function(delta) i=i+delta*2; btn.BackgroundColor3=cores[math.floor(i)%#cores+1] end)
    btn.MouseButton1Click:Connect(function() btn.Visible=not btn.Visible end)

    local toggle=Instance.new("TextButton",GUI)
    toggle.Size=UDim2.new(0,150,0,50);toggle.Position=UDim2.new(0.05,0,0.05,0);toggle.Text="Desativar Chao";toggle.TextScaled=true;toggle.BackgroundColor3=Color3.fromRGB(0,170,0)
    toggle.MouseButton1Click:Connect(function()
        chaoAtivo=not chaoAtivo
        if chaoAtivo then C.Transparency=CT;C.CanCollide=true;toggle.Text="Desativar Chao" else C.Transparency=1;C.CanCollide=false;toggle.Text="Ativar Chao" end
    end)
end

B.MouseButton1Click:Connect(function()
    if TB.Text==KEY then
        local welcome=Instance.new("TextLabel",G)
        welcome.Size=UDim2.new(0,300,0,50);welcome.Position=UDim2.new(0.5,-150,0.5,-25)
        welcome.Text="SEJA BEM-VINDO";welcome.TextScaled=true;welcome.BackgroundTransparency=0.5;welcome.BackgroundColor3=Color3.fromRGB(0,0,0);welcome.TextColor3=Color3.fromRGB(0,255,0)
        task.delay(2,function() welcome:Destroy();G:Destroy();iniciar() end)
    else
        TB.Text="";TB.PlaceholderText="KEY INCORRETA"
    end
end)
