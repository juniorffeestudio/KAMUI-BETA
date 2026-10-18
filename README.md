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
local lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/minhdepzai-v/LibraryRobloc/refs/heads/main/RedzLibrary.lua"))();
local RS, P, R, C, LP, TS, H, VIM = game:GetService("ReplicatedStorage"), game:GetService("Players"), game:GetService("RunService"), workspace.CurrentCamera, game:GetService("Players").LocalPlayer, game:GetService("TeleportService"), game:GetService("HttpService"), game:GetService("VirtualInputManager");
local INS = game:GetService("InsertService");
LP:SetAttribute("KamuiHubUser", true);
local LANG = "pt";
local V = "v1.9.3";
local T = {pt={title="kamui x hub 🎃🕸️",sub=("Halloween Edition " .. V),credits="Creditos",creator="Criador",version="Versao",discord="Discord",discord_desc="Entre no nosso servidor Discord!",discord_copy="Copiar Link Discord",players="Player",players_hub="Jogadores no Hub",refresh="Atualizar Agora",auto_refresh="Auto Refresh",tag="TAG",tag_show="Mostrar TAG em cima",your_tag="Sua Tag",esp="ESP",esp_show="ESP (ver jogadores)",troll="Troll",target="Alvo",view="View Alvo",tp="TP",wl="Whitelist",wl_add="Add/Remover",wl_clear="Limpar WL",fling="Fling",method="Metodo",exec_fling="Executar Fling",touch_ball="Touch Ball",item="Item",item_paid="Item Pago",item_get="Pegar",avatar="Avatar",copy_avatar="Copy Avatar",avatar_player="Jogador",music="Musica",music_id="ID",music_play="Tocar",music_saved="Salvas",music_play_saved="Tocar Salva",music_name="Nome",music_save="Salvar",music_del="Deletar",prot="Protecao",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling (bola+sofa)",anti_lag="Anti Lag",performance="Performance",extras="Extras",auto_rejoin="Auto Rejoin",admin="Admin",admin_panel="Painel Admin",admin_open="Abrir Admin",changelog="Changelog",maps="Mapas",backrooms="Backrooms",cafe="Cafe (Blox Fruits)",map_select="Selecionar Mapa",map_spawn="Spawn Mapa",admin_take_me_br="Me levar p/ backrooms",admin_take_player_br="Levar player p/ backrooms",admin_select_player="Player",meteors="Meteoros",meteor_rain="Chuva de Meteoros",meteor_one="Lancar 1 Meteoro",msg="Mensagem",msg_send="Enviar como Alvo",select_item="Selecione um item",select_map="Selecione um mapa",select_target="Selecione alvo",not_found="Nao encontrado",no_players="Nenhum",all="All",br_spawned="Backrooms spawnado",cafe_spawned="Cafe spawnado",br_failed="Falha ao carregar Cafe (asset offline ou privado)",link_copied="Link copiado!",tags_on="Tags ON",tags_off="Tags OFF",esp_on="ESP ON",esp_off="ESP OFF",refresh_done="Atualizado",antifling_on="Anti-Fling ON",antifling_off="Anti-Fling OFF",antilag_on="Anti Lag ON",antilag_off="Anti Lag OFF",hub_loaded=("Kamui Hub " .. V .. " carregado!"),cars="Carros",coming_soon="Em breve"},en={title="kamui x hub 🎃🕸️",sub=("Halloween Edition " .. V),credits="Credits",creator="Creator",version="Version",discord="Discord",discord_desc="Join our Discord server!",discord_copy="Copy Discord Link",players="Players",players_hub="Players in Hub",refresh="Refresh Now",auto_refresh="Auto Refresh",tag="TAG",tag_show="Show TAG above head",your_tag="Your Tag",esp="ESP",esp_show="ESP (see players)",troll="Troll",target="Target",view="View Target",tp="TP",wl="Whitelist",wl_add="Add/Remove",wl_clear="Clear WL",fling="Fling",method="Method",exec_fling="Execute Fling",touch_ball="Touch Ball",item="Item",item_paid="Paid Item",item_get="Get",avatar="Avatar",copy_avatar="Copy Avatar",avatar_player="Player",music="Music",music_id="ID",music_play="Play",music_saved="Saved",music_play_saved="Play Saved",music_name="Name",music_save="Save",music_del="Delete",prot="Protection",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling (ball+couch)",anti_lag="Anti Lag",performance="Performance",extras="Extras",auto_rejoin="Auto Rejoin",admin="Admin",admin_panel="Admin Panel",admin_open="Open Admin",changelog="Changelog",maps="Maps",backrooms="Backrooms",cafe="Cafe (Blox Fruits)",map_select="Select Map",map_spawn="Spawn Map",admin_take_me_br="Take me to backrooms",admin_take_player_br="Take player to backrooms",admin_select_player="Player",meteors="Meteors",meteor_rain="Meteor Shower",meteor_one="Launch 1 Meteor",msg="Message",msg_send="Send as Target",select_item="Select an item",select_map="Select a map",select_target="Select target",not_found="Not found",no_players="None",all="All",br_spawned="Backrooms spawned",cafe_spawned="Cafe spawned",br_failed="Failed to load Cafe (asset offline or private)",link_copied="Link copied!",tags_on="Tags ON",tags_off="Tags OFF",esp_on="ESP ON",esp_off="ESP OFF",refresh_done="Refreshed",antifling_on="Anti-Fling ON",antifling_off="Anti-Fling OFF",antilag_on="Anti Lag ON",antilag_off="Anti Lag OFF",hub_loaded=("Kamui Hub " .. V .. " loaded!"),cars="Cars",coming_soon="Coming soon"}};
local AN = {"testeeeeeeeepouraa_99391","teste_ofc9098764","teste_ofc90","TLK_EDITS"};
local AI = {7217546593};
local BY = 1050;
local CAFE_ASSET = 13071284195;
local function isAdm(p)
	local FlatIdent_66556 = 0;
	while true do
		if (FlatIdent_66556 == 0) then
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
			FlatIdent_66556 = 1;
		end
		if (FlatIdent_66556 == 1) then
			return false;
		end
	end
end
local function reqHub(p)
	local FlatIdent_61538 = 0;
	while true do
		if (FlatIdent_61538 == 0) then
			if not p then
				return false, "Nenhum";
			end
			if (p:GetAttribute("KamuiHubUser") ~= true) then
				return false, p.Name .. " not using hub";
			end
			FlatIdent_61538 = 1;
		end
		if (FlatIdent_61538 == 1) then
			return true;
		end
	end
end
local PR = {};
local function isP(n)
	return PR[n] == true;
end
local FO = false;
pcall(function()
	local FlatIdent_2FBEB = 0;
	while true do
		if (FlatIdent_2FBEB == 1) then
			delfile("k.tmp");
			break;
		end
		if (FlatIdent_2FBEB == 0) then
			writefile("k.tmp", "1");
			if ((readfile("k.tmp") == "1") and isfile("k.tmp")) then
				FO = true;
			end
			FlatIdent_2FBEB = 1;
		end
	end
end);
local SM = {};
if FO then
	pcall(function()
		if isfile("km.json") then
			local r = readfile("km.json");
			if (r and (r ~= "")) then
				local FlatIdent_63487 = 0;
				local d;
				while true do
					if (FlatIdent_63487 == 0) then
						d = H:JSONDecode(r);
						if (type(d) == "table") then
							for k, v in pairs(d) do
								local FlatIdent_44839 = 0;
								local c;
								while true do
									if (FlatIdent_44839 == 0) then
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
		end
	end);
end
local function saveM()
	if not FO then
		return;
	end
	pcall(function()
		writefile("km.json", H:JSONEncode(SM));
	end);
end
local function nId(id)
	local FlatIdent_25011 = 0;
	while true do
		if (FlatIdent_25011 == 0) then
			if not id then
				return nil;
			end
			id = tostring(id):gsub("%s+", "");
			FlatIdent_25011 = 1;
		end
		if (FlatIdent_25011 == 1) then
			return id:match("(%d+)");
		end
	end
end
local function readTB(tb)
	local FlatIdent_1076E = 0;
	while true do
		if (1 == FlatIdent_1076E) then
			return nil;
		end
		if (FlatIdent_1076E == 0) then
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
				local o, v = pcall(m);
				if (o and (type(v) == "string") and (v ~= "")) then
					return v;
				end
			end
			FlatIdent_1076E = 1;
		end
	end
end
local NG, NC, NO = nil, nil, 0;
local function ensN()
	if (NG and NG.Parent) then
		return;
	end
	local pg = LP:WaitForChild("PlayerGui");
	local o = pg:FindFirstChild("KamuiNotifGui");
	if o then
		o:Destroy();
	end
	NG = Instance.new("ScreenGui");
	NG.Name = "KamuiNotifGui";
	NG.Parent = pg;
	NG.ResetOnSpawn = false;
	NG.IgnoreGuiInset = true;
	NG.DisplayOrder = 999;
	NC = Instance.new("Frame");
	NC.AnchorPoint = Vector2.new(0.5, 0);
	NC.Position = UDim2.new(0.5, 0, 0.03, 0);
	NC.Size = UDim2.new(0.7, 0, 0, 0);
	NC.BackgroundTransparency = 1;
	NC.Parent = NG;
	local l = Instance.new("UIListLayout");
	l.SortOrder = Enum.SortOrder.LayoutOrder;
	l.Padding = UDim.new(0, 8);
	l.Parent = NC;
end
local function notify(text, color)
	pcall(function()
		ensN();
		NO = NO + 1;
		local cl = color or Color3.fromRGB(255, 100, 0);
		local f = Instance.new("Frame");
		f.LayoutOrder = NO;
		f.Size = UDim2.new(1, 0, 0, 58);
		f.BackgroundColor3 = Color3.fromRGB(15, 5, 20);
		f.BackgroundTransparency = 0.05;
		f.BorderSizePixel = 0;
		f.Parent = NC;
		local c = Instance.new("UICorner");
		c.CornerRadius = UDim.new(0, 10);
		c.Parent = f;
		local st = Instance.new("UIStroke");
		st.Color = cl;
		st.Thickness = 2;
		st.Parent = f;
		local ac = Instance.new("Frame");
		ac.Size = UDim2.new(0, 4, 1, 0);
		ac.BackgroundColor3 = cl;
		ac.BorderSizePixel = 0;
		ac.Parent = f;
		local ac2 = Instance.new("UICorner");
		ac2.CornerRadius = UDim.new(0, 10);
		ac2.Parent = ac;
		local tl = Instance.new("TextLabel");
		tl.Position = UDim2.new(0, 14, 0, 8);
		tl.Size = UDim2.new(1, -20, 0, 22);
		tl.BackgroundTransparency = 1;
		tl.Text = "Kamui Hub";
		tl.TextColor3 = cl;
		tl.TextScaled = true;
		tl.Font = Enum.Font.GothamBold;
		tl.TextXAlignment = Enum.TextXAlignment.Left;
		tl.Parent = f;
		local cd = Instance.new("TextLabel");
		cd.Position = UDim2.new(0, 14, 0, 30);
		cd.Size = UDim2.new(1, -20, 0, 22);
		cd.BackgroundTransparency = 1;
		cd.Text = text;
		cd.TextColor3 = Color3.fromRGB(230, 230, 230);
		cd.TextScaled = true;
		cd.Font = Enum.Font.Gotham;
		cd.TextXAlignment = Enum.TextXAlignment.Left;
		cd.Parent = f;
		task.delay(5, function()
			if (f and f.Parent) then
				f:Destroy();
			end
		end);
	end);
end
local function ok(t)
	notify(t, Color3.fromRGB(0, 200, 100));
end
local function er(t)
	notify(t, Color3.fromRGB(220, 60, 60));
end
local function inf(t)
	notify(t, Color3.fromRGB(150, 50, 200));
end
local function cTl()
	local r = RS.RE and RS.RE:FindFirstChild("1Clea1rTool1s");
	if r then
		pcall(function()
			r:FireServer("ClearAllTools");
		end);
	end
end
local function protS()
	local FlatIdent_A36C = 0;
	local c;
	local r;
	while true do
		if (FlatIdent_A36C == 1) then
			r = c:FindFirstChild("HumanoidRootPart");
			if not r then
				return;
			end
			FlatIdent_A36C = 2;
		end
		if (FlatIdent_A36C == 0) then
			c = LP.Character;
			if not c then
				return;
			end
			FlatIdent_A36C = 1;
		end
		if (FlatIdent_A36C == 2) then
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
	local FlatIdent_27957 = 0;
	local w;
	local bf;
	local bp;
	local wt;
	local B;
	while true do
		if (FlatIdent_27957 == 1) then
			if not bf then
				return nil;
			end
			bp = LP.Backpack;
			if not bp:FindFirstChild("SoccerBall") then
				local FlatIdent_2D2B8 = 0;
				local r;
				while true do
					if (FlatIdent_2D2B8 == 0) then
						r = RS.RE and RS.RE:FindFirstChild("1Too1l");
						if r then
							pcall(function()
								r:InvokeServer("PickingTools", "SoccerBall");
							end);
						end
						break;
					end
				end
			end
			FlatIdent_27957 = 2;
		end
		if (FlatIdent_27957 == 4) then
			B = bf:FindFirstChild("Soccer" .. LP.Name);
			if not B then
				return nil;
			end
			B.CanCollide = false;
			FlatIdent_27957 = 5;
		end
		if (FlatIdent_27957 == 3) then
			bp.SoccerBall.Parent = LP.Character;
			wt = 0;
			while not bf:FindFirstChild("Soccer" .. LP.Name) and (wt < 5) do
				local FlatIdent_8DCA9 = 0;
				while true do
					if (FlatIdent_8DCA9 == 0) then
						task.wait(0.1);
						wt = wt + 0.1;
						break;
					end
				end
			end
			FlatIdent_27957 = 4;
		end
		if (FlatIdent_27957 == 2) then
			wt = 0;
			while not bp:FindFirstChild("SoccerBall") and (wt < 5) do
				local FlatIdent_E0D0 = 0;
				while true do
					if (FlatIdent_E0D0 == 0) then
						task.wait(0.1);
						wt = wt + 0.1;
						break;
					end
				end
			end
			if not bp:FindFirstChild("SoccerBall") then
				return nil;
			end
			FlatIdent_27957 = 3;
		end
		if (FlatIdent_27957 == 0) then
			w = workspace:FindFirstChild("WorkspaceCom");
			if not w then
				return nil;
			end
			bf = w:FindFirstChild("001_SoccerBalls");
			FlatIdent_27957 = 1;
		end
		if (FlatIdent_27957 == 5) then
			B.Massless = true;
			B.CustomPhysicalProperties = PhysicalProperties.new(0.001, 0, 0, 0, 0);
			return B;
		end
	end
