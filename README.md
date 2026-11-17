--[[
 .____                  ________ ___.    _____                           __                
 |    |    __ _______   \_____  \\_ |___/ ____\_ __  ______ ____ _____ _/  |_  ___________ 
 |    |   |  |  \__  \   /   |   \| __ \   __\  |  \/  ___// ___\\__  \\   __\/  _ \_  __ \
 |    |___|  |  // __ \_/    |    \ \_\ \  | |  |  /\___ \\  \___ / __ \|  | (  <_> )  | \/
 |_______ \____/(____  /\_______  /___  /__| |____//____  >\___  >____  /__|  \____/|__|   
         \/          \/         \/    \/                \/     \/     \/                   
          \_Welcome to LuaObfuscator.com   (Alpha 0.10.9) ~  Much Love, Ferib 

]]--

print("[K] init");
local urls = {"https://raw.githubusercontent.com/minhdepzai-v/LibraryRobloc/refs/heads/main/RedzLibrary.lua","https://raw.githubusercontent.com/REDzHUB/RedzLibV5/main/Source.Lua"};
local lib = nil;
for _, url in ipairs(urls) do
	local success, result = pcall(function()
		local FlatIdent_76979 = 0;
		local src;
		while true do
			if (FlatIdent_76979 == 1) then
				return loadstring(src)();
			end
			if (FlatIdent_76979 == 0) then
				src = game:HttpGet(url, true);
				if (not src or (src == "") or (src:sub(1, 3) == "404")) then
					return nil;
				end
				FlatIdent_76979 = 1;
			end
		end
	end);
	if (success and result and (type(result) == "table") and result.MakeWindow) then
		lib = result;
		break;
	end
end
if not lib then
	local FlatIdent_6D4CB = 0;
	while true do
		if (FlatIdent_6D4CB == 0) then
			pcall(function()
				game:GetService("StarterGui"):SetCore("SendNotification", {Title="Kamui Hub",Text="Falha ao carregar a biblioteca.",Duration=5});
			end);
			return;
		end
	end
end
local RS, P, R, C, LP, TS, H, VIM = game:GetService("ReplicatedStorage"), game:GetService("Players"), game:GetService("RunService"), workspace.CurrentCamera, game:GetService("Players").LocalPlayer, game:GetService("TeleportService"), game:GetService("HttpService"), game:GetService("VirtualInputManager");
local INS, PS, UIS, L, SS, GS = game:GetService("InsertService"), game:GetService("PhysicsService"), game:GetService("UserInputService"), game:GetService("Lighting"), game:GetService("SoundService"), game:GetService("GuiService");
if (game.PlaceId ~= 4924922222) then
	local pg = LP:WaitForChild("PlayerGui", 15);
	if pg then
		local FlatIdent_10BCC = 0;
		local sg;
		local f;
		local b;
		local st;
		local lbl;
		while true do
			if (FlatIdent_10BCC == 3) then
				b.Size = UDim2.new(0.6, 0, 0.2, 0);
				b.BackgroundColor3 = Color3.fromRGB(20, 20, 30);
				Instance.new("UICorner", b).CornerRadius = UDim.new(0, 12);
				FlatIdent_10BCC = 4;
			end
			if (FlatIdent_10BCC == 1) then
				f = Instance.new("Frame", sg);
				f.Size = UDim2.new(1, 0, 1, 0);
				f.BackgroundColor3 = Color3.fromRGB(10, 10, 15);
				FlatIdent_10BCC = 2;
			end
			if (6 == FlatIdent_10BCC) then
				lbl.Text = "Kamui x Hub only works in Brookhaven RP";
				lbl.TextColor3 = Color3.fromRGB(0, 150, 255);
				lbl.TextScaled = true;
				FlatIdent_10BCC = 7;
			end
			if (FlatIdent_10BCC == 7) then
				lbl.Font = Enum.Font.GothamBold;
				break;
			end
			if (FlatIdent_10BCC == 5) then
				lbl = Instance.new("TextLabel", b);
				lbl.Size = UDim2.new(1, 0, 0.6, 0);
				lbl.BackgroundTransparency = 1;
				FlatIdent_10BCC = 6;
			end
			if (FlatIdent_10BCC == 4) then
				st = Instance.new("UIStroke", b);
				st.Color = Color3.fromRGB(0, 150, 255);
				st.Thickness = 2;
				FlatIdent_10BCC = 5;
			end
			if (FlatIdent_10BCC == 0) then
				sg = Instance.new("ScreenGui", pg);
				sg.IgnoreGuiInset = true;
				sg.DisplayOrder = 99999;
				FlatIdent_10BCC = 1;
			end
			if (FlatIdent_10BCC == 2) then
				b = Instance.new("Frame", f);
				b.AnchorPoint = Vector2.new(0.5, 0.5);
				b.Position = UDim2.new(0.5, 0, 0.5, 0);
				FlatIdent_10BCC = 3;
			end
		end
	end
	return;
end
LP:SetAttribute("KamuiHubUser", true);
pcall(function()
	local FlatIdent_61585 = 0;
	while true do
		if (1 == FlatIdent_61585) then
			PS:CollisionGroupSetCollidable("KamuiBall", "KamuiHolder", false);
			break;
		end
		if (0 == FlatIdent_61585) then
			PS:RegisterCollisionGroup("KamuiBall");
			PS:RegisterCollisionGroup("KamuiHolder");
			FlatIdent_61585 = 1;
		end
	end
end);
local clickSound = Instance.new("Sound", SS);
clickSound.SoundId = "rbxassetid://6895079853";
clickSound.Volume = 0.5;
local isBuildingHub = false;
local function playClick()
	clickSound:Play();
end
local function hookButton(btn)
	if btn:IsA("GuiButton") then
		local root = btn;
		while root.Parent and not root:IsA("ScreenGui") do
			root = root.Parent;
		end
		if (root and root:GetAttribute("KamuiHubUI")) then
			btn.MouseButton1Click:Connect(playClick);
			btn.MouseButton1Down:Connect(playClick);
		end
	end
end
LP.PlayerGui.ChildAdded:Connect(function(obj)
	if (obj:IsA("ScreenGui") and isBuildingHub) then
		obj:SetAttribute("KamuiHubUI", true);
		for _, desc in ipairs(obj:GetDescendants()) do
			hookButton(desc);
		end
	end
end);
LP.PlayerGui.DescendantAdded:Connect(function(obj)
	if obj:IsA("GuiButton") then
		local FlatIdent_1BCFB = 0;
		local root;
		while true do
			if (FlatIdent_1BCFB == 1) then
				if (root and root:GetAttribute("KamuiHubUI")) then
					hookButton(obj);
				end
				break;
			end
			if (FlatIdent_1BCFB == 0) then
				root = obj;
				while root.Parent and not root:IsA("ScreenGui") do
					root = root.Parent;
				end
				FlatIdent_1BCFB = 1;
			end
		end
	end
end);
local LANG = "pt";
local V = "v1.9.6";
local LOGO_ID = "rbxassetid://0";
local T = {pt={title="kamui x hub ⚡",sub=("Standard Edition " .. V),credits="Creditos",creator="Criador",version="Versao",discord="Discord",discord_desc="Entre no nosso Discord!",discord_copy="Copiar Link",players="Player",players_hub="Jogadores no Hub",refresh="Atualizar",auto_refresh="Auto Refresh",tag="TAG",tag_show="Mostrar TAG",your_tag="Sua Tag",esp="ESP",esp_show="ESP",troll="Troll",target="Alvo",view="View",tp="TP",wl="Whitelist",wl_add="Add/Remover",wl_clear="Limpar WL",fling="Fling",method="Metodo",exec_fling="Executar Fling",touch_ball="Touch Fling",tool_ball="Tool Ball",item="Item",item_paid="Item Pago",item_get="Pegar",avatar="Avatar",copy_avatar="Copy Avatar",avatar_player="Jogador",music="Musica",music_id="ID",music_play="Tocar",music_saved="Salvas",music_play_saved="Tocar Salva",music_name="Nome",music_save="Salvar",music_del="Deletar",prot="Protecao",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling",anti_lag="Anti Lag",performance="Performance",cfg="Configuração",extras="Extras",auto_rejoin="Auto Rejoin",open_admin="Admin Panel",admin="Admin",admin_panel="Admin",admin_open="Abrir Admin",changelog="Changelog",maps="Mapas",backrooms="Backrooms",cafe="Cafe",map_select="Mapa",map_spawn="Spawnar",admin_take_me_br="Me levar p/ backrooms",admin_take_player_br="Levar player p/ backrooms",admin_select_player="Player",meteors="Meteoros",meteor_rain="Chuva Meteoros",meteor_one="Lancar Meteoro",msg="Mensagem",msg_send="Say",select_item="Selecione",select_map="Selecione",select_target="Selecione",not_found="Nao encontrado",no_players="Nenhum",all="All",br_spawned="Backrooms ON",cafe_spawned="Cafe ON",br_failed="Falha Cafe",link_copied="Copiado!",tags_on="ON",tags_off="OFF",esp_on="ON",esp_off="OFF",refresh_done="Atualizado",antifling_on="ON",antifling_off="OFF",antilag_on="ON",antilag_off="OFF",hub_loaded=("Kamui " .. V .. " ON"),cars="Carros",coming_soon="Em breve",user_tag="{USER}",not_hub="Sem Hub",freeze="Freeze",jail="Jail",unjail="Unjail",say="Say",frozen="Congelado",jailed="Preso",unjailed="Solto",flung="Arremessado",no_target="Alvo invalido",self_target="Nao pode usar em si",need_fling_type="Selecione Fling Ball",ball_ok="Bola OK",no_ball="Sem Bola",tool_ball_on="ON ->",tool_ball_off="OFF",hd="Aplicar HD",freecam="Freecam",freecam_speed="Velocidade",rgb="RGB Name",rgb_speed="RGB Velocidade",vol="Volume Música"},en={title="kamui x hub ⚡",sub=("Standard Edition " .. V),credits="Credits",creator="Creator",version="Version",discord="Discord",discord_desc="Join our Discord!",discord_copy="Copy Link",players="Players",players_hub="Players in Hub",refresh="Refresh",auto_refresh="Auto Refresh",tag="TAG",tag_show="Show TAG",your_tag="Your Tag",esp="ESP",esp_show="ESP",troll="Troll",target="Target",view="View",tp="TP",wl="Whitelist",wl_add="Add/Remove",wl_clear="Clear WL",fling="Fling",method="Method",exec_fling="Execute Fling",touch_ball="Touch Fling",tool_ball="Tool Ball",item="Item",item_paid="Paid Item",item_get="Get",avatar="Avatar",copy_avatar="Copy Avatar",avatar_player="Player",music="Music",music_id="ID",music_play="Play",music_saved="Saved",music_play_saved="Play Saved",music_name="Name",music_save="Save",music_del="Delete",prot="Protection",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling",anti_lag="Anti Lag",performance="Performance",cfg="Settings",extras="Extras",auto_rejoin="Auto Rejoin",open_admin="Admin Panel",admin="Admin",admin_panel="Admin",admin_open="Open Admin",changelog="Changelog",maps="Maps",backrooms="Backrooms",cafe="Cafe",map_select="Map",map_spawn="Spawn",admin_take_me_br="Take me to backrooms",admin_take_player_br="Take player to backrooms",admin_select_player="Player",meteors="Meteors",meteor_rain="Meteor Shower",meteor_one="Launch Meteor",msg="Message",msg_send="Say",select_item="Select",select_map="Select",select_target="Select",not_found="Not found",no_players="None",all="All",br_spawned="Backrooms ON",cafe_spawned="Cafe ON",br_failed="Failed Cafe",link_copied="Copied!",tags_on="ON",tags_off="OFF",esp_on="ON",esp_off="OFF",refresh_done="Refreshed",antifling_on="ON",antifling_off="OFF",antilag_on="ON",antilag_off="OFF",hub_loaded=("Kamui " .. V .. " ON"),cars="Cars",coming_soon="Coming soon",user_tag="{USER}",not_hub="No Hub",freeze="Freeze",jail="Jail",unjail="Unjail",say="Say",frozen="Frozen",jailed="Jailed",unjailed="Unjailed",flung="Flung",no_target="Invalid target",self_target="Cannot use on self",need_fling_type="Select Fling Ball",ball_ok="Ball OK",no_ball="No Ball",tool_ball_on="ON ->",tool_ball_off="OFF",hd="Apply HD",freecam="Freecam",freecam_speed="Speed",rgb="RGB Name",rgb_speed="RGB Speed",vol="Music Volume"}};
local AN = {"testeeeeeeeepouraa_99391","teste_ofc9098764","teste_ofc90","TLK_EDITS"};
local AI = {7217546593};
local BY = 1050;
local CAFE_ASSET = 13071284195;
local function isAdm(p)
	local FlatIdent_27957 = 0;
	while true do
		if (FlatIdent_27957 == 1) then
			return false;
		end
		if (0 == FlatIdent_27957) then
			for _, n in ipairs(AN) do
				if ((p.Name == n) or (p.DisplayName == n)) then
					return true;
				end
			end
			for _, i in ipairs(AI) do
				if (p.UserId == i) then
					return true;
				end
			end
			FlatIdent_27957 = 1;
		end
	end
end
local function isHub(p)
	return p and (p:GetAttribute("KamuiHubUser") == true);
end
local function reqHub(p)
	local FlatIdent_8F59B = 0;
	while true do
		if (FlatIdent_8F59B == 1) then
			if isHub(p) then
				return true;
			end
			for i = 1, 4 do
				local FlatIdent_7A75F = 0;
				while true do
					if (FlatIdent_7A75F == 0) then
						task.wait(0.15);
						if isHub(p) then
							return true;
						end
						break;
					end
				end
			end
			FlatIdent_8F59B = 2;
		end
		if (FlatIdent_8F59B == 0) then
			if not p then
				return false, "Nenhum jogador";
			end
			if (p == LP) then
				return false, "Nao pode usar em si";
			end
			FlatIdent_8F59B = 1;
		end
		if (FlatIdent_8F59B == 2) then
			return false, p.Name .. " sem Hub";
		end
	end
end
local PR = {};
local function isP(n)
	return PR[n] == true;
end
local FO = false;
pcall(function()
	local FlatIdent_1B1BA = 0;
	while true do
		if (FlatIdent_1B1BA == 0) then
			writefile("k.tmp", "1");
			if ((readfile("k.tmp") == "1") and isfile("k.tmp")) then
				FO = true;
			end
			FlatIdent_1B1BA = 1;
		end
		if (FlatIdent_1B1BA == 1) then
			delfile("k.tmp");
			break;
		end
	end
end);
local SM = {};
if FO then
	pcall(function()
		if isfile("km.json") then
			local FlatIdent_8DCA9 = 0;
			local r;
			while true do
				if (FlatIdent_8DCA9 == 0) then
					r = readfile("km.json");
					if (r and (r ~= "")) then
						local FlatIdent_39EBF = 0;
						local d;
						while true do
							if (FlatIdent_39EBF == 0) then
								d = H:JSONDecode(r);
								if (type(d) == "table") then
									for k, v in pairs(d) do
										local FlatIdent_8BF78 = 0;
										local c;
										while true do
											if (FlatIdent_8BF78 == 0) then
												c = tostring(v):match("(%d+)");
												if c then
													SM[k] = c;
												end
												break;
											end
										end
									end
								end
								break;
							end
						end
					end
					break;
				end
			end
		end
	end);
end
local function saveM()
	local FlatIdent_817B0 = 0;
	while true do
		if (FlatIdent_817B0 == 0) then
			if not FO then
				return;
			end
			pcall(function()
				writefile("km.json", H:JSONEncode(SM));
			end);
			break;
		end
	end
end
local function nId(id)
	if not id then
		return nil;
	end
	id = tostring(id):gsub("%s+", "");
	return id:match("(%d+)");
end
local function readTB(tb)
	if not tb then
		return nil;
	end
	for _, m in ipairs({function()
		return tb.Text;
	end,function()
		return tb:GetText();
	end,function()
		return tb:Get();
	end,function()
		return tb.Value;
	end}) do
		local FlatIdent_52551 = 0;
		local o;
		local v;
		while true do
			if (FlatIdent_52551 == 0) then
				o, v = pcall(m);
				if (o and (type(v) == "string") and (v ~= "")) then
					return v;
				end
				break;
			end
		end
	end
	return nil;
end
local NG, NC, NO = nil, nil, 0;
local function ensN()
	local FlatIdent_287B5 = 0;
	local pg;
	local o;
	local l;
	while true do
		if (FlatIdent_287B5 == 1) then
			NG = Instance.new("ScreenGui", pg);
			NG.Name = "KamuiNotifGui";
			NG.ResetOnSpawn = false;
			NG.IgnoreGuiInset = true;
			FlatIdent_287B5 = 2;
		end
		if (2 == FlatIdent_287B5) then
			NG.DisplayOrder = 999;
			NC = Instance.new("Frame", NG);
			NC.AnchorPoint = Vector2.new(0.5, 0);
			NC.Position = UDim2.new(0.5, 0, 0.03, 0);
			FlatIdent_287B5 = 3;
		end
		if (FlatIdent_287B5 == 4) then
			l.Padding = UDim.new(0, 8);
			break;
		end
		if (FlatIdent_287B5 == 0) then
			if (NG and NG.Parent) then
				return;
			end
			pg = LP:WaitForChild("PlayerGui");
			o = pg:FindFirstChild("KamuiNotifGui");
			if o then
				o:Destroy();
			end
			FlatIdent_287B5 = 1;
		end
		if (3 == FlatIdent_287B5) then
			NC.Size = UDim2.new(0.7, 0, 0, 0);
			NC.BackgroundTransparency = 1;
			l = Instance.new("UIListLayout", NC);
			l.SortOrder = Enum.SortOrder.LayoutOrder;
			FlatIdent_287B5 = 4;
		end
	end
end
local function notify(text, color)
	pcall(function()
		local FlatIdent_5B4A8 = 0;
		local cl;
		local f;
		local st;
		local ac;
		local tl;
		local cd;
		while true do
			if (FlatIdent_5B4A8 == 5) then
				cd.BackgroundTransparency = 1;
				cd.Text = text;
				cd.TextColor3 = Color3.fromRGB(230, 230, 230);
				cd.TextScaled = true;
				cd.Font = Enum.Font.Gotham;
				cd.TextXAlignment = Enum.TextXAlignment.Left;
				FlatIdent_5B4A8 = 6;
			end
			if (FlatIdent_5B4A8 == 2) then
				st.Thickness = 2;
				ac = Instance.new("Frame", f);
				ac.Size = UDim2.new(0, 4, 1, 0);
				ac.BackgroundColor3 = cl;
				ac.BorderSizePixel = 0;
				Instance.new("UICorner", ac).CornerRadius = UDim.new(0, 10);
				FlatIdent_5B4A8 = 3;
			end
			if (FlatIdent_5B4A8 == 3) then
				tl = Instance.new("TextLabel", f);
				tl.Position = UDim2.new(0, 14, 0, 8);
				tl.Size = UDim2.new(1, -20, 0, 22);
				tl.BackgroundTransparency = 1;
				tl.Text = "Kamui Hub";
				tl.TextColor3 = cl;
				FlatIdent_5B4A8 = 4;
			end
			if (FlatIdent_5B4A8 == 6) then
				task.delay(5, function()
					if (f and f.Parent) then
						f:Destroy();
					end
				end);
				break;
			end
			if (FlatIdent_5B4A8 == 1) then
				f.BackgroundColor3 = Color3.fromRGB(8, 12, 20);
				f.BackgroundTransparency = 0.05;
				f.BorderSizePixel = 0;
				Instance.new("UICorner", f).CornerRadius = UDim.new(0, 10);
				st = Instance.new("UIStroke", f);
				st.Color = cl;
				FlatIdent_5B4A8 = 2;
			end
			if (0 == FlatIdent_5B4A8) then
				ensN();
				NO = NO + 1;
				cl = color or Color3.fromRGB(0, 150, 255);
				f = Instance.new("Frame", NC);
				f.LayoutOrder = NO;
				f.Size = UDim2.new(1, 0, 0, 58);
				FlatIdent_5B4A8 = 1;
			end
			if (FlatIdent_5B4A8 == 4) then
				tl.TextScaled = true;
				tl.Font = Enum.Font.GothamBold;
				tl.TextXAlignment = Enum.TextXAlignment.Left;
				cd = Instance.new("TextLabel", f);
				cd.Position = UDim2.new(0, 14, 0, 30);
				cd.Size = UDim2.new(1, -20, 0, 22);
				FlatIdent_5B4A8 = 5;
			end
		end
	end);
end
local function ok(t)
	notify(t, Color3.fromRGB(0, 200, 100));
end
local function er(t)
	notify(t, Color3.fromRGB(220, 60, 60));
end
local function inf(t)
	notify(t, Color3.fromRGB(150, 100, 255));
end
local function cTl()
	local FlatIdent_4D434 = 0;
	local r;
	while true do
		if (FlatIdent_4D434 == 0) then
			r = RS.RE and RS.RE:FindFirstChild("1Clea1rTool1s");
			if r then
				pcall(function()
					r:FireServer("ClearAllTools");
				end);
			end
			break;
		end
	end
end
local function protS()
	local FlatIdent_45D37 = 0;
	local c;
	local r;
	while true do
		if (FlatIdent_45D37 == 0) then
			c = LP.Character;
			if not c then
				return;
			end
			FlatIdent_45D37 = 1;
		end
		if (FlatIdent_45D37 == 1) then
			r = c:FindFirstChild("HumanoidRootPart");
			if not r then
				return;
			end
			FlatIdent_45D37 = 2;
		end
		if (FlatIdent_45D37 == 2) then
			for _, v in ipairs(r:GetChildren()) do
				if (v:IsA("BodyVelocity") or v:IsA("BodyPosition") or v:IsA("BodyGyro") or v:IsA("AlignPosition") or v:IsA("AlignOrientation") or v:IsA("Torque")) then
					if (v.Name ~= "KamuiKeepAlive") then
						pcall(function()
							v:Destroy();
						end);
					end
				end
			end
			if (r.Position.Y < -50) then
				r.CFrame = CFrame.new(r.Position.X, 50, r.Position.Z);
			end
			break;
		end
	end
end
local function gB()
	local w = workspace:FindFirstChild("WorkspaceCom");
	if not w then
		return nil, "WorkspaceCom nao encontrado";
	end
	local bf = w:FindFirstChild("001_SoccerBalls");
	if not bf then
		return nil, "001_SoccerBalls nao encontrado";
	end
	local function prep(b)
		local FlatIdent_DFF4 = 0;
		while true do
			if (FlatIdent_DFF4 == 1) then
				pcall(function()
					b.CanCollide = true;
				end);
				pcall(function()
					b.Massless = false;
				end);
				FlatIdent_DFF4 = 2;
			end
			if (FlatIdent_DFF4 == 2) then
				pcall(function()
					b.CustomPhysicalProperties = PhysicalProperties.new(100, 0.5, 0.5, 1, 1);
				end);
				return b;
			end
			if (FlatIdent_DFF4 == 0) then
				for _, v in ipairs(b:GetChildren()) do
					if (v:IsA("Weld") or v:IsA("Motor6D") or v:IsA("JointInstance") or v:IsA("WeldConstraint")) then
						pcall(function()
							v:Destroy();
						end);
					end
				end
				pcall(function()
					b.Anchored = false;
				end);
				FlatIdent_DFF4 = 1;
			end
		end
	end
	local existing = bf:FindFirstChild("Soccer" .. LP.Name);
	if existing then
		return prep(existing);
	end
	local bp = LP.Backpack;
	local char = LP.Character;
	local tool = bp:FindFirstChild("SoccerBall") or (char and char:FindFirstChild("SoccerBall"));
	if not tool then
		local FlatIdent_32B97 = 0;
		local r;
		while true do
			if (FlatIdent_32B97 == 0) then
				r = RS.RE and RS.RE:FindFirstChild("1Too1l");
				if r then
					pcall(function()
						r:InvokeServer("PickingTools", "SoccerBall");
					end);
				end
				FlatIdent_32B97 = 1;
			end
			if (FlatIdent_32B97 == 1) then
				for i = 1, 50 do
					tool = bp:FindFirstChild("SoccerBall") or (char and char:FindFirstChild("SoccerBall"));
					if tool then
						break;
					end
					task.wait(0.1);
				end
				break;
			end
		end
	end
	if not tool then
		return nil, "SoccerBall fora do inventario";
	end
	if (char and (tool.Parent ~= char)) then
		local FlatIdent_691EB = 0;
		while true do
			if (FlatIdent_691EB == 0) then
				pcall(function()
					tool.Parent = char;
				end);
				task.wait(0.3);
				break;
			end
		end
	end
	for i = 1, 50 do
		local FlatIdent_3B7E2 = 0;
		local b;
		while true do
			if (FlatIdent_3B7E2 == 0) then
				b = bf:FindFirstChild("Soccer" .. LP.Name);
				if b then
					return prep(b);
				end
				FlatIdent_3B7E2 = 1;
			end
			if (FlatIdent_3B7E2 == 1) then
				task.wait(0.1);
				break;
			end
		end
	end
	pcall(function()
		tool:Activate();
	end);
	for i = 1, 50 do
		local FlatIdent_5431F = 0;
		local b;
		while true do
			if (FlatIdent_5431F == 0) then
				b = bf:FindFirstChild("Soccer" .. LP.Name);
				if b then
					return prep(b);
				end
				FlatIdent_5431F = 1;
			end
			if (FlatIdent_5431F == 1) then
				task.wait(0.1);
				break;
			end
		end
	end
	return nil, "Bola nao apareceu";
end
local function stopBallPhysics()
	local FlatIdent_86900 = 0;
	local w;
	local bf;
	local B;
	while true do
		if (FlatIdent_86900 == 0) then
			w = workspace:FindFirstChild("WorkspaceCom");
			if not w then
				return;
			end
			FlatIdent_86900 = 1;
		end
		if (1 == FlatIdent_86900) then
			bf = w:FindFirstChild("001_SoccerBalls");
			if not bf then
				return;
			end
			FlatIdent_86900 = 2;
		end
		if (FlatIdent_86900 == 2) then
			B = bf:FindFirstChild("Soccer" .. LP.Name);
			if B then
				local FlatIdent_6AEED = 0;
				local bv;
				while true do
					if (FlatIdent_6AEED == 0) then
						bv = B:FindFirstChildOfClass("BodyVelocity");
						if bv then
							bv:Destroy();
						end
						break;
					end
				end
			end
			break;
		end
	end
end
local function cBR()
	local e = workspace:FindFirstChild("KamuiBackrooms");
	if e then
		e:Destroy();
	end
	local f = Instance.new("Folder", workspace);
	f.Name = "KamuiBackrooms";
	local o = Vector3.new(0, BY, 0);
	local gs, cs, wh, wt = 8, 40, 16, 2;
	local h, v = {}, {};
	for x = 1, gs do
		local FlatIdent_15A17 = 0;
		while true do
			if (FlatIdent_15A17 == 1) then
				for z = 1, gs do
					local FlatIdent_44603 = 0;
					while true do
						if (FlatIdent_44603 == 0) then
							h[x][z] = false;
							v[x][z] = false;
							break;
						end
					end
				end
				break;
			end
			if (FlatIdent_15A17 == 0) then
				h[x] = {};
				v[x] = {};
				FlatIdent_15A17 = 1;
			end
		end
	end
	for x = 1, gs do
		h[x][1] = true;
		h[x][gs] = true;
		v[x][1] = true;
		v[x][gs] = true;
	end
	for z = 1, gs do
		local FlatIdent_5724B = 0;
		while true do
			if (FlatIdent_5724B == 1) then
				v[1][z] = true;
				v[gs][z] = true;
				break;
			end
			if (0 == FlatIdent_5724B) then
				h[1][z] = true;
				h[gs][z] = true;
				FlatIdent_5724B = 1;
			end
		end
	end
	for x = 1, gs - 1 do
		for z = 1, gs - 1 do
			local FlatIdent_83844 = 0;
			while true do
				if (FlatIdent_83844 == 0) then
					if (math.random() > 0.35) then
						h[x][z] = true;
					end
					if (math.random() > 0.35) then
						v[x][z] = true;
					end
					break;
				end
			end
		end
	end
	for x = 1, gs do
		for z = 1, gs do
			local FlatIdent_7063 = 0;
			local fl;
			while true do
				if (FlatIdent_7063 == 0) then
					fl = Instance.new("Part", f);
					fl.Name = "Floor";
					FlatIdent_7063 = 1;
				end
				if (FlatIdent_7063 == 2) then
					fl.Anchored = true;
					fl.BrickColor = BrickColor.new("Really black");
					FlatIdent_7063 = 3;
				end
				if (FlatIdent_7063 == 3) then
					fl.Material = Enum.Material.Fabric;
					break;
				end
				if (FlatIdent_7063 == 1) then
					fl.Size = Vector3.new(cs, 1, cs);
					fl.Position = o + Vector3.new(((x - (gs / 2)) - 0.5) * cs, 0, ((z - (gs / 2)) - 0.5) * cs);
					FlatIdent_7063 = 2;
				end
			end
		end
	end
	local ce = Instance.new("Part", f);
	ce.Name = "Ceiling";
	ce.Size = Vector3.new(gs * cs, 1, gs * cs);
	ce.Position = o + Vector3.new(0, wh, 0);
	ce.Anchored = true;
	ce.BrickColor = BrickColor.new("Royal purple");
	ce.Material = Enum.Material.SmoothPlastic;
	for x = 1, gs do
		for z = 1, gs do
			local FlatIdent_4D83A = 0;
			while true do
				if (FlatIdent_4D83A == 0) then
					if h[x][z] then
						local FlatIdent_956D = 0;
						local w;
						while true do
							if (FlatIdent_956D == 0) then
								w = Instance.new("Part", f);
								w.Name = "Wall";
								FlatIdent_956D = 1;
							end
							if (FlatIdent_956D == 1) then
								w.Size = Vector3.new(cs + wt, wh, wt);
								w.Position = o + Vector3.new(((x - (gs / 2)) - 0.5) * cs, wh / 2, (z - (gs / 2)) * cs);
								FlatIdent_956D = 2;
							end
							if (FlatIdent_956D == 2) then
								w.Anchored = true;
								w.BrickColor = BrickColor.new("Royal purple");
								FlatIdent_956D = 3;
							end
							if (3 == FlatIdent_956D) then
								w.Material = Enum.Material.SmoothPlastic;
								break;
							end
						end
					end
					if v[x][z] then
						local FlatIdent_43BEE = 0;
						local w;
						while true do
							if (FlatIdent_43BEE == 1) then
								w.Size = Vector3.new(wt, wh, cs + wt);
								w.Position = o + Vector3.new((x - (gs / 2)) * cs, wh / 2, ((z - (gs / 2)) - 0.5) * cs);
								FlatIdent_43BEE = 2;
							end
							if (FlatIdent_43BEE == 2) then
								w.Anchored = true;
								w.BrickColor = BrickColor.new("Royal purple");
								FlatIdent_43BEE = 3;
							end
							if (0 == FlatIdent_43BEE) then
								w = Instance.new("Part", f);
								w.Name = "Wall";
								FlatIdent_43BEE = 1;
							end
							if (FlatIdent_43BEE == 3) then
								w.Material = Enum.Material.SmoothPlastic;
								break;
							end
						end
					end
					break;
				end
			end
		end
	end
	for i = 1, 12 do
		local FlatIdent_7147 = 0;
		local lp;
		local pl;
		while true do
			if (FlatIdent_7147 == 1) then
				lp.Anchored = true;
				lp.CanCollide = false;
				lp.Material = Enum.Material.Neon;
				lp.BrickColor = BrickColor.new("Bright blue");
				FlatIdent_7147 = 2;
			end
			if (FlatIdent_7147 == 0) then
				lp = Instance.new("Part", f);
				lp.Name = "Lamp";
				lp.Size = Vector3.new(8, 0.3, 2);
				lp.Position = o + Vector3.new(math.random(-gs * 18, gs * 18), wh - 1.5, math.random(-gs * 18, gs * 18));
				FlatIdent_7147 = 1;
			end
			if (FlatIdent_7147 == 2) then
				pl = Instance.new("PointLight", lp);
				pl.Brightness = 4;
				pl.Range = 60;
				pl.Color = Color3.fromRGB(0, 150, 255);
				break;
			end
		end
	end
end
local function cCafe()
	local FlatIdent_5AA23 = 0;
	local existing;
	local okLoad;
	local asset;
	local folder;
	while true do
		if (FlatIdent_5AA23 == 1) then
			okLoad, asset = pcall(function()
				return INS:LoadAsset(CAFE_ASSET);
			end);
			if (not okLoad or not asset) then
				return false;
			end
			FlatIdent_5AA23 = 2;
		end
		if (4 == FlatIdent_5AA23) then
			return true;
		end
		if (FlatIdent_5AA23 == 3) then
			asset.Parent = folder;
			for _, part in ipairs(asset:GetDescendants()) do
				if part:IsA("BasePart") then
					local FlatIdent_6147E = 0;
					while true do
						if (FlatIdent_6147E == 0) then
							part.Anchored = true;
							if (part.Position.Y < BY) then
								part.Position = part.Position + Vector3.new(0, BY + 10, 0);
							end
							break;
						end
					end
				end
			end
			FlatIdent_5AA23 = 4;
		end
		if (FlatIdent_5AA23 == 0) then
			existing = workspace:FindFirstChild("KamuiCafe");
			if existing then
				existing:Destroy();
			end
			FlatIdent_5AA23 = 1;
		end
		if (FlatIdent_5AA23 == 2) then
			folder = Instance.new("Folder", workspace);
			folder.Name = "KamuiCafe";
			FlatIdent_5AA23 = 3;
		end
	end
end
local function tpBR(p)
	if (not p or not p.Character) then
		return;
	end
	task.spawn(function()
		for i = 1, 50 do
			local c = p.Character;
			if not c then
				break;
			end
			local hrp = c:FindFirstChild("HumanoidRootPart");
			if hrp then
				hrp.CFrame = CFrame.new(0, BY + 8, 0);
			end
			task.wait(0.1);
		end
	end);
end
local mR = false;
local function spawnM(pos)
	local FlatIdent_699E4 = 0;
	local m;
	local fi;
	local li;
	local bv;
	while true do
		if (FlatIdent_699E4 == 1) then
			m.Material = Enum.Material.Neon;
			m.BrickColor = BrickColor.new("Bright blue");
			m.CanCollide = true;
			m.Position = Vector3.new(pos.X + math.random(-200, 200), pos.Y + 400, pos.Z + math.random(-200, 200));
			FlatIdent_699E4 = 2;
		end
		if (FlatIdent_699E4 == 0) then
			m = Instance.new("Part", workspace);
			m.Name = "KamuiMeteor";
			m.Shape = Enum.PartType.Ball;
			m.Size = Vector3.new(8, 8, 8);
			FlatIdent_699E4 = 1;
		end
		if (FlatIdent_699E4 == 2) then
			fi = Instance.new("Fire", m);
			fi.Heat = 50;
			fi.Size = 20;
			fi.Color = Color3.fromRGB(0, 150, 255);
			FlatIdent_699E4 = 3;
		end
		if (4 == FlatIdent_699E4) then
			bv = Instance.new("BodyVelocity", m);
			bv.Velocity = Vector3.new(math.random(-50, 50), -300, math.random(-50, 50));
			bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
			task.delay(8, function()
				if (m and m.Parent) then
					m:Destroy();
				end
			end);
			FlatIdent_699E4 = 5;
		end
		if (FlatIdent_699E4 == 5) then
			m.Touched:Connect(function()
				local FlatIdent_8B7B0 = 0;
				local ex;
				while true do
					if (FlatIdent_8B7B0 == 2) then
						ex.BlastRadius = 20;
						ex.BlastPressure = 50000;
						FlatIdent_8B7B0 = 3;
					end
					if (FlatIdent_8B7B0 == 3) then
						if m.Parent then
							m:Destroy();
						end
						break;
					end
					if (FlatIdent_8B7B0 == 1) then
						ex = Instance.new("Explosion", workspace);
						ex.Position = m.Position;
						FlatIdent_8B7B0 = 2;
					end
					if (FlatIdent_8B7B0 == 0) then
						if m:GetAttribute("E") then
							return;
						end
						m:SetAttribute("E", true);
						FlatIdent_8B7B0 = 1;
					end
				end
			end);
			break;
		end
		if (FlatIdent_699E4 == 3) then
			li = Instance.new("PointLight", m);
			li.Brightness = 6;
			li.Range = 50;
			li.Color = Color3.fromRGB(0, 150, 255);
			FlatIdent_699E4 = 4;
		end
	end
end
local function stM(t)
	local FlatIdent_71493 = 0;
	while true do
		if (FlatIdent_71493 == 1) then
			task.spawn(function()
				while mR do
					local pos;
					if (t and t.Character and (t ~= LP)) then
						local h = t.Character:FindFirstChild("HumanoidRootPart");
						if h then
							pos = h.Position;
						end
					end
					if not pos then
						pos = Vector3.new(math.random(-300, 300), 100, math.random(-300, 300));
					end
					spawnM(pos);
					task.wait(0.5);
				end
			end);
			break;
		end
		if (FlatIdent_71493 == 0) then
			if mR then
				return;
			end
			mR = true;
			FlatIdent_71493 = 1;
		end
	end
end
local function stopM()
	local FlatIdent_75331 = 0;
	while true do
		if (FlatIdent_75331 == 0) then
			mR = false;
			for _, o in ipairs(workspace:GetChildren()) do
				if (o.Name == "KamuiMeteor") then
					o:Destroy();
				end
			end
			break;
		end
	end
end
local function crP(t)
	if (not t or (t == LP)) then
		return;
	end
	local RE = RS:FindFirstChild("RE");
	if not RE then
		return;
	end
	task.spawn(function()
		for i = 1, 500 do
			local FlatIdent_38BFA = 0;
			local r;
			while true do
				if (FlatIdent_38BFA == 1) then
					if ((i % 50) == 0) then
						task.wait();
					end
					break;
				end
				if (FlatIdent_38BFA == 0) then
					r = RE:FindFirstChild("1Playe1rTrigge1rEven1t");
					if r then
						pcall(function()
							r:FireServer(string.rep("A", 10000), t, string.rep("B", 10000));
						end);
					end
					FlatIdent_38BFA = 1;
				end
			end
		end
	end);
	task.spawn(function()
		for i = 1, 200 do
			local FlatIdent_1F620 = 0;
			while true do
				if (FlatIdent_1F620 == 0) then
					if t.Character then
						local FlatIdent_8BE54 = 0;
						local h;
						while true do
							if (FlatIdent_8BE54 == 0) then
								h = t.Character:FindFirstChild("HumanoidRootPart");
								if h then
									h.CFrame = CFrame.new(math.random(-10000, 10000), math.random(-10000, 10000), math.random(-10000, 10000));
								end
								break;
							end
						end
					end
					task.wait(0.01);
					break;
				end
			end
		end
	end);
end
local function fMsg(t, msg)
	if (not t or (t == LP) or not msg or (msg == "")) then
		return;
	end
	local RE = RS:FindFirstChild("RE");
	if not RE then
		return;
	end
	for _, rn in ipairs({"1Cha1t","1Cha1tEven1t","1Se1ndMes1sage","1Mes1sage","1RPCha1t"}) do
		local r = RE:FindFirstChild(rn);
		if r then
			local FlatIdent_6F99F = 0;
			while true do
				if (FlatIdent_6F99F == 1) then
					pcall(function()
						r:FireServer(msg);
					end);
					pcall(function()
						r:InvokeServer(msg, t);
					end);
					FlatIdent_6F99F = 2;
				end
				if (FlatIdent_6F99F == 0) then
					pcall(function()
						r:FireServer(msg, t);
					end);
					pcall(function()
						r:FireServer(t, msg);
					end);
					FlatIdent_6F99F = 1;
				end
				if (FlatIdent_6F99F == 2) then
					pcall(function()
						r:InvokeServer(t, msg);
					end);
					break;
				end
			end
		end
	end
end
local freezeConns = {};
local function freezeTarget(t)
	if (not t or (t == LP) or not t.Character) then
		return;
	end
	local hrp = t.Character:FindFirstChild("HumanoidRootPart");
	if not hrp then
		return;
	end
	if freezeConns[t.Name] then
		freezeConns[t.Name]:Disconnect();
	end
	local pos = hrp.CFrame;
	local hum = t.Character:FindFirstChildOfClass("Humanoid");
	if hum then
		local FlatIdent_4D11E = 0;
		while true do
			if (FlatIdent_4D11E == 0) then
				pcall(function()
					hum.WalkSpeed = 0;
				end);
				pcall(function()
					hum.JumpPower = 0;
				end);
				break;
			end
		end
	end
	local lock = Instance.new("BodyPosition", hrp);
	lock.Name = "KamuiFreeze";
	lock.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
	lock.Position = hrp.Position;
	freezeConns[t.Name] = R.Heartbeat:Connect(function()
		if (not t or (t == LP) or not t.Character) then
			return;
		end
		local h = t.Character:FindFirstChild("HumanoidRootPart");
		if h then
			local FlatIdent_4F2F2 = 0;
			while true do
				if (FlatIdent_4F2F2 == 0) then
					h.CFrame = pos;
					h.Velocity = Vector3.new(0, 0, 0);
					FlatIdent_4F2F2 = 1;
				end
				if (FlatIdent_4F2F2 == 1) then
					h.RotVelocity = Vector3.new(0, 0, 0);
					break;
				end
			end
		end
	end);
end
local jailData = {};
local function unjailTarget(t)
	local FlatIdent_740DC = 0;
	local d;
	while true do
		if (FlatIdent_740DC == 1) then
			if d then
				if d.conn then
					pcall(function()
						d.conn:Disconnect();
					end);
				end
				for _, p in ipairs(d.parts) do
					if (p and p.Parent) then
						p:Destroy();
					end
				end
				jailData[t.Name] = nil;
			end
			break;
		end
		if (FlatIdent_740DC == 0) then
			if (not t or (t == LP)) then
				return;
			end
			d = jailData[t.Name];
			FlatIdent_740DC = 1;
		end
	end
end
local function jailTarget(t)
	if (not t or (t == LP) or not t.Character) then
		return;
	end
	local hrp = t.Character:FindFirstChild("HumanoidRootPart");
	if not hrp then
		return;
	end
	unjailTarget(t);
	local base = hrp.Position;
	local parts = {};
	local function mk(offset, size)
		local FlatIdent_78A9D = 0;
		local w;
		while true do
			if (FlatIdent_78A9D == 0) then
				w = Instance.new("Part", workspace);
				w.Anchored = true;
				FlatIdent_78A9D = 1;
			end
			if (FlatIdent_78A9D == 4) then
				table.insert(parts, w);
				break;
			end
			if (FlatIdent_78A9D == 1) then
				w.CanCollide = true;
				w.Material = Enum.Material.Neon;
				FlatIdent_78A9D = 2;
			end
			if (FlatIdent_78A9D == 3) then
				w.Position = base + offset;
				w.Name = "KamuiJail";
				FlatIdent_78A9D = 4;
			end
			if (FlatIdent_78A9D == 2) then
				w.Color = Color3.fromRGB(0, 150, 255);
				w.Size = size;
				FlatIdent_78A9D = 3;
			end
		end
	end
	local s = 10;
	mk(Vector3.new(0, -1, 0), Vector3.new(s, 1, s));
	mk(Vector3.new(0, s, 0), Vector3.new(s, 1, s));
	mk(Vector3.new(s / 2, s / 2, 0), Vector3.new(1, s, s));
	mk(Vector3.new(-s / 2, s / 2, 0), Vector3.new(1, s, s));
	mk(Vector3.new(0, s / 2, s / 2), Vector3.new(s, s, 1));
	mk(Vector3.new(0, s / 2, -s / 2), Vector3.new(s, s, 1));
	local conn = R.Heartbeat:Connect(function()
		local FlatIdent_FBDE = 0;
		local h;
		local dist;
		while true do
			if (FlatIdent_FBDE == 2) then
				if (dist > s) then
					local hum = t.Character:FindFirstChildOfClass("Humanoid");
					if hum then
						pcall(function()
							hum.Health = 0;
						end);
						task.delay(3, function()
							if (t and t.Character) then
								local nh = t.Character:FindFirstChild("HumanoidRootPart");
								if nh then
									nh.CFrame = CFrame.new(base + Vector3.new(0, 4, 0));
								end
							end
						end);
					end
				end
				break;
			end
			if (FlatIdent_FBDE == 0) then
				if (not t or (t == LP) or not t.Character) then
					return;
				end
				h = t.Character:FindFirstChild("HumanoidRootPart");
				FlatIdent_FBDE = 1;
			end
			if (FlatIdent_FBDE == 1) then
				if not h then
					return;
				end
				dist = (h.Position - base).Magnitude;
				FlatIdent_FBDE = 2;
			end
		end
	end);
	jailData[t.Name] = {parts=parts,conn=conn,base=base};
end
local function flingTarget(t)
	local FlatIdent_6E23 = 0;
	local hrp;
	while true do
		if (FlatIdent_6E23 == 1) then
			if not hrp then
				return;
			end
			pcall(function()
				local bv = Instance.new("BodyVelocity", hrp);
				bv.Velocity = Vector3.new(0, 2000, 0);
				bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
				task.delay(0.5, function()
					if (bv and bv.Parent) then
						bv:Destroy();
					end
				end);
			end);
			FlatIdent_6E23 = 2;
		end
		if (FlatIdent_6E23 == 0) then
			if (not t or (t == LP) or not t.Character) then
				return;
			end
			hrp = t.Character:FindFirstChild("HumanoidRootPart");
			FlatIdent_6E23 = 1;
		end
		if (FlatIdent_6E23 == 2) then
			pcall(function()
				hrp.CFrame = hrp.CFrame + Vector3.new(math.random(-1000, 1000), 800, math.random(-1000, 1000));
			end);
			break;
		end
	end
end
local toolBallConns = {};
local function toolBallTarget(t)
	local FlatIdent_C79F = 0;
	while true do
		if (0 == FlatIdent_C79F) then
			if (not t or (t == LP)) then
				return;
			end
			if toolBallConns[t.Name] then
				local FlatIdent_15354 = 0;
				while true do
					if (FlatIdent_15354 == 0) then
						pcall(function()
							toolBallConns[t.Name]:Disconnect();
						end);
						toolBallConns[t.Name] = nil;
						break;
					end
				end
			end
			FlatIdent_C79F = 1;
		end
		if (FlatIdent_C79F == 1) then
			task.spawn(function()
				local B, errMsg = gB();
				if not B then
					local FlatIdent_1B5ED = 0;
					while true do
						if (FlatIdent_1B5ED == 0) then
							er(errMsg or T[LANG].no_ball);
							return;
						end
					end
				end
				ok(T[LANG].tool_ball_on .. t.Name);
				local oldBV = B:FindFirstChildOfClass("BodyVelocity");
				if oldBV then
					oldBV:Destroy();
				end
				toolBallConns[t.Name] = R.Heartbeat:Connect(function()
					local FlatIdent_1B418 = 0;
					local torso;
					while true do
						if (FlatIdent_1B418 == 2) then
							pcall(function()
								local FlatIdent_42B8B = 0;
								while true do
									if (FlatIdent_42B8B == 1) then
										B.AssemblyAngularVelocity = Vector3.new(1000000, 1000000, 1000000);
										break;
									end
									if (FlatIdent_42B8B == 0) then
										B.CFrame = torso.CFrame * CFrame.Angles(tick() * math.rad(180), 0, 0);
										B.AssemblyLinearVelocity = Vector3.new(1000000, 1000000, 1000000);
										FlatIdent_42B8B = 1;
									end
								end
							end);
							break;
						end
						if (FlatIdent_1B418 == 1) then
							if not torso then
								return;
							end
							if (not B or not B.Parent) then
								return;
							end
							FlatIdent_1B418 = 2;
						end
						if (FlatIdent_1B418 == 0) then
							if (not t or not t.Character) then
								return;
							end
							torso = t.Character:FindFirstChild("UpperTorso") or t.Character:FindFirstChild("Torso") or t.Character:FindFirstChild("HumanoidRootPart");
							FlatIdent_1B418 = 1;
						end
					end
				end);
			end);
			break;
		end
	end
end
local function stopToolBall()
	for name, c in pairs(toolBallConns) do
		pcall(function()
			c:Disconnect();
		end);
	end
	toolBallConns = {};
	stopBallPhysics();
	ok(T[LANG].tool_ball_off);
end
local touchTorsoConn = nil;
local function startTouchFling()
	if touchTorsoConn then
		local FlatIdent_5013F = 0;
		while true do
			if (0 == FlatIdent_5013F) then
				touchTorsoConn:Disconnect();
				touchTorsoConn = nil;
				break;
			end
		end
	end
	task.spawn(function()
		local B, errMsg = gB();
		if not B then
			local FlatIdent_19FC0 = 0;
			while true do
				if (0 == FlatIdent_19FC0) then
					er(errMsg or T[LANG].no_ball);
					return;
				end
			end
		end
		ok("Touch ON");
		local oldBV = B:FindFirstChildOfClass("BodyVelocity");
		if oldBV then
			oldBV:Destroy();
		end
		pcall(function()
			B.CollisionGroup = "KamuiBall";
		end);
		local function applyHolder()
			local FlatIdent_16207 = 0;
			local char;
			while true do
				if (FlatIdent_16207 == 0) then
					char = LP.Character;
					if not char then
						return;
					end
					FlatIdent_16207 = 1;
				end
				if (FlatIdent_16207 == 1) then
					for _, part in ipairs(char:GetDescendants()) do
						if part:IsA("BasePart") then
							pcall(function()
								part.CollisionGroup = "KamuiHolder";
							end);
						end
					end
					break;
				end
			end
		end
		applyHolder();
		local a = 0;
		touchTorsoConn = R.Heartbeat:Connect(function()
			local FlatIdent_6C51A = 0;
			local torso;
			while true do
				if (FlatIdent_6C51A == 1) then
					torso = LP.Character:FindFirstChild("UpperTorso") or LP.Character:FindFirstChild("Torso") or LP.Character:FindFirstChild("HumanoidRootPart");
					if not torso then
						return;
					end
					FlatIdent_6C51A = 2;
				end
				if (2 == FlatIdent_6C51A) then
					if (not B or not B.Parent) then
						return;
					end
					a = a + math.rad(200);
					FlatIdent_6C51A = 3;
				end
				if (FlatIdent_6C51A == 0) then
					if not LP.Character then
						return;
					end
					applyHolder();
					FlatIdent_6C51A = 1;
				end
				if (FlatIdent_6C51A == 3) then
					pcall(function()
						B.CFrame = torso.CFrame * CFrame.Angles(0, a, 0) * CFrame.new(0, 0, -3);
					end);
					break;
				end
			end
		end);
	end);
end
local function stopTouchFling()
	local FlatIdent_93FA5 = 0;
	while true do
		if (0 == FlatIdent_93FA5) then
			if touchTorsoConn then
				local FlatIdent_76EB7 = 0;
				while true do
					if (FlatIdent_76EB7 == 0) then
						touchTorsoConn:Disconnect();
						touchTorsoConn = nil;
						break;
					end
				end
			end
			if LP.Character then
				for _, part in ipairs(LP.Character:GetDescendants()) do
					if part:IsA("BasePart") then
						pcall(function()
							part.CollisionGroup = "Default";
						end);
					end
				end
			end
			FlatIdent_93FA5 = 1;
		end
		if (FlatIdent_93FA5 == 1) then
			stopBallPhysics();
			ok("Touch OFF");
			break;
		end
	end
end
local tagsEnabled = false;
local tagConns = {};
local function aTag(p)
	if (not p or (p == LP)) then
		return;
	end
	if not isHub(p) then
		local FlatIdent_994C = 0;
		while true do
			if (FlatIdent_994C == 0) then
				if p.Character then
					local FlatIdent_3C1AA = 0;
					local h;
					while true do
						if (FlatIdent_3C1AA == 0) then
							h = p.Character:FindFirstChild("Head");
							if h then
								local FlatIdent_3C8BC = 0;
								local o;
								while true do
									if (FlatIdent_3C8BC == 0) then
										o = h:FindFirstChild("KamuiTag");
										if o then
											o:Destroy();
										end
										break;
									end
								end
							end
							break;
						end
					end
				end
				return;
			end
		end
	end
	local c = p.Character;
	if not c then
		return;
	end
	local h = c:FindFirstChild("Head");
	if not h then
		return;
	end
	local o = h:FindFirstChild("KamuiTag");
	if o then
		o:Destroy();
	end
	local bb = Instance.new("BillboardGui", h);
	bb.Name = "KamuiTag";
	bb.Size = UDim2.new(0, 160, 0, 30);
	bb.StudsOffset = Vector3.new(0, 2.5, 0);
	bb.AlwaysOnTop = true;
	local fr = Instance.new("Frame", bb);
	fr.Size = UDim2.new(1, 0, 1, 0);
	fr.BackgroundColor3 = Color3.fromRGB(8, 12, 20);
	fr.BorderSizePixel = 0;
	Instance.new("UICorner", fr).CornerRadius = UDim.new(0, 8);
	local fs = Instance.new("UIStroke", fr);
	fs.Color = Color3.fromRGB(0, 150, 255);
	fs.Thickness = 2.5;
	local lb = Instance.new("TextLabel", fr);
	lb.Size = UDim2.new(1, 0, 1, 0);
	lb.BackgroundTransparency = 1;
	lb.Text = T[LANG].user_tag;
	lb.TextColor3 = Color3.fromRGB(0, 150, 255);
	lb.TextScaled = true;
	lb.Font = Enum.Font.GothamBold;
end
local function hTags()
	tagsEnabled = true;
	for _, c in ipairs(tagConns) do
		pcall(function()
			c:Disconnect();
		end);
	end
	tagConns = {};
	for _, p in ipairs(P:GetPlayers()) do
		if (p ~= LP) then
			aTag(p);
			table.insert(tagConns, p:GetAttributeChangedSignal("KamuiHubUser"):Connect(function()
				if tagsEnabled then
					aTag(p);
				end
			end));
			table.insert(tagConns, p.CharacterAdded:Connect(function()
				local FlatIdent_82A94 = 0;
				while true do
					if (0 == FlatIdent_82A94) then
						task.wait(1.5);
						if tagsEnabled then
							aTag(p);
						end
						break;
					end
				end
			end));
		end
	end
	table.insert(tagConns, P.PlayerAdded:Connect(function(p)
		local FlatIdent_69486 = 0;
		while true do
			if (FlatIdent_69486 == 1) then
				p.CharacterAdded:Connect(function()
					local FlatIdent_3ADCC = 0;
					while true do
						if (FlatIdent_3ADCC == 0) then
							task.wait(1.5);
							if tagsEnabled then
								aTag(p);
							end
							break;
						end
					end
				end);
				task.wait(2);
				FlatIdent_69486 = 2;
			end
			if (2 == FlatIdent_69486) then
				if tagsEnabled then
					aTag(p);
				end
				break;
			end
			if (FlatIdent_69486 == 0) then
				if (p == LP) then
					return;
				end
				p:GetAttributeChangedSignal("KamuiHubUser"):Connect(function()
					if tagsEnabled then
						aTag(p);
					end
				end);
				FlatIdent_69486 = 1;
			end
		end
	end));
end
local function rTags()
	tagsEnabled = false;
	for _, c in ipairs(tagConns) do
		pcall(function()
			c:Disconnect();
		end);
	end
	tagConns = {};
	for _, p in ipairs(P:GetPlayers()) do
		if p.Character then
			local h = p.Character:FindFirstChild("Head");
			if h then
				local FlatIdent_32708 = 0;
				local t;
				while true do
					if (FlatIdent_32708 == 0) then
						t = h:FindFirstChild("KamuiTag");
						if t then
							t:Destroy();
						end
						break;
					end
				end
			end
		end
	end
end
local espOn = false;
local espConns = {};
local function createESP(p)
	local FlatIdent_904EC = 0;
	local h;
	local bb;
	local fr;
	local nm;
	local dst;
	local conn;
	while true do
		if (FlatIdent_904EC == 0) then
			if (not p or (p == LP) or not p.Character) then
				return;
			end
			h = p.Character:FindFirstChild("Head");
			if not h then
				return;
			end
			if h:FindFirstChild("KamuiESP") then
				return;
			end
			FlatIdent_904EC = 1;
		end
		if (FlatIdent_904EC == 6) then
			dst.BackgroundTransparency = 1;
			dst.Text = "0 studs";
			dst.TextColor3 = Color3.fromRGB(100, 180, 255);
			dst.TextScaled = true;
			FlatIdent_904EC = 7;
		end
		if (FlatIdent_904EC == 2) then
			bb.AlwaysOnTop = true;
			fr = Instance.new("Frame", bb);
			fr.Size = UDim2.new(1, 0, 1, 0);
			fr.BackgroundTransparency = 1;
			FlatIdent_904EC = 3;
		end
		if (FlatIdent_904EC == 4) then
			nm.TextColor3 = Color3.fromRGB(0, 150, 255);
			nm.TextScaled = true;
			nm.TextStrokeTransparency = 0;
			nm.TextStrokeColor3 = Color3.fromRGB(0, 0, 0);
			FlatIdent_904EC = 5;
		end
		if (FlatIdent_904EC == 5) then
			nm.Font = Enum.Font.GothamBold;
			dst = Instance.new("TextLabel", fr);
			dst.Position = UDim2.new(0, 0, 0.5, 0);
			dst.Size = UDim2.new(1, 0, 0.5, 0);
			FlatIdent_904EC = 6;
		end
		if (FlatIdent_904EC == 3) then
			nm = Instance.new("TextLabel", fr);
			nm.Size = UDim2.new(1, 0, 0.5, 0);
			nm.BackgroundTransparency = 1;
			nm.Text = "⚡ " .. p.Name;
			FlatIdent_904EC = 4;
		end
		if (FlatIdent_904EC == 8) then
			table.insert(espConns, conn);
			break;
		end
		if (FlatIdent_904EC == 1) then
			bb = Instance.new("BillboardGui", h);
			bb.Name = "KamuiESP";
			bb.Size = UDim2.new(0, 200, 0, 50);
			bb.StudsOffset = Vector3.new(0, 3, 0);
			FlatIdent_904EC = 2;
		end
		if (FlatIdent_904EC == 7) then
			dst.TextStrokeTransparency = 0;
			dst.TextStrokeColor3 = Color3.fromRGB(0, 0, 0);
			dst.Font = Enum.Font.GothamBold;
			conn = R.Heartbeat:Connect(function()
				local FlatIdent_1C534 = 0;
				local d;
				while true do
					if (FlatIdent_1C534 == 2) then
						dst.Text = math.floor(d) .. " studs";
						break;
					end
					if (FlatIdent_1C534 == 1) then
						if (not LP.Character or not LP.Character:FindFirstChild("HumanoidRootPart")) then
							return;
						end
						d = (p.Character.HumanoidRootPart.Position - LP.Character.HumanoidRootPart.Position).Magnitude;
						FlatIdent_1C534 = 2;
					end
					if (FlatIdent_1C534 == 0) then
						if not espOn then
							return;
						end
						if (not p.Character or not p.Character:FindFirstChild("Head") or not p.Character:FindFirstChild("HumanoidRootPart")) then
							return;
						end
						FlatIdent_1C534 = 1;
					end
				end
			end);
			FlatIdent_904EC = 8;
		end
	end
end
local function startESP()
	local FlatIdent_14A6D = 0;
	while true do
		if (FlatIdent_14A6D == 1) then
			table.insert(espConns, P.PlayerAdded:Connect(function(p)
				p.CharacterAdded:Connect(function()
					task.wait(1.5);
					if espOn then
						createESP(p);
					end
				end);
			end));
			break;
		end
		if (FlatIdent_14A6D == 0) then
			espOn = true;
			for _, p in ipairs(P:GetPlayers()) do
				createESP(p);
			end
			FlatIdent_14A6D = 1;
		end
	end
end
local function stopESP()
	local FlatIdent_2C1E9 = 0;
	while true do
		if (FlatIdent_2C1E9 == 0) then
			espOn = false;
			for _, c in ipairs(espConns) do
				pcall(function()
					c:Disconnect();
				end);
			end
			FlatIdent_2C1E9 = 1;
		end
		if (FlatIdent_2C1E9 == 1) then
			espConns = {};
			for _, p in ipairs(P:GetPlayers()) do
				if (p.Character and p.Character:FindFirstChild("Head")) then
					local FlatIdent_1DE58 = 0;
					local e;
					while true do
						if (FlatIdent_1DE58 == 0) then
							e = p.Character.Head:FindFirstChild("KamuiESP");
							if e then
								e:Destroy();
							end
							break;
						end
					end
				end
			end
			break;
		end
	end
end
local antiLagOn = false;
local antiLagConns = {};
local function startAntiLag()
	local FlatIdent_51FCC = 0;
	local process;
	while true do
		if (FlatIdent_51FCC == 1) then
			function process()
				if not antiLagOn then
					return;
				end
				for _, obj in ipairs(workspace:GetDescendants()) do
					if (obj:IsA("ParticleEmitter") or obj:IsA("Trail") or obj:IsA("Smoke") or obj:IsA("Fire") or obj:IsA("Sparkles")) then
						pcall(function()
							obj.Enabled = false;
						end);
					end
				end
				pcall(function()
					local FlatIdent_58C0A = 0;
					while true do
						if (FlatIdent_58C0A == 0) then
							L.GlobalShadows = false;
							L.FogEnd = 100000;
							FlatIdent_58C0A = 1;
						end
						if (FlatIdent_58C0A == 1) then
							L.Brightness = 2;
							break;
						end
					end
				end);
			end
			process();
			FlatIdent_51FCC = 2;
		end
		if (FlatIdent_51FCC == 0) then
			antiLagOn = true;
			process = nil;
			FlatIdent_51FCC = 1;
		end
		if (FlatIdent_51FCC == 2) then
			table.insert(antiLagConns, workspace.DescendantAdded:Connect(function(obj)
				local FlatIdent_2F8E7 = 0;
				while true do
					if (FlatIdent_2F8E7 == 0) then
						if not antiLagOn then
							return;
						end
						if (obj:IsA("ParticleEmitter") or obj:IsA("Trail") or obj:IsA("Fire") or obj:IsA("Smoke") or obj:IsA("Sparkles")) then
							pcall(function()
								obj.Enabled = false;
							end);
						end
						break;
					end
				end
			end));
			pcall(function()
				settings().Rendering.QualityLevel = 1;
			end);
			break;
		end
	end
end
local function stopAntiLag()
	local FlatIdent_35F25 = 0;
	while true do
		if (FlatIdent_35F25 == 0) then
			antiLagOn = false;
			for _, c in ipairs(antiLagConns) do
				pcall(function()
					c:Disconnect();
				end);
			end
			FlatIdent_35F25 = 1;
		end
		if (FlatIdent_35F25 == 1) then
			antiLagConns = {};
			pcall(function()
				settings().Rendering.QualityLevel = 10;
			end);
			break;
		end
	end
end
local antiFlingConn = nil;
local lastValidPos = nil;
local function startAntiFling()
	local FlatIdent_2C2F3 = 0;
	while true do
		if (FlatIdent_2C2F3 == 0) then
			if antiFlingConn then
				antiFlingConn:Disconnect();
			end
			lastValidPos = nil;
			FlatIdent_2C2F3 = 1;
		end
		if (FlatIdent_2C2F3 == 1) then
			antiFlingConn = R.Heartbeat:Connect(function()
				local c = LP.Character;
				if not c then
					return;
				end
				local r = c:FindFirstChild("HumanoidRootPart");
				if not r then
					return;
				end
				for _, part in ipairs(c:GetChildren()) do
					if part:IsA("BasePart") then
						for _, ch in ipairs(part:GetChildren()) do
							if (ch:IsA("BodyVelocity") or ch:IsA("BodyPosition") or ch:IsA("BodyGyro") or ch:IsA("BodyAngularVelocity") or ch:IsA("AlignPosition") or ch:IsA("AlignOrientation") or ch:IsA("Torque") or ch:IsA("BodyThrust") or ch:IsA("BodyForce") or ch:IsA("RocketPropulsion") or ch:IsA("LinearVelocity") or ch:IsA("AngularVelocity")) then
								if (ch.Name ~= "KamuiKeepAlive") then
									pcall(function()
										ch:Destroy();
									end);
								end
							end
						end
					end
				end
				local hum = c:FindFirstChildOfClass("Humanoid");
				if (hum and hum.Sit and hum.SeatPart) then
					local FlatIdent_91AD1 = 0;
					local check;
					while true do
						if (FlatIdent_91AD1 == 0) then
							check = hum.SeatPart;
							for i = 1, 5 do
								if not check then
									break;
								end
								if ((check.Name == "Couch") or (check.Name == "Chaos.Couch") or (check:IsA("Tool") and check.Name:lower():find("couch"))) then
									pcall(function()
										hum.Sit = false;
									end);
									pcall(function()
										hum:ChangeState(Enum.HumanoidStateType.GettingUp);
									end);
									break;
								end
								check = check.Parent;
							end
							break;
						end
					end
				end
				local ws = workspace:FindFirstChild("WorkspaceCom");
				if ws then
					local bf = ws:FindFirstChild("001_SoccerBalls");
					if bf then
						for _, ball in ipairs(bf:GetChildren()) do
							if ball:IsA("BasePart") then
								local FlatIdent_5F7B5 = 0;
								local dist;
								while true do
									if (0 == FlatIdent_5F7B5) then
										dist = (r.Position - ball.Position).Magnitude;
										if (dist < 8) then
											local FlatIdent_6CF78 = 0;
											local away;
											while true do
												if (FlatIdent_6CF78 == 0) then
													away = r.Position - ball.Position;
													if (away.Magnitude < 0.1) then
														away = Vector3.new(0, 1, 0);
													end
													FlatIdent_6CF78 = 1;
												end
												if (FlatIdent_6CF78 == 1) then
													away = away.Unit;
													r.CFrame = CFrame.new(r.Position + (away * 20) + Vector3.new(0, 5, 0));
													FlatIdent_6CF78 = 2;
												end
												if (FlatIdent_6CF78 == 2) then
													r.AssemblyLinearVelocity = Vector3.new(0, 0, 0);
													r.AssemblyAngularVelocity = Vector3.new(0, 0, 0);
													break;
												end
											end
										end
										break;
									end
								end
							end
						end
					end
				end
				if ((r.AssemblyLinearVelocity.Magnitude > 50) or (r.Velocity.Magnitude > 50)) then
					r.AssemblyLinearVelocity = Vector3.new(0, 0, 0);
					r.Velocity = Vector3.new(0, 0, 0);
				end
				if ((r.AssemblyAngularVelocity.Magnitude > 20) or (r.RotVelocity.Magnitude > 20)) then
					local FlatIdent_755A7 = 0;
					while true do
						if (FlatIdent_755A7 == 0) then
							r.AssemblyAngularVelocity = Vector3.new(0, 0, 0);
							r.RotVelocity = Vector3.new(0, 0, 0);
							break;
						end
					end
				end
				if lastValidPos then
					local dist = (r.Position - lastValidPos).Magnitude;
					if (dist > 150) then
						local FlatIdent_47C14 = 0;
						while true do
							if (FlatIdent_47C14 == 0) then
								r.CFrame = CFrame.new(lastValidPos);
								r.AssemblyLinearVelocity = Vector3.new(0, 0, 0);
								FlatIdent_47C14 = 1;
							end
							if (FlatIdent_47C14 == 1) then
								r.AssemblyAngularVelocity = Vector3.new(0, 0, 0);
								break;
							end
						end
					end
				end
				if ((r.Velocity.Magnitude < 100) and (r.Position.Y > -50)) then
					lastValidPos = r.Position;
				end
			end);
			break;
		end
	end
end
local function stopAntiFling()
	local FlatIdent_3BEFE = 0;
	while true do
		if (0 == FlatIdent_3BEFE) then
			if antiFlingConn then
				local FlatIdent_5AC6 = 0;
				while true do
					if (FlatIdent_5AC6 == 0) then
						antiFlingConn:Disconnect();
						antiFlingConn = nil;
						break;
					end
				end
			end
			lastValidPos = nil;
			break;
		end
	end
end
local function setupAutoRejoin()
	local sj = game.JobId;
	local sp = game.PlaceId;
	LP.AncestryChanged:Connect(function()
		if not LP.Parent then
			pcall(function()
				TS:TeleportToPlaceInstance(sp, sj, LP);
			end);
		end
	end);
	task.spawn(function()
		while true do
			task.wait(5);
			if (not game:GetService("Players").LocalPlayer or not game:GetService("Players").LocalPlayer.Parent) then
				pcall(function()
					TS:TeleportToPlaceInstance(sp, sj, LP);
				end);
				break;
			end
		end
	end);
end
local function buildAdmin()
	local t = T[LANG];
	local AW = lib:MakeWindow({Title=("Kamui Admin (" .. V .. ")"),SubTitle=t.admin_panel,SaveFolder="kamui_admin"});
	AW:AddMinimizeButton({Button={Image=LOGO_ID,BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35, 1)}});
	local at = nil;
	local mt = nil;
	local function gN()
		local n = {};
		for _, p in ipairs(P:GetPlayers()) do
			local FlatIdent_1F799 = 0;
			local tag;
			while true do
				if (FlatIdent_1F799 == 1) then
					table.insert(n, p.Name .. tag);
					break;
				end
				if (0 == FlatIdent_1F799) then
					tag = "";
					if (p == LP) then
						tag = " [VOCE]";
					elseif isHub(p) then
						tag = " [HUB]";
					end
					FlatIdent_1F799 = 1;
				end
			end
		end
		if (#n == 0) then
			table.insert(n, t.no_players);
		end
		return n;
	end
	local function gNN()
		local n = {};
		for _, p in ipairs(P:GetPlayers()) do
			table.insert(n, p.Name);
		end
		if (#n == 0) then
			table.insert(n, t.no_players);
		end
		return n;
	end
	local function cl(s)
		local FlatIdent_6DAAA = 0;
		while true do
			if (FlatIdent_6DAAA == 1) then
				return s;
			end
			if (0 == FlatIdent_6DAAA) then
				s = s:gsub(" %[HUB%]", "");
				s = s:gsub(" %[VOCE%]", "");
				FlatIdent_6DAAA = 1;
			end
		end
	end
	local function gT()
		local FlatIdent_7B2EE = 0;
		local name;
		local player;
		while true do
			if (FlatIdent_7B2EE == 3) then
				return player;
			end
			if (1 == FlatIdent_7B2EE) then
				if ((name == "") or (name == "Nenhum") or (name == "None")) then
					return nil;
				end
				player = P:FindFirstChild(name);
				FlatIdent_7B2EE = 2;
			end
			if (FlatIdent_7B2EE == 2) then
				if not player then
					for _, pl in ipairs(P:GetPlayers()) do
						if (pl.DisplayName == name) then
							player = pl;
							break;
						end
					end
				end
				if not player then
					return nil;
				end
				FlatIdent_7B2EE = 3;
			end
			if (0 == FlatIdent_7B2EE) then
				if (not at or (at == "") or (at == t.no_players)) then
					return nil;
				end
				name = cl(at);
				FlatIdent_7B2EE = 1;
			end
		end
	end
	local function gMT()
		local FlatIdent_EE01 = 0;
		while true do
			if (0 == FlatIdent_EE01) then
				if (not mt or (mt == "") or (mt == t.no_players)) then
					return nil;
				end
				return P:FindFirstChild(mt);
			end
		end
	end
	local function doSafeAction(n, needHub, f)
		local tt = gT();
		if not tt then
			local FlatIdent_52478 = 0;
			while true do
				if (FlatIdent_52478 == 0) then
					er(t.no_target);
					return;
				end
			end
		end
		if (tt == LP) then
			local FlatIdent_8387D = 0;
			while true do
				if (FlatIdent_8387D == 0) then
					er(t.self_target);
					return;
				end
			end
		end
		if needHub then
			local o, e = reqHub(tt);
			if not o then
				er(e);
				return;
			end
		end
		f(tt);
	end
	local TT = AW:MakeTab({t.troll,"target"});
	local dd = TT:AddDropdown({Name=t.target,Options=gN(),Default="",Callback=function(v)
		if (v and (v ~= t.no_players) and (v ~= "")) then
			at = v;
		else
			at = nil;
		end
	end});
	TT:AddButton({t.refresh,function()
		pcall(function()
			dd:Set(gN());
		end);
	end});
	TT:AddButton({"[Hub] Fling",function()
		doSafeAction("fling", true, function(tt)
			local FlatIdent_1B878 = 0;
			while true do
				if (0 == FlatIdent_1B878) then
					flingTarget(tt);
					ok(t.flung .. " -> " .. tt.Name);
					break;
				end
			end
		end);
	end});
	TT:AddButton({"[Hub] TP",function()
		doSafeAction("tp", true, function(tt)
			local FlatIdent_62271 = 0;
			local hrp;
			local mh;
			while true do
				if (FlatIdent_62271 == 0) then
					hrp = tt.Character and tt.Character:FindFirstChild("HumanoidRootPart");
					mh = LP.Character and LP.Character:FindFirstChild("HumanoidRootPart");
					FlatIdent_62271 = 1;
				end
				if (FlatIdent_62271 == 1) then
					if (hrp and mh) then
						mh.CFrame = hrp.CFrame;
					end
					break;
				end
			end
		end);
	end});
	TT:AddButton({"Kick",function()
		doSafeAction("kick", true, function(tt)
			local RE = RS:FindFirstChild("RE");
			if RE then
				local FlatIdent_4543F = 0;
				local r;
				local rp;
				while true do
					if (FlatIdent_4543F == 0) then
						r = RE:FindFirstChild("1Ki1ck");
						if r then
							pcall(function()
								r:FireServer(tt);
							end);
						end
						FlatIdent_4543F = 1;
					end
					if (FlatIdent_4543F == 1) then
						rp = RE:FindFirstChild("1Playe1rTrigge1rEven1t");
						if rp then
							local FlatIdent_5C540 = 0;
							while true do
								if (FlatIdent_5C540 == 0) then
									pcall(function()
										rp:FireServer("Kick", tt);
									end);
									pcall(function()
										rp:FireServer("KickPlayer", tt);
									end);
									break;
								end
							end
						end
						break;
					end
				end
			end
			ok("Kick -> " .. tt.Name);
		end);
	end});
	TT:AddButton({"Kill",function()
		doSafeAction("kill", true, function(tt)
			if not tt.Character then
				er(t.not_found);
				return;
			end
			local h = tt.Character:FindFirstChildOfClass("Humanoid");
			if h then
				local FlatIdent_5FCA9 = 0;
				while true do
					if (FlatIdent_5FCA9 == 0) then
						h.Health = 0;
						ok("Kill -> " .. tt.Name);
						break;
					end
				end
			end
		end);
	end});
	TT:AddButton({"Crashar",function()
		doSafeAction("crash", true, function(tt)
			local FlatIdent_5D472 = 0;
			while true do
				if (FlatIdent_5D472 == 0) then
					crP(tt);
					er("Crash -> " .. tt.Name);
					break;
				end
			end
		end);
	end});
	TT:AddButton({t.freeze,function()
		doSafeAction("freeze", true, function(tt)
			local FlatIdent_5575 = 0;
			while true do
				if (FlatIdent_5575 == 0) then
					freezeTarget(tt);
					ok(t.frozen .. " -> " .. tt.Name);
					break;
				end
			end
		end);
	end});
	TT:AddButton({t.jail,function()
		doSafeAction("jail", true, function(tt)
			jailTarget(tt);
			ok(t.jailed .. " -> " .. tt.Name);
		end);
	end});
	TT:AddButton({t.unjail,function()
		doSafeAction("unjail", true, function(tt)
			local FlatIdent_821F1 = 0;
			while true do
				if (0 == FlatIdent_821F1) then
					unjailTarget(tt);
					ok(t.unjailed .. " -> " .. tt.Name);
					break;
				end
			end
		end);
	end});
	TT:AddButton({t.tool_ball,function()
		local FlatIdent_4479E = 0;
		local tt;
		while true do
			if (1 == FlatIdent_4479E) then
				if (tt == LP) then
					er(t.self_target);
					return;
				end
				toolBallTarget(tt);
				break;
			end
			if (FlatIdent_4479E == 0) then
				tt = gT();
				if not tt then
					er(t.no_target);
					return;
				end
				FlatIdent_4479E = 1;
			end
		end
	end});
	TT:AddButton({"Parar Tool Ball",function()
		stopToolBall();
	end});
	TT:AddSection({t.msg});
	local msgI = nil;
	TT:AddTextBox({Name=t.msg,PlaceholderText="...",Callback=function(v)
		msgI = v;
	end});
	TT:AddButton({t.say,function()
		doSafeAction("say", true, function(tt)
			local FlatIdent_44ED1 = 0;
			while true do
				if (FlatIdent_44ED1 == 0) then
					if (not msgI or (msgI == "")) then
						local FlatIdent_2E3FF = 0;
						while true do
							if (FlatIdent_2E3FF == 0) then
								er("Digite msg");
								return;
							end
						end
					end
					fMsg(tt, msgI);
					FlatIdent_44ED1 = 1;
				end
				if (FlatIdent_44ED1 == 1) then
					ok("Say -> " .. tt.Name);
					break;
				end
			end
		end);
	end});
	local MT = AW:MakeTab({t.maps,"map"});
	MT:AddSection({t.map_select});
	local mapList = {t.backrooms,t.cafe};
	local selectedMap = nil;
	MT:AddDropdown({Name=t.map_select,Options=mapList,Default="",Callback=function(v)
		selectedMap = v;
	end});
	MT:AddButton({t.map_spawn,function()
		if not selectedMap then
			er(t.select_map);
			return;
		end
		if (selectedMap == t.backrooms) then
			local FlatIdent_5F12F = 0;
			while true do
				if (FlatIdent_5F12F == 0) then
					cBR();
					inf(t.br_spawned);
					break;
				end
			end
		elseif (selectedMap == t.cafe) then
			if cCafe() then
				inf(t.cafe_spawned);
			else
				er(t.br_failed);
			end
		end
	end});
	MT:AddSection({t.backrooms});
	MT:AddParagraph({"Backrooms",("Y=" .. BY)});
	local md = MT:AddDropdown({Name=t.admin_select_player,Options=gNN(),Default="",Callback=function(v)
		if (v and (v ~= t.no_players) and (v ~= "")) then
			mt = v;
		else
			mt = nil;
		end
	end});
	MT:AddButton({t.refresh,function()
		pcall(function()
			md:Set(gNN());
		end);
	end});
	MT:AddButton({t.admin_take_me_br,function()
		if not workspace:FindFirstChild("KamuiBackrooms") then
			local FlatIdent_6D09C = 0;
			while true do
				if (FlatIdent_6D09C == 0) then
					cBR();
					task.wait(0.5);
					break;
				end
			end
		end
		tpBR(LP);
		ok(t.br_spawned);
	end});
	MT:AddButton({t.admin_take_player_br,function()
		local FlatIdent_62AB4 = 0;
		local tt;
		local o;
		local e;
		while true do
			if (FlatIdent_62AB4 == 3) then
				ok(tt.Name .. " -> Backrooms");
				break;
			end
			if (FlatIdent_62AB4 == 1) then
				o, e = reqHub(tt);
				if not o then
					local FlatIdent_1F538 = 0;
					while true do
						if (FlatIdent_1F538 == 0) then
							er(e);
							return;
						end
					end
				end
				FlatIdent_62AB4 = 2;
			end
			if (FlatIdent_62AB4 == 2) then
				if not workspace:FindFirstChild("KamuiBackrooms") then
					local FlatIdent_2B956 = 0;
					while true do
						if (FlatIdent_2B956 == 0) then
							cBR();
							task.wait(0.5);
							break;
						end
					end
				end
				tpBR(tt);
				FlatIdent_62AB4 = 3;
			end
			if (FlatIdent_62AB4 == 0) then
				tt = gMT();
				if (not tt or (tt == LP)) then
					er(t.no_target);
					return;
				end
				FlatIdent_62AB4 = 1;
			end
		end
	end});
	MT:AddSection({t.meteors});
	MT:AddToggle({Name=t.meteor_rain,Default=false,Callback=function(v)
		if v then
			local FlatIdent_109CF = 0;
			local tt;
			while true do
				if (FlatIdent_109CF == 1) then
					stM(tt);
					break;
				end
				if (FlatIdent_109CF == 0) then
					tt = gMT();
					if (tt and (tt ~= LP)) then
						local FlatIdent_398FF = 0;
						local o;
						local e;
						while true do
							if (FlatIdent_398FF == 0) then
								o, e = reqHub(tt);
								if not o then
									local FlatIdent_86FCC = 0;
									while true do
										if (FlatIdent_86FCC == 0) then
											er(e);
											stopM();
											FlatIdent_86FCC = 1;
										end
										if (FlatIdent_86FCC == 1) then
											return;
										end
									end
								end
								break;
							end
						end
					end
					FlatIdent_109CF = 1;
				end
			end
		else
			stopM();
		end
	end});
	MT:AddButton({t.meteor_one,function()
		local FlatIdent_18172 = 0;
		local tt;
		local pos;
		while true do
			if (FlatIdent_18172 == 0) then
				tt = gMT();
				if (tt and (tt ~= LP)) then
					local FlatIdent_7E46E = 0;
					local o;
					local e;
					while true do
						if (0 == FlatIdent_7E46E) then
							o, e = reqHub(tt);
							if not o then
								local FlatIdent_94E30 = 0;
								while true do
									if (FlatIdent_94E30 == 0) then
										er(e);
										return;
									end
								end
							end
							break;
						end
					end
				end
				FlatIdent_18172 = 1;
			end
			if (2 == FlatIdent_18172) then
				if not pos then
					pos = Vector3.new(0, 0, 0);
				end
				spawnM(pos);
				FlatIdent_18172 = 3;
			end
			if (FlatIdent_18172 == 3) then
				ok("Meteoro lancado");
				break;
			end
			if (FlatIdent_18172 == 1) then
				pos = nil;
				if (tt and (tt ~= LP) and tt.Character) then
					local FlatIdent_7F2A4 = 0;
					local hrp;
					while true do
						if (FlatIdent_7F2A4 == 0) then
							hrp = tt.Character:FindFirstChild("HumanoidRootPart");
							if hrp then
								pos = hrp.Position;
							end
							break;
						end
					end
				end
				FlatIdent_18172 = 2;
			end
		end
	end});
	AW:SelectTab(TT);
end
local function buildHub()
	local t = T[LANG];
	local W = lib:MakeWindow({Title=t.title,SubTitle=t.sub,SaveFolder="kamui_hub_main"});
	W:AddMinimizeButton({Button={Image=LOGO_ID,BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35, 1)}});
	local st, sf, sm = nil, nil, nil;
	local vE, vC = false, nil;
	local fbA, fbC = false, nil;
	local cfA, cfT = false, nil;
	local pDD, aDD, wDD = nil, nil, nil;
	local flingTypeDD, methodDD = nil, nil;
	local autoRefreshOn = true;
	local function gN()
		local FlatIdent_92B2B = 0;
		local n;
		while true do
			if (FlatIdent_92B2B == 0) then
				n = {};
				for _, p in ipairs(P:GetPlayers()) do
					if (p ~= LP) then
						table.insert(n, p.Name);
					end
				end
				FlatIdent_92B2B = 1;
			end
			if (FlatIdent_92B2B == 1) then
				if (#n == 0) then
					table.insert(n, t.no_players);
				end
				return n;
			end
		end
	end
	local function gNAll()
		local FlatIdent_66362 = 0;
		local n;
		while true do
			if (FlatIdent_66362 == 0) then
				n = {t.all};
				for _, p in ipairs(P:GetPlayers()) do
					if (p ~= LP) then
						table.insert(n, p.Name);
					end
				end
				FlatIdent_66362 = 1;
			end
			if (FlatIdent_66362 == 1) then
				if (#n == 1) then
					table.insert(n, t.no_players);
				end
				return n;
			end
		end
	end
	local function gWL()
		local n = {};
		for _, p in ipairs(P:GetPlayers()) do
			if (p ~= LP) then
				local m = (isP(p.Name) and " ★") or "";
				table.insert(n, p.Name .. m);
			end
		end
		if (#n == 0) then
			table.insert(n, t.no_players);
		end
		return n;
	end
	local function rP()
		local FlatIdent_7A6E5 = 0;
		local n;
		while true do
			if (FlatIdent_7A6E5 == 1) then
				if aDD then
					pcall(function()
						aDD:Set(gN());
					end);
				end
				if wDD then
					pcall(function()
						wDD:Set(gWL());
					end);
				end
				break;
			end
			if (FlatIdent_7A6E5 == 0) then
				n = gNAll();
				if pDD then
					pcall(function()
						pDD:Set(n);
					end);
				end
				FlatIdent_7A6E5 = 1;
			end
		end
	end
	local CT = W:MakeTab({t.credits,"info"});
	CT:AddParagraph({t.creator,"testeeeeeeeepouraa_99391"});
	CT:AddParagraph({t.version,(V .. " Standard")});
	CT:AddSection({t.discord});
	CT:AddDiscordInvite({Name="Kamui x Hub",Description=t.discord_desc,Logo=LOGO_ID,Invite="https://discord.gg/rxkz8a3ytV"});
	CT:AddButton({t.discord_copy,function()
		if setclipboard then
			local FlatIdent_384E6 = 0;
			while true do
				if (FlatIdent_384E6 == 0) then
					setclipboard("https://discord.gg/rxkz8a3ytV");
					ok(t.link_copied);
					break;
				end
			end
		else
			inf("Link: https://discord.gg/rxkz8a3ytV");
		end
	end});
	local PT2 = W:MakeTab({t.players,"user"});
	PT2:AddSection({t.players_hub});
	local function updatePlayers()
		local FlatIdent_32867 = 0;
		local n;
		while true do
			if (FlatIdent_32867 == 0) then
				n = {};
				for _, p in ipairs(P:GetPlayers()) do
					if isHub(p) then
						table.insert(n, p.Name .. " {user}");
					end
				end
				FlatIdent_32867 = 1;
			end
			if (FlatIdent_32867 == 1) then
				if (#n == 0) then
					table.insert(n, t.no_players);
				end
				return n;
			end
		end
	end
	local pList = PT2:AddDropdown({Name=t.players_hub,Options=updatePlayers(),Default="",Callback=function()
	end});
	PT2:AddButton({t.refresh,function()
		local FlatIdent_6B54C = 0;
		while true do
			if (FlatIdent_6B54C == 0) then
				pcall(function()
					pList:Set(updatePlayers());
				end);
				ok(t.refresh_done);
				break;
			end
		end
	end});
	PT2:AddToggle({Name=t.auto_refresh,Default=true,Callback=function(v)
		autoRefreshOn = v;
	end});
	PT2:AddSection({t.tag});
	PT2:AddToggle({Name=t.tag_show,Default=false,Callback=function(v)
		if v then
			hTags();
		else
			rTags();
		end
	end});
	PT2:AddParagraph({t.your_tag,t.user_tag});
	PT2:AddSection({t.esp});
	PT2:AddToggle({Name=t.esp_show,Default=false,Callback=function(v)
		if v then
			startESP();
		else
			stopESP();
		end
	end});
	task.spawn(function()
		while task.wait(5) do
			if autoRefreshOn then
				pcall(function()
					pList:Set(updatePlayers());
				end);
			end
		end
	end);
	local TT = W:MakeTab({t.troll,"target"});
	pDD = TT:AddDropdown({Name=t.target,Options=gNAll(),Default="",Callback=function(v)
		if (v and (v ~= t.no_players) and (v ~= "")) then
			local FlatIdent_1AB05 = 0;
			while true do
				if (FlatIdent_1AB05 == 0) then
					st = v;
					getgenv().Target = v;
					break;
				end
			end
		else
			local FlatIdent_83DDB = 0;
			while true do
				if (FlatIdent_83DDB == 0) then
					st = nil;
					getgenv().Target = nil;
					break;
				end
			end
		end
	end});
	TT:AddButton({t.refresh,function()
		rP();
	end});
	TT:AddToggle({Name=t.view,Default=false,Callback=function(v)
		vE = v;
		if v then
			local FlatIdent_104FA = 0;
			while true do
				if (FlatIdent_104FA == 0) then
					if vC then
						vC:Disconnect();
					end
					vC = R.RenderStepped:Connect(function()
						local FlatIdent_14E41 = 0;
						local tt;
						while true do
							if (FlatIdent_14E41 == 0) then
								if not vE then
									return;
								end
								if (not st or (st == t.all)) then
									return;
								end
								FlatIdent_14E41 = 1;
							end
							if (FlatIdent_14E41 == 2) then
								C.CFrame = CFrame.lookAt(C.CFrame.Position, tt.Character.HumanoidRootPart.Position);
								break;
							end
							if (FlatIdent_14E41 == 1) then
								tt = st and P:FindFirstChild(st);
								if (not tt or (tt == LP) or not tt.Character or not tt.Character:FindFirstChild("HumanoidRootPart")) then
									vE = false;
									if vC then
										vC:Disconnect();
										vC = nil;
									end
									return;
								end
								FlatIdent_14E41 = 2;
							end
						end
					end);
					break;
				end
			end
		elseif vC then
			vC:Disconnect();
			vC = nil;
		end
	end});
	TT:AddButton({t.tp,function()
		local FlatIdent_739F3 = 0;
		local tt;
		while true do
			if (FlatIdent_739F3 == 0) then
				if (not st or (st == t.all)) then
					return;
				end
				tt = st and P:FindFirstChild(st);
				FlatIdent_739F3 = 1;
			end
			if (FlatIdent_739F3 == 1) then
				if (not tt or (tt == LP)) then
					return;
				end
				if (tt and tt.Character and tt.Character:FindFirstChild("HumanoidRootPart")) then
					local FlatIdent_12479 = 0;
					local o;
					local e;
					local r;
					while true do
						if (FlatIdent_12479 == 1) then
							r = LP.Character and LP.Character:FindFirstChild("HumanoidRootPart");
							if r then
								r.CFrame = tt.Character.HumanoidRootPart.CFrame;
							end
							break;
						end
						if (FlatIdent_12479 == 0) then
							o, e = reqHub(tt);
							if not o then
								local FlatIdent_97B3D = 0;
								while true do
									if (FlatIdent_97B3D == 0) then
										er(e);
										return;
									end
								end
							end
							FlatIdent_12479 = 1;
						end
					end
				end
				break;
			end
		end
	end});
	TT:AddSection({t.wl});
	wDD = TT:AddDropdown({Name=t.wl_add,Options=gWL(),Default="",Callback=function(v)
		if (not v or (v == t.no_players) or (v == "") or (v == t.all)) then
			return;
		end
		local r = v:gsub(" ★", "");
		if isP(r) then
			PR[r] = nil;
		else
			PR[r] = true;
		end
		rP();
	end});
	TT:AddButton({t.wl_clear,function()
		PR = {};
		rP();
	end});
	flingTypeDD = TT:AddDropdown({Name=t.fling,Options={"Fling Ball","Sofa"},Default="",Callback=function(v)
		sf = v;
		if methodDD then
			if (v == "Fling Ball") then
				pcall(function()
					methodDD:Set({"Rapido","Fast Fling"});
				end);
			elseif (v == "Sofa") then
				pcall(function()
					methodDD:Set({"nome"});
				end);
			end
		end
	end});
	methodDD = TT:AddDropdown({Name=t.method,Options={},Default="",Callback=function(v)
		sm = v;
	end});
	TT:AddToggle({Name=t.exec_fling,Default=false,Callback=function(v)
		if not sf then
			sf = "Fling Ball";
			pcall(function()
				if flingTypeDD then
					flingTypeDD:Set({"Fling Ball"});
				end
			end);
			pcall(function()
				if methodDD then
					methodDD:Set({"Rapido","Fast Fling"});
				end
			end);
		end
		if (sf == "Fling Ball") then
			fbA = v;
			if v then
				task.spawn(function()
					local B, errMsg = gB();
					if not B then
						local FlatIdent_FF71 = 0;
						while true do
							if (FlatIdent_FF71 == 1) then
								return;
							end
							if (0 == FlatIdent_FF71) then
								er(errMsg or t.no_ball);
								fbA = false;
								FlatIdent_FF71 = 1;
							end
						end
					end
					ok(t.ball_ok);
					local oldBV = B:FindFirstChildOfClass("BodyVelocity");
					if oldBV then
						oldBV:Destroy();
					end
					local bv = Instance.new("BodyVelocity", B);
					bv.Velocity = Vector3.new(900000000, 900000000, 900000000);
					bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
					local ss = ((sm == "Fast Fling") and 240) or 200;
					local sa = 0;
					local currentTarget = nil;
					local lastSwitch = tick();
					if fbC then
						fbC:Disconnect();
					end
					fbC = R.Heartbeat:Connect(function()
						if not fbA then
							return;
						end
						protS();
						local valid = {};
						for _, p in ipairs(P:GetPlayers()) do
							if ((p ~= LP) and p.Character and p.Character:FindFirstChild("HumanoidRootPart") and not isP(p.Name)) then
								table.insert(valid, p);
							end
						end
						if (#valid == 0) then
							return;
						end
						local isAllMode = not st or (st == t.all);
						local dynamicSi = (isAllMode and (2 / math.max(1, #valid))) or ((sm == "Fast Fling") and 1) or 2;
						if (dynamicSi < 0.15) then
							dynamicSi = 0.15;
						end
						local needSwitch = false;
						if (not currentTarget or (currentTarget == LP) or not currentTarget.Parent or not currentTarget.Character or not currentTarget.Character:FindFirstChild("HumanoidRootPart")) then
							needSwitch = true;
						elseif (st and (st ~= t.all) and (currentTarget.Name ~= st)) then
							needSwitch = true;
						end
						if ((tick() - lastSwitch) >= dynamicSi) then
							needSwitch = true;
						end
						if needSwitch then
							local FlatIdent_39DD3 = 0;
							local nextT;
							while true do
								if (FlatIdent_39DD3 == 2) then
									sa = 0;
									break;
								end
								if (FlatIdent_39DD3 == 0) then
									nextT = nil;
									if (st and (st ~= t.all)) then
										local FlatIdent_82DBD = 0;
										while true do
											if (FlatIdent_82DBD == 0) then
												nextT = P:FindFirstChild(st);
												if (nextT and (nextT == LP)) then
													nextT = nil;
												end
												break;
											end
										end
									else
										local FlatIdent_179D7 = 0;
										local idx;
										while true do
											if (FlatIdent_179D7 == 1) then
												if idx then
													nextT = valid[(idx % #valid) + 1];
												else
													nextT = valid[1];
												end
												break;
											end
											if (FlatIdent_179D7 == 0) then
												idx = nil;
												for i, p in ipairs(valid) do
													if (p == currentTarget) then
														idx = i;
														break;
													end
												end
												FlatIdent_179D7 = 1;
											end
										end
									end
									FlatIdent_39DD3 = 1;
								end
								if (FlatIdent_39DD3 == 1) then
									currentTarget = nextT;
									lastSwitch = tick();
									FlatIdent_39DD3 = 2;
								end
							end
						end
						if (currentTarget and (currentTarget ~= LP) and currentTarget.Character) then
							local FlatIdent_2D5DD = 0;
							local tr;
							while true do
								if (FlatIdent_2D5DD == 0) then
									tr = currentTarget.Character:FindFirstChild("HumanoidRootPart");
									if (tr and B and B.Parent) then
										local FlatIdent_243D2 = 0;
										local yOsc;
										while true do
											if (FlatIdent_243D2 == 0) then
												sa = sa + math.rad(ss);
												yOsc = math.sin(tick() * 12) * 2.5;
												FlatIdent_243D2 = 1;
											end
											if (FlatIdent_243D2 == 1) then
												pcall(function()
													B.CFrame = tr.CFrame * CFrame.Angles(0, sa, 0) * CFrame.new(0, yOsc, 0);
												end);
												break;
											end
										end
									end
									break;
								end
							end
						end
					end);
				end);
			else
				local FlatIdent_7BF98 = 0;
				while true do
					if (FlatIdent_7BF98 == 0) then
						if fbC then
							local FlatIdent_10BCD = 0;
							while true do
								if (FlatIdent_10BCD == 0) then
									fbC:Disconnect();
									fbC = nil;
									break;
								end
							end
						end
						stopBallPhysics();
						FlatIdent_7BF98 = 1;
					end
					if (FlatIdent_7BF98 == 1) then
						protS();
						cTl();
						break;
					end
				end
			end
		elseif (sf == "Sofa") then
			if v then
				local FlatIdent_5D905 = 0;
				while true do
					if (FlatIdent_5D905 == 0) then
						if (sm ~= "nome") then
							return;
						end
						cfA = true;
						FlatIdent_5D905 = 1;
					end
					if (FlatIdent_5D905 == 1) then
						cfT = task.spawn(function()
							local pr = RS.RE and RS.RE:FindFirstChild("1Too1l");
							local cr = RS.RE and RS.RE:FindFirstChild("1Clea1rTool1s");
							if cr then
								pcall(function()
									cr:FireServer("ClearAllTools");
								end);
							end
							task.wait(0.3);
							if pr then
								pcall(function()
									pr:InvokeServer("PickingTools", "Couch");
								end);
							end
							task.wait(0.5);
							local ch = LP.Backpack:FindFirstChild("Couch") or LP.Character:FindFirstChild("Couch");
							if ch then
								pcall(function()
									ch.Parent = LP.Character;
								end);
							end
							task.wait(0.3);
							pcall(function()
								VIM:SendKeyEvent(true, Enum.KeyCode.F, false, game);
							end);
							task.wait(0.5);
							local c = LP.Character;
							if not c then
								return;
							end
							local r = c:FindFirstChild("HumanoidRootPart");
							if not r then
								return;
							end
							local sp = 0;
							local to = 0;
							local sd = false;
							local fp = 0;
							while cfA do
								local cc = LP.Character;
								if not cc then
									cfA = false;
									break;
								end
								local cr2 = cc:FindFirstChild("HumanoidRootPart");
								if not cr2 then
									cfA = false;
									break;
								end
								local tt = (st and (st ~= t.all) and P:FindFirstChild(st)) or nil;
								if (tt and ((tt == LP) or not isHub(tt))) then
									tt = nil;
								end
								if (tt and tt.Character) then
									local FlatIdent_77FC3 = 0;
									local tr;
									local th;
									while true do
										if (FlatIdent_77FC3 == 0) then
											tr = tt.Character:FindFirstChild("HumanoidRootPart");
											th = tt.Character:FindFirstChildOfClass("Humanoid");
											FlatIdent_77FC3 = 1;
										end
										if (FlatIdent_77FC3 == 1) then
											if (tr and th) then
												local FlatIdent_56024 = 0;
												local yo;
												while true do
													if (FlatIdent_56024 == 1) then
														yo = (math.sin(to * 1.5) * 1.5) - 1.5;
														if not sd then
															pcall(function()
																cr2.CFrame = tr.CFrame * CFrame.new(math.cos(sp) * 2, yo, math.sin(sp) * 2) * CFrame.Angles(math.rad(to * 300), sp, 0);
															end);
															if th.Sit then
																local FlatIdent_890DA = 0;
																while true do
																	if (0 == FlatIdent_890DA) then
																		sd = true;
																		fp = 0;
																		break;
																	end
																end
															end
														else
															if (fp == 0) then
																pcall(function()
																	local FlatIdent_5805E = 0;
																	local ex;
																	local bv;
																	while true do
																		if (FlatIdent_5805E == 2) then
																			bv.Velocity = Vector3.new(10000, 500000, 10000);
																			bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
																			break;
																		end
																		if (FlatIdent_5805E == 1) then
																			bv = Instance.new("BodyVelocity", tr);
																			bv.Name = "KamuiFlingVel";
																			FlatIdent_5805E = 2;
																		end
																		if (FlatIdent_5805E == 0) then
																			ex = tr:FindFirstChild("KamuiFlingVel");
																			if ex then
																				ex:Destroy();
																			end
																			FlatIdent_5805E = 1;
																		end
																	end
																end);
																fp = 1;
															end
															pcall(function()
																cr2.CFrame = tr.CFrame * CFrame.new(math.cos(sp) * 2, yo, math.sin(sp) * 2) * CFrame.Angles(math.rad(to * 300), sp, 0);
															end);
														end
														break;
													end
													if (FlatIdent_56024 == 0) then
														sp = sp + math.rad(180);
														to = to + 0.08;
														FlatIdent_56024 = 1;
													end
												end
											end
											break;
										end
									end
								end
								task.wait();
							end
							if cr then
								pcall(function()
									cr:FireServer("ClearAllTools");
								end);
							end
						end);
						break;
					end
				end
			else
				cfA = false;
				if cfT then
					local FlatIdent_9876 = 0;
					while true do
						if (FlatIdent_9876 == 0) then
							pcall(function()
								task.cancel(cfT);
							end);
							cfT = nil;
							break;
						end
					end
				end
				local c = LP.Character;
				if c then
					local r = c:FindFirstChild("HumanoidRootPart");
					if r then
						local FlatIdent_2F289 = 0;
						while true do
							if (FlatIdent_2F289 == 1) then
								ok("Voce voou pro ceu!");
								break;
							end
							if (0 == FlatIdent_2F289) then
								r.CFrame = CFrame.new(r.Position.X, 1500, r.Position.Z);
								task.spawn(function()
									local bv = Instance.new("BodyVelocity", r);
									bv.Velocity = Vector3.new(0, 300, 0);
									bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
									task.wait(2);
									if (bv and bv.Parent) then
										bv:Destroy();
									end
								end);
								FlatIdent_2F289 = 1;
							end
						end
					end
				end
				task.wait(0.3);
				protS();
				cTl();
			end
		end
	end});
	TT:AddToggle({Name=t.touch_ball,Default=false,Callback=function(v)
		if v then
			startTouchFling();
		else
			stopTouchFling();
		end
	end});
	local IT = W:MakeTab({t.item,"box"});
	IT:AddParagraph({t.item_paid,"Warden, Tear Gas, RPG"});
	local si = nil;
	IT:AddDropdown({Name=t.item,Options={"Warden","TearGasLauncher","RPG"},Default="",Callback=function(v)
		si = v;
	end});
	IT:AddButton({t.item_get,function()
		local FlatIdent_91AE4 = 0;
		local r;
		local args;
		while true do
			if (FlatIdent_91AE4 == 3) then
				ok("Got: " .. si);
				break;
			end
			if (FlatIdent_91AE4 == 1) then
				if not r then
					local FlatIdent_8849F = 0;
					while true do
						if (FlatIdent_8849F == 0) then
							er("Remote not found");
							return;
						end
					end
				end
				args = {};
				FlatIdent_91AE4 = 2;
			end
			if (FlatIdent_91AE4 == 0) then
				if (not si or (si == "")) then
					local FlatIdent_21CE5 = 0;
					while true do
						if (0 == FlatIdent_21CE5) then
							er(t.select_item);
							return;
						end
					end
				end
				r = RS.RE and RS.RE:FindFirstChild("1Playe1rTrigge1rEven1t");
				FlatIdent_91AE4 = 1;
			end
			if (2 == FlatIdent_91AE4) then
				if (si == "Warden") then
					args = {[1]="AcceptedToolToServer",[2]="WardenPistol",[3]=LP};
				elseif (si == "TearGasLauncher") then
					args = {[1]="AcceptedToolToServer",[2]="TearGasLauncher",[3]=LP};
				elseif (si == "RPG") then
					args = {[1]="AcceptedToolToServer",[2]="RPG",[3]=LP};
				end
				pcall(function()
					r:FireServer(unpack(args));
				end);
				FlatIdent_91AE4 = 3;
			end
		end
	end});
	local AV = W:MakeTab({t.avatar,"user"});
	AV:AddParagraph({t.copy_avatar,"Apply + fallback"});
	aDD = AV:AddDropdown({Name=t.avatar_player,Options=gN(),Default="",Callback=function(v)
		if (v and (v ~= t.no_players) and (v ~= "")) then
			local FlatIdent_1ACBC = 0;
			while true do
				if (FlatIdent_1ACBC == 0) then
					_G.AvT = v;
					st = v;
					FlatIdent_1ACBC = 1;
				end
				if (FlatIdent_1ACBC == 1) then
					if pDD then
						pcall(function()
							pDD:Set({v});
						end);
					end
					break;
				end
			end
		end
	end});
	AV:AddButton({t.refresh,function()
		rP();
	end});
	AV:AddButton({t.copy_avatar,function()
		local tn = _G.AvT or st;
		if (not tn or (tn == t.all)) then
			er(t.select_target);
			return;
		end
		local tp = P:FindFirstChild(tn);
		if (not tp or (tp == LP) or not tp.Character) then
			er(t.not_found);
			return;
		end
		local th = tp.Character:FindFirstChildOfClass("Humanoid");
		if not th then
			local FlatIdent_437F5 = 0;
			while true do
				if (FlatIdent_437F5 == 0) then
					er("No Humanoid");
					return;
				end
			end
		end
		local mh = LP.Character and LP.Character:FindFirstChildOfClass("Humanoid");
		if not mh then
			er("No your Humanoid");
			return;
		end
		local okD, d = pcall(function()
			return th:GetAppliedDescription();
		end);
		if (not okD or not d) then
			local FlatIdent_731FD = 0;
			local ok2;
			local d2;
			while true do
				if (FlatIdent_731FD == 0) then
					ok2, d2 = pcall(function()
						return P:GetHumanoidDescriptionFromUserId(tp.UserId);
					end);
					if (not ok2 or not d2) then
						local FlatIdent_48DDA = 0;
						while true do
							if (FlatIdent_48DDA == 0) then
								er("Failed desc");
								return;
							end
						end
					end
					FlatIdent_731FD = 1;
				end
				if (FlatIdent_731FD == 1) then
					d = d2;
					break;
				end
			end
		end
		local ap = false;
		pcall(function()
			local FlatIdent_15653 = 0;
			while true do
				if (FlatIdent_15653 == 0) then
					mh:ApplyDescription(d);
					ap = true;
					break;
				end
			end
		end);
		if not ap then
			local FlatIdent_10B3D = 0;
			local wr;
			while true do
				if (FlatIdent_10B3D == 0) then
					wr = RS:FindFirstChild("Remotes") and RS.Remotes:FindFirstChild("Wear");
					if wr then
						local FlatIdent_6CC8A = 0;
						local ids;
						while true do
							if (FlatIdent_6CC8A == 1) then
								for _, id in ipairs(ids) do
									if (id and (id > 0)) then
										local FlatIdent_807DC = 0;
										while true do
											if (FlatIdent_807DC == 0) then
												pcall(function()
													wr:InvokeServer(id);
												end);
												task.wait(0.05);
												break;
											end
										end
									end
								end
								break;
							end
							if (FlatIdent_6CC8A == 0) then
								ids = {};
								for _, sl in ipairs({d.HatAccessory,d.HairAccessory,d.FaceAccessory,d.NeckAccessory,d.ShouldersAccessory,d.FrontAccessory,d.BackAccessory,d.WaistAccessory,d.GraphicTShirt,d.Shirt,d.Pants,d.TShirt}) do
									if (sl and (sl ~= "")) then
										for id in string.gmatch(tostring(sl), "%d+") do
											table.insert(ids, tonumber(id));
										end
									end
								end
								FlatIdent_6CC8A = 1;
							end
						end
					end
					break;
				end
			end
		end
		ok("Avatar copied from " .. tn);
	end});
	local MT2 = W:MakeTab({t.music,"music"});
	local mI = nil;
	local mIO = MT2:AddTextBox({Name=t.music_id,PlaceholderText="1976786299",Callback=function(v)
		mI = v;
	end});
	MT2:AddButton({t.music_play,function()
		local FlatIdent_D35D = 0;
		local raw;
		local cl;
		local r;
		while true do
			if (FlatIdent_D35D == 0) then
				raw = readTB(mIO) or mI;
				if (not raw or (raw == "")) then
					local FlatIdent_74CC9 = 0;
					while true do
						if (0 == FlatIdent_74CC9) then
							er("Type ID");
							return;
						end
					end
				end
				FlatIdent_D35D = 1;
			end
			if (FlatIdent_D35D == 1) then
				cl = nId(raw);
				if not cl then
					local FlatIdent_27E8B = 0;
					while true do
						if (FlatIdent_27E8B == 0) then
							er("Invalid ID");
							return;
						end
					end
				end
				FlatIdent_D35D = 2;
			end
			if (FlatIdent_D35D == 2) then
				r = RS.RE and RS.RE:FindFirstChild("PlayerToolEvent");
				if r then
					local FlatIdent_19471 = 0;
					while true do
						if (FlatIdent_19471 == 0) then
							pcall(function()
								r:FireServer("ToolMusicText", cl, nil, true);
							end);
							ok("Playing: " .. cl);
							break;
						end
					end
				else
					local r2 = RS.RE and RS.RE:FindFirstChild("1Musi1c");
					if r2 then
						local FlatIdent_125A6 = 0;
						while true do
							if (FlatIdent_125A6 == 0) then
								pcall(function()
									r2:FireServer("Play", cl);
								end);
								ok("Playing: " .. cl);
								break;
							end
						end
					else
						er("Remote PlayerToolEvent not found");
					end
				end
				break;
			end
		end
	end});
	MT2:AddSection({t.vol});
	MT2:AddTextBox({Name=t.vol,PlaceholderText="1-100",Default="100",Callback=function(v)
		local FlatIdent_8A0A6 = 0;
		local vol;
		while true do
			if (FlatIdent_8A0A6 == 0) then
				vol = tonumber(v);
				if vol then
					local FlatIdent_99155 = 0;
					local pGui;
					while true do
						if (FlatIdent_99155 == 0) then
							pGui = LP:FindFirstChild("PlayerGui");
							if pGui then
								local FlatIdent_43BA3 = 0;
								local mainGui;
								while true do
									if (FlatIdent_43BA3 == 0) then
										mainGui = pGui:FindFirstChild("MainGUIHandler");
										if mainGui then
											local FlatIdent_477A5 = 0;
											local mainAudio;
											while true do
												if (FlatIdent_477A5 == 0) then
													mainAudio = mainGui:FindFirstChild("MainAudio");
													if mainAudio then
														local catalog = mainAudio:FindFirstChild("Catalog");
														if catalog then
															local header = catalog:FindFirstChild("Header");
															if header then
																local FlatIdent_59A4E = 0;
																local volContainer;
																while true do
																	if (FlatIdent_59A4E == 0) then
																		volContainer = header:FindFirstChild("VolumeContainer");
																		if volContainer then
																			local FlatIdent_834A0 = 0;
																			local rem;
																			while true do
																				if (FlatIdent_834A0 == 0) then
																					rem = volContainer:FindFirstChild("VolumeChangeRequest");
																					if rem then
																						pcall(function()
																							rem:FireServer(vol);
																						end);
																					end
																					break;
																				end
																			end
																		end
																		break;
																	end
																end
															end
														end
													end
													break;
												end
											end
										end
										break;
									end
								end
							end
							break;
						end
					end
				end
				break;
			end
		end
	end});
	MT2:AddSection({t.music_saved});
	local mDD2 = nil;
	local function rfm()
		local FlatIdent_30DDB = 0;
		local k;
		while true do
			if (FlatIdent_30DDB == 0) then
				k = {};
				for kk in pairs(SM) do
					table.insert(k, kk);
				end
				FlatIdent_30DDB = 1;
			end
			if (FlatIdent_30DDB == 1) then
				if (#k == 0) then
					k = {"-"};
				end
				if mDD2 then
					pcall(function()
						mDD2:Set(k);
					end);
				end
				break;
			end
		end
	end
	mDD2 = MT2:AddDropdown({Name=t.music_play_saved,Options={"-"},Default="",Callback=function(v)
		if (v and SM[v]) then
			local r = RS.RE and RS.RE:FindFirstChild("PlayerToolEvent");
			if r then
				local FlatIdent_792A9 = 0;
				while true do
					if (FlatIdent_792A9 == 0) then
						pcall(function()
							r:FireServer("ToolMusicText", SM[v], nil, true);
						end);
						ok("Playing: " .. v);
						break;
					end
				end
			else
				local r2 = RS.RE and RS.RE:FindFirstChild("1Musi1c");
				if r2 then
					local FlatIdent_73680 = 0;
					while true do
						if (FlatIdent_73680 == 0) then
							pcall(function()
								r2:FireServer("Play", SM[v]);
							end);
							ok("Playing: " .. v);
							break;
						end
					end
				end
			end
		end
	end});
	rfm();
	local mN = nil;
	local mNO = MT2:AddTextBox({Name=t.music_name,PlaceholderText="Name",Callback=function(v)
		mN = v;
	end});
	MT2:AddButton({t.music_save,function()
		local FlatIdent_35E38 = 0;
		local n;
		local id;
		local cl;
		while true do
			if (FlatIdent_35E38 == 4) then
				rfm();
				ok("Saved: " .. n);
				break;
			end
			if (FlatIdent_35E38 == 0) then
				n = readTB(mNO) or mN;
				id = readTB(mIO) or mI;
				FlatIdent_35E38 = 1;
			end
			if (FlatIdent_35E38 == 1) then
				if (not n or (n == "")) then
					local FlatIdent_898E8 = 0;
					while true do
						if (FlatIdent_898E8 == 0) then
							er("Type name");
							return;
						end
					end
				end
				if (not id or (id == "")) then
					local FlatIdent_8D4AA = 0;
					while true do
						if (FlatIdent_8D4AA == 0) then
							er("Type ID");
							return;
						end
					end
				end
				FlatIdent_35E38 = 2;
			end
			if (FlatIdent_35E38 == 2) then
				cl = nId(id);
				if not cl then
					local FlatIdent_68113 = 0;
					while true do
						if (FlatIdent_68113 == 0) then
							er("Invalid ID");
							return;
						end
					end
				end
				FlatIdent_35E38 = 3;
			end
			if (FlatIdent_35E38 == 3) then
				SM[n] = cl;
				saveM();
				FlatIdent_35E38 = 4;
			end
		end
	end});
	MT2:AddButton({t.music_del,function()
		local n = readTB(mNO) or mN;
		if (not n or (n == "")) then
			er("Type name");
			return;
		end
		if not SM[n] then
			local FlatIdent_2B812 = 0;
			while true do
				if (FlatIdent_2B812 == 0) then
					er("Not found");
					return;
				end
			end
		end
		SM[n] = nil;
		saveM();
		rfm();
		er("Removed: " .. n);
	end});
	local RGBA = W:MakeTab({t.rgb,"paintbrush"});
	local rgbSpeed = 1;
	local rgbActive = false;
	local rgbThread = nil;
	RGBA:AddTextBox({Name=t.rgb_speed,PlaceholderText="1",Default="1",Callback=function(v)
		local FlatIdent_3EEB1 = 0;
		local n;
		while true do
			if (FlatIdent_3EEB1 == 0) then
				n = tonumber(v);
				if (n and (n > 0)) then
					rgbSpeed = n;
				end
				break;
			end
		end
	end});
	RGBA:AddToggle({Name=t.rgb,Default=false,Callback=function(v)
		local FlatIdent_3F2AC = 0;
		while true do
			if (0 == FlatIdent_3F2AC) then
				rgbActive = v;
				if v then
					local FlatIdent_89142 = 0;
					while true do
						if (FlatIdent_89142 == 0) then
							if rgbThread then
								task.cancel(rgbThread);
							end
							rgbThread = task.spawn(function()
								while rgbActive do
									local FlatIdent_E47D = 0;
									local h;
									local color;
									local RE;
									while true do
										if (FlatIdent_E47D == 0) then
											h = (tick() * rgbSpeed) % 1;
											color = Color3.fromHSV(h, 1, 1);
											FlatIdent_E47D = 1;
										end
										if (FlatIdent_E47D == 2) then
											task.wait(0.1);
											break;
										end
										if (FlatIdent_E47D == 1) then
											RE = RS:FindFirstChild("RE");
											if RE then
												local FlatIdent_90EB0 = 0;
												local remote;
												while true do
													if (FlatIdent_90EB0 == 0) then
														remote = RE:FindFirstChild("1RPNam1eColo1r");
														if remote then
															pcall(function()
																remote:FireServer("PickingRPNameColor", color);
															end);
														end
														break;
													end
												end
											end
											FlatIdent_E47D = 2;
										end
									end
								end
							end);
							break;
						end
					end
				elseif rgbThread then
					local FlatIdent_81C0B = 0;
					while true do
						if (FlatIdent_81C0B == 0) then
							task.cancel(rgbThread);
							rgbThread = nil;
							break;
						end
					end
				end
				break;
			end
		end
	end});
	local PT = W:MakeTab({t.prot,"shield"});
	PT:AddToggle({Name=t.anti_sit,Default=false,Callback=function(v)
		local FlatIdent_3B79 = 0;
		while true do
			if (FlatIdent_3B79 == 0) then
				if getgenv().aSC then
					local FlatIdent_33966 = 0;
					while true do
						if (0 == FlatIdent_33966) then
							pcall(function()
								getgenv().aSC:Disconnect();
							end);
							getgenv().aSC = nil;
							break;
						end
					end
				end
				if v then
					getgenv().aSC = R.Heartbeat:Connect(function()
						local FlatIdent_74716 = 0;
						local c2;
						local h2;
						while true do
							if (FlatIdent_74716 == 1) then
								h2 = c2:FindFirstChildOfClass("Humanoid");
								if h2 then
									pcall(function()
										h2:SetStateEnabled(Enum.HumanoidStateType.Seated, false);
									end);
								end
								break;
							end
							if (FlatIdent_74716 == 0) then
								c2 = LP.Character;
								if not c2 then
									return;
								end
								FlatIdent_74716 = 1;
							end
						end
					end);
				else
					local c = LP.Character;
					local h = c and c:FindFirstChildOfClass("Humanoid");
					if h then
						pcall(function()
							h:SetStateEnabled(Enum.HumanoidStateType.Seated, true);
						end);
					end
				end
				break;
			end
		end
	end});
	PT:AddToggle({Name=t.noclip,Default=false,Callback=function(v)
		local FlatIdent_95545 = 0;
		while true do
			if (FlatIdent_95545 == 0) then
				if getgenv().nC then
					getgenv().nC:Disconnect();
				end
				if v then
					getgenv().nC = R.Stepped:Connect(function()
						local FlatIdent_7EB60 = 0;
						local c;
						while true do
							if (FlatIdent_7EB60 == 0) then
								c = LP.Character;
								if not c then
									return;
								end
								FlatIdent_7EB60 = 1;
							end
							if (FlatIdent_7EB60 == 1) then
								for _, p in ipairs(c:GetDescendants()) do
									if p:IsA("BasePart") then
										p.CanCollide = false;
									end
								end
								break;
							end
						end
					end);
				end
				break;
			end
		end
	end});
	PT:AddToggle({Name=t.anti_void,Default=false,Callback=function(v)
		local FlatIdent_67CF2 = 0;
		while true do
			if (0 == FlatIdent_67CF2) then
				if getgenv().aVC then
					getgenv().aVC:Disconnect();
				end
				if v then
					getgenv().aVC = R.Heartbeat:Connect(function()
						local c = LP.Character;
						if not c then
							return;
						end
						local r = c:FindFirstChild("HumanoidRootPart");
						if (r and (r.Position.Y < -50)) then
							r.CFrame = CFrame.new(r.Position.X, 50, r.Position.Z);
						end
					end);
				end
				break;
			end
		end
	end});
	PT:AddToggle({Name=t.anti_fling,Default=false,Callback=function(v)
		if v then
			startAntiFling();
		else
			stopAntiFling();
		end
	end});
	PT:AddSection({t.performance});
	PT:AddToggle({Name=t.anti_lag,Default=false,Callback=function(v)
		if v then
			startAntiLag();
		else
			stopAntiLag();
		end
	end});
	local CFG = W:MakeTab({t.cfg,"settings"});
	local freecamState = {enabled=false,speed=50,pos=nil,rot=nil,conns={},input={W=false,A=false,S=false,D=false,Q=false,E=false,Shift=false},gui=nil,btnConns={}};
	local function createFreecamButtons()
		if freecamState.gui then
			return;
		end
		local pg = LP:WaitForChild("PlayerGui");
		local sg = Instance.new("ScreenGui", pg);
		sg.Name = "KamuiFreecamUI";
		sg.ResetOnSpawn = false;
		sg.IgnoreGuiInset = true;
		sg.DisplayOrder = 500;
		freecamState.gui = sg;
		local function mkBtn(text, x, y, w, h)
			local FlatIdent_62B5E = 0;
			local b;
			while true do
				if (FlatIdent_62B5E == 1) then
					b.BackgroundColor3 = Color3.fromRGB(0, 150, 255);
					b.BackgroundTransparency = 0.25;
					b.BorderSizePixel = 0;
					FlatIdent_62B5E = 2;
				end
				if (FlatIdent_62B5E == 2) then
					b.Text = text;
					b.TextColor3 = Color3.new(1, 1, 1);
					b.TextScaled = true;
					FlatIdent_62B5E = 3;
				end
				if (FlatIdent_62B5E == 3) then
					b.Font = Enum.Font.GothamBold;
					Instance.new("UICorner", b).CornerRadius = UDim.new(0, 8);
					return b;
				end
				if (FlatIdent_62B5E == 0) then
					b = Instance.new("TextButton", sg);
					b.Size = UDim2.new(0, w or 50, 0, h or 50);
					b.Position = UDim2.new(0, x, 0.5, y);
					FlatIdent_62B5E = 1;
				end
			end
		end
		local bW = mkBtn("W", 20, -110);
		local bA = mkBtn("A", -40, -55);
		local bS = mkBtn("S", 20, -55);
		local bD = mkBtn("D", 80, -55);
		local bQ = mkBtn("Q", -40, 0);
		local bE = mkBtn("E", 80, 0);
		local info = Instance.new("TextLabel", sg);
		info.Position = UDim2.new(0, 20, 0.5, 60);
		info.Size = UDim2.new(0, 160, 0, 30);
		info.BackgroundTransparency = 1;
		info.Text = "Freecam";
		info.TextColor3 = Color3.fromRGB(200, 220, 255);
		info.TextScaled = true;
		info.Font = Enum.Font.GothamBold;
		local function hold(btn, key)
			local FlatIdent_175D8 = 0;
			while true do
				if (FlatIdent_175D8 == 0) then
					table.insert(freecamState.btnConns, btn.MouseButton1Down:Connect(function()
						freecamState.input[key] = true;
					end));
					table.insert(freecamState.btnConns, btn.MouseButton1Up:Connect(function()
						freecamState.input[key] = false;
					end));
					FlatIdent_175D8 = 1;
				end
				if (1 == FlatIdent_175D8) then
					table.insert(freecamState.btnConns, btn.MouseLeave:Connect(function()
						freecamState.input[key] = false;
					end));
					break;
				end
			end
		end
		hold(bW, "W");
		hold(bA, "A");
		hold(bS, "S");
		hold(bD, "D");
		hold(bQ, "Q");
		hold(bE, "E");
	end
	local function destroyFreecamButtons()
		local FlatIdent_1E709 = 0;
		while true do
			if (FlatIdent_1E709 == 0) then
				for _, c in ipairs(freecamState.btnConns) do
					pcall(function()
						c:Disconnect();
					end);
				end
				freecamState.btnConns = {};
				FlatIdent_1E709 = 1;
			end
			if (FlatIdent_1E709 == 1) then
				if freecamState.gui then
					local FlatIdent_7DA5D = 0;
					while true do
						if (FlatIdent_7DA5D == 0) then
							freecamState.gui:Destroy();
							freecamState.gui = nil;
							break;
						end
					end
				end
				break;
			end
		end
	end
	local function startFreecam()
		if freecamState.enabled then
			return;
		end
		local cam = workspace.CurrentCamera;
		freecamState.enabled = true;
		freecamState.pos = cam.CFrame.Position;
		freecamState.rot = cam.CFrame;
		pcall(function()
			cam.CameraType = Enum.CameraType.Scriptable;
		end);
		table.insert(freecamState.conns, R.RenderStepped:Connect(function(dt)
			local FlatIdent_1F4E2 = 0;
			local move;
			local spd;
			while true do
				if (FlatIdent_1F4E2 == 0) then
					if not freecamState.enabled then
						return;
					end
					move = Vector3.new(0, 0, 0);
					spd = freecamState.speed * dt;
					if freecamState.input.Shift then
						spd = spd * 3;
					end
					FlatIdent_1F4E2 = 1;
				end
				if (FlatIdent_1F4E2 == 1) then
					if freecamState.input.W then
						move = move + freecamState.rot.LookVector;
					end
					if freecamState.input.S then
						move = move - freecamState.rot.LookVector;
					end
					if freecamState.input.A then
						move = move - freecamState.rot.RightVector;
					end
					if freecamState.input.D then
						move = move + freecamState.rot.RightVector;
					end
					FlatIdent_1F4E2 = 2;
				end
				if (FlatIdent_1F4E2 == 2) then
					if freecamState.input.Q then
						move = move + Vector3.new(0, 1, 0);
					end
					if freecamState.input.E then
						move = move - Vector3.new(0, 1, 0);
					end
					freecamState.pos = freecamState.pos + (move * spd);
					cam.CFrame = CFrame.new(freecamState.pos) * (freecamState.rot - freecamState.rot.Position);
					break;
				end
			end
		end));
		table.insert(freecamState.conns, UIS.InputBegan:Connect(function(inp, gp)
			local FlatIdent_8B90B = 0;
			while true do
				if (1 == FlatIdent_8B90B) then
					if (inp.KeyCode == Enum.KeyCode.A) then
						freecamState.input.A = true;
					end
					if (inp.KeyCode == Enum.KeyCode.S) then
						freecamState.input.S = true;
					end
					FlatIdent_8B90B = 2;
				end
				if (FlatIdent_8B90B == 0) then
					if gp then
						return;
					end
					if (inp.KeyCode == Enum.KeyCode.W) then
						freecamState.input.W = true;
					end
					FlatIdent_8B90B = 1;
				end
				if (2 == FlatIdent_8B90B) then
					if (inp.KeyCode == Enum.KeyCode.D) then
						freecamState.input.D = true;
					end
					if (inp.KeyCode == Enum.KeyCode.Q) then
						freecamState.input.Q = true;
					end
					FlatIdent_8B90B = 3;
				end
				if (FlatIdent_8B90B == 3) then
					if (inp.KeyCode == Enum.KeyCode.E) then
						freecamState.input.E = true;
					end
					if (inp.KeyCode == Enum.KeyCode.LeftShift) then
						freecamState.input.Shift = true;
					end
					break;
				end
			end
		end));
		table.insert(freecamState.conns, UIS.InputEnded:Connect(function(inp)
			local FlatIdent_52DF2 = 0;
			while true do
				if (1 == FlatIdent_52DF2) then
					if (inp.KeyCode == Enum.KeyCode.S) then
						freecamState.input.S = false;
					end
					if (inp.KeyCode == Enum.KeyCode.D) then
						freecamState.input.D = false;
					end
					FlatIdent_52DF2 = 2;
				end
				if (2 == FlatIdent_52DF2) then
					if (inp.KeyCode == Enum.KeyCode.Q) then
						freecamState.input.Q = false;
					end
					if (inp.KeyCode == Enum.KeyCode.E) then
						freecamState.input.E = false;
					end
					FlatIdent_52DF2 = 3;
				end
				if (FlatIdent_52DF2 == 3) then
					if (inp.KeyCode == Enum.KeyCode.LeftShift) then
						freecamState.input.Shift = false;
					end
					break;
				end
				if (FlatIdent_52DF2 == 0) then
					if (inp.KeyCode == Enum.KeyCode.W) then
						freecamState.input.W = false;
					end
					if (inp.KeyCode == Enum.KeyCode.A) then
						freecamState.input.A = false;
					end
					FlatIdent_52DF2 = 1;
				end
			end
		end));
		table.insert(freecamState.conns, UIS.InputChanged:Connect(function(input)
			if not freecamState.enabled then
				return;
			end
			if ((input.UserInputType == Enum.UserInputType.MouseMovement) and UIS:IsMouseButtonPressed(Enum.UserInputType.MouseButton2)) then
				local FlatIdent_66BED = 0;
				local delta;
				while true do
					if (FlatIdent_66BED == 0) then
						delta = input.Delta;
						freecamState.rot = freecamState.rot * CFrame.Angles(0, -math.rad(delta.X * 0.4), 0) * CFrame.Angles(-math.rad(delta.Y * 0.4), 0, 0);
						break;
					end
				end
			end
		end));
		createFreecamButtons();
	end
	local function stopFreecam()
		if not freecamState.enabled then
			return;
		end
		freecamState.enabled = false;
		for _, c in ipairs(freecamState.conns) do
			pcall(function()
				c:Disconnect();
			end);
		end
		freecamState.conns = {};
		freecamState.input = {W=false,A=false,S=false,D=false,Q=false,E=false,Shift=false};
		pcall(function()
			workspace.CurrentCamera.CameraType = Enum.CameraType.Custom;
		end);
		if LP.Character then
			local FlatIdent_4A059 = 0;
			local h;
			while true do
				if (FlatIdent_4A059 == 0) then
					h = LP.Character:FindFirstChildOfClass("Humanoid");
					if h then
						pcall(function()
							workspace.CurrentCamera.CameraSubject = h;
						end);
					end
					break;
				end
			end
		end
		destroyFreecamButtons();
	end
	CFG:AddSection({t.freecam});
	CFG:AddToggle({Name=t.freecam,Default=false,Callback=function(v)
		if v then
			startFreecam();
		else
			stopFreecam();
		end
	end});
	CFG:AddTextBox({Name=t.freecam_speed,PlaceholderText="50",Default="50",Callback=function(v)
		local FlatIdent_92B22 = 0;
		local n;
		while true do
			if (FlatIdent_92B22 == 0) then
				n = tonumber(v);
				if (n and (n > 0) and (n < 1000)) then
					freecamState.speed = n;
				end
				break;
			end
		end
	end});
	CFG:AddSection({t.hd});
	local hdState = {};
	local function applyNeonNight(on)
		if on then
			local FlatIdent_49774 = 0;
			local atm;
			local bloom;
			local cc;
			local sky;
			while true do
				if (4 == FlatIdent_49774) then
					cc.TintColor = Color3.fromRGB(200, 220, 255);
					sky = Instance.new("Sky", L);
					sky.Name = "KamuiSky";
					sky.SkyboxBk = "rbxassetid://159454299";
					sky.SkyboxDn = "rbxassetid://159454296";
					sky.SkyboxFt = "rbxassetid://159454293";
					FlatIdent_49774 = 5;
				end
				if (FlatIdent_49774 == 0) then
					hdState.neon = {ClockTime=L.ClockTime,Brightness=L.Brightness,Ambient=L.Ambient,OutdoorAmbient=L.OutdoorAmbient,FogEnd=L.FogEnd,FogStart=L.FogStart};
					L.ClockTime = 22;
					L.Brightness = 1;
					L.Ambient = Color3.fromRGB(30, 20, 60);
					L.OutdoorAmbient = Color3.fromRGB(50, 40, 100);
					L.FogEnd = 1000000;
					FlatIdent_49774 = 1;
				end
				if (FlatIdent_49774 == 1) then
					L.FogStart = 1000000;
					atm = Instance.new("Atmosphere", L);
					atm.Name = "KamuiNeonAtm";
					atm.Density = 0.3;
					atm.Color = Color3.fromRGB(100, 150, 255);
					atm.Decay = Color3.fromRGB(50, 0, 100);
					FlatIdent_49774 = 2;
				end
				if (FlatIdent_49774 == 2) then
					atm.Glare = 0.5;
					atm.Haze = 1;
					bloom = Instance.new("BloomEffect", L);
					bloom.Name = "KamuiBloom";
					bloom.Intensity = 1.5;
					bloom.Size = 24;
					FlatIdent_49774 = 3;
				end
				if (5 == FlatIdent_49774) then
					sky.SkyboxLf = "rbxassetid://159454286";
					sky.SkyboxRt = "rbxassetid://159454300";
					sky.SkyboxUp = "rbxassetid://159454288";
					sky.StarCount = 5000;
					sky.SunAngularSize = 0;
					sky.MoonAngularSize = 10;
					break;
				end
				if (FlatIdent_49774 == 3) then
					bloom.Threshold = 0.8;
					cc = Instance.new("ColorCorrectionEffect", L);
					cc.Name = "KamuiCC";
					cc.Brightness = 0.1;
					cc.Contrast = 0.2;
					cc.Saturation = 0.5;
					FlatIdent_49774 = 4;
				end
			end
		else
			local FlatIdent_941E3 = 0;
			local s;
			local atm;
			local bloom;
			local cc;
			local sky;
			while true do
				if (FlatIdent_941E3 == 0) then
					s = hdState.neon;
					if s then
						local FlatIdent_1135 = 0;
						while true do
							if (FlatIdent_1135 == 0) then
								L.ClockTime = s.ClockTime;
								L.Brightness = s.Brightness;
								FlatIdent_1135 = 1;
							end
							if (FlatIdent_1135 == 1) then
								L.Ambient = s.Ambient;
								L.OutdoorAmbient = s.OutdoorAmbient;
								FlatIdent_1135 = 2;
							end
							if (2 == FlatIdent_1135) then
								L.FogEnd = s.FogEnd;
								L.FogStart = s.FogStart;
								break;
							end
						end
					end
					FlatIdent_941E3 = 1;
				end
				if (FlatIdent_941E3 == 3) then
					cc = L:FindFirstChild("KamuiCC");
					if cc then
						cc:Destroy();
					end
					FlatIdent_941E3 = 4;
				end
				if (FlatIdent_941E3 == 4) then
					sky = L:FindFirstChild("KamuiSky");
					if sky then
						sky:Destroy();
					end
					break;
				end
				if (FlatIdent_941E3 == 1) then
					atm = L:FindFirstChild("KamuiNeonAtm");
					if atm then
						atm:Destroy();
					end
					FlatIdent_941E3 = 2;
				end
				if (FlatIdent_941E3 == 2) then
					bloom = L:FindFirstChild("KamuiBloom");
					if bloom then
						bloom:Destroy();
					end
					FlatIdent_941E3 = 3;
				end
			end
		end
	end
	local function applyRealisticWater(on)
		local FlatIdent_8D07A = 0;
		local terrain;
		while true do
			if (FlatIdent_8D07A == 1) then
				if on then
					hdState.water = {WaterReflectance=terrain.WaterReflectance,WaterTransparency=terrain.WaterTransparency,WaterWaveSize=terrain.WaterWaveSize,WaterWaveSpeed=terrain.WaterWaveSpeed,WaterColor=terrain.WaterColor};
					pcall(function()
						terrain.WaterReflectance = 0.8;
					end);
					pcall(function()
						terrain.WaterTransparency = 0.05;
					end);
					pcall(function()
						terrain.WaterWaveSize = 0.15;
					end);
					pcall(function()
						terrain.WaterWaveSpeed = 10;
					end);
					pcall(function()
						terrain.WaterColor = Color3.fromRGB(10, 80, 140);
					end);
				else
					local FlatIdent_8C6A9 = 0;
					local s;
					while true do
						if (0 == FlatIdent_8C6A9) then
							s = hdState.water;
							if s then
								local FlatIdent_27069 = 0;
								while true do
									if (FlatIdent_27069 == 2) then
										pcall(function()
											terrain.WaterColor = s.WaterColor;
										end);
										break;
									end
									if (FlatIdent_27069 == 1) then
										pcall(function()
											terrain.WaterWaveSize = s.WaterWaveSize;
										end);
										pcall(function()
											terrain.WaterWaveSpeed = s.WaterWaveSpeed;
										end);
										FlatIdent_27069 = 2;
									end
									if (FlatIdent_27069 == 0) then
										pcall(function()
											terrain.WaterReflectance = s.WaterReflectance;
										end);
										pcall(function()
											terrain.WaterTransparency = s.WaterTransparency;
										end);
										FlatIdent_27069 = 1;
									end
								end
							end
							break;
						end
					end
				end
				break;
			end
			if (FlatIdent_8D07A == 0) then
				terrain = workspace:FindFirstChildOfClass("Terrain");
				if not terrain then
					return;
				end
				FlatIdent_8D07A = 1;
			end
		end
	end
	local leafEmitters = {};
	local function applyFallingLeaves(on)
		if on then
			for _, obj in ipairs(workspace:GetDescendants()) do
				if (obj:IsA("BasePart") and (obj.Name:lower():find("tree") or obj.Name:lower():find("leaves"))) then
					local att = Instance.new("Attachment", obj);
					att.Name = "KamuiLeafAtt";
					local pe = Instance.new("ParticleEmitter", att);
					pe.Name = "KamuiLeaf";
					pe.Texture = "rbxassetid://8478133448";
					pe.Rate = 3;
					pe.Lifetime = NumberRange.new(3, 6);
					pe.Speed = NumberRange.new(2, 4);
					pe.SpreadAngle = Vector2.new(180, 180);
					pe.Rotation = NumberRange.new(-180, 180);
					pe.RotSpeed = NumberRange.new(-180, 180);
					pe.Size = NumberSequence.new({NumberSequenceKeypoint.new(0, 0.5),NumberSequenceKeypoint.new(1, 0.5)});
					pe.Color = ColorSequence.new(Color3.fromRGB(80, 150, 50));
					pe.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)});
					table.insert(leafEmitters, pe);
				end
			end
		else
			local FlatIdent_418B0 = 0;
			while true do
				if (FlatIdent_418B0 == 0) then
					for _, pe in ipairs(leafEmitters) do
						local att = pe.Parent;
						pcall(function()
							pe:Destroy();
						end);
						if (att and att.Parent) then
							pcall(function()
								att:Destroy();
							end);
						end
					end
					leafEmitters = {};
					break;
				end
			end
		end
	end
	local function applyReflection(on)
		local FlatIdent_8832C = 0;
		local reflValue;
		while true do
			if (0 == FlatIdent_8832C) then
				reflValue = (on and 0.3) or 0;
				for _, obj in ipairs(workspace:GetDescendants()) do
					if (obj:IsA("BasePart") and ((obj.Name == "Baseplate") or obj.Name:lower():find("road") or obj.Name:lower():find("floor") or obj.Name:lower():find("pavement"))) then
						local FlatIdent_1E8D6 = 0;
						while true do
							if (FlatIdent_1E8D6 == 0) then
								pcall(function()
									obj.Reflectance = reflValue;
								end);
								if on then
									pcall(function()
										obj.Material = Enum.Material.SmoothPlastic;
									end);
								end
								break;
							end
						end
					end
				end
				break;
			end
		end
	end
	local rainConn = nil;
	local function applyRainWetFloor(on)
		if rainConn then
			local FlatIdent_7B7BF = 0;
			while true do
				if (FlatIdent_7B7BF == 0) then
					rainConn:Disconnect();
					rainConn = nil;
					break;
				end
			end
		end
		if on then
			local function wet()
				for _, obj in ipairs(workspace:GetDescendants()) do
					if (obj:IsA("BasePart") and ((obj.Name == "Baseplate") or obj.Name:lower():find("road") or obj.Name:lower():find("floor") or obj.Name:lower():find("pavement"))) then
						local FlatIdent_24505 = 0;
						while true do
							if (FlatIdent_24505 == 1) then
								pcall(function()
									obj.Transparency = 0.05;
								end);
								break;
							end
							if (FlatIdent_24505 == 0) then
								pcall(function()
									obj.Reflectance = 0.5;
								end);
								pcall(function()
									obj.Material = Enum.Material.Glass;
								end);
								FlatIdent_24505 = 1;
							end
						end
					end
				end
			end
			local function dry()
				for _, obj in ipairs(workspace:GetDescendants()) do
					if (obj:IsA("BasePart") and ((obj.Name == "Baseplate") or obj.Name:lower():find("road") or obj.Name:lower():find("floor") or obj.Name:lower():find("pavement"))) then
						local FlatIdent_4CCD = 0;
						while true do
							if (FlatIdent_4CCD == 0) then
								pcall(function()
									obj.Reflectance = 0;
								end);
								pcall(function()
									obj.Material = Enum.Material.Plastic;
								end);
								FlatIdent_4CCD = 1;
							end
							if (FlatIdent_4CCD == 1) then
								pcall(function()
									obj.Transparency = 0;
								end);
								break;
							end
						end
					end
				end
			end
			local isRaining = false;
			for _, obj in ipairs(workspace:GetDescendants()) do
				if (obj.Name:lower():find("rain") and (obj:IsA("ParticleEmitter") or obj:IsA("Sound")) and (obj.Enabled ~= false)) then
					isRaining = true;
					break;
				end
			end
			if isRaining then
				wet();
			end
			rainConn = workspace.DescendantAdded:Connect(function(obj)
				if (obj.Name:lower():find("rain") and (obj:IsA("ParticleEmitter") or obj:IsA("Sound"))) then
					local FlatIdent_68107 = 0;
					while true do
						if (FlatIdent_68107 == 0) then
							task.wait(0.5);
							wet();
							break;
						end
					end
				end
			end);
			hdState.rainConn = rainConn;
			hdState.dry = dry;
		elseif hdState.dry then
			hdState.dry();
		end
	end
	local tNeon, tWater, tLeaves, tRefl, tRain;
	CFG:AddToggle({Name=t.hd,Default=false,Callback=function(v)
		pcall(function()
			local FlatIdent_13092 = 0;
			while true do
				if (FlatIdent_13092 == 2) then
					if tRain then
						tRain:Set(v);
					end
					break;
				end
				if (FlatIdent_13092 == 0) then
					if tNeon then
						tNeon:Set(v);
					end
					if tWater then
						tWater:Set(v);
					end
					FlatIdent_13092 = 1;
				end
				if (FlatIdent_13092 == 1) then
					if tLeaves then
						tLeaves:Set(v);
					end
					if tRefl then
						tRefl:Set(v);
					end
					FlatIdent_13092 = 2;
				end
			end
		end);
	end});
	tNeon = CFG:AddToggle({Name="Noite Neon",Default=false,Callback=function(v)
		pcall(function()
			applyNeonNight(v);
		end);
	end});
	tWater = CFG:AddToggle({Name="Agua Realista",Default=false,Callback=function(v)
		pcall(function()
			applyRealisticWater(v);
		end);
	end});
	tLeaves = CFG:AddToggle({Name="Folhas",Default=false,Callback=function(v)
		pcall(function()
			applyFallingLeaves(v);
		end);
	end});
	tRefl = CFG:AddToggle({Name="Reflexo",Default=false,Callback=function(v)
		pcall(function()
			applyReflection(v);
		end);
	end});
	tRain = CFG:AddToggle({Name="Chuva",Default=false,Callback=function(v)
		pcall(function()
			applyRainWetFloor(v);
		end);
	end});
	local ET = W:MakeTab({t.extras,"cog"});
	ET:AddToggle({Name=t.auto_rejoin,Default=false,Callback=function(v)
		if v then
			setupAutoRejoin();
		end
	end});
	local CTab = W:MakeTab({t.cars,"car"});
	CTab:AddParagraph({t.cars,t.coming_soon});
	if isAdm(LP) then
		local AT = W:MakeTab({t.admin,"star"});
		AT:AddParagraph({t.admin_panel,"Hub"});
		AT:AddButton({t.admin_open,function()
			buildAdmin();
		end});
	end
	local CH = W:MakeTab({t.changelog,"list"});
	CH:AddSection({(V .. " - RGB & Fix")});
	CH:AddParagraph({"+ RGB Name","Cores automaticas no nome RP"});
	CH:AddParagraph({"+ Music Volume","Controle de volume"});
	CH:AddParagraph({"+ Logos","Atualizado"});
	W:SelectTab(PT2);
	ok(t.hub_loaded);
end
local CHAT_ATTR_SERVER = "KamuiChatS";
local CHAT_ATTR_GLOBAL = "KamuiChatG";
local chatSeen = {};
local chatMessages = {server={},global={}};
local chatRefs = nil;
local function sendChat(channel, msg)
	if (not msg or (msg == "")) then
		return;
	end
	local attr = ((channel == "server") and CHAT_ATTR_SERVER) or CHAT_ATTR_GLOBAL;
	local payload = LP.Name .. "||" .. msg .. "||" .. tostring(tick());
	pcall(function()
		LP:SetAttribute(attr, payload);
	end);
end
local function parseMsg(payload)
	local FlatIdent_7D968 = 0;
	local name;
	local msg;
	while true do
		if (FlatIdent_7D968 == 0) then
			if not payload then
				return nil;
			end
			name, msg = payload:match("([^|]+)||([^|]+)||");
			FlatIdent_7D968 = 1;
		end
		if (1 == FlatIdent_7D968) then
			if (not name or not msg) then
				local FlatIdent_2B4DB = 0;
				while true do
					if (FlatIdent_2B4DB == 0) then
						name = payload:match("^([^|]+)");
						msg = payload:match("||([^|]+)||");
						break;
					end
				end
			end
			return name, msg;
		end
	end
end
local function refreshChatUI()
	if not chatRefs then
		return;
	end
	local ch = chatRefs.current;
	local list = chatRefs.lists[ch];
	if not list then
		return;
	end
	list:ClearAllChildren();
	local layout = Instance.new("UIListLayout", list);
	layout.SortOrder = Enum.SortOrder.LayoutOrder;
	layout.Padding = UDim.new(0, 3);
	for _, m in ipairs(chatMessages[ch]) do
		local FlatIdent_85382 = 0;
		local row;
		while true do
			if (FlatIdent_85382 == 0) then
				row = Instance.new("TextLabel", list);
				row.Size = UDim2.new(1, -8, 0, 22);
				FlatIdent_85382 = 1;
			end
			if (FlatIdent_85382 == 3) then
				row.Font = Enum.Font.Gotham;
				row.TextXAlignment = Enum.TextXAlignment.Left;
				break;
			end
			if (FlatIdent_85382 == 1) then
				row.BackgroundTransparency = 1;
				row.Text = "[" .. m.name .. "] " .. m.msg;
				FlatIdent_85382 = 2;
			end
			if (FlatIdent_85382 == 2) then
				row.TextColor3 = Color3.fromRGB(240, 240, 240);
				row.TextScaled = true;
				FlatIdent_85382 = 3;
			end
		end
	end
	list.CanvasSize = UDim2.new(0, 0, 0, layout.AbsoluteContentSize.Y + 8);
end
local function pollChatAll()
	local FlatIdent_14F07 = 0;
	while true do
		if (FlatIdent_14F07 == 0) then
			for _, p in ipairs(P:GetPlayers()) do
				if (p:GetAttribute("KamuiHubUser") == true) then
					for _, ch in ipairs({"server","global"}) do
						local FlatIdent_74CC4 = 0;
						local attr;
						local val;
						while true do
							if (FlatIdent_74CC4 == 0) then
								attr = ((ch == "server") and CHAT_ATTR_SERVER) or CHAT_ATTR_GLOBAL;
								val = p:GetAttribute(attr);
								FlatIdent_74CC4 = 1;
							end
							if (FlatIdent_74CC4 == 1) then
								if (val and not chatSeen[val]) then
									local FlatIdent_88145 = 0;
									local n;
									local m;
									while true do
										if (FlatIdent_88145 == 1) then
											if (n and m) then
												table.insert(chatMessages[ch], {name=n,msg=m});
											end
											break;
										end
										if (FlatIdent_88145 == 0) then
											chatSeen[val] = true;
											n, m = parseMsg(val);
											FlatIdent_88145 = 1;
										end
									end
								end
								break;
							end
						end
					end
				end
			end
			refreshChatUI();
			break;
		end
	end
end
task.spawn(function()
	while true do
		local FlatIdent_EDE4 = 0;
		while true do
			if (FlatIdent_EDE4 == 0) then
				task.wait(0.6);
				pcall(pollChatAll);
				break;
			end
		end
	end
end);
local function openChatGUI(onClose)
	local FlatIdent_1A2FD = 0;
	local pg;
	local old;
	local gui;
	local frame;
	local fs;
	local title;
	local tabS;
	local tabG;
	local scroll;
	local sl;
	local input;
	local send;
	local close;
	local cont;
	local selectTab;
	while true do
		if (FlatIdent_1A2FD == 8) then
			close.Size = UDim2.new(0, 28, 0, 28);
			close.BackgroundColor3 = Color3.fromRGB(200, 50, 50);
			close.Text = "X";
			close.TextColor3 = Color3.new(1, 1, 1);
			close.TextScaled = true;
			close.Font = Enum.Font.GothamBold;
			close.BorderSizePixel = 0;
			Instance.new("UICorner", close).CornerRadius = UDim.new(0, 6);
			cont = Instance.new("TextButton", frame);
			cont.AnchorPoint = Vector2.new(0.5, 0.5);
			FlatIdent_1A2FD = 9;
		end
		if (0 == FlatIdent_1A2FD) then
			pg = LP:WaitForChild("PlayerGui");
			old = pg:FindFirstChild("KamuiChatUI");
			if old then
				old:Destroy();
			end
			gui = Instance.new("ScreenGui", pg);
			gui.Name = "KamuiChatUI";
			gui.ResetOnSpawn = false;
			gui.IgnoreGuiInset = true;
			gui.DisplayOrder = 1050;
			frame = Instance.new("Frame", gui);
			frame.AnchorPoint = Vector2.new(0.5, 0.5);
			FlatIdent_1A2FD = 1;
		end
		if (FlatIdent_1A2FD == 3) then
			tabS.TextColor3 = Color3.new(1, 1, 1);
			tabS.TextScaled = true;
			tabS.Font = Enum.Font.GothamBold;
			tabS.BorderSizePixel = 0;
			Instance.new("UICorner", tabS).CornerRadius = UDim.new(0, 8);
			tabG = Instance.new("TextButton", frame);
			tabG.Position = UDim2.new(0.51, 0, 0.12, 0);
			tabG.Size = UDim2.new(0.47, 0, 0.08, 0);
			tabG.BackgroundColor3 = Color3.fromRGB(30, 60, 100);
			tabG.Text = "Global (todos servidor)";
			FlatIdent_1A2FD = 4;
		end
		if (FlatIdent_1A2FD == 10) then
			selectTab = nil;
			function selectTab(ch)
				local FlatIdent_55B85 = 0;
				while true do
					if (FlatIdent_55B85 == 1) then
						refreshChatUI();
						break;
					end
					if (0 == FlatIdent_55B85) then
						chatRefs.current = ch;
						if (ch == "server") then
							tabS.BackgroundColor3 = Color3.fromRGB(0, 150, 255);
							tabG.BackgroundColor3 = Color3.fromRGB(30, 60, 100);
							tabS.TextColor3 = Color3.new(1, 1, 1);
							tabG.TextColor3 = Color3.fromRGB(180, 220, 255);
						else
							local FlatIdent_877A3 = 0;
							while true do
								if (FlatIdent_877A3 == 1) then
									tabS.TextColor3 = Color3.fromRGB(180, 220, 255);
									tabG.TextColor3 = Color3.new(1, 1, 1);
									break;
								end
								if (FlatIdent_877A3 == 0) then
									tabS.BackgroundColor3 = Color3.fromRGB(30, 60, 100);
									tabG.BackgroundColor3 = Color3.fromRGB(0, 150, 255);
									FlatIdent_877A3 = 1;
								end
							end
						end
						FlatIdent_55B85 = 1;
					end
				end
			end
			tabS.MouseButton1Click:Connect(function()
				selectTab("server");
			end);
			tabG.MouseButton1Click:Connect(function()
				selectTab("global");
			end);
			send.MouseButton1Click:Connect(function()
				local FlatIdent_4771B = 0;
				local msg;
				while true do
					if (FlatIdent_4771B == 0) then
						msg = input.Text;
						if (msg and (msg ~= "")) then
							local FlatIdent_2A476 = 0;
							while true do
								if (FlatIdent_2A476 == 0) then
									sendChat(chatRefs.current, msg);
									input.Text = "";
									break;
								end
							end
						end
						break;
					end
				end
			end);
			input.FocusLost:Connect(function(enter)
				if enter then
					send.MouseButton1Click:Fire();
				end
			end);
			close.MouseButton1Click:Connect(function()
				gui:Destroy();
				chatRefs = nil;
				if onClose then
					onClose();
				end
			end);
			cont.MouseButton1Click:Connect(function()
				local FlatIdent_6226C = 0;
				while true do
					if (FlatIdent_6226C == 1) then
						if onClose then
							onClose();
						end
						break;
					end
					if (FlatIdent_6226C == 0) then
						gui:Destroy();
						chatRefs = nil;
						FlatIdent_6226C = 1;
					end
				end
			end);
			refreshChatUI();
			return gui;
		end
		if (FlatIdent_1A2FD == 6) then
			input.BorderSizePixel = 0;
			input.PlaceholderText = "Digite uma mensagem...";
			input.Text = "";
			input.TextColor3 = Color3.fromRGB(255, 255, 255);
			input.TextScaled = true;
			input.Font = Enum.Font.Gotham;
			Instance.new("UICorner", input).CornerRadius = UDim.new(0, 8);
			send = Instance.new("TextButton", frame);
			send.Position = UDim2.new(0.76, 0, 0.83, 0);
			send.Size = UDim2.new(0.22, 0, 0.09, 0);
			FlatIdent_1A2FD = 7;
		end
		if (FlatIdent_1A2FD == 2) then
			title.BackgroundTransparency = 1;
			title.Text = "Kamui Chat";
			title.TextColor3 = Color3.fromRGB(0, 150, 255);
			title.TextScaled = true;
			title.Font = Enum.Font.GothamBold;
			tabS = Instance.new("TextButton", frame);
			tabS.Position = UDim2.new(0.02, 0, 0.12, 0);
			tabS.Size = UDim2.new(0.47, 0, 0.08, 0);
			tabS.BackgroundColor3 = Color3.fromRGB(0, 150, 255);
			tabS.Text = "Chat (servidor)";
			FlatIdent_1A2FD = 3;
		end
		if (1 == FlatIdent_1A2FD) then
			frame.Position = UDim2.new(0.5, 0, 0.5, 0);
			frame.Size = UDim2.new(0.75, 0, 0.68, 0);
			frame.BackgroundColor3 = Color3.fromRGB(15, 20, 30);
			frame.BorderSizePixel = 0;
			Instance.new("UICorner", frame).CornerRadius = UDim.new(0, 14);
			fs = Instance.new("UIStroke", frame);
			fs.Color = Color3.fromRGB(0, 150, 255);
			fs.Thickness = 2.5;
			title = Instance.new("TextLabel", frame);
			title.Size = UDim2.new(1, 0, 0.1, 0);
			FlatIdent_1A2FD = 2;
		end
		if (FlatIdent_1A2FD == 9) then
			cont.Position = UDim2.new(0.5, 0, 0.96, 0);
			cont.Size = UDim2.new(0.5, 0, 0.05, 0);
			cont.BackgroundColor3 = Color3.fromRGB(0, 180, 90);
			cont.BorderSizePixel = 0;
			cont.Text = "▶ Continuar";
			cont.TextColor3 = Color3.new(1, 1, 1);
			cont.TextScaled = true;
			cont.Font = Enum.Font.GothamBold;
			Instance.new("UICorner", cont).CornerRadius = UDim.new(0, 8);
			chatRefs = {current="server",lists={server=scroll,global=scroll},gui=gui};
			FlatIdent_1A2FD = 10;
		end
		if (FlatIdent_1A2FD == 5) then
			scroll.ScrollBarThickness = 5;
			scroll.CanvasSize = UDim2.new(0, 0, 0, 0);
			Instance.new("UICorner", scroll).CornerRadius = UDim.new(0, 8);
			sl = Instance.new("UIListLayout", scroll);
			sl.SortOrder = Enum.SortOrder.LayoutOrder;
			sl.Padding = UDim.new(0, 3);
			input = Instance.new("TextBox", frame);
			input.Position = UDim2.new(0.02, 0, 0.83, 0);
			input.Size = UDim2.new(0.72, 0, 0.09, 0);
			input.BackgroundColor3 = Color3.fromRGB(20, 30, 45);
			FlatIdent_1A2FD = 6;
		end
		if (FlatIdent_1A2FD == 4) then
			tabG.TextColor3 = Color3.fromRGB(180, 220, 255);
			tabG.TextScaled = true;
			tabG.Font = Enum.Font.GothamBold;
			tabG.BorderSizePixel = 0;
			Instance.new("UICorner", tabG).CornerRadius = UDim.new(0, 8);
			scroll = Instance.new("ScrollingFrame", frame);
			scroll.Position = UDim2.new(0.02, 0, 0.21, 0);
			scroll.Size = UDim2.new(0.96, 0, 0.55, 0);
			scroll.BackgroundColor3 = Color3.fromRGB(8, 12, 20);
			scroll.BorderSizePixel = 0;
			FlatIdent_1A2FD = 5;
		end
		if (FlatIdent_1A2FD == 7) then
			send.BackgroundColor3 = Color3.fromRGB(0, 150, 255);
			send.Text = "Enviar";
			send.TextColor3 = Color3.new(1, 1, 1);
			send.TextScaled = true;
			send.Font = Enum.Font.GothamBold;
			send.BorderSizePixel = 0;
			Instance.new("UICorner", send).CornerRadius = UDim.new(0, 8);
			close = Instance.new("TextButton", frame);
			close.AnchorPoint = Vector2.new(1, 0);
			close.Position = UDim2.new(1, -6, 0, 6);
			FlatIdent_1A2FD = 8;
		end
	end
end
local pg = LP:WaitForChild("PlayerGui");
local s = Instance.new("ScreenGui", pg);
s.Name = "KamuiLang";
s.ResetOnSpawn = false;
s.IgnoreGuiInset = true;
s.DisplayOrder = 1100;
local bg = Instance.new("Frame", s);
bg.Size = UDim2.new(1, 0, 1, 0);
bg.BackgroundColor3 = Color3.fromRGB(8, 12, 20);
bg.BorderSizePixel = 0;
local box = Instance.new("Frame", bg);
box.AnchorPoint = Vector2.new(0.5, 0.5);
box.Position = UDim2.new(0.5, 0, 0.5, 0);
box.Size = UDim2.new(0.78, 0, 0.35, 0);
box.BackgroundColor3 = Color3.fromRGB(15, 20, 30);
box.BorderSizePixel = 0;
Instance.new("UICorner", box).CornerRadius = UDim.new(0, 14);
local bs = Instance.new("UIStroke", box);
bs.Color = Color3.fromRGB(0, 150, 255);
bs.Thickness = 2.5;
local tl = Instance.new("TextLabel", box);
tl.Position = UDim2.new(0, 0, 0.08, 0);
tl.Size = UDim2.new(1, 0, 0.25, 0);
tl.BackgroundTransparency = 1;
tl.Text = "Kamui Hub ⚡";
tl.TextColor3 = Color3.fromRGB(0, 150, 255);
tl.TextScaled = true;
tl.Font = Enum.Font.GothamBold;
local sl = Instance.new("TextLabel", box);
sl.Position = UDim2.new(0, 0, 0.35, 0);
sl.Size = UDim2.new(1, 0, 0.12, 0);
sl.BackgroundTransparency = 1;
sl.Text = "Selecione o idioma / Select language";
sl.TextColor3 = Color3.fromRGB(180, 180, 180);
sl.TextScaled = true;
sl.Font = Enum.Font.Gotham;
local pb = Instance.new("TextButton", box);
pb.AnchorPoint = Vector2.new(0.5, 0.5);
pb.Position = UDim2.new(0.5, 0, 0.58, 0);
pb.Size = UDim2.new(0.7, 0, 0.13, 0);
pb.BackgroundColor3 = Color3.fromRGB(0, 100, 200);
pb.BorderSizePixel = 0;
pb.Text = "Português";
pb.TextColor3 = Color3.new(1, 1, 1);
pb.TextScaled = true;
pb.Font = Enum.Font.GothamBold;
Instance.new("UICorner", pb).CornerRadius = UDim.new(0, 10);
local eb = Instance.new("TextButton", box);
eb.AnchorPoint = Vector2.new(0.5, 0.5);
eb.Position = UDim2.new(0.5, 0, 0.78, 0);
eb.Size = UDim2.new(0.7, 0, 0.13, 0);
eb.BackgroundColor3 = Color3.fromRGB(40, 60, 90);
eb.BorderSizePixel = 0;
eb.Text = "English";
eb.TextColor3 = Color3.new(1, 1, 1);
eb.TextScaled = true;
eb.Font = Enum.Font.GothamBold;
Instance.new("UICorner", eb).CornerRadius = UDim.new(0, 10);
local function showLoader(cb)
	s:Destroy();
	local pg2 = LP:WaitForChild("PlayerGui");
	local old = pg2:FindFirstChild("KamuiLoader");
	if old then
		old:Destroy();
	end
	local s2 = Instance.new("ScreenGui", pg2);
	s2.Name = "KamuiLoader";
	s2.ResetOnSpawn = false;
	s2.IgnoreGuiInset = true;
	s2.DisplayOrder = 1000;
	local bg2 = Instance.new("Frame", s2);
	bg2.Size = UDim2.new(1, 0, 1, 0);
	bg2.BackgroundColor3 = Color3.fromRGB(8, 12, 20);
	bg2.BorderSizePixel = 0;
	local box2 = Instance.new("Frame", bg2);
	box2.AnchorPoint = Vector2.new(0.5, 0.5);
	box2.Position = UDim2.new(0.5, 0, 0.5, 0);
	box2.Size = UDim2.new(0.78, 0, 0.42, 0);
	box2.BackgroundColor3 = Color3.fromRGB(15, 20, 30);
	box2.BorderSizePixel = 0;
	Instance.new("UICorner", box2).CornerRadius = UDim.new(0, 14);
	local bs2 = Instance.new("UIStroke", box2);
	bs2.Color = Color3.fromRGB(0, 150, 255);
	bs2.Thickness = 2.5;
	local logo = Instance.new("ImageLabel", box2);
	logo.Position = UDim2.new(0.5, -40, 0.05, 0);
	logo.Size = UDim2.new(0, 80, 0, 80);
	logo.BackgroundTransparency = 1;
	logo.Image = LOGO_ID;
	logo.ScaleType = Enum.ScaleType.Fit;
	local tl2 = Instance.new("TextLabel", box2);
	tl2.Position = UDim2.new(0, 0, 0.35, 0);
	tl2.Size = UDim2.new(1, 0, 0.2, 0);
	tl2.BackgroundTransparency = 1;
	tl2.Text = "Kamui Hub ⚡";
	tl2.TextColor3 = Color3.fromRGB(0, 150, 255);
	tl2.TextScaled = true;
	tl2.Font = Enum.Font.GothamBold;
	local sl2 = Instance.new("TextLabel", box2);
	sl2.Position = UDim2.new(0, 0, 0.55, 0);
	sl2.Size = UDim2.new(1, 0, 0.12, 0);
	sl2.BackgroundTransparency = 1;
	sl2.Text = "Standard Edition " .. V;
	sl2.TextColor3 = Color3.fromRGB(100, 180, 255);
	sl2.TextScaled = true;
	sl2.Font = Enum.Font.GothamSemibold;
	local bar = Instance.new("Frame", box2);
	bar.AnchorPoint = Vector2.new(0.5, 1);
	bar.Position = UDim2.new(0.5, 0, 0.95, 0);
	bar.Size = UDim2.new(0.8, 0, 0.035, 0);
	bar.BackgroundColor3 = Color3.fromRGB(30, 40, 55);
	bar.BorderSizePixel = 0;
	Instance.new("UICorner", bar).CornerRadius = UDim.new(1, 0);
	local fl = Instance.new("Frame", bar);
	fl.Size = UDim2.new(0, 0, 1, 0);
	fl.BackgroundColor3 = Color3.fromRGB(0, 150, 255);
	fl.BorderSizePixel = 0;
	Instance.new("UICorner", fl).CornerRadius = UDim.new(1, 0);
	task.spawn(function()
		for i = 0, 100, 4 do
			fl.Size = UDim2.new(i / 100, 0, 1, 0);
			task.wait(0.02);
		end
		task.wait(0.3);
		tl2.Visible = false;
		sl2.Visible = false;
		bar.Visible = false;
		logo.Visible = false;
		local optTitle = Instance.new("TextLabel", box2);
		optTitle.AnchorPoint = Vector2.new(0.5, 0);
		optTitle.Position = UDim2.new(0.5, 0, 0.1, 0);
		optTitle.Size = UDim2.new(0.9, 0, 0.15, 0);
		optTitle.BackgroundTransparency = 1;
		optTitle.Text = "Como deseja iniciar?";
		optTitle.TextColor3 = Color3.fromRGB(0, 150, 255);
		optTitle.TextScaled = true;
		optTitle.Font = Enum.Font.GothamBold;
		local btn1 = Instance.new("TextButton", box2);
		btn1.AnchorPoint = Vector2.new(0.5, 0.5);
		btn1.Position = UDim2.new(0.5, 0, 0.42, 0);
		btn1.Size = UDim2.new(0.82, 0, 0.15, 0);
		btn1.BackgroundColor3 = Color3.fromRGB(30, 60, 100);
		btn1.BorderSizePixel = 0;
		btn1.Text = "Executar sem chat";
		btn1.TextColor3 = Color3.fromRGB(180, 220, 255);
		btn1.TextScaled = true;
		btn1.Font = Enum.Font.GothamBold;
		Instance.new("UICorner", btn1).CornerRadius = UDim.new(0, 10);
		local btn2 = Instance.new("TextButton", box2);
		btn2.AnchorPoint = Vector2.new(0.5, 0.5);
		btn2.Position = UDim2.new(0.5, 0, 0.68, 0);
		btn2.Size = UDim2.new(0.82, 0, 0.15, 0);
		btn2.BackgroundColor3 = Color3.fromRGB(0, 150, 255);
		btn2.BorderSizePixel = 0;
		btn2.Text = "Executar com chat";
		btn2.TextColor3 = Color3.new(1, 1, 1);
		btn2.TextScaled = true;
		btn2.Font = Enum.Font.GothamBold;
		Instance.new("UICorner", btn2).CornerRadius = UDim.new(0, 10);
		local function runFinal()
			local FlatIdent_8982C = 0;
			local suc;
			local err;
			while true do
				if (FlatIdent_8982C == 0) then
					optTitle:Destroy();
					btn1:Destroy();
					FlatIdent_8982C = 1;
				end
				if (FlatIdent_8982C == 3) then
					task.delay(5, function()
						isBuildingHub = false;
					end);
					if not suc then
						warn("[Kamui] Hub error: " .. tostring(err));
						pcall(function()
							er("Hub error: " .. tostring(err));
						end);
					end
					break;
				end
				if (FlatIdent_8982C == 1) then
					btn2:Destroy();
					s2:Destroy();
					FlatIdent_8982C = 2;
				end
				if (2 == FlatIdent_8982C) then
					isBuildingHub = true;
					suc, err = pcall(cb);
					FlatIdent_8982C = 3;
				end
			end
		end
		btn1.MouseButton1Click:Connect(function()
			runFinal();
		end);
		btn2.MouseButton1Click:Connect(function()
			openChatGUI(function()
				runFinal();
			end);
		end);
	end);
end
pb.MouseButton1Click:Connect(function()
	local FlatIdent_4415F = 0;
	while true do
		if (0 == FlatIdent_4415F) then
			LANG = "pt";
			showLoader(function()
				buildHub();
			end);
			break;
		end
	end
end);
eb.MouseButton1Click:Connect(function()
	LANG = "en";
	showLoader(function()
		buildHub();
	end);
end);
