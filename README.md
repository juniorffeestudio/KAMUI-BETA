print("[K] init")

-- ============ CARREGAMENTO DA BIBLIOTECA (FIX ROBUSTO) ============
local function loadLibrary()
    local urls = {
        "https://raw.githubusercontent.com/REDzHUB/RedzLibV5/main/Source.Lua",
        "https://raw.githubusercontent.com/REDzHUB/RedzLib/main/Source.Lua",
        "https://raw.githubusercontent.com/minhdepzai-v/LibraryRobloc/refs/heads/main/RedzLibrary.lua"
    }
    for _, url in ipairs(urls) do
        local success, result = pcall(function()
            local src = game:HttpGet(url, true)
            if not src or src == "" or src:sub(1,3) == "404" or src:sub(1,3) == "<!D" then return nil end
            local func = loadstring(src)
            if not func then return nil end
            return func()
        end)
        if success and result and type(result) == "table" and result.MakeWindow then
            return result
        end
    end
    return nil
end

local lib = loadLibrary()
if not lib then
    local StarterGui = game:GetService("StarterGui")
    pcall(function()
        StarterGui:SetCore("SendNotification", {
            Title = "Kamui Hub",
            Text = "Falha ao carregar a biblioteca. Verifique sua conexão.",
            Duration = 5
        })
    end)
    warn("[Kamui] Falha ao carregar Redz Library.")
    return
end
print("[K] Library carregada")

local RS,P,R,C,LP,TS,H,VIM=game:GetService("ReplicatedStorage"),game:GetService("Players"),game:GetService("RunService"),workspace.CurrentCamera,game:GetService("Players").LocalPlayer,game:GetService("TeleportService"),game:GetService("HttpService"),game:GetService("VirtualInputManager")
local INS=game:GetService("InsertService")
local PS=game:GetService("PhysicsService")
local UIS=game:GetService("UserInputService")
local L=game:GetService("Lighting")
local SoundService=game:GetService("SoundService")
local GuiService=game:GetService("GuiService")

-- ============ BROOKHAVEN CHECK — ONLY PLACEID 4924922222 ============
local function isBrookhaven()
    return game.PlaceId == 4924922222
end
if not isBrookhaven() then
    pcall(function()
        local pg = LP:WaitForChild("PlayerGui", 15)
        if pg then
            local sg = Instance.new("ScreenGui")
            sg.Name = "KamuiUnsupported"
            sg.Parent = pg
            sg.IgnoreGuiInset = true
            sg.DisplayOrder = 99999
            
            local bg = Instance.new("Frame")
            bg.Size = UDim2.new(1,0,1,0)
            bg.BackgroundColor3 = Color3.fromRGB(10,10,15)
            bg.BorderSizePixel = 0
            bg.Parent = sg
            
            local box = Instance.new("Frame")
            box.AnchorPoint = Vector2.new(0.5,0.5)
            box.Position = UDim2.new(0.5,0,0.5,0)
            box.Size = UDim2.new(0.6,0,0.22,0)
            box.BackgroundColor3 = Color3.fromRGB(20,20,30)
            box.BorderSizePixel = 0
            box.Parent = bg
            
            local bc = Instance.new("UICorner")
            bc.CornerRadius = UDim.new(0,12)
            bc.Parent = box
            
            local st = Instance.new("UIStroke")
            st.Color = Color3.fromRGB(0,150,255)
            st.Thickness = 2
            st.Parent = box
            
            local lbl = Instance.new("TextLabel")
            lbl.Size = UDim2.new(1,0,0.55,0)
            lbl.Position = UDim2.new(0,0,0.1,0)
            lbl.BackgroundTransparency = 1
            lbl.Text = "Kamui x Hub only works in Brookhaven RP"
            lbl.TextColor3 = Color3.fromRGB(0,150,255)
            lbl.TextScaled = true
            lbl.Font = Enum.Font.GothamBold
            lbl.Parent = box
            
            local sub = Instance.new("TextLabel")
            sub.Size = UDim2.new(1,0,0.3,0)
            sub.Position = UDim2.new(0,0,0.65,0)
            sub.BackgroundTransparency = 1
            sub.Text = "PlaceId: "..tostring(game.PlaceId)
            sub.TextColor3 = Color3.fromRGB(200,200,200)
            sub.TextScaled = true
            sub.Font = Enum.Font.Gotham
            sub.Parent = box
        end
    end)
    return
end