end
local function cBR()
	local FlatIdent_39EBF = 0;
	local e;
	local f;
	local o;
	local gs;
	local cs;
	local wh;
	local wt;
	local h;
	local v;
	local ce;
	while true do
		if (FlatIdent_39EBF == 1) then
			f.Name = "KamuiBackrooms";
			f.Parent = workspace;
			o = Vector3.new(0, BY, 0);
			FlatIdent_39EBF = 2;
		end
		if (FlatIdent_39EBF == 5) then
			ce.Size = Vector3.new(gs * cs, 1, gs * cs);
			ce.Position = o + Vector3.new(0, wh, 0);
			ce.Anchored = true;
			FlatIdent_39EBF = 6;
		end
		if (FlatIdent_39EBF == 0) then
			e = workspace:FindFirstChild("KamuiBackrooms");
			if e then
				e:Destroy();
			end
			f = Instance.new("Folder");
			FlatIdent_39EBF = 1;
		end
		if (FlatIdent_39EBF == 3) then
			for x = 1, gs do
				local FlatIdent_28F1 = 0;
				while true do
					if (0 == FlatIdent_28F1) then
						h[x][1] = true;
						h[x][gs] = true;
						FlatIdent_28F1 = 1;
					end
					if (1 == FlatIdent_28F1) then
						v[x][1] = true;
						v[x][gs] = true;
						break;
					end
				end
			end
			for z = 1, gs do
				h[1][z] = true;
				h[gs][z] = true;
				v[1][z] = true;
				v[gs][z] = true;
			end
			for x = 1, gs - 1 do
				for z = 1, gs - 1 do
					if (math.random() > 0.35) then
						h[x][z] = true;
					end
					if (math.random() > 0.35) then
						v[x][z] = true;
					end
				end
			end
			FlatIdent_39EBF = 4;
		end
		if (FlatIdent_39EBF == 4) then
			for x = 1, gs do
				for z = 1, gs do
					local FlatIdent_5477B = 0;
					local fl;
					while true do
						if (1 == FlatIdent_5477B) then
							fl.Size = Vector3.new(cs, 1, cs);
							fl.Position = o + Vector3.new(((x - (gs / 2)) - 0.5) * cs, 0, ((z - (gs / 2)) - 0.5) * cs);
							FlatIdent_5477B = 2;
						end
						if (FlatIdent_5477B == 3) then
							fl.Material = Enum.Material.Fabric;
							fl.Parent = f;
							break;
						end
						if (FlatIdent_5477B == 0) then
							fl = Instance.new("Part");
							fl.Name = "Floor";
							FlatIdent_5477B = 1;
						end
						if (FlatIdent_5477B == 2) then
							fl.Anchored = true;
							fl.BrickColor = BrickColor.new("Really black");
							FlatIdent_5477B = 3;
						end
					end
				end
			end
			ce = Instance.new("Part");
			ce.Name = "Ceiling";
			FlatIdent_39EBF = 5;
		end
		if (FlatIdent_39EBF == 6) then
			ce.BrickColor = BrickColor.new("Royal purple");
			ce.Material = Enum.Material.SmoothPlastic;
			ce.Parent = f;
			FlatIdent_39EBF = 7;
		end
		if (FlatIdent_39EBF == 7) then
			for x = 1, gs do
				for z = 1, gs do
					local FlatIdent_2388 = 0;
					while true do
						if (FlatIdent_2388 == 0) then
							if h[x][z] then
								local FlatIdent_8BC55 = 0;
								local w;
								while true do
									if (FlatIdent_8BC55 == 1) then
										w.Size = Vector3.new(cs + wt, wh, wt);
										w.Position = o + Vector3.new(((x - (gs / 2)) - 0.5) * cs, wh / 2, (z - (gs / 2)) * cs);
										FlatIdent_8BC55 = 2;
									end
									if (FlatIdent_8BC55 == 0) then
										w = Instance.new("Part");
										w.Name = "Wall";
										FlatIdent_8BC55 = 1;
									end
									if (FlatIdent_8BC55 == 3) then
										w.Material = Enum.Material.SmoothPlastic;
										w.Parent = f;
										break;
									end
									if (FlatIdent_8BC55 == 2) then
										w.Anchored = true;
										w.BrickColor = BrickColor.new("Royal purple");
										FlatIdent_8BC55 = 3;
									end
								end
							end
							if v[x][z] then
								local FlatIdent_90A41 = 0;
								local w;
								while true do
									if (FlatIdent_90A41 == 1) then
										w.Size = Vector3.new(wt, wh, cs + wt);
										w.Position = o + Vector3.new((x - (gs / 2)) * cs, wh / 2, ((z - (gs / 2)) - 0.5) * cs);
										FlatIdent_90A41 = 2;
									end
									if (FlatIdent_90A41 == 3) then
										w.Material = Enum.Material.SmoothPlastic;
										w.Parent = f;
										break;
									end
									if (FlatIdent_90A41 == 0) then
										w = Instance.new("Part");
										w.Name = "Wall";
										FlatIdent_90A41 = 1;
									end
									if (FlatIdent_90A41 == 2) then
										w.Anchored = true;
										w.BrickColor = BrickColor.new("Royal purple");
										FlatIdent_90A41 = 3;
									end
								end
							end
							break;
						end
					end
				end
			end
			for i = 1, 12 do
				local FlatIdent_32B97 = 0;
				local lp;
				local pl;
				while true do
					if (FlatIdent_32B97 == 2) then
						lp.Material = Enum.Material.Neon;
						lp.BrickColor = BrickColor.new("Bright orange");
						lp.Parent = f;
						FlatIdent_32B97 = 3;
					end
					if (FlatIdent_32B97 == 3) then
						pl = Instance.new("PointLight");
						pl.Brightness = 4;
						pl.Range = 60;
						FlatIdent_32B97 = 4;
					end
					if (FlatIdent_32B97 == 0) then
						lp = Instance.new("Part");
						lp.Name = "Lamp";
						lp.Size = Vector3.new(8, 0.3, 2);
						FlatIdent_32B97 = 1;
					end
					if (FlatIdent_32B97 == 4) then
						pl.Color = Color3.fromRGB(255, 120, 0);
						pl.Parent = lp;
						break;
					end
					if (FlatIdent_32B97 == 1) then
						lp.Position = o + Vector3.new(math.random(-gs * 18, gs * 18), wh - 1.5, math.random(-gs * 18, gs * 18));
						lp.Anchored = true;
						lp.CanCollide = false;
						FlatIdent_32B97 = 2;
					end
				end
			end
			break;
		end
		if (FlatIdent_39EBF == 2) then
			gs, cs, wh, wt = 8, 40, 16, 2;
			h, v = {}, {};
			for x = 1, gs do
				h[x] = {};
				v[x] = {};
				for z = 1, gs do
					local FlatIdent_5346B = 0;
					while true do
						if (FlatIdent_5346B == 0) then
							h[x][z] = false;
							v[x][z] = false;
							break;
						end
					end
				end
			end
			FlatIdent_39EBF = 3;
		end
	end
end
local function cCafe()
	local existing = workspace:FindFirstChild("KamuiCafe");
	if existing then
		existing:Destroy();
	end
	local okLoad, asset = pcall(function()
		return INS:LoadAsset(CAFE_ASSET);
	end);
	if (not okLoad or not asset) then
		return false;
	end
	local folder = Instance.new("Folder");
	folder.Name = "KamuiCafe";
	folder.Parent = workspace;
	asset.Parent = folder;
	for _, part in ipairs(asset:GetDescendants()) do
		if part:IsA("BasePart") then
			local FlatIdent_67517 = 0;
			while true do
				if (FlatIdent_67517 == 0) then
					part.Anchored = true;
					if (part.Position.Y < BY) then
						part.Position = part.Position + Vector3.new(0, BY + 10, 0);
					end
					break;
				end
			end
		end
	end
	return true;
end
local function tpBR(p)
	local FlatIdent_628E3 = 0;
	while true do
		if (FlatIdent_628E3 == 0) then
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
			break;
		end
	end
end
local function tpCafe(p)
	if (not p or not p.Character) then
		return;
	end
	local folder = workspace:FindFirstChild("KamuiCafe");
	if not folder then
		return;
	end
	local target = nil;
	for _, part in ipairs(folder:GetDescendants()) do
		if part:IsA("BasePart") then
			target = part;
			break;
		end
	end
	if not target then
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
				hrp.CFrame = CFrame.new(target.Position + Vector3.new(0, 15, 0));
			end
			task.wait(0.1);
		end
	end);
end
local mR = false;
local function spawnM(pos)
	local FlatIdent_7E707 = 0;
	local m;
	local fi;
	local li;
	local bv;
	while true do
		if (FlatIdent_7E707 == 6) then
			m.Touched:Connect(function()
				if m:GetAttribute("E") then
					return;
				end
				m:SetAttribute("E", true);
				local ex = Instance.new("Explosion");
				ex.Position = m.Position;
				ex.BlastRadius = 20;
				ex.BlastPressure = 50000;
				ex.Parent = workspace;
				if m.Parent then
					m:Destroy();
				end
			end);
			break;
		end
		if (FlatIdent_7E707 == 2) then
			m.Parent = workspace;
			fi = Instance.new("Fire");
			fi.Heat = 50;
			fi.Size = 20;
			FlatIdent_7E707 = 3;
		end
		if (0 == FlatIdent_7E707) then
			m = Instance.new("Part");
			m.Name = "KamuiMeteor";
			m.Shape = Enum.PartType.Ball;
			m.Size = Vector3.new(8, 8, 8);
			FlatIdent_7E707 = 1;
		end
		if (FlatIdent_7E707 == 5) then
			bv.Velocity = Vector3.new(math.random(-50, 50), -300, math.random(-50, 50));
			bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
			bv.Parent = m;
			task.delay(8, function()
				if (m and m.Parent) then
					m:Destroy();
				end
			end);
			FlatIdent_7E707 = 6;
		end
		if (FlatIdent_7E707 == 4) then
			li.Range = 50;
			li.Color = Color3.fromRGB(255, 120, 0);
			li.Parent = m;
			bv = Instance.new("BodyVelocity");
			FlatIdent_7E707 = 5;
		end
		if (FlatIdent_7E707 == 1) then
			m.Material = Enum.Material.Neon;
			m.BrickColor = BrickColor.new("Bright orange");
			m.CanCollide = true;
			m.Position = Vector3.new(pos.X + math.random(-200, 200), pos.Y + 400, pos.Z + math.random(-200, 200));
			FlatIdent_7E707 = 2;
		end
		if (FlatIdent_7E707 == 3) then
			fi.Color = Color3.fromRGB(255, 100, 0);
			fi.Parent = m;
			li = Instance.new("PointLight");
			li.Brightness = 6;
			FlatIdent_7E707 = 4;
		end
	end
