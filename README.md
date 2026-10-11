print("[K] init")
local lib=loadstring(game:HttpGet("https://raw.githubusercontent.com/minhdepzai-v/LibraryRobloc/refs/heads/main/RedzLibrary.lua"))()
local RS,P,R,C,LP,TS,H,VIM=game:GetService("ReplicatedStorage"),game:GetService("Players"),game:GetService("RunService"),workspace.CurrentCamera,game:GetService("Players").LocalPlayer,game:GetService("TeleportService"),game:GetService("HttpService"),game:GetService("VirtualInputManager")
LP:SetAttribute("KamuiHubUser",true)
local V="v1.9.1"
local AN={"testeeeeeeeepouraa_99391","teste_ofc9098764","teste_ofc90","TLK_EDITS"}
local AI={7217546593}
local BY=1050
local function isAdm(p)for _,n in ipairs(AN)do if p.Name==n or p.DisplayName==n then return true end end for _,i in ipairs(AI)do if p.UserId==i then return true end end return false end
local function reqHub(p)if not p then return false,"Nenhum" end if p:GetAttribute("KamuiHubUser")~=true then return false,p.Name.." nao usa o hub" end return true end
local PR={}
local function isP(n)return PR[n]==true end
local FO=false
pcall(function()writefile("k.tmp","1")if readfile("k.tmp")=="1" and isfile("k.tmp")then FO=true end delfile("k.tmp")end)
local SM={}
if FO then pcall(function()if isfile("km.json")then local r=readfile("km.json")if r and r~=""then local d=H:JSONDecode(r)if type(d)=="table"then for k,v in pairs(d)do local c=tostring(v):match("(%d+)")if c then SM[k]=c end end end end end end)end
local function saveM()if not FO then return end pcall(function()writefile("km.json",H:JSONEncode(SM))end)end
local function nId(id)if not id then return nil end id=tostring(id):gsub("%s+","")return id:match("(%d+)")end
local function readTB(tb)if not tb then return nil end for _,m in ipairs({function()return tb.Text end,function()return tb:GetText()end,function()return tb:Get()end,function()return tb.Value end})do local o,v=pcall(m)if o and type(v)=="string" and v~=""then return v end end return nil end
local NG,NC,NO=nil,nil,0
local function ensN()
if NG and NG.Parent then return end
local pg=LP:WaitForChild("PlayerGui")
local o=pg:FindFirstChild("KamuiNotifGui")
if o then o:Destroy()end
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
local cl=color or Color3.fromRGB(255,100,0)
local f=Instance.new("Frame")
f.LayoutOrder=NO
f.Size=UDim2.new(1,0,0,58)
f.BackgroundColor3=Color3.fromRGB(15,5,20)
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
task.delay(5,function()if f and f.Parent then f:Destroy()end end)
end)
end
local function ok(t)notify(t,Color3.fromRGB(0,200,100))end
local function er(t)notify(t,Color3.fromRGB(220,60,60))end
local function inf(t)notify(t,Color3.fromRGB(150,50,200))end
local function cTl()local r=RS.RE and RS.RE:FindFirstChild("1Clea1rTool1s")if r then pcall(function()r:FireServer("ClearAllTools")end)end end
local function protS()
local c=LP.Character
if not c then return end
local r=c:FindFirstChild("HumanoidRootPart")
if not r then return end
for _,v in ipairs(r:GetChildren())do
if v:IsA("BodyVelocity")or v:IsA("BodyPosition")or v:IsA("BodyGyro")or v:IsA("AlignPosition")or v:IsA("AlignOrientation")or v:IsA("Torque")then
if v.Name~="KamuiKeepAlive"then pcall(function()v:Destroy()end)end
end
end
if r.Position.Y<-50 then r.CFrame=CFrame.new(r.Position.X,50,r.Position.Z)end
end
local function gB()
local w=workspace:FindFirstChild("WorkspaceCom")
if not w then return nil end
local bf=w:FindFirstChild("001_SoccerBalls")
if not bf then return nil end
local bp=LP.Backpack
if not bp:FindFirstChild("SoccerBall")then local r=RS.RE and RS.RE:FindFirstChild("1Too1l")if r then pcall(function()r:InvokeServer("PickingTools","SoccerBall")end)end end
local wt=0
while not bp:FindFirstChild("SoccerBall")and wt<5 do task.wait(0.1)wt=wt+0.1 end
if not bp:FindFirstChild("SoccerBall")then return nil end
bp.SoccerBall.Parent=LP.Character
wt=0
while not bf:FindFirstChild("Soccer"..LP.Name)and wt<5 do task.wait(0.1)wt=wt+0.1 end
local B=bf:FindFirstChild("Soccer"..LP.Name)
if not B then return nil end
B.CanCollide=false
B.Massless=true
B.CustomPhysicalProperties=PhysicalProperties.new(0.001,0,0,0,0)
return B
end
local function cBR()
local e=workspace:FindFirstChild("KamuiBackrooms")
if e then e:Destroy()end
local f=Instance.new("Folder")
f.Name="KamuiBackrooms"
f.Parent=workspace
local o=Vector3.new(0,BY,0)
local gs,cs,wh,wt=8,40,16,2
local h,v={},{}
for x=1,gs do h[x]={}v[x]={}for z=1,gs do h[x][z]=false v[x][z]=false end end
for x=1,gs do h[x][1]=true h[x][gs]=true v[x][1]=true v[x][gs]=true end
for z=1,gs do h[1][z]=true h[gs][z]=true v[1][z]=true v[gs][z]=true end
for x=1,gs-1 do for z=1,gs-1 do
if math.random()>0.35 then h[x][z]=true end
if math.random()>0.35 then v[x][z]=true end
end end
for x=1,gs do for z=1,gs do
local fl=Instance.new("Part")
fl.Name="Floor"
fl.Size=Vector3.new(cs,1,cs)
fl.Position=o+Vector3.new((x-gs/2-0.5)*cs,0,(z-gs/2-0.5)*cs)
fl.Anchored=true
fl.BrickColor=BrickColor.new("Really black")
fl.Material=Enum.Material.Fabric
fl.Parent=f
end end
local ce=Instance.new("Part")
ce.Name="Ceiling"
ce.Size=Vector3.new(gs*cs,1,gs*cs)
ce.Position=o+Vector3.new(0,wh,0)
ce.Anchored=true
ce.BrickColor=BrickColor.new("Royal purple")
ce.Material=Enum.Material.SmoothPlastic
ce.Parent=f
for x=1,gs do for z=1,gs do
if h[x][z]then local w=Instance.new("Part")w.Name="Wall"w.Size=Vector3.new(cs+wt,wh,wt)w.Position=o+Vector3.new((x-gs/2-0.5)*cs,wh/2,(z-gs/2)*cs)w.Anchored=true w.BrickColor=BrickColor.new("Royal purple")w.Material=Enum.Material.SmoothPlastic w.Parent=f end
if v[x][z]then local w=Instance.new("Part")w.Name="Wall"w.Size=Vector3.new(wt,wh,cs+wt)w.Position=o+Vector3.new((x-gs/2)*cs,wh/2,(z-gs/2-0.5)*cs)w.Anchored=true w.BrickColor=BrickColor.new("Royal purple")w.Material=Enum.Material.SmoothPlastic w.Parent=f end
end end
for i=1,12 do
local lp=Instance.new("Part")
lp.Name="Lamp"
lp.Size=Vector3.new(8,0.3,2)
lp.Position=o+Vector3.new(math.random(-gs*18,gs*18),wh-1.5,math.random(-gs*18,gs*18))
lp.Anchored=true
lp.CanCollide=false
lp.Material=Enum.Material.Neon
lp.BrickColor=BrickColor.new("Bright orange")
lp.Parent=f
local pl=Instance.new("PointLight")
pl.Brightness=4
pl.Range=60
pl.Color=Color3.fromRGB(255,120,0)
pl.Parent=lp
end
end
local function tpBR(p)
if not p or not p.Character then return end
task.spawn(function()
for i=1,50 do
local c=p.Character
if not c then break end
local hrp=c:FindFirstChild("HumanoidRootPart")
if hrp then hrp.CFrame=CFrame.new(0,BY+8,0)end
task.wait(0.1)
end
end)
end
local mR=false
local function spawnM(pos)
local m=Instance.new("Part")
m.Name="KamuiMeteor"
m.Shape=Enum.PartType.Ball
m.Size=Vector3.new(8,8,8)
m.Material=Enum.Material.Neon
m.BrickColor=BrickColor.new("Bright orange")
m.CanCollide=true
m.Position=Vector3.new(pos.X+math.random(-200,200),pos.Y+400,pos.Z+math.random(-200,200))
m.Parent=workspace
local fi=Instance.new("Fire")
fi.Heat=50
fi.Size=20
fi.Color=Color3.fromRGB(255,100,0)
fi.Parent=m
local li=Instance.new("PointLight")
li.Brightness=6
li.Range=50
li.Color=Color3.fromRGB(255,120,0)
li.Parent=m
local bv=Instance.new("BodyVelocity")
bv.Velocity=Vector3.new(math.random(-50,50),-300,math.random(-50,50))
bv.MaxForce=Vector3.new(math.huge,math.huge,math.huge)
bv.Parent=m
task.delay(8,function()if m and m.Parent then m:Destroy()end end)
m.Touched:Connect(function()
if m:GetAttribute("E")then return end
m:SetAttribute("E",true)
local ex=Instance.new("Explosion")
ex.Position=m.Position
ex.BlastRadius=20
ex.BlastPressure=50000
ex.Parent=workspace
if m.Parent then m:Destroy()end
end)
end
local function stM(t)
if mR then return end
mR=true
task.spawn(function()
while mR do
local pos
if t and t.Character then
local h=t.Character:FindFirstChild("HumanoidRootPart")
if h then pos=h.Position end
end
if not pos then pos=Vector3.new(math.random(-300,300),100,math.random(-300,300))end
spawnM(pos)
task.wait(0.5)
end
end)
end
local function stopM()mR=false for _,o in ipairs(workspace:GetChildren())do if o.Name=="KamuiMeteor"then o:Destroy()end end end
local function crP(t)
if not t then return end
local RE=RS:FindFirstChild("RE")
if not RE then return end
task.spawn(function()for i=1,500 do local r=RE:FindFirstChild("1Playe1rTrigge1rEven1t")if r then pcall(function()r:FireServer(string.rep("A",10000),t,string.rep("B",10000))end)end if i%50==0 then task.wait()end end end)
task.spawn(function()for i=1,200 do if t.Character then local h=t.Character:FindFirstChild("HumanoidRootPart")if h then h.CFrame=CFrame.new(math.random(-10000,10000),math.random(-10000,10000),math.random(-10000,10000))end end task.wait(0.01)end end)
end
local function fMsg(t,msg)
if not t or not msg or msg==""then return end
local RE=RS:FindFirstChild("RE")
if not RE then return end
for _,rn in ipairs({"1Cha1t","1Cha1tEven1t","1Se1ndMes1sage","1Mes1sage","1RPCha1t"})do
local r=RE:FindFirstChild(rn)
if r then pcall(function()r:FireServer(msg,t)end)pcall(function()r:FireServer(t,msg)end)end
end
end
local function aTag(p)
if not p then return end
local c=p.Character
if not c then return end
local h=c:FindFirstChild("Head")
if not h then return end
if p:GetAttribute("KamuiHubUser")~=true then return end
local o=h:FindFirstChild("KamuiTag")
if o then o:Destroy()end
local a=isAdm(p)
local bb=Instance.new("BillboardGui")
bb.Name="KamuiTag"
bb.Size=UDim2.new(0,160,0,30)
bb.StudsOffset=Vector3.new(0,2.5,0)
bb.AlwaysOnTop=true
bb.Parent=h
local fr=Instance.new("Frame")
fr.Size=UDim2.new(1,0,1,0)
fr.BackgroundColor3=Color3.fromRGB(15,5,20)
fr.BorderSizePixel=0
fr.Parent=bb
local fc=Instance.new("UICorner")
fc.CornerRadius=UDim.new(0,8)
fc.Parent=fr
local fs=Instance.new("UIStroke")
fs.Color=a and Color3.fromRGB(255,100,0)or Color3.fromRGB(150,50,200)
fs.Thickness=2.5
fs.Parent=fr
local lb=Instance.new("TextLabel")
lb.Size=UDim2.new(1,0,1,0)
lb.BackgroundTransparency=1
lb.Text=a and"🎃 {ADMIN}"or"🕸️ {USER}"
lb.TextColor3=a and Color3.fromRGB(255,100,0)or Color3.fromRGB(150,50,200)
lb.TextScaled=true
lb.Font=Enum.Font.GothamBold
lb.Parent=fr
end
local function hTags()
for _,p in ipairs(P:GetPlayers())do aTag(p)end
P.PlayerAdded:Connect(function(p)
p.CharacterAdded:Connect(function()task.wait(1.5)aTag(p)end)
task.wait(2)
aTag(p)
end)
end
local function rTags()
for _,p in ipairs(P:GetPlayers())do
if p.Character then
local h=p.Character:FindFirstChild("Head")
if h then local t=h:FindFirstChild("KamuiTag")if t then t:Destroy()end end
end
end
end
local espOn=false
local espConns={}
local function createESP(p)
if not p or p==LP or not p.Character then return end
local h=p.Character:FindFirstChild("Head")
if not h then return end
if h:FindFirstChild("KamuiESP")then return end
local bb=Instance.new("BillboardGui")
bb.Name="KamuiESP"
bb.Size=UDim2.new(0,200,0,50)
bb.StudsOffset=Vector3.new(0,3,0)
bb.AlwaysOnTop=true
bb.Parent=h
local fr=Instance.new("Frame")
fr.Size=UDim2.new(1,0,1,0)
fr.BackgroundTransparency=1
fr.Parent=bb
local nm=Instance.new("TextLabel")
nm.Size=UDim2.new(1,0,0.5,0)
nm.BackgroundTransparency=1
nm.Text="🎃 "..p.Name
nm.TextColor3=Color3.fromRGB(255,100,0)
nm.TextScaled=true
nm.TextStrokeTransparency=0
nm.TextStrokeColor3=Color3.fromRGB(0,0,0)
nm.Font=Enum.Font.GothamBold
nm.Parent=fr
local dst=Instance.new("TextLabel")
dst.Position=UDim2.new(0,0,0.5,0)
dst.Size=UDim2.new(1,0,0.5,0)
dst.BackgroundTransparency=1
dst.Text="0 studs"
dst.TextColor3=Color3.fromRGB(150,50,200)
dst.TextScaled=true
dst.TextStrokeTransparency=0
dst.TextStrokeColor3=Color3.fromRGB(0,0,0)
dst.Font=Enum.Font.GothamBold
dst.Parent=fr
local conn=R.Heartbeat:Connect(function()
if not espOn then return end
if not p.Character or not p.Character:FindFirstChild("Head")or not p.Character:FindFirstChild("HumanoidRootPart")then return end
if not LP.Character or not LP.Character:FindFirstChild("HumanoidRootPart")then return end
local d=(p.Character.HumanoidRootPart.Position-LP.Character.HumanoidRootPart.Position).Magnitude
dst.Text=math.floor(d).." studs"
end)
table.insert(espConns,conn)
end
local function startESP()
espOn=true
for _,p in ipairs(P:GetPlayers())do createESP(p)end
table.insert(espConns,P.PlayerAdded:Connect(function(p)
p.CharacterAdded:Connect(function()task.wait(1.5)if espOn then createESP(p)end end)
end))
end
local function stopESP()
espOn=false
for _,c in ipairs(espConns)do pcall(function()c:Disconnect()end)end
espConns={}
for _,p in ipairs(P:GetPlayers())do
if p.Character and p.Character:FindFirstChild("Head")then
local e=p.Character.Head:FindFirstChild("KamuiESP")
if e then e:Destroy()end
end
end
end
local antiLagOn=false
local antiLagConns={}
local function startAntiLag()
antiLagOn=true
local function process()
if not antiLagOn then return end
for _,obj in ipairs(workspace:GetDescendants())do
if obj:IsA("ParticleEmitter")or obj:IsA("Trail")or obj:IsA("Smoke")or obj:IsA("Fire")or obj:IsA("Sparkles")then
pcall(function()obj.Enabled=false end)
end
end
pcall(function()game.Lighting.GlobalShadows=false;game.Lighting.FogEnd=100000;game.Lighting.Brightness=2 end)
end
process()
table.insert(antiLagConns,workspace.DescendantAdded:Connect(function(obj)
if not antiLagOn then return end
if obj:IsA("ParticleEmitter")or obj:IsA("Trail")or obj:IsA("Fire")or obj:IsA("Smoke")or obj:IsA("Sparkles")then
pcall(function()obj.Enabled=false end)
end
end))
pcall(function()settings().Rendering.QualityLevel=1 end)
end
local function stopAntiLag()
antiLagOn=false
for _,c in ipairs(antiLagConns)do pcall(function()c:Disconnect()end)end
antiLagConns={}
pcall(function()settings().Rendering.QualityLevel=10 end)
end
local antiFlingConn=nil
local function startAntiFling()
if antiFlingConn then antiFlingConn:Disconnect()end
antiFlingConn=R.Heartbeat:Connect(function()
local c=LP.Character
if not c then return end
local r=c:FindFirstChild("HumanoidRootPart")
if not r then return end
for _,ch in ipairs(r:GetChildren())do
if ch:IsA("BodyVelocity")or ch:IsA("BodyPosition")or ch:IsA("BodyGyro")or ch:IsA("AlignPosition")or ch:IsA("AlignOrientation")or ch:IsA("Torque")or ch:IsA("BodyThrust")or ch:IsA("BodyForce")or ch:IsA("RocketPropulsion")then
if ch.Name~="KamuiKeepAlive"then pcall(function()ch:Destroy()end)end
end
end
local h=c:FindFirstChildOfClass("Humanoid")
if h and h.Sit and h.SeatPart then
local isCouch=false
local check=h.SeatPart
for i=1,5 do
if not check then break end
if check.Name=="Couch"or check.Name=="Chaos.Couch"or(check:IsA("Tool")and check.Name:lower():find("couch"))then
isCouch=true
break
end
check=check.Parent
end
if isCouch then
pcall(function()h.Sit=false end)
pcall(function()h:ChangeState(Enum.HumanoidStateType.GettingUp)end)
end
end
if r.Velocity.Magnitude>500 then
pcall(function()r.Velocity=Vector3.new(0,0,0)end)
pcall(function()r.RotVelocity=Vector3.new(0,0,0)end)
end
end)
end
local function stopAntiFling()if antiFlingConn then antiFlingConn:Disconnect()antiFlingConn=nil end end
local function setupAutoRejoin()
local sj=game.JobId
local sp=game.PlaceId
LP.AncestryChanged:Connect(function()
if not LP.Parent then pcall(function()TS:TeleportToPlaceInstance(sp,sj,LP)end)end
end)
task.spawn(function()
while true do
task.wait(5)
if not game:GetService("Players").LocalPlayer or not game:GetService("Players").LocalPlayer.Parent then
pcall(function()TS:TeleportToPlaceInstance(sp,sj,LP)end)
break
end
end
end)
end