LP:SetAttribute("KamuiHubUser",true)
pcall(function() PS:RegisterCollisionGroup("KamuiBall") end)
pcall(function() PS:RegisterCollisionGroup("KamuiHolder") end)
pcall(function() PS:CollisionGroupSetCollidable("KamuiBall","KamuiHolder",false) end)

-- ============ SISTEMA DE SOM DE CLIQUE GLOBAL ============
local clickSound = Instance.new("Sound")
clickSound.SoundId = "rbxassetid://6895079853"
clickSound.Volume = 0.4
clickSound.Parent = SoundService

UIS.InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        local pos = UIS:GetMouseLocation()
        local objects = GuiService:GetGuiObjectsAtPosition(pos.X, pos.Y)
        if #objects > 0 then
            clickSound:Play()
        end
    end
end)

local LANG="pt"
local V="v1.9.7"

local T={
    pt={title="kamui x hub ⚡",sub="Standard Edition "..V,credits="Creditos",creator="Criador",version="Versao",discord="Discord",discord_desc="Entre no nosso servidor Discord!",discord_copy="Copiar Link Discord",players="Player",players_hub="Jogadores no Hub",refresh="Atualizar Agora",auto_refresh="Auto Refresh",tag="TAG",tag_show="Mostrar TAG em cima",your_tag="Sua Tag",esp="ESP",esp_show="ESP (ver jogadores)",troll="Troll",target="Alvo",view="View Alvo",tp="TP",wl="Whitelist",wl_add="Add/Remover",wl_clear="Limpar WL",fling="Fling",method="Metodo",exec_fling="Executar Fling",touch_ball="Touch Fling (tronco)",tool_ball="Tool Ball (manda p/ alvo)",item="Item",item_paid="Item Pago",item_get="Pegar",avatar="Avatar",copy_avatar="Copy Avatar",avatar_player="Jogador",music="Musica",music_id="ID",music_play="Tocar",music_saved="Salvas",music_play_saved="Tocar Salva",music_name="Nome",music_save="Salvar",music_del="Deletar",prot="Protecao",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling (bola+sofa)",anti_lag="Anti Lag",performance="Performance",cfg="Configuração",extras="Extras",auto_rejoin="Auto Rejoin",open_admin="Abrir Painel Admin",admin="Admin",admin_panel="Painel Admin",admin_open="Abrir Admin",changelog="Changelog",maps="Mapas",backrooms="Backrooms",cafe="Cafe (Blox Fruits)",map_select="Selecionar Mapa",map_spawn="Spawn Mapa",admin_take_me_br="Me levar p/ backrooms",admin_take_player_br="Levar player p/ backrooms",admin_select_player="Player",meteors="Meteoros",meteor_rain="Chuva de Meteoros",meteor_one="Lancar 1 Meteoro",msg="Mensagem",msg_send="Say (Enviar como Alvo)",select_item="Selecione um item",select_map="Selecione um mapa",select_target="Selecione alvo",not_found="Nao encontrado",no_players="Nenhum",all="All",br_spawned="Backrooms spawnado",cafe_spawned="Cafe spawnado",br_failed="Falha ao carregar Cafe",link_copied="Link copiado!",tags_on="Tags ON",tags_off="Tags OFF",esp_on="ESP ON",esp_off="ESP OFF",refresh_done="Atualizado",antifling_on="Anti-Fling ON",antifling_off="Anti-Fling OFF",antilag_on="Anti Lag ON",antilag_off="Anti Lag OFF",hub_loaded="Kamui Hub "..V.." carregado!",cars="Carros",coming_soon="Em breve",user_tag="{USER}",not_hub="nao esta usando o Kamui Hub",freeze="Freeze",jail="Jail",unjail="Unjail",say="Say",frozen="Congelado",jailed="Preso",unjailed="Solto",flung="Arremessado",no_target="Selecione um alvo valido",self_target="Nao pode usar em si mesmo",need_fling_type="Selecione 'Fling Ball' no dropdown Fling primeiro",ball_ok="Bola obtida! Iniciando fling...",no_ball="Bola nao encontrada",tool_ball_on="Tool Ball ativo -> ",tool_ball_off="Tool Ball desligado"},
    en={title="kamui x hub ⚡",sub="Standard Edition "..V,credits="Credits",creator="Creator",version="Version",discord="Discord",discord_desc="Join our Discord server!",discord_copy="Copy Discord Link",players="Players",players_hub="Players in Hub",refresh="Refresh Now",auto_refresh="Auto Refresh",tag="TAG",tag_show="Show TAG above head",your_tag="Your Tag",esp="ESP",esp_show="ESP (see players)",troll="Troll",target="Target",view="View Target",tp="TP",wl="Whitelist",wl_add="Add/Remove",wl_clear="Clear WL",fling="Fling",method="Method",exec_fling="Execute Fling",touch_ball="Touch Fling (torso)",tool_ball="Tool Ball (send to target)",item="Item",item_paid="Paid Item",item_get="Get",avatar="Avatar",copy_avatar="Copy Avatar",avatar_player="Player",music="Music",music_id="ID",music_play="Play",music_saved="Saved",music_play_saved="Play Saved",music_name="Name",music_save="Save",music_del="Delete",prot="Protection",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling (ball+couch)",anti_lag="Anti Lag",performance="Performance",cfg="Settings",extras="Extras",auto_rejoin="Auto Rejoin",open_admin="Open Admin Panel",admin="Admin",admin_panel="Admin Panel",admin_open="Open Admin",changelog="Changelog",maps="Maps",backrooms="Backrooms",cafe="Cafe (Blox Fruits)",map_select="Select Map",map_spawn="Spawn Map",admin_take_me_br="Take me to backrooms",admin_take_player_br="Take player to backrooms",admin_select_player="Player",meteors="Meteors",meteor_rain="Meteor Shower",meteor_one="Launch 1 Meteor",msg="Message",msg_send="Say (Send as Target)",select_item="Select an item",select_map="Select a map",select_target="Select target",not_found="Not found",no_players="None",all="All",br_spawned="Backrooms spawned",cafe_spawned="Cafe spawned",br_failed="Failed to load Cafe",link_copied="Link copied!",tags_on="Tags ON",tags_off="Tags OFF",esp_on="ESP ON",esp_off="ESP OFF",refresh_done="Refreshed",antifling_on="Anti-Fling ON",antifling_off="Anti-Fling OFF",antilag_on="Anti Lag ON",antilag_off="Anti Lag OFF",hub_loaded="Kamui Hub "..V.." loaded!",cars="Cars",coming_soon="Coming soon",user_tag="{USER}",not_hub="is not using Kamui Hub",freeze="Freeze",jail="Jail",unjail="Unjail",say="Say",frozen="Frozen",jailed="Jailed",unjailed="Unjailed",flung="Flung",no_target="Select a valid target",self_target="Cannot use on yourself",need_fling_type="Select 'Fling Ball' in Fling dropdown first",ball_ok="Ball acquired! Starting fling...",no_ball="Ball not found",tool_ball_on="Tool Ball active -> ",tool_ball_off="Tool Ball disabled"}
}

local AN={"testeeeeeeeepouraa_99391","teste_ofc9098764","teste_ofc90","TLK_EDITS"}
local AI={7217546593}
local BY=1050
local CAFE_ASSET=13071284195
local function isAdm(p)
    for _,n in ipairs(AN) do
        if p.Name==n or p.DisplayName==n then return true end
    end
    for _,i in ipairs(AI) do
        if p.UserId==i then return true end
    end
    return false
end
local function isHub(p)
    return p and p:GetAttribute("KamuiHubUser")==true
end
local function reqHub(p)
    if not p then return false,"Nenhum jogador selecionado" end
    if p == LP then return false,"Nao pode usar em si mesmo" end
    if isHub(p) then return true end
    for i=1,4 do
        task.wait(0.15)
        if isHub(p) then return true end
    end
    return false,p.Name.." nao esta usando o Kamui Hub"
end
local PR={}
local function isP(n) return PR[n]==true end
local FO=false
pcall(function()
    writefile("k.tmp","1")
    if readfile("k.tmp")=="1" and isfile("k.tmp") then FO=true end
    delfile("k.tmp")
end)
local SM={}
if FO then
    pcall(function()
        if isfile("km.json") then
            local r=readfile("km.json")
            if r and r~="" then
                local d=H:JSONDecode(r)
                if type(d)=="table" then
                    for k,v in pairs(d) do
                        local c=tostring(v):match("(%d+)")
                        if c then SM[k]=c end
                    end
                end
            end
        end
    end)
end
local function saveM()
    if not FO then return end
    pcall(function() writefile("km.json",H:JSONEncode(SM)) end)
end
local function nId(id)
    if not id then return nil end
    id=tostring(id):gsub("%s+","")
    return id:match("(%d+)")
end
local function readTB(tb)
    if not tb then return nil end
    for _,m in ipairs({
        function() return tb.Text end,
        function() return tb:GetText() end,
        function() return tb:Get() end,
        function() return tb.Value end
    }) do
        local o,v=pcall(m)
        if o and type(v)=="string" and v~="" then return v end
    end
    return nil
end

local NG,NC,NO=nil,nil,0
local function ensN()
    if NG and NG.Parent then return end
    local pg=LP:WaitForChild("PlayerGui")
    local o=pg:FindFirstChild("KamuiNotifGui")
    if o then o:Destroy() end
    NG=Instance.new("ScreenGui")
    NG.Name="KamuiNotifGui"
    NG.Parent=pg
    NG.ResetOnSpawn=false
    NG.IgnoreGuiInset=true
    NG.DisplayOrder=999
    NC=Instance.new("Frame")
    NC.AnchorPoint=Vector2.new(0.5,0)
    NC.Position=UDim2.new(0.5,0,0.03,0)
    NC.Size=UDim2.new(0.7,0,0,0)
    NC.BackgroundTransparency=1
    NC.Parent=NG
    local l=Instance.new("UIListLayout")
    l.SortOrder=Enum.SortOrder.LayoutOrder
    l.Padding=UDim.new(0,8)
    l.Parent=NC
end

local function notify(text,color)
    pcall(function()
        ensN()
        NO=NO+1
        local cl=color or Color3.fromRGB(0,150,255)
        local f=Instance.new("Frame")
        f.LayoutOrder=NO
        f.Size=UDim2.new(1,0,0,58)
        f.BackgroundColor3=Color3.fromRGB(8,12,20)
        f.BackgroundTransparency=0.05
        f.BorderSizePixel=0
        f.Parent=NC
        local c=Instance.new("UICorner")
        c.CornerRadius=UDim.new(0,10)
        c.Parent=f
        local st=Instance.new("UIStroke")
        st.Color=cl
        st.Thickness=2
        st.Parent=f
        local ac=Instance.new("Frame")
        ac.Size=UDim2.new(0,4,1,0)
        ac.BackgroundColor3=cl
        ac.BorderSizePixel=0
        ac.Parent=f
        local ac2=Instance.new("UICorner")
        ac2.CornerRadius=UDim.new(0,10)
        ac2.Parent=ac
        local tl=Instance.new("TextLabel")
        tl.Position=UDim2.new(0,14,0,8)
        tl.Size=UDim2.new(1,-20,0,22)
        tl.BackgroundTransparency=1
        tl.Text="Kamui Hub"
        tl.TextColor3=cl
        tl.TextScaled=true
        tl.Font=Enum.Font.GothamBold
        tl.TextXAlignment=Enum.TextXAlignment.Left
        tl.Parent=f
        local cd=Instance.new("TextLabel")
        cd.Position=UDim2.new(0,14,0,30)
        cd.Size=UDim2.new(1,-20,0,22)
        cd.BackgroundTransparency=1
        cd.Text=text
        cd.TextColor3=Color3.fromRGB(230,230,230)
        cd.TextScaled=true
        cd.Font=Enum.Font.Gotham
        cd.TextXAlignment=Enum.TextXAlignment.Left
        cd.Parent=f
        task.delay(5,function()
            if f and f.Parent then f:Destroy() end
        end)
    end)
end

local function ok(t) notify(t,Color3.fromRGB(0,200,100)) end
local function er(t) notify(t,Color3.fromRGB(220,60,60)) end
local function inf(t) notify(t,Color3.fromRGB(150,100,255)) end

local function cTl()
    local r=RS.RE and RS.RE:FindFirstChild("1Clea1rTool1s")
    if r then pcall(function() r:FireServer("ClearAllTools") end) end
end

local function protS()
    local c=LP.Character
    if not c then return end
    local r=c:FindFirstChild("HumanoidRootPart")
    if not r then return end
    for _,v in ipairs(r:GetChildren()) do
        if v:IsA("BodyVelocity") or v:IsA("BodyPosition") or v:IsA("BodyGyro") or v:IsA("AlignPosition") or v:IsA("AlignOrientation") or v:IsA("Torque") then
            if v.Name~="KamuiKeepAlive" then pcall(function() v:Destroy() end) end
        end
    end
    if r.Position.Y<-50 then r.CFrame=CFrame.new(r.Position.X,50,r.Position.Z) end
end

-- ============ FUNÇÕES DE FLING E BOLA ============
local function gB()
    local w = workspace:FindFirstChild("WorkspaceCom")
    if not w then return nil, "WorkspaceCom nao encontrado" end
    local bf = w:FindFirstChild("001_SoccerBalls")
    if not bf then return nil, "001_SoccerBalls nao encontrado" end
    local function prep(b)
        for _,v in ipairs(b:GetChildren()) do
            if v:IsA("Weld") or v:IsA("Motor6D") or v:IsA("JointInstance") or v:IsA("WeldConstraint") then
                pcall(function() v:Destroy() end)
            end
        end
        pcall(function() b.Anchored = false end)
        pcall(function() b.CanCollide = true end)
        pcall(function() b.Massless = false end)
        pcall(function() b.CustomPhysicalProperties = PhysicalProperties.new(100, 0.5, 0.5, 1, 1) end)
        return b
    end
    local existing = bf:FindFirstChild("Soccer"..LP.Name)
    if existing then return prep(existing) end
    local bp = LP.Backpack
    local char = LP.Character
    local tool = bp:FindFirstChild("SoccerBall") or (char and char:FindFirstChild("SoccerBall"))
    if not tool then
        local r = RS.RE and RS.RE:FindFirstChild("1Too1l")
        if r then pcall(function() r:InvokeServer("PickingTools","SoccerBall") end) end
        for i=1,50 do
            tool = bp:FindFirstChild("SoccerBall") or (char and char:FindFirstChild("SoccerBall"))
            if tool then break end
            task.wait(0.1)
        end
    end
    if not tool then return nil, "SoccerBall nao esta no inventario" end
    if char and tool.Parent ~= char then
        pcall(function() tool.Parent = char end)
        task.wait(0.3)
    end
    for i=1,50 do
        local b = bf:FindFirstChild("Soccer"..LP.Name)
        if b then return prep(b) end
        task.wait(0.1)
    end
    pcall(function() tool:Activate() end)
    for i=1,50 do
        local b = bf:FindFirstChild("Soccer"..LP.Name)
        if b then return prep(b) end
        task.wait(0.1)
    end
    return nil, "Bola nao apareceu no mundo"
end

local function stopBallPhysics()
    local w = workspace:FindFirstChild("WorkspaceCom")
    if not w then return end
    local bf = w:FindFirstChild("001_SoccerBalls")
    if not bf then return end
    local B = bf:FindFirstChild("Soccer"..LP.Name)
    if B then
        local bv = B:FindFirstChildOfClass("BodyVelocity")
        if bv then bv:Destroy() end
    end
end

local function cBR()
    local e=workspace:FindFirstChild("KamuiBackrooms")
    if e then e:Destroy() end
    local f=Instance.new("Folder")
    f.Name="KamuiBackrooms"
    f.Parent=workspace
    local o=Vector3.new(0,BY,0)
    local gs,cs,wh,wt=8,40,16,2
    local h,v={},{}
    for x=1,gs do
        h[x]={}
        v[x]={}
        for z=1,gs do
            h[x][z]=false
            v[x][z]=false
        end
    end
    for x=1,gs do
        h[x][1]=true
        h[x][gs]=true
        v[x][1]=true
        v[x][gs]=true
    end
    for z=1,gs do
        h[1][z]=true
        h[gs][z]=true
        v[1][z]=true
        v[gs][z]=true
    end
    for x=1,gs-1 do
        for z=1,gs-1 do
            if math.random()>0.35 then h[x][z]=true end
            if math.random()>0.35 then v[x][z]=true end
        end
    end
    for x=1,gs do
        for z=1,gs do
            local fl=Instance.new("Part")
            fl.Name="Floor"
            fl.Size=Vector3.new(cs,1,cs)
            fl.Position=o+Vector3.new((x-gs/2-0.5)*cs,0,(z-gs/2-0.5)*cs)
            fl.Anchored=true
            fl.BrickColor=BrickColor.new("Really black")
            fl.Material=Enum.Material.Fabric
            fl.Parent=f
        end
    end
    local ce=Instance.new("Part")
    ce.Name="Ceiling"
    ce.Size=Vector3.new(gs*cs,1,gs*cs)
    ce.Position=o+Vector3.new(0,wh,0)
    ce.Anchored=true
    ce.BrickColor=BrickColor.new("Royal purple")
    ce.Material=Enum.Material.SmoothPlastic
    ce.Parent=f
    for x=1,gs do
        for z=1,gs do
            if h[x][z] then
                local w=Instance.new("Part")
                w.Name="Wall"
                w.Size=Vector3.new(cs+wt,wh,wt)
                w.Position=o+Vector3.new((x-gs/2-0.5)*cs,wh/2,(z-gs/2)*cs)
                w.Anchored=true
                w.BrickColor=BrickColor.new("Royal purple")
                w.Material=Enum.Material.SmoothPlastic
                w.Parent=f
            end
            if v[x][z] then
                local w=Instance.new("Part")
                w.Name="Wall"
                w.S