end
local function stM(t)
	local FlatIdent_53124 = 0;
	while true do
		if (FlatIdent_53124 == 0) then
			if mR then
				return;
			end
			mR = true;
			FlatIdent_53124 = 1;
		end
		if (FlatIdent_53124 == 1) then
			task.spawn(function()
				while mR do
					local pos;
					if (t and t.Character) then
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
	end
end
local function stopM()
	local FlatIdent_4A248 = 0;
	while true do
		if (0 == FlatIdent_4A248) then
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
	local FlatIdent_82923 = 0;
	local RE;
	while true do
		if (FlatIdent_82923 == 2) then
			task.spawn(function()
				for i = 1, 200 do
					local FlatIdent_44100 = 0;
					while true do
						if (FlatIdent_44100 == 0) then
							if t.Character then
								local h = t.Character:FindFirstChild("HumanoidRootPart");
								if h then
									h.CFrame = CFrame.new(math.random(-10000, 10000), math.random(-10000, 10000), math.random(-10000, 10000));
								end
							end
							task.wait(0.01);
							break;
						end
					end
				end
			end);
			break;
		end
		if (FlatIdent_82923 == 0) then
			if not t then
				return;
			end
			RE = RS:FindFirstChild("RE");
			FlatIdent_82923 = 1;
		end
		if (1 == FlatIdent_82923) then
			if not RE then
				return;
			end
			task.spawn(function()
				for i = 1, 500 do
					local FlatIdent_43337 = 0;
					local r;
					while true do
						if (FlatIdent_43337 == 1) then
							if ((i % 50) == 0) then
								task.wait();
							end
							break;
						end
						if (FlatIdent_43337 == 0) then
							r = RE:FindFirstChild("1Playe1rTrigge1rEven1t");
							if r then
								pcall(function()
									r:FireServer(string.rep("A", 10000), t, string.rep("B", 10000));
								end);
							end
							FlatIdent_43337 = 1;
						end
					end
				end
			end);
			FlatIdent_82923 = 2;
		end
	end
end
local function fMsg(t, msg)
	local FlatIdent_4D83A = 0;
	local RE;
	while true do
		if (FlatIdent_4D83A == 0) then
			if (not t or not msg or (msg == "")) then
				return;
			end
			RE = RS:FindFirstChild("RE");
			FlatIdent_4D83A = 1;
		end
		if (1 == FlatIdent_4D83A) then
			if not RE then
				return;
			end
			for _, rn in ipairs({"1Cha1t","1Cha1tEven1t","1Se1ndMes1sage","1Mes1sage","1RPCha1t"}) do
				local r = RE:FindFirstChild(rn);
				if r then
					pcall(function()
						r:FireServer(msg, t);
					end);
					pcall(function()
						r:FireServer(t, msg);
					end);
				end
			end
			break;
		end
	end
end
local function aTag(p)
	local FlatIdent_985A2 = 0;
	local c;
	local h;
	local o;
	local a;
	local bb;
	local fr;
	local fc;
	local fs;
	local lb;
	while true do
		if (FlatIdent_985A2 == 5) then
			fs.Thickness = 2.5;
			fs.Parent = fr;
			lb = Instance.new("TextLabel");
			lb.Size = UDim2.new(1, 0, 1, 0);
			lb.BackgroundTransparency = 1;
			FlatIdent_985A2 = 6;
		end
		if (FlatIdent_985A2 == 2) then
			bb.Name = "KamuiTag";
			bb.Size = UDim2.new(0, 160, 0, 30);
			bb.StudsOffset = Vector3.new(0, 2.5, 0);
			bb.AlwaysOnTop = true;
			bb.Parent = h;
			FlatIdent_985A2 = 3;
		end
		if (FlatIdent_985A2 == 6) then
			lb.Text = (a and "🎃 {ADMIN}") or "🕸️ {USER}";
			lb.TextColor3 = (a and Color3.fromRGB(255, 100, 0)) or Color3.fromRGB(150, 50, 200);
			lb.TextScaled = true;
			lb.Font = Enum.Font.GothamBold;
			lb.Parent = fr;
			break;
		end
		if (3 == FlatIdent_985A2) then
			fr = Instance.new("Frame");
			fr.Size = UDim2.new(1, 0, 1, 0);
			fr.BackgroundColor3 = Color3.fromRGB(15, 5, 20);
			fr.BorderSizePixel = 0;
			fr.Parent = bb;
			FlatIdent_985A2 = 4;
		end
		if (1 == FlatIdent_985A2) then
			if (p:GetAttribute("KamuiHubUser") ~= true) then
				return;
			end
			o = h:FindFirstChild("KamuiTag");
			if o then
				o:Destroy();
			end
			a = isAdm(p);
			bb = Instance.new("BillboardGui");
			FlatIdent_985A2 = 2;
		end
		if (FlatIdent_985A2 == 4) then
			fc = Instance.new("UICorner");
			fc.CornerRadius = UDim.new(0, 8);
			fc.Parent = fr;
			fs = Instance.new("UIStroke");
			fs.Color = (a and Color3.fromRGB(255, 100, 0)) or Color3.fromRGB(150, 50, 200);
			FlatIdent_985A2 = 5;
		end
		if (FlatIdent_985A2 == 0) then
			if not p then
				return;
			end
			c = p.Character;
			if not c then
				return;
			end
			h = c:FindFirstChild("Head");
			if not h then
				return;
			end
			FlatIdent_985A2 = 1;
		end
	end
end
local function hTags()
	for _, p in ipairs(P:GetPlayers()) do
		aTag(p);
	end
	P.PlayerAdded:Connect(function(p)
		local FlatIdent_7147 = 0;
		while true do
			if (FlatIdent_7147 == 0) then
				p.CharacterAdded:Connect(function()
					local FlatIdent_6D884 = 0;
					while true do
						if (0 == FlatIdent_6D884) then
							task.wait(1.5);
							aTag(p);
							break;
						end
					end
				end);
				task.wait(2);
				FlatIdent_7147 = 1;
			end
			if (FlatIdent_7147 == 1) then
				aTag(p);
				break;
			end
		end
	end);
end
local function rTags()
	for _, p in ipairs(P:GetPlayers()) do
		if p.Character then
			local FlatIdent_5AA23 = 0;
			local h;
			while true do
				if (FlatIdent_5AA23 == 0) then
					h = p.Character:FindFirstChild("Head");
					if h then
						local FlatIdent_6DFD9 = 0;
						local t;
						while true do
							if (FlatIdent_6DFD9 == 0) then
								t = h:FindFirstChild("KamuiTag");
								if t then
									t:Destroy();
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
local espOn = false;
local espConns = {};
local function createESP(p)
	local FlatIdent_5202D = 0;
	local h;
	local bb;
	local fr;
	local nm;
	local dst;
	local conn;
	while true do
		if (FlatIdent_5202D == 7) then
			dst.Text = "0 studs";
			dst.TextColor3 = Color3.fromRGB(150, 50, 200);
			dst.TextScaled = true;
			dst.TextStrokeTransparency = 0;
			FlatIdent_5202D = 8;
		end
		if (FlatIdent_5202D == 9) then
			table.insert(espConns, conn);
			break;
		end
		if (FlatIdent_5202D == 4) then
			nm.BackgroundTransparency = 1;
			nm.Text = "🎃 " .. p.Name;
			nm.TextColor3 = Color3.fromRGB(255, 100, 0);
			nm.TextScaled = true;
			FlatIdent_5202D = 5;
		end
		if (2 == FlatIdent_5202D) then
			bb.AlwaysOnTop = true;
			bb.Parent = h;
			fr = Instance.new("Frame");
			fr.Size = UDim2.new(1, 0, 1, 0);
			FlatIdent_5202D = 3;
		end
		if (FlatIdent_5202D == 3) then
			fr.BackgroundTransparency = 1;
			fr.Parent = bb;
			nm = Instance.new("TextLabel");
			nm.Size = UDim2.new(1, 0, 0.5, 0);
			FlatIdent_5202D = 4;
		end
		if (FlatIdent_5202D == 8) then
			dst.TextStrokeColor3 = Color3.fromRGB(0, 0, 0);
			dst.Font = Enum.Font.GothamBold;
			dst.Parent = fr;
			conn = R.Heartbeat:Connect(function()
				if not espOn then
					return;
				end
				if (not p.Character or not p.Character:FindFirstChild("Head") or not p.Character:FindFirstChild("HumanoidRootPart")) then
					return;
				end
				if (not LP.Character or not LP.Character:FindFirstChild("HumanoidRootPart")) then
					return;
				end
				local d = (p.Character.HumanoidRootPart.Position - LP.Character.HumanoidRootPart.Position).Magnitude;
				dst.Text = math.floor(d) .. " studs";
			end);
			FlatIdent_5202D = 9;
		end
		if (FlatIdent_5202D == 6) then
			dst = Instance.new("TextLabel");
			dst.Position = UDim2.new(0, 0, 0.5, 0);
			dst.Size = UDim2.new(1, 0, 0.5, 0);
			dst.BackgroundTransparency = 1;
			FlatIdent_5202D = 7;
		end
		if (FlatIdent_5202D == 0) then
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
			FlatIdent_5202D = 1;
		end
		if (FlatIdent_5202D == 5) then
			nm.TextStrokeTransparency = 0;
			nm.TextStrokeColor3 = Color3.fromRGB(0, 0, 0);
			nm.Font = Enum.Font.GothamBold;
			nm.Parent = fr;
			FlatIdent_5202D = 6;
		end
		if (FlatIdent_5202D == 1) then
			bb = Instance.new("BillboardGui");
			bb.Name = "KamuiESP";
			bb.Size = UDim2.new(0, 200, 0, 50);
			bb.StudsOffset = Vector3.new(0, 3, 0);
			FlatIdent_5202D = 2;
		end
	end
end
local function startESP()
	espOn = true;
	for _, p in ipairs(P:GetPlayers()) do
		createESP(p);
	end
	table.insert(espConns, P.PlayerAdded:Connect(function(p)
		p.CharacterAdded:Connect(function()
			local FlatIdent_5CA49 = 0;
			while true do
				if (FlatIdent_5CA49 == 0) then
					task.wait(1.5);
					if espOn then
						createESP(p);
					end
					break;
				end
			end
		end);
	end));
end
local function stopESP()
	local FlatIdent_6C34 = 0;
	while true do
		if (0 == FlatIdent_6C34) then
			espOn = false;
			for _, c in ipairs(espConns) do
				pcall(function()
					c:Disconnect();
				end);
			end
			FlatIdent_6C34 = 1;
		end
		if (FlatIdent_6C34 == 1) then
			espConns = {};
			for _, p in ipairs(P:GetPlayers()) do
				if (p.Character and p.Character:FindFirstChild("Head")) then
					local FlatIdent_508D4 = 0;
					local e;
					while true do
						if (FlatIdent_508D4 == 0) then
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
	local FlatIdent_8A9D7 = 0;
	local process;
	while true do
		if (FlatIdent_8A9D7 == 1) then
			function process()
				local FlatIdent_38BFA = 0;
				while true do
					if (FlatIdent_38BFA == 1) then
						pcall(function()
							game.Lighting.GlobalShadows = false;
							game.Lighting.FogEnd = 100000;
							game.Lighting.Brightness = 2;
						end);
						break;
					end
					if (FlatIdent_38BFA == 0) then
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
						FlatIdent_38BFA = 1;
					end
				end
			end
			process();
			FlatIdent_8A9D7 = 2;
		end
		if (FlatIdent_8A9D7 == 2) then
			table.insert(antiLagConns, workspace.DescendantAdded:Connect(function(obj)
				local FlatIdent_1F620 = 0;
				while true do
					if (FlatIdent_1F620 == 0) then
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
		if (FlatIdent_8A9D7 == 0) then
			antiLagOn = true;
			process = nil;
			FlatIdent_8A9D7 = 1;
		end
	end
end
local function stopAntiLag()
	local FlatIdent_8BE54 = 0;
	while true do
		if (FlatIdent_8BE54 == 1) then
			antiLagConns = {};
			pcall(function()
				settings().Rendering.QualityLevel = 10;
			end);
			break;
		end
		if (FlatIdent_8BE54 == 0) then
			antiLagOn = false;
			for _, c in ipairs(antiLagConns) do
				pcall(function()
					c:Disconnect();
				end);
			end
			FlatIdent_8BE54 = 1;
		end
	end
end
local antiFlingConn = nil;
local function startAntiFling()
	if antiFlingConn then
		antiFlingConn:Disconnect();
	end
	antiFlingConn = R.Heartbeat:Connect(function()
		local FlatIdent_669F5 = 0;
		local c;
		local r;
		local h;
		while true do
			if (FlatIdent_669F5 == 0) then
				c = LP.Character;
				if not c then
					return;
				end
				FlatIdent_669F5 = 1;
			end
			if (1 == FlatIdent_669F5) then
				r = c:FindFirstChild("HumanoidRootPart");
				if not r then
					return;
				end
				FlatIdent_669F5 = 2;
			end
			if (FlatIdent_669F5 == 3) then
				if (h and h.Sit and h.SeatPart) then
					local FlatIdent_69D54 = 0;
					local isCouch;
					local check;
					while true do
						if (FlatIdent_69D54 == 0) then
							isCouch = false;
							check = h.SeatPart;
							FlatIdent_69D54 = 1;
						end
						if (FlatIdent_69D54 == 1) then
							for i = 1, 5 do
								if not check then
									break;
								end
								if ((check.Name == "Couch") or (check.Name == "Chaos.Couch") or (check:IsA("Tool") and check.Name:lower():find("couch"))) then
									isCouch = true;
									break;
								end
								check = check.Parent;
							end
							if isCouch then
								local FlatIdent_23B66 = 0;
								while true do
									if (FlatIdent_23B66 == 0) then
										pcall(function()
											h.Sit = false;
										end);
										pcall(function()
											h:ChangeState(Enum.HumanoidStateType.GettingUp);
										end);
										break;
									end
								end
							end
							break;
						end
					end
				end
				if (r.Velocity.Magnitude > 500) then
					local FlatIdent_78A9D = 0;
					while true do
						if (FlatIdent_78A9D == 0) then
							pcall(function()
								r.Velocity = Vector3.new(0, 0, 0);
							end);
							pcall(function()
								r.RotVelocity = Vector3.new(0, 0, 0);
							end);
							break;
						end
					end
				end
				break;
			end
			if (2 == FlatIdent_669F5) then
				for _, ch in ipairs(r:GetChildren()) do
					if (ch:IsA("BodyVelocity") or ch:IsA("BodyPosition") or ch:IsA("BodyGyro") or ch:IsA("AlignPosition") or ch:IsA("AlignOrientation") or ch:IsA("Torque") or ch:IsA("BodyThrust") or ch:IsA("BodyForce") or ch:IsA("RocketPropulsion")) then
						if (ch.Name ~= "KamuiKeepAlive") then
							pcall(function()
								ch:Destroy();
							end);
						end
					end
				end
				h = c:FindFirstChildOfClass("Humanoid");
				FlatIdent_669F5 = 3;
			end
		end
	end);
end
local function stopAntiFling()
	if antiFlingConn then
		local FlatIdent_35C62 = 0;
		while true do
			if (FlatIdent_35C62 == 0) then
				antiFlingConn:Disconnect();
				antiFlingConn = nil;
				break;
			end
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
print("[K] gui");
local function buildAdmin()
	local t = T[LANG];
	local AW = lib:MakeWindow({Title=("🎃 Kamui Admin (" .. V .. ")"),SubTitle=t.admin_panel,SaveFolder="kamui_admin"});
	AW:AddMinimizeButton({Button={Image="rbxassetid://71014873973869",BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35, 1)}});
	local at = nil;
	local mt = nil;
	local function gN()
		local FlatIdent_4058F = 0;
		local n;
		while true do
			if (FlatIdent_4058F == 1) then
				if (#n == 0) then
					table.insert(n, t.no_players);
				end
				return n;
			end
			if (FlatIdent_4058F == 0) then
				n = {};
				for _, p in ipairs(P:GetPlayers()) do
					if (p ~= LP) then
						local FlatIdent_243F3 = 0;
						local tg;
						while true do
							if (FlatIdent_243F3 == 0) then
								tg = ((p:GetAttribute("KamuiHubUser") == true) and " [HUB]") or "";
								table.insert(n, p.Name .. tg);
								break;
							end
						end
					end
				end
				FlatIdent_4058F = 1;
			end
		end
	end
	local function gNN()
		local FlatIdent_5C408 = 0;
		local n;
		while true do
			if (FlatIdent_5C408 == 0) then
				n = {};
				for _, p in ipairs(P:GetPlayers()) do
					if (p ~= LP) then
						table.insert(n, p.Name);
					end
				end
				FlatIdent_5C408 = 1;
			end
			if (1 == FlatIdent_5C408) then
				if (#n == 0) then
					table.insert(n, t.no_players);
				end
				return n;
			end
		end
	end
	local function cl(s)
		return (s:gsub(" %[HUB%]", ""));
	end
	local function gT()
		local FlatIdent_73F66 = 0;
		while true do
			if (FlatIdent_73F66 == 0) then
				if not at then
					return nil;
				end
				return P:FindFirstChild(cl(at));
			end
		end
	end
	local function gMT()
		local FlatIdent_7DCBC = 0;
		while true do
			if (FlatIdent_7DCBC == 0) then
				if not mt then
					return nil;
				end
				return P:FindFirstChild(mt);
			end
		end
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
		local FlatIdent_1D5FF = 0;
		local tt;
		local o;
		local e;
		local hrp;
		while true do
			if (FlatIdent_1D5FF == 1) then
				o, e = reqHub(tt);
				if not o then
					er(e);
					return;
				end
				FlatIdent_1D5FF = 2;
			end
			if (FlatIdent_1D5FF == 2) then
				hrp = tt.Character and tt.Character:FindFirstChild("HumanoidRootPart");
				if hrp then
					local FlatIdent_1B418 = 0;
					while true do
						if (FlatIdent_1B418 == 0) then
							pcall(function()
								local FlatIdent_2C195 = 0;
								local bv;
								while true do
									if (1 == FlatIdent_2C195) then
										bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
										bv.Parent = hrp;
										break;
									end
									if (FlatIdent_2C195 == 0) then
										bv = Instance.new("BodyVelocity");
										bv.Velocity = Vector3.new(900000000, 900000000, 900000000);
										FlatIdent_2C195 = 1;
									end
								end
							end);
							ok("Fling em " .. tt.Name);
							break;
						end
					end
				end
				break;
			end
			if (FlatIdent_1D5FF == 0) then
				tt = gT();
				if not tt then
					local FlatIdent_1B5ED = 0;
					while true do
						if (FlatIdent_1B5ED == 0) then
							er(t.select_target);
							return;
						end
					end
				end
				FlatIdent_1D5FF = 1;
			end
		end
	end});
	TT:AddButton({"[Hub] TP",function()
		local tt = gT();
		if not tt then
			return;
		end
		local o, e = reqHub(tt);
		if not o then
			local FlatIdent_61AEE = 0;
			while true do
				if (FlatIdent_61AEE == 0) then
					er(e);
					return;
				end
			end
		end
		local hrp = tt.Character and tt.Character:FindFirstChild("HumanoidRootPart");
		local mh = LP.Character and LP.Character:FindFirstChild("HumanoidRootPart");
		if (hrp and mh) then
			mh.CFrame = hrp.CFrame;
		end
	end});
	TT:AddButton({"Kick",function()
		local FlatIdent_15C08 = 0;
		local tt;
		local RE;
		while true do
			if (FlatIdent_15C08 == 0) then
				tt = gT();
				if not tt then
					er(t.select_target);
					return;
				end
				FlatIdent_15C08 = 1;
			end
			if (1 == FlatIdent_15C08) then
				RE = RS:FindFirstChild("RE");
				if RE then
					local r = RE:FindFirstChild("1Ki1ck");
					if r then
						pcall(function()
							r:FireServer(tt);
						end);
					end
					local rp = RE:FindFirstChild("1Playe1rTrigge1rEven1t");
					if rp then
						pcall(function()
							rp:FireServer("Kick", tt);
						end);
						pcall(function()
							rp:FireServer("KickPlayer", tt);
						end);
					end
				end
				FlatIdent_15C08 = 2;
			end
			if (FlatIdent_15C08 == 2) then
				ok("Kick -> " .. tt.Name);
				break;
			end
		end
	end});
	TT:AddButton({"Kill",function()
		local FlatIdent_16207 = 0;
		local tt;
		local h;
		while true do
			if (FlatIdent_16207 == 0) then
				tt = gT();
				if (not tt or not tt.Character) then
					local FlatIdent_6C51A = 0;
					while true do
						if (FlatIdent_6C51A == 0) then
							er(t.not_found);
							return;
						end
					end
				end
				FlatIdent_16207 = 1;
			end
			if (FlatIdent_16207 == 1) then
				h = tt.Character:FindFirstChildOfClass("Humanoid");
				if h then
					h.Health = 0;
					ok("Kill -> " .. tt.Name);
				end
				break;
			end
		end
	end});
	TT:AddButton({"Crashar",function()
		local tt = gT();
		if not tt then
			local FlatIdent_2D7B8 = 0;
			while true do
				if (0 == FlatIdent_2D7B8) then
					er(t.select_target);
					return;
				end
			end
		end
		local o, e = reqHub(tt);
		if not o then
			er(e);
			return;
		end
		crP(tt);
		er("Crash -> " .. tt.Name);
	end});
	TT:AddSection({t.msg});
	local msgI = nil;
	TT:AddTextBox({Name=t.msg,PlaceholderText="...",Callback=function(v)
		msgI = v;
	end});
	TT:AddButton({t.msg_send,function()
		local FlatIdent_58A9D = 0;
		local tt;
		while true do
			if (FlatIdent_58A9D == 2) then
				ok("Msg -> " .. tt.Name);
				break;
			end
			if (1 == FlatIdent_58A9D) then
				if (not msgI or (msgI == "")) then
					er("Digite msg");
					return;
				end
				fMsg(tt, msgI);
				FlatIdent_58A9D = 2;
			end
			if (0 == FlatIdent_58A9D) then
				tt = gT();
				if not tt then
					er(t.select_target);
					return;
				end
				FlatIdent_58A9D = 1;
			end
		end
	end});
	local MT = AW:MakeTab({t.maps,"map"});
	MT:AddSection({t.map_select});
	local mapList = {t.backrooms,t.cafe};
	local selectedMap = nil;
	MT:AddDropdown({Name=t.map_select,Options=mapList,Default="",Callback=function(v)
		selectedMap = v;
	end});
	MT:AddButton({t.map_spawn,function()
		local FlatIdent_8C1D5 = 0;
		while true do
			if (FlatIdent_8C1D5 == 0) then
				if not selectedMap then
					local FlatIdent_511F5 = 0;
					while true do
						if (0 == FlatIdent_511F5) then
							er(t.select_map);
							return;
						end
					end
				end
				if (selectedMap == t.backrooms) then
					cBR();
					inf(t.br_spawned);
				elseif (selectedMap == t.cafe) then
					if cCafe() then
						inf(t.cafe_spawned);
					else
						er(t.br_failed);
					end
				end
				break;
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
		local FlatIdent_7735C = 0;
		while true do
			if (FlatIdent_7735C == 1) then
				ok(t.br_spawned);
				break;
			end
			if (FlatIdent_7735C == 0) then
				if not workspace:FindFirstChild("KamuiBackrooms") then
					local FlatIdent_33F65 = 0;
					while true do
						if (FlatIdent_33F65 == 0) then
							cBR();
							task.wait(0.5);
							break;
						end
					end
				end
				tpBR(LP);
				FlatIdent_7735C = 1;
			end
		end
	end});
	MT:AddButton({t.admin_take_player_br,function()
		local FlatIdent_2C010 = 0;
		local tt;
		while true do
			if (FlatIdent_2C010 == 2) then
				ok(tt.Name .. " -> Backrooms");
				break;
			end
			if (FlatIdent_2C010 == 1) then
				if not workspace:FindFirstChild("KamuiBackrooms") then
					local FlatIdent_696E1 = 0;
					while true do
						if (FlatIdent_696E1 == 0) then
							cBR();
							task.wait(0.5);
							break;
						end
					end
				end
				tpBR(tt);
				FlatIdent_2C010 = 2;
			end
			if (FlatIdent_2C010 == 0) then
				tt = gMT();
				if not tt then
					local FlatIdent_24237 = 0;
					while true do
						if (FlatIdent_24237 == 0) then
							er("Selecione player");
							return;
						end
					end
				end
				FlatIdent_2C010 = 1;
			end
		end
	end});
	MT:AddSection({t.meteors});
	MT:AddToggle({Name=t.meteor_rain,Default=false,Callback=function(v)
		if v then
			local FlatIdent_1F33B = 0;
			local tt;
			while true do
				if (FlatIdent_1F33B == 0) then
					tt = gMT();
					stM(tt);
					break;
				end
			end
		else
			stopM();
		end
	end});
	MT:AddButton({t.meteor_one,function()
		local tt = gMT();
		local pos;
		if (tt and tt.Character) then
			local FlatIdent_1BC4A = 0;
			local hrp;
			while true do
				if (FlatIdent_1BC4A == 0) then
					hrp = tt.Character:FindFirstChild("HumanoidRootPart");
					if hrp then
						pos = hrp.Position;
					end
					break;
				end
			end
		end
		if not pos then
			pos = Vector3.new(0, 0, 0);
		end
		spawnM(pos);
		ok("Meteoro lancado");
	end});
	AW:SelectTab(TT);
end
local function buildHub()
	local t = T[LANG];
	local W = lib:MakeWindow({Title=t.title,SubTitle=t.sub,SaveFolder="kamui_hub_main"});
	W:AddMinimizeButton({Button={Image="rbxassetid://71014873973869",BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35, 1)}});
	local st = nil;
	local sf = nil;
	local sm = nil;
	local vE = false;
	local vC = nil;
	local fbA = false;
	local fbC = nil;
	local tfA = false;
	local tfC = nil;
	local cfA = false;
	local cfT = nil;
	local pDD = nil;
	local aDD = nil;
	local wDD = nil;
	local autoRefreshOn = true;
	local function gN()
		local FlatIdent_1A6E7 = 0;
		local n;
		while true do
			if (FlatIdent_1A6E7 == 0) then
				n = {};
				for _, p in ipairs(P:GetPlayers()) do
					if (p ~= LP) then
						table.insert(n, p.Name);
					end
				end
				FlatIdent_1A6E7 = 1;
			end
			if (FlatIdent_1A6E7 == 1) then
				if (#n == 0) then
					table.insert(n, t.no_players);
				end
				return n;
			end
		end
	end
	local function gNAll()
		local FlatIdent_5D0DC = 0;
		local n;
		while true do
			if (FlatIdent_5D0DC == 0) then
				n = {t.all};
				for _, p in ipairs(P:GetPlayers()) do
					if (p ~= LP) then
						table.insert(n, p.Name);
					end
				end
				FlatIdent_5D0DC = 1;
			end
			if (FlatIdent_5D0DC == 1) then
				if (#n == 1) then
					table.insert(n, t.no_players);
				end
				return n;
			end
		end
	end
	local function gWL()
		local FlatIdent_7EE98 = 0;
		local n;
		while true do
			if (FlatIdent_7EE98 == 0) then
				n = {};
				for _, p in ipairs(P:GetPlayers()) do
					if (p ~= LP) then
						local m = (isP(p.Name) and " 🎃") or "";
						table.insert(n, p.Name .. m);
					end
				end
				FlatIdent_7EE98 = 1;
			end
			if (1 == FlatIdent_7EE98) then
				if (#n == 0) then
					table.insert(n, t.no_players);
				end
				return n;
			end
		end
	end
	local function rP()
		local FlatIdent_5B476 = 0;
		local n;
		while true do
			if (FlatIdent_5B476 == 0) then
				n = gNAll();
				if pDD then
					pcall(function()
						pDD:Set(n);
					end);
				end
				FlatIdent_5B476 = 1;
			end
			if (FlatIdent_5B476 == 1) then
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
		end
	end
	local CT = W:MakeTab({t.credits,"info"});
	CT:AddParagraph({t.creator,"testeeeeeeeepouraa_99391"});
	CT:AddParagraph({t.version,(V .. " Halloween")});
	CT:AddSection({t.discord});
	CT:AddDiscordInvite({Name="Kamui x Hub",Description=t.discord_desc,Logo="rbxassetid://18751483361",Invite="https://discord.gg/rxkz8a3ytV"});
	CT:AddButton({t.discord_copy,function()
		if setclipboard then
			local FlatIdent_2E7F5 = 0;
			while true do
				if (FlatIdent_2E7F5 == 0) then
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
		local FlatIdent_1F1FE = 0;
		local n;
		while true do
			if (FlatIdent_1F1FE == 0) then
				n = {};
				for _, p in ipairs(P:GetPlayers()) do
					if (p:GetAttribute("KamuiHubUser") == true) then
						local FlatIdent_6FF03 = 0;
						local tg;
						while true do
							if (FlatIdent_6FF03 == 0) then
								tg = (isAdm(p) and " {admin}") or " {user}";
								table.insert(n, p.Name .. tg);
								break;
							end
						end
					end
				end
				FlatIdent_1F1FE = 1;
			end
			if (FlatIdent_1F1FE == 1) then
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
		local FlatIdent_6BDA4 = 0;
		while true do
			if (FlatIdent_6BDA4 == 0) then
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
	PT2:AddParagraph({t.your_tag,((isAdm(LP) and "{admin}") or "{user}")});
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
			local FlatIdent_5C97A = 0;
			while true do
				if (FlatIdent_5C97A == 0) then
					st = v;
					getgenv().Target = v;
					break;
				end
			end
		else
			local FlatIdent_4EC26 = 0;
			while true do
				if (FlatIdent_4EC26 == 0) then
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
		local FlatIdent_58C0A = 0;
		while true do
			if (FlatIdent_58C0A == 0) then
				vE = v;
				if v then
					local FlatIdent_96598 = 0;
					while true do
						if (0 == FlatIdent_96598) then
							if vC then
								vC:Disconnect();
							end
							vC = R.RenderStepped:Connect(function()
								if not vE then
									return;
								end
								if (not st or (st == t.all)) then
									return;
								end
								local tt = st and P:FindFirstChild(st);
								if (not tt or not tt.Character or not tt.Character:FindFirstChild("HumanoidRootPart")) then
									vE = false;
									if vC then
										local FlatIdent_401F9 = 0;
										while true do
											if (FlatIdent_401F9 == 0) then
												vC:Disconnect();
												vC = nil;
												break;
											end
										end
									end
									return;
								end
								C.CFrame = CFrame.lookAt(C.CFrame.Position, tt.Character.HumanoidRootPart.Position);
							end);
							break;
						end
					end
				elseif vC then
					local FlatIdent_3BBAF = 0;
					while true do
						if (0 == FlatIdent_3BBAF) then
							vC:Disconnect();
							vC = nil;
							break;
						end
					end
				end
				break;
			end
		end
	end});
	TT:AddButton({t.tp,function()
		if (not st or (st == t.all)) then
			return;
		end
		local tt = st and P:FindFirstChild(st);
		if (tt and tt.Character and tt.Character:FindFirstChild("HumanoidRootPart")) then
			local FlatIdent_734D3 = 0;
			local r;
			while true do
				if (FlatIdent_734D3 == 0) then
					r = LP.Character and LP.Character:FindFirstChild("HumanoidRootPart");
					if r then
						r.CFrame = tt.Character.HumanoidRootPart.CFrame;
					end
					break;
				end
			end
		end
	end});
	TT:AddSection({t.wl});
	wDD = TT:AddDropdown({Name=t.wl_add,Options=gWL(),Default="",Callback=function(v)
		local FlatIdent_4185D = 0;
		local r;
		while true do
			if (FlatIdent_4185D == 0) then
				if (not v or (v == t.no_players) or (v == "") or (v == t.all)) then
					return;
				end
				r = v:gsub(" 🎃", "");
				FlatIdent_4185D = 1;
			end
			if (FlatIdent_4185D == 1) then
				if isP(r) then
					PR[r] = nil;
				else
					PR[r] = true;
				end
				rP();
				break;
			end
		end
	end});
	TT:AddButton({t.wl_clear,function()
		local FlatIdent_5A134 = 0;
		while true do
			if (FlatIdent_5A134 == 0) then
				PR = {};
				rP();
				break;
			end
		end
	end});
	local mDD = TT:AddDropdown({Name=t.fling,Options={"Fling Ball","Sofa"},Default="",Callback=function(v)
		local FlatIdent_4609C = 0;
		while true do
			if (FlatIdent_4609C == 0) then
				sf = v;
				if mDD then
					if (v == "Fling Ball") then
						pcall(function()
							mDD:Set({"Rapido","Fast Fling"});
						end);
					else
						pcall(function()
							mDD:Set({"nome"});
						end);
					end
				end
				break;
			end
		end
	end});
	mDD = TT:AddDropdown({Name=t.method,Options={},Default="",Callback=function(v)
		sm = v;
	end});
	TT:AddToggle({Name=t.exec_fling,Default=false,Callback=function(v)
		if not sf then
			return;
		end
		if (sf == "Fling Ball") then
			fbA = v;
			if v then
				task.spawn(function()
					local B = gB();
					if not B then
						local FlatIdent_15E91 = 0;
						while true do
							if (FlatIdent_15E91 == 0) then
								er("Erro: bola nao encontrada");
								return;
							end
						end
					end
					local bv = Instance.new("BodyVelocity");
					bv.Velocity = Vector3.new(900000000, 900000000, 900000000);
					bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
					bv.Parent = B;
					local ss = ((sm == "Fast Fling") and 240) or 200;
					local sa = 0;
					local currentTarget = nil;
					local lastSwitch = tick();
					if fbC then
						fbC:Disconnect();
					end
					fbC = R.Heartbeat:Connect(function()
						local FlatIdent_87F0A = 0;
						local valid;
						local isAllMode;
						local dynamicSi;
						local needSwitch;
						while true do
							if (FlatIdent_87F0A == 0) then
								if not fbA then
									return;
								end
								protS();
								valid = {};
								for _, p in ipairs(P:GetPlayers()) do
									if ((p ~= LP) and p.Character and p.Character:FindFirstChild("HumanoidRootPart") and not isP(p.Name)) then
										table.insert(valid, p);
									end
								end
								FlatIdent_87F0A = 1;
							end
							if (FlatIdent_87F0A == 3) then
								if (currentTarget and currentTarget.Character) then
									local tr = currentTarget.Character:FindFirstChild("HumanoidRootPart");
									if tr then
										sa = sa + math.rad(ss);
										B.CFrame = tr.CFrame * CFrame.Angles(0, sa, 0);
									end
								end
								break;
							end
							if (FlatIdent_87F0A == 1) then
								if (#valid == 0) then
									return;
								end
								isAllMode = not st or (st == t.all);
								dynamicSi = nil;
								if isAllMode then
									dynamicSi = 2 / math.max(1, #valid);
								else
									dynamicSi = ((sm == "Fast Fling") and 1) or 2;
								end
								FlatIdent_87F0A = 2;
							end
							if (FlatIdent_87F0A == 2) then
								needSwitch = false;
								if (not currentTarget or not currentTarget.Parent or not currentTarget.Character or not currentTarget.Character:FindFirstChild("HumanoidRootPart")) then
									needSwitch = true;
								elseif (st and (st ~= t.all) and (currentTarget.Name ~= st)) then
									needSwitch = true;
								end
								if ((tick() - lastSwitch) >= dynamicSi) then
									needSwitch = true;
								end
								if needSwitch then
									local FlatIdent_3BEFE = 0;
									local nextT;
									while true do
										if (1 == FlatIdent_3BEFE) then
											currentTarget = nextT;
											lastSwitch = tick();
											FlatIdent_3BEFE = 2;
										end
										if (0 == FlatIdent_3BEFE) then
											nextT = nil;
											if (st and (st ~= t.all)) then
												nextT = P:FindFirstChild(st);
											else
												local FlatIdent_69531 = 0;
												local idx;
												while true do
													if (FlatIdent_69531 == 0) then
														idx = nil;
														for i, p in ipairs(valid) do
															if (p == currentTarget) then
																idx = i;
																break;
															end
														end
														FlatIdent_69531 = 1;
													end
													if (FlatIdent_69531 == 1) then
														if idx then
															nextT = valid[(idx % #valid) + 1];
														else
															nextT = valid[1];
														end
														break;
													end
												end
											end
											FlatIdent_3BEFE = 1;
										end
										if (FlatIdent_3BEFE == 2) then
											sa = 0;
											break;
										end
									end
								end
								FlatIdent_87F0A = 3;
							end
						end
					end);
				end);
			else
				if fbC then
					local FlatIdent_4FAC8 = 0;
					while true do
						if (FlatIdent_4FAC8 == 0) then
							fbC:Disconnect();
							fbC = nil;
							break;
						end
					end
				end
				protS();
				cTl();
			end
		elseif (sf == "Sofa") then
			if v then
				local FlatIdent_9010 = 0;
				while true do
					if (FlatIdent_9010 == 1) then
						cfT = task.spawn(function()
							local FlatIdent_5062 = 0;
							local pr;
							local cr;
							local ch;
							local c;
							local r;
							local sp;
							local to;
							local sd;
							local fp;
							while true do
								if (2 == FlatIdent_5062) then
									ch = LP.Backpack:FindFirstChild("Couch") or LP.Character:FindFirstChild("Couch");
									if ch then
										pcall(function()
											ch.Parent = LP.Character;
										end);
									end
									task.wait(0.3);
									FlatIdent_5062 = 3;
								end
								if (FlatIdent_5062 == 1) then
									task.wait(0.3);
									if pr then
										pcall(function()
											pr:InvokeServer("PickingTools", "Couch");
										end);
									end
									task.wait(0.5);
									FlatIdent_5062 = 2;
								end
								if (FlatIdent_5062 == 0) then
									pr = RS.RE and RS.RE:FindFirstChild("1Too1l");
									cr = RS.RE and RS.RE:FindFirstChild("1Clea1rTool1s");
									if cr then
										pcall(function()
											cr:FireServer("ClearAllTools");
										end);
									end
									FlatIdent_5062 = 1;
								end
								if (FlatIdent_5062 == 3) then
									pcall(function()
										VIM:SendKeyEvent(true, Enum.KeyCode.F, false, game);
									end);
									task.wait(0.5);
									c = LP.Character;
									FlatIdent_5062 = 4;
								end
								if (4 == FlatIdent_5062) then
									if not c then
										return;
									end
									r = c:FindFirstChild("HumanoidRootPart");
									if not r then
										return;
									end
									FlatIdent_5062 = 5;
								end
								if (6 == FlatIdent_5062) then
									fp = 0;
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
										if (tt and tt.Character) then
											local FlatIdent_66193 = 0;
											local tr;
											local th;
											while true do
												if (FlatIdent_66193 == 0) then
													tr = tt.Character:FindFirstChild("HumanoidRootPart");
													th = tt.Character:FindFirstChildOfClass("Humanoid");
													FlatIdent_66193 = 1;
												end
												if (1 == FlatIdent_66193) then
													if (tr and th) then
														local FlatIdent_1B878 = 0;
														local yo;
														while true do
															if (FlatIdent_1B878 == 1) then
																yo = (math.sin(to * 1.5) * 1.5) - 1.5;
																if not sd then
																	local FlatIdent_60A2E = 0;
																	while true do
																		if (FlatIdent_60A2E == 0) then
																			pcall(function()
																				cr2.CFrame = tr.CFrame * CFrame.new(math.cos(sp) * 2, yo, math.sin(sp) * 2) * CFrame.Angles(math.rad(to * 300), sp, 0);
																			end);
																			if th.Sit then
																				sd = true;
																				fp = 0;
																			end
																			break;
																		end
																	end
																else
																	local FlatIdent_4543F = 0;
																	while true do
																		if (FlatIdent_4543F == 0) then
																			if (fp == 0) then
																				local FlatIdent_29662 = 0;
																				while true do
																					if (FlatIdent_29662 == 0) then
																						pcall(function()
																							local ex = tr:FindFirstChild("KamuiFlingVel");
																							if ex then
																								ex:Destroy();
																							end
																							local bv = Instance.new("BodyVelocity");
																							bv.Name = "KamuiFlingVel";
																							bv.Velocity = Vector3.new(10000, 500000, 10000);
																							bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
																							bv.Parent = tr;
																						end);
																						fp = 1;
																						break;
																					end
																				end
																			end
																			pcall(function()
																				cr2.CFrame = tr.CFrame * CFrame.new(math.cos(sp) * 2, yo, math.sin(sp) * 2) * CFrame.Angles(math.rad(to * 300), sp, 0);
																			end);
																			break;
																		end
																	end
																end
																break;
															end
															if (0 == FlatIdent_1B878) then
																sp = sp + math.rad(180);
																to = to + 0.08;
																FlatIdent_1B878 = 1;
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
									break;
								end
								if (FlatIdent_5062 == 5) then
									sp = 0;
									to = 0;
									sd = false;
									FlatIdent_5062 = 6;
								end
							end
						end);
						break;
					end
					if (FlatIdent_9010 == 0) then
						if (sm ~= "nome") then
							return;
						end
						cfA = true;
						FlatIdent_9010 = 1;
					end
				end
			else
				local FlatIdent_3A655 = 0;
				local c;
				while true do
					if (FlatIdent_3A655 == 1) then
						c = LP.Character;
						if c then
							local r = c:FindFirstChild("HumanoidRootPart");
							if r then
								r.CFrame = CFrame.new(r.Position.X, 1500, r.Position.Z);
								task.spawn(function()
									local bv = Instance.new("BodyVelocity");
									bv.Velocity = Vector3.new(0, 300, 0);
									bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
									bv.Parent = r;
									task.wait(2);
									if (bv and bv.Parent) then
										bv:Destroy();
									end
								end);
								ok("Voce voou pro ceu!");
							end
						end
						FlatIdent_3A655 = 2;
					end
					if (FlatIdent_3A655 == 2) then
						task.wait(0.3);
						protS();
						FlatIdent_3A655 = 3;
					end
					if (FlatIdent_3A655 == 3) then
						cTl();
						break;
					end
					if (FlatIdent_3A655 == 0) then
						cfA = false;
						if cfT then
							local FlatIdent_4B897 = 0;
							while true do
								if (0 == FlatIdent_4B897) then
									pcall(function()
										task.cancel(cfT);
									end);
									cfT = nil;
									break;
								end
							end
						end
						FlatIdent_3A655 = 1;
					end
				end
			end
		end
	end});
	TT:AddToggle({Name=t.touch_ball,Default=false,Callback=function(v)
		local FlatIdent_8B6F5 = 0;
		while true do
			if (FlatIdent_8B6F5 == 0) then
				tfA = v;
				if v then
					task.spawn(function()
						local FlatIdent_5CD30 = 0;
						local B;
						local a;
						while true do
							if (1 == FlatIdent_5CD30) then
								if B:FindFirstChildOfClass("BodyVelocity") then
									B:FindFirstChildOfClass("BodyVelocity"):Destroy();
								end
								a = 0;
								FlatIdent_5CD30 = 2;
							end
							if (FlatIdent_5CD30 == 2) then
								tfC = R.Heartbeat:Connect(function()
									local FlatIdent_6354D = 0;
									local c;
									local tp;
									while true do
										if (FlatIdent_6354D == 1) then
											c = LP.Character;
											if (not c or not c:FindFirstChild("HumanoidRootPart")) then
												local FlatIdent_6D09C = 0;
												while true do
													if (FlatIdent_6D09C == 0) then
														tfA = false;
														if tfC then
															local FlatIdent_64F8C = 0;
															while true do
																if (0 == FlatIdent_64F8C) then
																	tfC:Disconnect();
																	tfC = nil;
																	break;
																end
															end
														end
														FlatIdent_6D09C = 1;
													end
													if (FlatIdent_6D09C == 1) then
														cTl();
														return;
													end
												end
											end
											FlatIdent_6354D = 2;
										end
										if (FlatIdent_6354D == 0) then
											if not tfA then
												return;
											end
											protS();
											FlatIdent_6354D = 1;
										end
										if (FlatIdent_6354D == 2) then
											tp = c:FindFirstChild("HumanoidRootPart");
											if (tp and B and B.Parent) then
												local FlatIdent_2E48C = 0;
												while true do
													if (FlatIdent_2E48C == 0) then
														a = a + math.rad(150);
														B.CFrame = tp.CFrame * CFrame.Angles(0, a, 0);
														break;
													end
												end
											end
											break;
										end
									end
								end);
								break;
							end
							if (0 == FlatIdent_5CD30) then
								B = gB();
								if not B then
									return;
								end
								FlatIdent_5CD30 = 1;
							end
						end
					end);
				else
					if tfC then
						tfC:Disconnect();
						tfC = nil;
					end
					protS();
					cTl();
				end
				break;
			end
		end
	end});
	local IT = W:MakeTab({t.item,"box"});
	IT:AddParagraph({t.item_paid,"Warden, Tear Gas, RPG"});
	local si = nil;
	IT:AddDropdown({Name=t.item,Options={"Warden","TearGasLauncher","RPG"},Default="",Callback=function(v)
		si = v;
	end});
	IT:AddButton({t.item_get,function()
		local FlatIdent_6FC5B = 0;
		local r;
		local args;
		while true do
			if (FlatIdent_6FC5B == 3) then
				ok("Got: " .. si);
				break;
			end
			if (FlatIdent_6FC5B == 1) then
				if not r then
					local FlatIdent_398FF = 0;
					while true do
						if (FlatIdent_398FF == 0) then
							er("Remote not found");
							return;
						end
					end
				end
				args = {};
				FlatIdent_6FC5B = 2;
			end
			if (FlatIdent_6FC5B == 0) then
				if (not si or (si == "")) then
					local FlatIdent_2BF13 = 0;
					while true do
						if (0 == FlatIdent_2BF13) then
							er(t.select_item);
							return;
						end
					end
				end
				r = RS.RE and RS.RE:FindFirstChild("1Playe1rTrigge1rEven1t");
				FlatIdent_6FC5B = 1;
			end
			if (FlatIdent_6FC5B == 2) then
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
				FlatIdent_6FC5B = 3;
			end
		end
	end});
	local AV = W:MakeTab({t.avatar,"user"});
	AV:AddParagraph({t.copy_avatar,"Apply + fallback"});
	aDD = AV:AddDropdown({Name=t.avatar_player,Options=gN(),Default="",Callback=function(v)
		if (v and (v ~= t.no_players) and (v ~= "")) then
			local FlatIdent_86FCC = 0;
			while true do
				if (FlatIdent_86FCC == 0) then
					_G.AvT = v;
					st = v;
					FlatIdent_86FCC = 1;
				end
				if (FlatIdent_86FCC == 1) then
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
		if (not tp or not tp.Character) then
			local FlatIdent_18172 = 0;
			while true do
				if (FlatIdent_18172 == 0) then
					er(t.not_found);
					return;
				end
			end
		end
		local th = tp.Character:FindFirstChildOfClass("Humanoid");
		if not th then
			er("No Humanoid");
			return;
		end
		local mh = LP.Character and LP.Character:FindFirstChildOfClass("Humanoid");
		if not mh then
			local FlatIdent_132C0 = 0;
			while true do
				if (0 == FlatIdent_132C0) then
					er("No your Humanoid");
					return;
				end
			end
		end
		local okD, d = pcall(function()
			return th:GetAppliedDescription();
		end);
		if (not okD or not d) then
			local FlatIdent_40BF6 = 0;
			local ok2;
			local d2;
			while true do
				if (FlatIdent_40BF6 == 0) then
					ok2, d2 = pcall(function()
						return P:GetHumanoidDescriptionFromUserId(tp.UserId);
					end);
					if (not ok2 or not d2) then
						local FlatIdent_B716 = 0;
						while true do
							if (FlatIdent_B716 == 0) then
								er("Failed desc");
								return;
							end
						end
					end
					FlatIdent_40BF6 = 1;
				end
				if (FlatIdent_40BF6 == 1) then
					d = d2;
					break;
				end
			end
		end
		local ap = false;
		pcall(function()
			local FlatIdent_3A079 = 0;
			while true do
				if (FlatIdent_3A079 == 0) then
					mh:ApplyDescription(d);
					ap = true;
					break;
				end
			end
		end);
		if not ap then
			local wr = RS:FindFirstChild("Remotes") and RS.Remotes:FindFirstChild("Wear");
			if wr then
				local ids = {};
				for _, sl in ipairs({d.HatAccessory,d.HairAccessory,d.FaceAccessory,d.NeckAccessory,d.ShouldersAccessory,d.FrontAccessory,d.BackAccessory,d.WaistAccessory,d.GraphicTShirt,d.Shirt,d.Pants,d.TShirt}) do
					if (sl and (sl ~= "")) then
						for id in string.gmatch(tostring(sl), "%d+") do
							table.insert(ids, tonumber(id));
						end
					end
				end
				for _, id in ipairs(ids) do
					if (id and (id > 0)) then
						local FlatIdent_8E526 = 0;
						while true do
							if (FlatIdent_8E526 == 0) then
								pcall(function()
									wr:InvokeServer(id);
								end);
								task.wait(0.05);
								break;
							end
						end
					end
				end
			end
			pcall(function()
				mh.BodyType = th.BodyType;
			end);
			pcall(function()
				mh.HeadScale = th.HeadScale;
			end);
			pcall(function()
				mh.BodyDepthScale = th.BodyDepthScale;
			end);
			pcall(function()
				mh.BodyWidthScale = th.BodyWidthScale;
			end);
			pcall(function()
				mh.BodyHeightScale = th.BodyHeightScale;
			end);
		end
		ok("Avatar copied from " .. tn);
	end});
	local MT2 = W:MakeTab({t.music,"music"});
	local mI = nil;
	local mIO = MT2:AddTextBox({Name=t.music_id,PlaceholderText="1976786299",Callback=function(v)
		mI = v;
	end});
	MT2:AddButton({t.music_play,function()
		local FlatIdent_82627 = 0;
		local raw;
		local cl;
		local r;
		while true do
			if (FlatIdent_82627 == 0) then
				raw = readTB(mIO) or mI;
				if (not raw or (raw == "")) then
					local FlatIdent_66362 = 0;
					while true do
						if (FlatIdent_66362 == 0) then
							er("Type ID");
							return;
						end
					end
				end
				FlatIdent_82627 = 1;
			end
			if (FlatIdent_82627 == 2) then
				r = RS.RE and RS.RE:FindFirstChild("1Musi1c");
				if r then
					local FlatIdent_413A0 = 0;
					while true do
						if (FlatIdent_413A0 == 0) then
							pcall(function()
								r:FireServer("Play", cl);
							end);
							ok("Playing: " .. cl);
							break;
						end
					end
				else
					er("Remote not found");
				end
				break;
			end
			if (FlatIdent_82627 == 1) then
				cl = nId(raw);
				if not cl then
					local FlatIdent_373F8 = 0;
					while true do
						if (FlatIdent_373F8 == 0) then
							er("Invalid ID");
							return;
						end
					end
				end
				FlatIdent_82627 = 2;
			end
		end
	end});
	MT2:AddSection({t.music_saved});
	local mDD2 = nil;
	local function rfm()
		local FlatIdent_30046 = 0;
		local k;
		while true do
			if (FlatIdent_30046 == 0) then
				k = {};
				for kk in pairs(SM) do
					table.insert(k, kk);
				end
				FlatIdent_30046 = 1;
			end
			if (FlatIdent_30046 == 1) then
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
			local FlatIdent_3CB5D = 0;
			local r;
			while true do
				if (0 == FlatIdent_3CB5D) then
					r = RS.RE and RS.RE:FindFirstChild("1Musi1c");
					if r then
						pcall(function()
							r:FireServer("Play", SM[v]);
						end);
						ok("Playing: " .. v);
					end
					break;
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
		local FlatIdent_87A87 = 0;
		local n;
		local id;
		local cl;
		while true do
			if (FlatIdent_87A87 == 3) then
				SM[n] = cl;
				saveM();
				FlatIdent_87A87 = 4;
			end
			if (FlatIdent_87A87 == 2) then
				cl = nId(id);
				if not cl then
					local FlatIdent_1B30C = 0;
					while true do
						if (FlatIdent_1B30C == 0) then
							er("Invalid ID");
							return;
						end
					end
				end
				FlatIdent_87A87 = 3;
			end
			if (FlatIdent_87A87 == 0) then
				n = readTB(mNO) or mN;
				id = readTB(mIO) or mI;
				FlatIdent_87A87 = 1;
			end
			if (FlatIdent_87A87 == 1) then
				if (not n or (n == "")) then
					local FlatIdent_1A0B9 = 0;
					while true do
						if (FlatIdent_1A0B9 == 0) then
							er("Type name");
							return;
						end
					end
				end
				if (not id or (id == "")) then
					local FlatIdent_1C823 = 0;
					while true do
						if (FlatIdent_1C823 == 0) then
							er("Type ID");
							return;
						end
					end
				end
				FlatIdent_87A87 = 2;
			end
			if (4 == FlatIdent_87A87) then
				rfm();
				ok("Saved: " .. n);
				break;
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
			local FlatIdent_739F3 = 0;
			while true do
				if (FlatIdent_739F3 == 0) then
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
	local PT = W:MakeTab({t.prot,"shield"});
	PT:AddToggle({Name=t.anti_sit,Default=false,Callback=function(v)
		local FlatIdent_733BE = 0;
		while true do
			if (FlatIdent_733BE == 0) then
				if getgenv().aSC then
					getgenv().aSC:Disconnect();
				end
				if v then
					getgenv().aSC = R.Heartbeat:Connect(function()
						local FlatIdent_65844 = 0;
						local c;
						local h;
						while true do
							if (FlatIdent_65844 == 1) then
								h = c:FindFirstChildOfClass("Humanoid");
								if h then
									h:SetStateEnabled(Enum.HumanoidStateType.Seated, false);
								end
								break;
							end
							if (FlatIdent_65844 == 0) then
								c = LP.Character;
								if not c then
									return;
								end
								FlatIdent_65844 = 1;
							end
						end
					end);
				end
				break;
			end
		end
	end});
	PT:AddToggle({Name=t.noclip,Default=false,Callback=function(v)
		local FlatIdent_94DD1 = 0;
		while true do
			if (FlatIdent_94DD1 == 0) then
				if getgenv().nC then
					getgenv().nC:Disconnect();
				end
				if v then
					getgenv().nC = R.Stepped:Connect(function()
						local FlatIdent_35814 = 0;
						local c;
						while true do
							if (FlatIdent_35814 == 1) then
								for _, p in ipairs(c:GetDescendants()) do
									if p:IsA("BasePart") then
										p.CanCollide = false;
									end
								end
								break;
							end
							if (FlatIdent_35814 == 0) then
								c = LP.Character;
								if not c then
									return;
								end
								FlatIdent_35814 = 1;
							end
						end
					end);
				end
				break;
			end
		end
	end});
	PT:AddToggle({Name=t.anti_void,Default=false,Callback=function(v)
		local FlatIdent_4965B = 0;
		while true do
			if (0 == FlatIdent_4965B) then
				if getgenv().aVC then
					getgenv().aVC:Disconnect();
				end
				if v then
					getgenv().aVC = R.Heartbeat:Connect(function()
						local FlatIdent_7FA07 = 0;
						local c;
						local r;
						while true do
							if (FlatIdent_7FA07 == 1) then
								r = c:FindFirstChild("HumanoidRootPart");
								if (r and (r.Position.Y < -50)) then
									r.CFrame = CFrame.new(r.Position.X, 50, r.Position.Z);
								end
								break;
							end
							if (FlatIdent_7FA07 == 0) then
								c = LP.Character;
								if not c then
									return;
								end
								FlatIdent_7FA07 = 1;
							end
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
	local ET = W:MakeTab({t.extras,"cog"});
	ET:AddToggle({Name=t.auto_rejoin,Default=false,Callback=function(v)
		if v then
			setupAutoRejoin();
		end
	end});
	local CTab = W:MakeTab({t.cars,"car"});
	CTab:AddParagraph({t.cars,t.coming_soon});
	do
		local FlatIdent_B6A2 = 0;
		local AT;
		while true do
			if (FlatIdent_B6A2 == 1) then
				AT:AddButton({t.admin_open,function()
					buildAdmin();
				end});
				break;
			end
			if (FlatIdent_B6A2 == 0) then
				AT = W:MakeTab({t.admin,"star"});
				AT:AddParagraph({t.admin_panel,"Hub"});
				FlatIdent_B6A2 = 1;
			end
		end
	end
	local CH = W:MakeTab({t.changelog,"list"});
	CH:AddSection({"v1.9.3 - Halloween"});
	CH:AddParagraph({"+ Map list fixed","Backrooms + Cafe in Admin Maps"});
	CH:AddParagraph({"+ EN translation","full English language"});
	CH:AddParagraph({"+ Discord","discord.gg/rxkz8a3ytV"});
	CH:AddParagraph({"+ Syntax fixed","lang button working"});
	W:SelectTab(PT2);
	ok(t.hub_loaded);
end
local CHAT_ATTR_SERVER = "KamuiChatS";
local CHAT_ATTR_GLOBAL = "KamuiChatG";
local chatSeen = {};
local chatMessages = {server={},global={}};
local chatRefs = nil;
local function sendChat(channel, msg)
	local FlatIdent_190B6 = 0;
	local attr;
	local payload;
	while true do
		if (FlatIdent_190B6 == 1) then
			payload = LP.Name .. "||" .. msg .. "||" .. tostring(tick());
			pcall(function()
				LP:SetAttribute(attr, payload);
			end);
			break;
		end
		if (0 == FlatIdent_190B6) then
			if (not msg or (msg == "")) then
				return;
			end
			attr = ((channel == "server") and CHAT_ATTR_SERVER) or CHAT_ATTR_GLOBAL;
			FlatIdent_190B6 = 1;
		end
	end
end
local function parseMsg(payload)
	local FlatIdent_7B4B6 = 0;
	local name;
	local msg;
	while true do
		if (FlatIdent_7B4B6 == 1) then
			if (not name or not msg) then
				local FlatIdent_4D046 = 0;
				while true do
					if (FlatIdent_4D046 == 0) then
						name = payload:match("^([^|]+)");
						msg = payload:match("||([^|]+)||");
						break;
					end
				end
			end
			return name, msg;
		end
		if (FlatIdent_7B4B6 == 0) then
			if not payload then
				return nil;
			end
			name, msg = payload:match("([^|]+)||([^|]+)||");
			FlatIdent_7B4B6 = 1;
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
	local layout = Instance.new("UIListLayout");
	layout.SortOrder = Enum.SortOrder.LayoutOrder;
	layout.Padding = UDim.new(0, 3);
	layout.Parent = list;
	for _, m in ipairs(chatMessages[ch]) do
		local FlatIdent_67611 = 0;
		local row;
		while true do
			if (FlatIdent_67611 == 0) then
				row = Instance.new("TextLabel");
				row.Size = UDim2.new(1, -8, 0, 22);
				FlatIdent_67611 = 1;
			end
			if (FlatIdent_67611 == 2) then
				row.TextColor3 = Color3.fromRGB(240, 240, 240);
				row.TextScaled = true;
				FlatIdent_67611 = 3;
			end
			if (FlatIdent_67611 == 1) then
				row.BackgroundTransparency = 1;
				row.Text = "[" .. m.name .. "] " .. m.msg;
				FlatIdent_67611 = 2;
			end
			if (FlatIdent_67611 == 4) then
				row.Parent = list;
				break;
			end
			if (FlatIdent_67611 == 3) then
				row.Font = Enum.Font.Gotham;
				row.TextXAlignment = Enum.TextXAlignment.Left;
				FlatIdent_67611 = 4;
			end
		end
	end
	list.CanvasSize = UDim2.new(0, 0, 0, layout.AbsoluteContentSize.Y + 8);
end
local function pollChatAll()
	local FlatIdent_9072E = 0;
	while true do
		if (FlatIdent_9072E == 0) then
			for _, p in ipairs(P:GetPlayers()) do
				for _, ch in ipairs({"server","global"}) do
					local FlatIdent_2D245 = 0;
					local attr;
					local val;
					while true do
						if (FlatIdent_2D245 == 1) then
							if (val and not chatSeen[val]) then
								local FlatIdent_1DC1B = 0;
								local n;
								local m;
								while true do
									if (FlatIdent_1DC1B == 0) then
										chatSeen[val] = true;
										n, m = parseMsg(val);
										FlatIdent_1DC1B = 1;
									end
									if (FlatIdent_1DC1B == 1) then
										if (n and m) then
											table.insert(chatMessages[ch], {name=n,msg=m});
										end
										break;
									end
								end
							end
							break;
						end
						if (0 == FlatIdent_2D245) then
							attr = ((ch == "server") and CHAT_ATTR_SERVER) or CHAT_ATTR_GLOBAL;
							val = p:GetAttribute(attr);
							FlatIdent_2D245 = 1;
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
		local FlatIdent_3174 = 0;
		while true do
			if (FlatIdent_3174 == 0) then
				task.wait(0.6);
				pcall(pollChatAll);
				break;
			end
		end
	end
end);
local function openChatGUI(onClose)
	local pg = LP:WaitForChild("PlayerGui");
	local old = pg:FindFirstChild("KamuiChatUI");
	if old then
		old:Destroy();
	end
	local gui = Instance.new("ScreenGui");
	gui.Name = "KamuiChatUI";
	gui.Parent = pg;
	gui.ResetOnSpawn = false;
	gui.IgnoreGuiInset = true;
	gui.DisplayOrder = 1050;
	local frame = Instance.new("Frame");
	frame.AnchorPoint = Vector2.new(0.5, 0.5);
	frame.Position = UDim2.new(0.5, 0, 0.5, 0);
	frame.Size = UDim2.new(0.75, 0, 0.68, 0);
	frame.BackgroundColor3 = Color3.fromRGB(20, 8, 30);
	frame.BorderSizePixel = 0;
	frame.Parent = gui;
	local fc = Instance.new("UICorner");
	fc.CornerRadius = UDim.new(0, 14);
	fc.Parent = frame;
	local fs = Instance.new("UIStroke");
	fs.Color = Color3.fromRGB(255, 100, 0);
	fs.Thickness = 2.5;
	fs.Parent = frame;
	local title = Instance.new("TextLabel");
	title.Size = UDim2.new(1, 0, 0.1, 0);
	title.BackgroundTransparency = 1;
	title.Text = "🎃 Kamui Chat 🕸️";
	title.TextColor3 = Color3.fromRGB(255, 100, 0);
	title.TextScaled = true;
	title.Font = Enum.Font.GothamBold;
	title.Parent = frame;
	local tabS = Instance.new("TextButton");
	tabS.Position = UDim2.new(0.02, 0, 0.12, 0);
	tabS.Size = UDim2.new(0.47, 0, 0.08, 0);
	tabS.BackgroundColor3 = Color3.fromRGB(255, 100, 0);
	tabS.Text = "Chat (servidor)";
	tabS.TextColor3 = Color3.new(1, 1, 1);
	tabS.TextScaled = true;
	tabS.Font = Enum.Font.GothamBold;
	tabS.BorderSizePixel = 0;
	tabS.Parent = frame;
	local tsc = Instance.new("UICorner");
	tsc.CornerRadius = UDim.new(0, 8);
	tsc.Parent = tabS;
	local tabG = Instance.new("TextButton");
	tabG.Position = UDim2.new(0.51, 0, 0.12, 0);
	tabG.Size = UDim2.new(0.47, 0, 0.08, 0);
	tabG.BackgroundColor3 = Color3.fromRGB(60, 25, 90);
	tabG.Text = "Global (todos servidor)";
	tabG.TextColor3 = Color3.fromRGB(220, 200, 255);
	tabG.TextScaled = true;
	tabG.Font = Enum.Font.GothamBold;
	tabG.BorderSizePixel = 0;
	tabG.Parent = frame;
	local tgc = Instance.new("UICorner");
	tgc.CornerRadius = UDim.new(0, 8);
	tgc.Parent = tabG;
	local scroll = Instance.new("ScrollingFrame");
	scroll.Position = UDim2.new(0.02, 0, 0.21, 0);
	scroll.Size = UDim2.new(0.96, 0, 0.55, 0);
	scroll.BackgroundColor3 = Color3.fromRGB(10, 4, 16);
	scroll.BorderSizePixel = 0;
	scroll.ScrollBarThickness = 5;
	scroll.CanvasSize = UDim2.new(0, 0, 0, 0);
	scroll.Parent = frame;
	local sc = Instance.new("UICorner");
	sc.CornerRadius = UDim.new(0, 8);
	sc.Parent = scroll;
	local sl = Instance.new("UIListLayout");
	sl.SortOrder = Enum.SortOrder.LayoutOrder;
	sl.Padding = UDim.new(0, 3);
	sl.Parent = scroll;
	local input = Instance.new("TextBox");
	input.Position = UDim2.new(0.02, 0, 0.83, 0);
	input.Size = UDim2.new(0.72, 0, 0.09, 0);
	input.BackgroundColor3 = Color3.fromRGB(30, 12, 45);
	input.BorderSizePixel = 0;
	input.PlaceholderText = "Digite uma mensagem...";
	input.Text = "";
	input.TextColor3 = Color3.fromRGB(255, 255, 255);
	input.TextScaled = true;
	input.Font = Enum.Font.Gotham;
	input.Parent = frame;
	local ic = Instance.new("UICorner");
	ic.CornerRadius = UDim.new(0, 8);
	ic.Parent = input;
	local send = Instance.new("TextButton");
	send.Position = UDim2.new(0.76, 0, 0.83, 0);
	send.Size = UDim2.new(0.22, 0, 0.09, 0);
	send.BackgroundColor3 = Color3.fromRGB(255, 100, 0);
	send.Text = "Enviar";
	send.TextColor3 = Color3.new(1, 1, 1);
	send.TextScaled = true;
	send.Font = Enum.Font.GothamBold;
	send.BorderSizePixel = 0;
	send.Parent = frame;
	local sc2 = Instance.new("UICorner");
	sc2.CornerRadius = UDim.new(0, 8);
	sc2.Parent = send;
	local close = Instance.new("TextButton");
	close.AnchorPoint = Vector2.new(1, 0);
	close.Position = UDim2.new(1, -6, 0, 6);
	close.Size = UDim2.new(0, 28, 0, 28);
	close.BackgroundColor3 = Color3.fromRGB(200, 50, 50);
	close.Text = "X";
	close.TextColor3 = Color3.new(1, 1, 1);
	close.TextScaled = true;
	close.Font = Enum.Font.GothamBold;
	close.BorderSizePixel = 0;
	close.Parent = frame;
	local cc = Instance.new("UICorner");
	cc.CornerRadius = UDim.new(0, 6);
	cc.Parent = close;
	local cont = Instance.new("TextButton");
	cont.AnchorPoint = Vector2.new(0.5, 0.5);
	cont.Position = UDim2.new(0.5, 0, 0.96, 0);
	cont.Size = UDim2.new(0.5, 0, 0.05, 0);
	cont.BackgroundColor3 = Color3.fromRGB(0, 180, 90);
	cont.BorderSizePixel = 0;
	cont.Text = "▶ Continuar";
	cont.TextColor3 = Color3.new(1, 1, 1);
	cont.TextScaled = true;
	cont.Font = Enum.Font.GothamBold;
	cont.Parent = frame;
	local contc = Instance.new("UICorner");
	contc.CornerRadius = UDim.new(0, 8);
	contc.Parent = cont;
	chatRefs = {current="server",lists={server=scroll,global=scroll},gui=gui};
	local function selectTab(ch)
		chatRefs.current = ch;
		if (ch == "server") then
			local FlatIdent_2F289 = 0;
			while true do
				if (FlatIdent_2F289 == 1) then
					tabS.TextColor3 = Color3.new(1, 1, 1);
					tabG.TextColor3 = Color3.fromRGB(220, 200, 255);
					break;
				end
				if (0 == FlatIdent_2F289) then
					tabS.BackgroundColor3 = Color3.fromRGB(255, 100, 0);
					tabG.BackgroundColor3 = Color3.fromRGB(60, 25, 90);
					FlatIdent_2F289 = 1;
				end
			end
		else
			local FlatIdent_91AE4 = 0;
			while true do
				if (FlatIdent_91AE4 == 0) then
					tabS.BackgroundColor3 = Color3.fromRGB(60, 25, 90);
					tabG.BackgroundColor3 = Color3.fromRGB(255, 100, 0);
					FlatIdent_91AE4 = 1;
				end
				if (FlatIdent_91AE4 == 1) then
					tabS.TextColor3 = Color3.fromRGB(220, 200, 255);
					tabG.TextColor3 = Color3.new(1, 1, 1);
					break;
				end
			end
		end
		refreshChatUI();
	end
	tabS.MouseButton1Click:Connect(function()
		selectTab("server");
	end);
	tabG.MouseButton1Click:Connect(function()
		selectTab("global");
	end);
	send.MouseButton1Click:Connect(function()
		local FlatIdent_4FB53 = 0;
		local msg;
		while true do
			if (FlatIdent_4FB53 == 0) then
				msg = input.Text;
				if (msg and (msg ~= "")) then
					local FlatIdent_91CC3 = 0;
					while true do
						if (FlatIdent_91CC3 == 0) then
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
		local FlatIdent_8585F = 0;
		while true do
			if (FlatIdent_8585F == 1) then
				if onClose then
					onClose();
				end
				break;
			end
			if (0 == FlatIdent_8585F) then
				gui:Destroy();
				chatRefs = nil;
				FlatIdent_8585F = 1;
			end
		end
	end);
	cont.MouseButton1Click:Connect(function()
		local FlatIdent_928A1 = 0;
		while true do
			if (FlatIdent_928A1 == 0) then
				gui:Destroy();
				chatRefs = nil;
				FlatIdent_928A1 = 1;
			end
			if (FlatIdent_928A1 == 1) then
				if onClose then
					onClose();
				end
				break;
			end
		end
	end);
	refreshChatUI();
	return gui;
end
local pg = LP:WaitForChild("PlayerGui");
local s = Instance.new("ScreenGui");
s.Name = "KamuiLang";
s.Parent = pg;
s.ResetOnSpawn = false;
s.IgnoreGuiInset = true;
s.DisplayOrder = 1100;
local bg = Instance.new("Frame");
bg.Size = UDim2.new(1, 0, 1, 0);
bg.BackgroundColor3 = Color3.fromRGB(8, 3, 12);
bg.BorderSizePixel = 0;
bg.Parent = s;
local box = Instance.new("Frame");
box.AnchorPoint = Vector2.new(0.5, 0.5);
box.Position = UDim2.new(0.5, 0, 0.5, 0);
box.Size = UDim2.new(0.78, 0, 0.35, 0);
box.BackgroundColor3 = Color3.fromRGB(20, 8, 30);
box.BorderSizePixel = 0;
box.Parent = bg;
local bc = Instance.new("UICorner");
bc.CornerRadius = UDim.new(0, 14);
bc.Parent = box;
local bs = Instance.new("UIStroke");
bs.Color = Color3.fromRGB(255, 100, 0);
bs.Thickness = 2.5;
bs.Parent = box;
local tl = Instance.new("TextLabel");
tl.Position = UDim2.new(0, 0, 0.08, 0);
tl.Size = UDim2.new(1, 0, 0.25, 0);
tl.BackgroundTransparency = 1;
tl.Text = "🎃 Kamui Hub 🕸️";
tl.TextColor3 = Color3.fromRGB(255, 100, 0);
tl.TextScaled = true;
tl.Font = Enum.Font.GothamBold;
tl.Parent = box;
local sl = Instance.new("TextLabel");
sl.Position = UDim2.new(0, 0, 0.35, 0);
sl.Size = UDim2.new(1, 0, 0.12, 0);
sl.BackgroundTransparency = 1;
sl.Text = "Selecione o idioma / Select language";
sl.TextColor3 = Color3.fromRGB(180, 180, 180);
sl.TextScaled = true;
sl.Font = Enum.Font.Gotham;
sl.Parent = box;
local pb = Instance.new("TextButton");
pb.AnchorPoint = Vector2.new(0.5, 0.5);
pb.Position = UDim2.new(0.5, 0, 0.58, 0);
pb.Size = UDim2.new(0.7, 0, 0.13, 0);
pb.BackgroundColor3 = Color3.fromRGB(200, 60, 0);
pb.BorderSizePixel = 0;
pb.Text = "🎃 Portugues";
pb.TextColor3 = Color3.new(1, 1, 1);
pb.TextScaled = true;
pb.Font = Enum.Font.GothamBold;
pb.Parent = box;
local pc = Instance.new("UICorner");
pc.CornerRadius = UDim.new(0, 10);
pc.Parent = pb;
local eb = Instance.new("TextButton");
eb.AnchorPoint = Vector2.new(0.5, 0.5);
eb.Position = UDim2.new(0.5, 0, 0.78, 0);
eb.Size = UDim2.new(0.7, 0, 0.13, 0);
eb.BackgroundColor3 = Color3.fromRGB(80, 20, 120);
eb.BorderSizePixel = 0;
eb.Text = "🕸️ English";
eb.TextColor3 = Color3.new(1, 1, 1);
eb.TextScaled = true;
eb.Font = Enum.Font.GothamBold;
eb.Parent = box;
local ec = Instance.new("UICorner");
ec.CornerRadius = UDim.new(0, 10);
ec.Parent = eb;
local function spiderAnimation(parent, onDone)
	local FlatIdent_45FBD = 0;
	local animFrame;
	local nameLabel;
	local webLine;
	local spider;
	while true do
		if (FlatIdent_45FBD == 8) then
			spider.TextColor3 = Color3.new(1, 1, 1);
			spider.Parent = animFrame;
			task.spawn(function()
				for i = 0, 70, 2 do
					local FlatIdent_807DC = 0;
					local p;
					while true do
						if (1 == FlatIdent_807DC) then
							webLine.Size = UDim2.new(0, 2, 0, animFrame.AbsoluteSize.Y * p, 0);
							task.wait(0.025);
							break;
						end
						if (FlatIdent_807DC == 0) then
							p = i / 100;
							spider.Position = UDim2.new(0.5, 0, p, 0);
							FlatIdent_807DC = 1;
						end
					end
				end
				task.wait(0.3);
				local webEmoji = Instance.new("TextLabel");
				webEmoji.AnchorPoint = Vector2.new(0.5, 0.5);
				webEmoji.Position = UDim2.new(0.5, 0, 0.72, 0);
				webEmoji.Size = UDim2.new(0.5, 0, 0.22, 0);
				webEmoji.BackgroundTransparency = 1;
				webEmoji.Text = "🕸️";
				webEmoji.TextScaled = true;
				webEmoji.Parent = animFrame;
				task.wait(1);
				if onDone then
					onDone();
				end
			end);
			break;
		end
		if (5 == FlatIdent_45FBD) then
			webLine.Position = UDim2.new(0.5, 0, 0, 0);
			webLine.Size = UDim2.new(0, 2, 0, 0);
			webLine.BackgroundColor3 = Color3.fromRGB(200, 200, 200);
			webLine.BorderSizePixel = 0;
			FlatIdent_45FBD = 6;
		end
		if (FlatIdent_45FBD == 7) then
			spider.Size = UDim2.new(0, 40, 0, 40);
			spider.BackgroundTransparency = 1;
			spider.Text = "🕷️";
			spider.TextScaled = true;
			FlatIdent_45FBD = 8;
		end
		if (6 == FlatIdent_45FBD) then
			webLine.Parent = animFrame;
			spider = Instance.new("TextLabel");
			spider.AnchorPoint = Vector2.new(0.5, 0.5);
			spider.Position = UDim2.new(0.5, 0, 0, 0);
			FlatIdent_45FBD = 7;
		end
		if (FlatIdent_45FBD == 3) then
			nameLabel.TextColor3 = Color3.fromRGB(255, 100, 0);
			nameLabel.TextScaled = true;
			nameLabel.Font = Enum.Font.GothamBold;
			nameLabel.TextStrokeTransparency = 0.4;
			FlatIdent_45FBD = 4;
		end
		if (FlatIdent_45FBD == 0) then
			animFrame = Instance.new("Frame");
			animFrame.AnchorPoint = Vector2.new(0.5, 0.5);
			animFrame.Position = UDim2.new(0.5, 0, 0.5, 0);
			animFrame.Size = UDim2.new(0.85, 0, 0.6, 0);
			FlatIdent_45FBD = 1;
		end
		if (FlatIdent_45FBD == 4) then
			nameLabel.TextStrokeColor3 = Color3.fromRGB(80, 0, 120);
			nameLabel.Parent = animFrame;
			webLine = Instance.new("Frame");
			webLine.AnchorPoint = Vector2.new(0.5, 0);
			FlatIdent_45FBD = 5;
		end
		if (FlatIdent_45FBD == 2) then
			nameLabel.Position = UDim2.new(0.5, 0, 0.72, 0);
			nameLabel.Size = UDim2.new(0.9, 0, 0.28, 0);
			nameLabel.BackgroundTransparency = 1;
			nameLabel.Text = "kamui x hub";
			FlatIdent_45FBD = 3;
		end
		if (FlatIdent_45FBD == 1) then
			animFrame.BackgroundTransparency = 1;
			animFrame.Parent = parent;
			nameLabel = Instance.new("TextLabel");
			nameLabel.AnchorPoint = Vector2.new(0.5, 0.5);
			FlatIdent_45FBD = 2;
		end
	end
end
local function showLoader(cb)
	s:Destroy();
	local pg2 = LP:WaitForChild("PlayerGui");
	local old = pg2:FindFirstChild("KamuiLoader");
	if old then
		old:Destroy();
	end
	local s2 = Instance.new("ScreenGui");
	s2.Name = "KamuiLoader";
	s2.Parent = pg2;
	s2.ResetOnSpawn = false;
	s2.IgnoreGuiInset = true;
	s2.DisplayOrder = 1000;
	local bg = Instance.new("Frame");
	bg.Size = UDim2.new(1, 0, 1, 0);
	bg.BackgroundColor3 = Color3.fromRGB(8, 3, 12);
	bg.BorderSizePixel = 0;
	bg.Parent = s2;
	local box = Instance.new("Frame");
	box.AnchorPoint = Vector2.new(0.5, 0.5);
	box.Position = UDim2.new(0.5, 0, 0.5, 0);
	box.Size = UDim2.new(0.78, 0, 0.42, 0);
	box.BackgroundColor3 = Color3.fromRGB(20, 8, 30);
	box.BorderSizePixel = 0;
	box.Parent = bg;
	local bc = Instance.new("UICorner");
	bc.CornerRadius = UDim.new(0, 14);
	bc.Parent = box;
	local bs = Instance.new("UIStroke");
	bs.Color = Color3.fromRGB(255, 100, 0);
	bs.Thickness = 2.5;
	bs.Parent = box;
	local tl = Instance.new("TextLabel");
	tl.Position = UDim2.new(0, 0, 0.05, 0);
	tl.Size = UDim2.new(1, 0, 0.2, 0);
	tl.BackgroundTransparency = 1;
	tl.Text = "🎃 Kamui Hub 🕸️";
	tl.TextColor3 = Color3.fromRGB(255, 100, 0);
	tl.TextScaled = true;
	tl.Font = Enum.Font.GothamBold;
	tl.Parent = box;
	local sl = Instance.new("TextLabel");
	sl.Position = UDim2.new(0, 0, 0.27, 0);
	sl.Size = UDim2.new(1, 0, 0.12, 0);
	sl.BackgroundTransparency = 1;
	sl.Text = "Halloween Edition " .. V;
	sl.TextColor3 = Color3.fromRGB(150, 50, 200);
	sl.TextScaled = true;
	sl.Font = Enum.Font.GothamSemibold;
	sl.Parent = box;
	local bar = Instance.new("Frame");
	bar.AnchorPoint = Vector2.new(0.5, 1);
	bar.Position = UDim2.new(0.5, 0, 0.95, 0);
	bar.Size = UDim2.new(0.8, 0, 0.035, 0);
	bar.BackgroundColor3 = Color3.fromRGB(40, 20, 50);
	bar.BorderSizePixel = 0;
	bar.Parent = box;
	local bc2 = Instance.new("UICorner");
	bc2.CornerRadius = UDim.new(1, 0);
	bc2.Parent = bar;
	local fl = Instance.new("Frame");
	fl.Size = UDim2.new(0, 0, 1, 0);
	fl.BackgroundColor3 = Color3.fromRGB(255, 100, 0);
	fl.BorderSizePixel = 0;
	fl.Parent = bar;
	local fc = Instance.new("UICorner");
	fc.CornerRadius = UDim.new(1, 0);
	fc.Parent = fl;
	task.spawn(function()
		local FlatIdent_8A0A6 = 0;
		local optTitle;
		local btn1;
		local b1c;
		local btn2;
		local b2c;
		local runFinal;
		while true do
			if (FlatIdent_8A0A6 == 3) then
				btn1.Size = UDim2.new(0.82, 0, 0.15, 0);
				btn1.BackgroundColor3 = Color3.fromRGB(60, 25, 90);
				btn1.BorderSizePixel = 0;
				btn1.Text = "Executar Kamui x Hub sem chat";
				btn1.TextColor3 = Color3.fromRGB(220, 200, 255);
				btn1.TextScaled = true;
				FlatIdent_8A0A6 = 4;
			end
			if (FlatIdent_8A0A6 == 4) then
				btn1.Font = Enum.Font.GothamBold;
				btn1.Parent = box;
				b1c = Instance.new("UICorner");
				b1c.CornerRadius = UDim.new(0, 10);
				b1c.Parent = btn1;
				btn2 = Instance.new("TextButton");
				FlatIdent_8A0A6 = 5;
			end
			if (FlatIdent_8A0A6 == 1) then
				optTitle.AnchorPoint = Vector2.new(0.5, 0);
				optTitle.Position = UDim2.new(0.5, 0, 0.1, 0);
				optTitle.Size = UDim2.new(0.9, 0, 0.15, 0);
				optTitle.BackgroundTransparency = 1;
				optTitle.Text = "🎃 Como deseja iniciar? 🕸️";
				optTitle.TextColor3 = Color3.fromRGB(255, 100, 0);
				FlatIdent_8A0A6 = 2;
			end
			if (FlatIdent_8A0A6 == 6) then
				btn2.TextColor3 = Color3.new(1, 1, 1);
				btn2.TextScaled = true;
				btn2.Font = Enum.Font.GothamBold;
				btn2.Parent = box;
				b2c = Instance.new("UICorner");
				b2c.CornerRadius = UDim.new(0, 10);
				FlatIdent_8A0A6 = 7;
			end
			if (FlatIdent_8A0A6 == 0) then
				for i = 0, 100, 4 do
					fl.Size = UDim2.new(i / 100, 0, 1, 0);
					task.wait(0.02);
				end
				task.wait(0.3);
				tl.Visible = false;
				sl.Visible = false;
				bar.Visible = false;
				optTitle = Instance.new("TextLabel");
				FlatIdent_8A0A6 = 1;
			end
			if (5 == FlatIdent_8A0A6) then
				btn2.AnchorPoint = Vector2.new(0.5, 0.5);
				btn2.Position = UDim2.new(0.5, 0, 0.68, 0);
				btn2.Size = UDim2.new(0.82, 0, 0.15, 0);
				btn2.BackgroundColor3 = Color3.fromRGB(255, 100, 0);
				btn2.BorderSizePixel = 0;
				btn2.Text = "Executar Kamui x Hub com chat";
				FlatIdent_8A0A6 = 6;
			end
			if (FlatIdent_8A0A6 == 2) then
				optTitle.TextScaled = true;
				optTitle.Font = Enum.Font.GothamBold;
				optTitle.Parent = box;
				btn1 = Instance.new("TextButton");
				btn1.AnchorPoint = Vector2.new(0.5, 0.5);
				btn1.Position = UDim2.new(0.5, 0, 0.42, 0);
				FlatIdent_8A0A6 = 3;
			end
			if (FlatIdent_8A0A6 == 7) then
				b2c.Parent = btn2;
				runFinal = nil;
				function runFinal()
					local FlatIdent_55E6D = 0;
					while true do
						if (FlatIdent_55E6D == 0) then
							optTitle:Destroy();
							btn1:Destroy();
							FlatIdent_55E6D = 1;
						end
						if (1 == FlatIdent_55E6D) then
							btn2:Destroy();
							spiderAnimation(box, function()
								local FlatIdent_1CF93 = 0;
								while true do
									if (FlatIdent_1CF93 == 0) then
										s2:Destroy();
										cb();
										break;
									end
								end
							end);
							break;
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
				break;
			end
		end
	end);
end
pb.MouseButton1Click:Connect(function()
	LANG = "pt";
	showLoader(function()
		buildHub();
	end);
end);
eb.MouseButton1Click:Connect(function()
	local FlatIdent_1BB9C = 0;
	while true do
		if (FlatIdent_1BB9C == 0) then
			LANG = "en";
			showLoader(function()
				buildHub();
			end);
			break;
		end
	end
end);