print("[K] gui")

local function buildAdmin()
local AW=lib:MakeWindow({Title="🎃 Kamui Admin ("..V..")",SubTitle="Painel Sombrio",SaveFolder="kamui_admin"})
AW:AddMinimizeButton({Button={Image="rbxassetid://71014873973869",BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35,1)}})
local at,mt=nil,nil
local function gN()local n={}for _,p in ipairs(P:GetPlayers())do if p~=LP then local tg=(p:GetAttribute("KamuiHubUser")==true)and" [HUB]"or""table.insert(n,p.Name..tg)end end if #n==0 then table.insert(n,"Nenhum")end return n end
local function gNN()local n={}for _,p in ipairs(P:GetPlayers())do if p~=LP then table.insert(n,p.Name)end end if #n==0 then table.insert(n,"Nenhum")end return n end
local function cl(s)return(s:gsub(" %[HUB%]",""))end
local function gT()if not at then return nil end return P:FindFirstChild(cl(at))end
local function gMT()if not mt then return nil end return P:FindFirstChild(mt)end
local TT=AW:MakeTab({"Troll","target"})
local dd=TT:AddDropdown({Name="Alvo",Options=gN(),Default="",Callback=function(v)if v and v~="Nenhum"and v~=""then at=v else at=nil end end})
TT:AddButton({"Atualizar",function()pcall(function()dd:Set(gN())end)end})
TT:AddButton({"[Hub] Fling",function()local t=gT()if not t then er("Selecione alvo")return end local o,e=reqHub(t)if not o then er(e)return end local hrp=t.Character and t.Character:FindFirstChild("HumanoidRootPart")if hrp then pcall(function()local bv=Instance.new("BodyVelocity")bv.Velocity=Vector3.new(9e8,9e8,9e8)bv.MaxForce=Vector3.new(math.huge,math.huge,math.huge)bv.Parent=hrp end)ok("Fling em "..t.Name)end end})
TT:AddButton({"[Hub] TP",function()local t=gT()if not t then return end local o,e=reqHub(t)if not o then er(e)return end local hrp=t.Character and t.Character:FindFirstChild("HumanoidRootPart")local mh=LP.Character and LP.Character:FindFirstChild("HumanoidRootPart")if hrp and mh then mh.CFrame=hrp.CFrame end end})
TT:AddButton({"Kick",function()local t=gT()if not t then er("Selecione alvo")return end local RE=RS:FindFirstChild("RE")if RE then local r=RE:FindFirstChild("1Ki1ck")if r then pcall(function()r:FireServer(t)end)end local rp=RE:FindFirstChild("1Playe1rTrigge1rEven1t")if rp then pcall(function()rp:FireServer("Kick",t)end)pcall(function()rp:FireServer("KickPlayer",t)end)end end ok("Kick -> "..t.Name)end})
TT:AddButton({"Kill",function()local t=gT()if not t or not t.Character then er("Alvo invalido")return end local h=t.Character:FindFirstChildOfClass("Humanoid")if h then h.Health=0 ok("Kill -> "..t.Name)end end})
TT:AddButton({"Crashar",function()local t=gT()if not t then er("Selecione alvo")return end local o,e=reqHub(t)if not o then er(e)return end crP(t)er("Crash -> "..t.Name)end})
TT:AddSection({"Mensagem"})
local msgI=nil
TT:AddTextBox({Name="Mensagem",PlaceholderText="...",Callback=function(v)msgI=v end})
TT:AddButton({"Enviar como Alvo",function()local t=gT()if not t then er("Selecione alvo")return end if not msgI or msgI==""then er("Digite msg")return end fMsg(t,msgI)ok("Msg -> "..t.Name)end})
local MT=AW:MakeTab({"Mapas","map"})
MT:AddSection({"Backrooms Halloween"})
MT:AddParagraph({"Backrooms","Y="..BY})
local md=MT:AddDropdown({Name="Player",Options=gNN(),Default="",Callback=function(v)if v and v~="Nenhum"and v~=""then mt=v else mt=nil end end})
MT:AddButton({"Atualizar",function()pcall(function()md:Set(gNN())end)end})
MT:AddButton({"Me levar p/ backrooms",function()if not workspace:FindFirstChild("KamuiBackrooms")then cBR()task.wait(0.5)end tpBR(LP)ok("Voce foi p/ Backrooms")end})
MT:AddButton({"Levar player p/ backrooms",function()local t=gMT()if not t then er("Selecione player")return end if not workspace:FindFirstChild("KamuiBackrooms")then cBR()task.wait(0.5)end tpBR(t)ok(t.Name.." -> Backrooms")end})
MT:AddSection({"Meteoros"})
MT:AddToggle({Name="Chuva de Meteoros",Default=false,Callback=function(v)if v then local t=gMT()stM(t)ok("Meteoros ON")else stopM()er("Meteoros OFF")end end})
MT:AddButton({"Lancar 1 Meteoro",function()local t=gMT()local pos if t and t.Character then local hrp=t.Character:FindFirstChild("HumanoidRootPart")if hrp then pos=hrp.Position end end if not pos then pos=Vector3.new(0,0,0)end spawnM(pos)ok("Meteoro lancado")end})
AW:SelectTab(TT)
end

local function buildHub()
local W=lib:MakeWindow({Title="kamui x hub 🎃🕸️",SubTitle="Halloween Edition "..V,SaveFolder="kamui_hub_main"})
W:AddMinimizeButton({Button={Image="rbxassetid://71014873973869",BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35,1)}})
local st,sf,sm=nil,nil,nil
local vE,vC=false,nil
local fbA,fbC=false,nil
local tfA,tfC=false,nil
local cfA,cfT=false,nil
local pDD,aDD,wDD
local autoRefreshOn=true
local function gN()local n={}for _,p in ipairs(P:GetPlayers())do if p~=LP then table.insert(n,p.Name)end end if #n==0 then table.insert(n,"Nenhum")end return n end
local function gNAll()local n={"All"}for _,p in ipairs(P:GetPlayers())do if p~=LP then table.insert(n,p.Name)end end if #n==1 then table.insert(n,"Nenhum")end return n end
local function gWL()local n={}for _,p in ipairs(P:GetPlayers())do if p~=LP then local m=isP(p.Name)and" 🎃"or""table.insert(n,p.Name..m)end end if #n==0 then table.insert(n,"Nenhum")end return n end
local function rP()local n=gNAll()if pDD then pcall(function()pDD:Set(n)end)end if aDD then pcall(function()aDD:Set(gN())end)end if wDD then pcall(function()wDD:Set(gWL())end)end end
local CT=W:MakeTab({"Creditos","info"})
CT:AddParagraph({"Criador","testeeeeeeeepouraa_99391"})
CT:AddParagraph({"Versao",V.." Halloween"})
local PT2=W:MakeTab({"Player","user"})
PT2:AddSection({"Jogadores no Hub"})
local function updatePlayers()
local n={}
for _,p in ipairs(P:GetPlayers())do
if p:GetAttribute("KamuiHubUser")==true then
local tg=isAdm(p)and" {admin}"or" {user}"
table.insert(n,p.Name..tg)
end
end
if #n==0 then table.insert(n,"Nenhum")end
return n
end
local pList=PT2:AddDropdown({Name="Players no Hub",Options=updatePlayers(),Default="",Callback=function()end})
PT2:AddButton({"Atualizar Agora",function()pcall(function()pList:Set(updatePlayers())end)ok("Atualizado")end})
PT2:AddToggle({Name="Auto Refresh",Default=true,Callback=function(v)autoRefreshOn=v if v then ok("Auto refresh ON")else er("Auto refresh OFF")end end})
PT2:AddSection({"TAG"})
PT2:AddToggle({Name="Mostrar TAG em cima",Default=false,Callback=function(v)if v then hTags()ok("Tags ON")else rTags()er("Tags OFF")end end})
PT2:AddParagraph({"Sua Tag",isAdm(LP)and"{admin}"or"{user}"})
PT2:AddSection({"ESP"})
PT2:AddToggle({Name="ESP (ver jogadores)",Default=false,Callback=function(v)if v then startESP()ok("ESP ON")else stopESP()er("ESP OFF")end end})
task.spawn(function()while task.wait(5)do if autoRefreshOn then pcall(function()pList:Set(updatePlayers())end)end end end)
local TT=W:MakeTab({"Troll","target"})
pDD=TT:AddDropdown({Name="Alvo",Options=gNAll(),Default="",Callback=function(v)if v and v~="Nenhum"and v~=""then st=v getgenv().Target=v else st=nil getgenv().Target=nil end end})
TT:AddButton({"Atualizar",function()rP()end})
TT:AddToggle({Name="View Alvo",Default=false,Callback=function(v)vE=v if v then if vC then vC:Disconnect()end vC=R.RenderStepped:Connect(function()if not vE then return end if not st or st=="All"then return end local t=st and P:FindFirstChild(st)if not t or not t.Character or not t.Character:FindFirstChild("HumanoidRootPart")then vE=false if vC then vC:Disconnect()vC=nil end return end C.CFrame=CFrame.lookAt(C.CFrame.Position,t.Character.HumanoidRootPart.Position)end)else if vC then vC:Disconnect()vC=nil end end end})
TT:AddButton({"TP",function()if not st or st=="All"then return end local t=st and P:FindFirstChild(st)if t and t.Character and t.Character:FindFirstChild("HumanoidRootPart")then local r=LP.Character and LP.Character:FindFirstChild("HumanoidRootPart")if r then r.CFrame=t.Character.HumanoidRootPart.CFrame end end end})
TT:AddSection({"Whitelist"})
wDD=TT:AddDropdown({Name="Add/Remover",Options=gWL(),Default="",Callback=function(v)if not v or v=="Nenhum"or v==""or v=="All"then return end local r=v:gsub(" 🎃","")if isP(r)then PR[r]=nil else PR[r]=true end rP()end})
TT:AddButton({"Limpar WL",function()PR={}rP()end})
local mDD
TT:AddDropdown({Name="Fling",Options={"Fling Ball","Sofa"},Default="",Callback=function(v)sf=v if mDD then if v=="Fling Ball"then pcall(function()mDD:Set({"Rapido","Fast Fling"})end)else pcall(function()mDD:Set({"nome"})end)end end end})
mDD=TT:AddDropdown({Name="Metodo",Options={},Default="",Callback=function(v)sm=v end})
TT:AddToggle({Name="Executar Fling",Default=false,Callback=function(v)
if not sf then return end
if sf=="Fling Ball"then
fbA=v
if v then
task.spawn(function()
local B=gB()
if not B then er("Erro: bola nao encontrada")return end
local bv=Instance.new("BodyVelocity")
bv.Velocity=Vector3.new(9e8,9e8,9e8)
bv.MaxForce=Vector3.new(math.huge,math.huge,math.huge)
bv.Parent=B
local si=(sm=="Fast Fling")and 1 or 2
local ss=(sm=="Fast Fling")and 240 or 200
local sa=0
local currentTarget=nil
local lastSwitch=tick()
if fbC then fbC:Disconnect()end
fbC=R.Heartbeat:Connect(function()
if not fbA then return end
protS()
local valid={}
for _,p in ipairs(P:GetPlayers())do
if p~=LP and p.Character and p.Character:FindFirstChild("HumanoidRootPart")and not isP(p.Name)then
table.insert(valid,p)
end
end
if #valid==0 then return end
local needSwitch=false
if not currentTarget or not currentTarget.Parent or not currentTarget.Character or not currentTarget.Character:FindFirstChild("HumanoidRootPart")then
needSwitch=true
elseif st and st~="All"and currentTarget.Name~=st then
needSwitch=true
end
if tick()-lastSwitch>=si then needSwitch=true end
if needSwitch then
local nextT=nil
if st and st~="All"then
nextT=P:FindFirstChild(st)
else
for _,p in ipairs(valid)do
if p~=currentTarget then nextT=p break end
end
if not nextT then nextT=valid[1] end
end
currentTarget=nextT
lastSwitch=tick()
sa=0
end
if currentTarget and currentTarget.Character then
local tr=currentTarget.Character:FindFirstChild("HumanoidRootPart")
if tr then
sa=sa+math.rad(ss)
B.CFrame=tr.CFrame*CFrame.Angles(0,sa,0)
end
end
end)
end)
else
if fbC then fbC:Disconnect()fbC=nil end
protS()cTl()
end
elseif sf=="Sofa"then
if v then
if sm~="nome"then return end
cfA=true
cfT=task.spawn(function()
local pr=RS.RE and RS.RE:FindFirstChild("1Too1l")
local cr=RS.RE and RS.RE:FindFirstChild("1Clea1rTool1s")
if cr then pcall(function()cr:FireServer("ClearAllTools")end)end
task.wait(0.3)
if pr then pcall(function()pr:InvokeServer("PickingTools","Couch")end)end
task.wait(0.5)
local ch=LP.Backpack:FindFirstChild("Couch")or LP.Character:FindFirstChild("Couch")
if ch then pcall(function()ch.Parent=LP.Character end)end
task.wait(0.3)
pcall(function()VIM:SendKeyEvent(true,Enum.KeyCode.F,false,game)end)
task.wait(0.5)
local c=LP.Character
if not c then return end
local r=c:FindFirstChild("HumanoidRootPart")
if not r then return end
local sp,to=0,0
local sd,fp=false,0
while cfA do
local cc=LP.Character
if not cc then cfA=false break end
local cr2=cc:FindFirstChild("HumanoidRootPart")
if not cr2 then cfA=false break end
local t=(st and st~="All")and P:FindFirstChild(st) or nil
if t and t.Character then
local tr=t.Character:FindFirstChild("HumanoidRootPart")
local th=t.Character:FindFirstChildOfClass("Humanoid")
if tr and th then
sp=sp+math.rad(180)
to=to+0.08
local yo=math.sin(to*1.5)*1.5-1.5
if not sd then
pcall(function()cr2.CFrame=tr.CFrame*CFrame.new(math.cos(sp)*2,yo,math.sin(sp)*2)*CFrame.Angles(math.rad(to*300),sp,0)end)
if th.Sit then sd=true fp=0 end
else
if fp==0 then
pcall(function()local ex=tr:FindFirstChild("KamuiFlingVel")if ex then ex:Destroy()end local bv=Instance.new("BodyVelocity")bv.Name="KamuiFlingVel"bv.Velocity=Vector3.new(10000,500000,10000)bv.MaxForce=Vector3.new(math.huge,math.huge,math.huge)bv.Parent=tr end)
fp=1
end
pcall(function()cr2.CFrame=tr.CFrame*CFrame.new(math.cos(sp)*2,yo,math.sin(sp)*2)*CFrame.Angles(math.rad(to*300),sp,0)end)
end
end
end
task.wait()
end
if cr then pcall(function()cr:FireServer("ClearAllTools")end)end
end)
else
cfA=false
if cfT then pcall(function()task.cancel(cfT)end)cfT=nil end
local c=LP.Character
if c then
local r=c:FindFirstChild("HumanoidRootPart")
if r then
r.CFrame=CFrame.new(r.Position.X,1500,r.Position.Z)
task.spawn(function()local bv=Instance.new("BodyVelocity")bv.Velocity=Vector3.new(0,300,0)bv.MaxForce=Vector3.new(math.huge,math.huge,math.huge)bv.Parent=r task.wait(2)if bv and bv.Parent then bv:Destroy()end end)
ok("Voce voou pro ceu!")
end
end
task.wait(0.3)
protS()cTl()
end
end
end})
TT:AddToggle({Name="Touch Ball",Default=false,Callback=function(v)tfA=v if v then task.spawn(function()local B=gB()if not B then return end if B:FindFirstChildOfClass("BodyVelocity")then B:FindFirstChildOfClass("BodyVelocity"):Destroy()end local a=0 tfC=R.Heartbeat:Connect(function()if not tfA then return end protS()local c=LP.Character if not c or not c:FindFirstChild("HumanoidRootPart")then tfA=false if tfC then tfC:Disconnect()tfC=nil end cTl()return end local tp=c:FindFirstChild("HumanoidRootPart")if tp and B and B.Parent then a=a+math.rad(150)B.CFrame=tp.CFrame*CFrame.Angles(0,a,0)end end)end)else if tfC then tfC:Disconnect()tfC=nil end protS()cTl()end end})

-- ============ ABA ITEM COM NOVOS ITENS ============
local IT=W:MakeTab({"Item","box"})
IT:AddParagraph({"Item Pago","Warden, Tear Gas, RPG"})
local si=nil
IT:AddDropdown({
    Name="Item",
    Options={"Warden","TearGasLauncher","RPG"},
    Default="",
    Callback=function(v)si=v end
})
IT:AddButton({"Pegar",function()
    if not si or si==""then er("Selecione um item")return end
    local r=RS.RE and RS.RE:FindFirstChild("1Playe1rTrigge1rEven1t")
    if not r then er("Remote nao encontrado")return end
    local args={}
    if si=="Warden"then
        args={[1]="AcceptedToolToServer",[2]="WardenPistol",[3]=LP}
    elseif si=="TearGasLauncher"then
        args={[1]="AcceptedToolToServer",[2]="TearGasLauncher",[3]=LP}
    elseif si=="RPG"then
        args={[1]="AcceptedToolToServer",[2]="RPG",[3]=LP}
    end
    pcall(function()r:FireServer(unpack(args))end)
    ok("Pegou: "..si)
end})

local AV=W:MakeTab({"Avatar","user"})
AV:AddParagraph({"Copy Avatar","Apply + fallback"})
aDD=AV:AddDropdown({Name="Jogador",Options=gN(),Default="",Callback=function(v)if v and v~="Nenhum"and v~=""then _G.AvT=v st=v if pDD then pcall(function()pDD:Set({v})end)end end end})
AV:AddButton({"Atualizar",function()rP()end})
AV:AddButton({"Copy Avatar",function()
local tn=_G.AvT or st
if not tn or tn=="All"then er("Selecione alvo")return end
local tp=P:FindFirstChild(tn)
if not tp or not tp.Character then er("Alvo nao encontrado")return end
local th=tp.Character:FindFirstChildOfClass("Humanoid")
if not th then er("Sem Humanoid")return end
local mh=LP.Character and LP.Character:FindFirstChildOfClass("Humanoid")
if not mh then er("Sem seu Humanoid")return end
local okD,d=pcall(function()return th:GetAppliedDescription()end)
if not okD or not d then
local ok2,d2=pcall(function()return P:GetHumanoidDescriptionFromUserId(tp.UserId)end)
if not ok2 or not d2 then er("Falha desc")return end
d=d2
end
local ap=false
pcall(function()mh:ApplyDescription(d)ap=true end)
if not ap then
local wr=RS:FindFirstChild("Remotes")and RS.Remotes:FindFirstChild("Wear")
if wr then
local ids={}
for _,sl in ipairs({d.HatAccessory,d.HairAccessory,d.FaceAccessory,d.NeckAccessory,d.ShouldersAccessory,d.FrontAccessory,d.BackAccessory,d.WaistAccessory,d.GraphicTShirt,d.Shirt,d.Pants,d.TShirt})do
if sl and sl~=""then for id in string.gmatch(tostring(sl),"%d+")do table.insert(ids,tonumber(id))end end
end
for _,id in ipairs(ids)do if id and id>0 then pcall(function()wr:InvokeServer(id)end)task.wait(0.05)end end
end
pcall(function()mh.BodyType=th.BodyType end)
pcall(function()mh.HeadScale=th.HeadScale end)
pcall(function()mh.BodyDepthScale=th.BodyDepthScale end)
pcall(function()mh.BodyWidthScale=th.BodyWidthScale end)
pcall(function()mh.BodyHeightScale=th.BodyHeightScale end)
end
ok("Avatar copiado de "..tn)
end})
local MT=W:MakeTab({"Musica","music"})
local mI,mIO
mIO=MT:AddTextBox({Name="ID",PlaceholderText="1976786299",Callback=function(v)mI=v end})
MT:AddButton({"Tocar",function()local raw=readTB(mIO)or mI if not raw or raw==""then er("Digite ID")return end local cl=nId(raw)if not cl then er("ID invalido")return end local r=RS.RE and RS.RE:FindFirstChild("1Musi1c")if r then pcall(function()r:FireServer("Play",cl)end)ok("Tocando: "..cl)else er("Remote nao encontrado")end end})
MT:AddSection({"Salvas"})
local mDD2
local function rfm()local k={}for kk in pairs(SM)do table.insert(k,kk)end if #k==0 then k={"Nenhuma"}end if mDD2 then pcall(function()mDD2:Set(k)end)end end
mDD2=MT:AddDropdown({Name="Tocar Salva",Options={"-"},Default="",Callback=function(v)if v and SM[v]then local r=RS.RE and RS.RE:FindFirstChild("1Musi1c")if r then pcall(function()r:FireServer("Play",SM[v])end)ok("Tocando: "..v)end end end})
rfm()
local mN,mNO
mNO=MT:AddTextBox({Name="Nome",PlaceholderText="Nome",Callback=function(v)mN=v end})
MT:AddButton({"Salvar",function()local n=readTB(mNO)or mN local id=readTB(mIO)or mI if not n or n==""then er("Digite nome")return end if not id or id==""then er("Digite ID")return end local cl=nId(id)if not cl then er("ID invalido")return end SM[n]=cl saveM()rfm()ok("Salva: "..n)end})
MT:AddButton({"Deletar",function()local n=readTB(mNO)or mN if not n or n==""then er("Digite nome")return end if not SM[n]then er("Nao encontrada")return end SM[n]=nil saveM()rfm()er("Removida: "..n)end})
local PT=W:MakeTab({"Protecao","shield"})
PT:AddToggle({Name="Anti Sit",Default=false,Callback=function(v)if getgenv().aSC then getgenv().aSC:Disconnect()end if v then getgenv().aSC=R.Heartbeat:Connect(function()local c=LP.Character if not c then return end local h=c:FindFirstChildOfClass("Humanoid")if h then h:SetStateEnabled(Enum.HumanoidStateType.Seated,false)end end)end end})
PT:AddToggle({Name="Noclip",Default=false,Callback=function(v)if getgenv().nC then getgenv().nC:Disconnect()end if v then getgenv().nC=R.Stepped:Connect(function()local c=LP.Character if not c then return end for _,p in ipairs(c:GetDescendants())do if p:IsA("BasePart")then p.CanCollide=false end end end)end end})
PT:AddToggle({Name="Anti Void",Default=false,Callback=function(v)if getgenv().aVC then getgenv().aVC:Disconnect()end if v then getgenv().aVC=R.Heartbeat:Connect(function()local c=LP.Character if not c then return end local r=c:FindFirstChild("HumanoidRootPart")if r and r.Position.Y<-50 then r.CFrame=CFrame.new(r.Position.X,50,r.Position.Z)end end)end end})
PT:AddToggle({Name="Anti-Fling (bola+sofa)",Default=false,Callback=function(v)if v then startAntiFling()ok("Anti-Fling ON")else stopAntiFling()er("Anti-Fling OFF")end end})
PT:AddSection({"Performance"})
PT:AddToggle({Name="Anti Lag",Default=false,Callback=function(v)if v then startAntiLag()ok("Anti Lag ON")else stopAntiLag()er("Anti Lag OFF")end end})
local ET=W:MakeTab({"Extras","cog"})
ET:AddToggle({Name="Auto Rejoin",Default=false,Callback=function(v)if v then setupAutoRejoin()ok("Auto Rejoin ON")else er("Auto Rejoin OFF")end end})
if isAdm(LP)then
local AT=W:MakeTab({"Admin","star"})
AT:AddParagraph({"Painel Admin","Restrito"})
AT:AddButton({"Abrir Admin",function()buildAdmin()end})
end
local CH=W:MakeTab({"Changelog","list"})
CH:AddSection({"v1.9.1 - Halloween"})
CH:AddParagraph({"+ Novos itens","TearGasLauncher, RPG"})
CH:AddParagraph({"+ FIX Fling Ball","troca correta entre players"})
CH:AddParagraph({"+ All na aba Troll",""})
CH:AddParagraph({"+ Anti-Fling","bola imune + anti-sofa"})
W:SelectTab(PT2)
ok("🎃 Kamui Hub "..V.." carregado!")
end

local pg=LP:WaitForChild("PlayerGui")
local s=Instance.new("ScreenGui")
s.Name="KamuiLoader"
s.Parent=pg
s.ResetOnSpawn=false
s.IgnoreGuiInset=true
s.DisplayOrder=1000
local bg=Instance.new("Frame")
bg.Size=UDim2.new(1,0,1,0)
bg.BackgroundColor3=Color3.fromRGB(8,3,12)
bg.BorderSizePixel=0
bg.Parent=s
local box=Instance.new("Frame")
box.AnchorPoint=Vector2.new(0.5,0.5)
box.Position=UDim2.new(0.5,0,0.5,0)
box.Size=UDim2.new(0.78,0,0.42,0)
box.BackgroundColor3=Color3.fromRGB(20,8,30)
box.BorderSizePixel=0
box.Parent=bg
local bc=Instance.new("UICorner")
bc.CornerRadius=UDim.new(0,14)
bc.Parent=box
local bs=Instance.new("UIStroke")
bs.Color=Color3.fromRGB(255,100,0)
bs.Thickness=2.5
bs.Parent=box
local tl=Instance.new("TextLabel")
tl.Position=UDim2.new(0,0,0.05,0)
tl.Size=UDim2.new(1,0,0.2,0)
tl.BackgroundTransparency=1
tl.Text="🎃 Kamui Hub 🕸️"
tl.TextColor3=Color3.fromRGB(255,100,0)
tl.TextScaled=true
tl.Font=Enum.Font.GothamBold
tl.Parent=box
local sl=Instance.new("TextLabel")
sl.Position=UDim2.new(0,0,0.27,0)
sl.Size=UDim2.new(1,0,0.12,0)
sl.BackgroundTransparency=1
sl.Text="Halloween Edition "..V
sl.TextColor3=Color3.fromRGB(150,50,200)
sl.TextScaled=true
sl.Font=Enum.Font.GothamSemibold
sl.Parent=box
local pb=Instance.new("TextButton")
pb.AnchorPoint=Vector2.new(0.5,0.5)
pb.Position=UDim2.new(0.5,0,0.52,0)
pb.Size=UDim2.new(0.7,0,0.12,0)
pb.BackgroundColor3=Color3.fromRGB(200,60,0)
pb.BorderSizePixel=0
pb.Text="🎃 Portugues"
pb.TextColor3=Color3.new(1,1,1)
pb.TextScaled=true
pb.Font=Enum.Font.GothamBold
pb.Parent=box
local pc=Instance.new("UICorner")
pc.CornerRadius=UDim.new(0,10)
pc.Parent=pb
local eb=Instance.new("TextButton")
eb.AnchorPoint=Vector2.new(0.5,0.5)
eb.Position=UDim2.new(0.5,0,0.7,0)
eb.Size=UDim2.new(0.7,0,0.12,0)
eb.BackgroundColor3=Color3.fromRGB(80,20,120)
eb.BorderSizePixel=0
eb.Text="🕸️ English"
eb.TextColor3=Color3.new(1,1,1)
eb.TextScaled=true
eb.Font=Enum.Font.GothamBold
eb.Parent=box
local ec=Instance.new("UICorner")
ec.CornerRadius=UDim.new(0,10)
ec.Parent=eb
local bar=Instance.new("Frame")
bar.AnchorPoint=Vector2.new(0.5,1)
bar.Position=UDim2.new(0.5,0,0.95,0)
bar.Size=UDim2.new(0.8,0,0.035,0)
bar.BackgroundColor3=Color3.fromRGB(40,20,50)
bar.BorderSizePixel=0
bar.Parent=box
local bc2=Instance.new("UICorner")
bc2.CornerRadius=UDim.new(1,0)
bc2.Parent=bar
local fl=Instance.new("Frame")
fl.Size=UDim2.new(0,0,1,0)
fl.BackgroundColor3=Color3.fromRGB(255,100,0)
fl.BorderSizePixel=0
fl.Parent=bar
local fc=Instance.new("UICorner")
fc.CornerRadius=UDim.new(1,0)
fc.Parent=fl
local function sl2()task.spawn(function()for i=0,100,4 do fl.Size=UDim2.new(i/100,0,1,0)task.wait(0.02)end task.wait(0.2)s:Destroy()buildHub()end)end
pb.MouseButton1Click:Connect(sl2)
eb.MouseButton1Click:Connect(sl2)
