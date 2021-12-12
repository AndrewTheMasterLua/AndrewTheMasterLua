local main = Instance.new("ScreenGui")

local Frame = Instance.new("Frame")

local up = Instance.new("TextButton")

local down = Instance.new("TextButton")

local onof = Instance.new("TextButton")

local TextLabel = Instance.new("TextLabel")

local plus = Instance.new("TextButton")

local speed = Instance.new("TextLabel")

local mine = Instance.new("TextButton")

--Properties:

main.Name = "main"

main.Parent = game.CoreGui

main.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Frame.Parent = main

Frame.BackgroundColor3 = Color3.fromRGB(163, 255, 137)

Frame.BorderColor3 = Color3.fromRGB(103, 221, 213)

Frame.Position = UDim2.new(0.100320168, 0, 0.379746825, 0)

Frame.Size = UDim2.new(0, 190, 0, 57)

up.Name = "up"

up.Parent = Frame

up.BackgroundColor3 = Color3.fromRGB(79, 255, 152)

up.Size = UDim2.new(0, 44, 0, 28)

up.Font = Enum.Font.SourceSans

up.Text = "UP"

up.TextColor3 = Color3.fromRGB(0, 0, 0)

up.TextSize = 14.000

down.Name = "down"

down.Parent = Frame

down.BackgroundColor3 = Color3.fromRGB(215, 255, 121)

down.Position = UDim2.new(0, 0, 0.491228074, 0)

down.Size = UDim2.new(0, 44, 0, 28)

down.Font = Enum.Font.SourceSans

down.Text = "DOWN"

down.TextColor3 = Color3.fromRGB(0, 0, 0)

down.TextSize = 14.000

onof.Name = "onof"

onof.Parent = Frame

onof.BackgroundColor3 = Color3.fromRGB(255, 249, 74)

onof.Position = UDim2.new(0.702823281, 0, 0.491228074, 0)

onof.Size = UDim2.new(0, 56, 0, 28)

onof.Font = Enum.Font.SourceSans

onof.Text = "fly"

onof.TextColor3 = Color3.fromRGB(0, 0, 0)

onof.TextSize = 14.000

TextLabel.Parent = Frame

TextLabel.BackgroundColor3 = Color3.fromRGB(242, 60, 255)

TextLabel.Position = UDim2.new(0.469327301, 0, 0, 0)

TextLabel.Size = UDim2.new(0, 100, 0, 28)

TextLabel.Font = Enum.Font.SourceSans

TextLabel.Text = "gui by me_ozoneYT"

TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)

TextLabel.TextScaled = true

TextLabel.TextSize = 14.000

TextLabel.TextWrapped = true

plus.Name = "plus"

plus.Parent = Frame

plus.BackgroundColor3 = Color3.fromRGB(133, 145, 255)

plus.Position = UDim2.new(0.231578946, 0, 0, 0)

plus.Size = UDim2.new(0, 45, 0, 28)

plus.Font = Enum.Font.SourceSans

plus.Text = "+"

plus.TextColor3 = Color3.fromRGB(0, 0, 0)

plus.TextScaled = true

plus.TextSize = 14.000

plus.TextWrapped = true

speed.Name = "speed"

speed.Parent = Frame

speed.BackgroundColor3 = Color3.fromRGB(255, 85, 0)

speed.Position = UDim2.new(0.468421042, 0, 0.491228074, 0)

speed.Size = UDim2.new(0, 44, 0, 28)

speed.Font = Enum.Font.SourceSans

speed.Text = "2"

speed.TextColor3 = Color3.fromRGB(0, 0, 0)

speed.TextScaled = true

speed.TextSize = 14.000

speed.TextWrapped = true

mine.Name = "mine"

mine.Parent = Frame

mine.BackgroundColor3 = Color3.fromRGB(123, 255, 247)

mine.Position = UDim2.new(0.231578946, 0, 0.491228074, 0)

mine.Size = UDim2.new(0, 45, 0, 29)

mine.Font = Enum.Font.SourceSans

mine.Text = "-"

mine.TextColor3 = Color3.fromRGB(0, 0, 0)

mine.TextScaled = true

mine.TextSize = 14.000

mine.TextWrapped = true

speeds = 2

local speaker = game:GetService("Players").LocalPlayer

local chr = game.Players.LocalPlayer.Character

local hum = chr and chr:FindFirstChildWhichIsA("Humanoid")

nowe = false

Frame.Active = true -- main = gui

Frame.Draggable = true

onof.MouseButton1Down:connect(function()

	if nowe == true then		nowe = false

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Climbing,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Flying,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Freefall,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.GettingUp,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Jumping,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Landed,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Physics,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.PlatformStanding,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Running,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.RunningNoPhysics,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.StrafingNoPhysics,true)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Swimming,true)

		speaker.Character.Humanoid:ChangeState(Enum.HumanoidStateType.RunningNoPhysics)

	else 

		nowe = true

		for i = 2, speeds do

			spawn(function()

				local hb = game:GetService("RunService").Heartbeat	

				tpwalking = true

				local chr = game.Players.LocalPlayer.Character

				local hum = chr and chr:FindFirstChildWhichIsA("Humanoid")

				while tpwalking and hb:Wait() and chr and hum and hum.Parent do

					if hum.MoveDirection.Magnitude > 0 then

						chr:TranslateBy(hum.MoveDirection)

					end

				end

			end)

		end

		game.Players.LocalPlayer.Character.Animate.Disabled = true

		local Char = game.Players.LocalPlayer.Character

		local Hum = Char:FindFirstChildOfClass("Humanoid") or Char:FindFirstChildOfClass("AnimationController")

		for i,v in next, Hum:GetPlayingAnimationTracks() do

			v:AdjustSpeed(0)

		end

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Climbing,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Flying,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Freefall,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.GettingUp,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Jumping,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Landed,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Physics,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.PlatformStanding,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Running,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.RunningNoPhysics,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.StrafingNoPhysics,false)

		speaker.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Swimming,false)

		speaker.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Swimming)

	end

	

		local plr = game.Players.LocalPlayer

		local UpperTorso = plr.Character.LowerTorso

		local flying = true

		local deb = true

		local ctrl = {f = 0, b = 0, l = 0, r = 0}

		local lastctrl = {f = 0, b = 0, l = 0, r = 0}

		local maxspeed = 50

		local speed = 0

		local bg = Instance.new("BodyGyro", UpperTorso)

		bg.P = 9e4

		bg.maxTorque = Vector3.new(9e9, 9e9, 9e9)

		bg.cframe = UpperTorso.CFrame

		local bv = Instance.new("BodyVelocity", UpperTorso)

		bv.velocity = Vector3.new(0,0.1,0)

		bv.maxForce = Vector3.new(9e9, 9e9, 9e9)

		if nowe == true then

			plr.Character.Humanoid.PlatformStand = true

		end

		while nowe == true or game:GetService("Players").LocalPlayer.Character.Humanoid.Health == 0 do

			wait()

			if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then

				speed = speed+.5+(speed/maxspeed)

				if speed > maxspeed then

					speed = maxspeed

				end

			elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then

				speed = speed-1

				if speed < 0 then

					speed = 0

				end

			end

			if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then

				bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed

				lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r}

			elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then

				bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed

			else

				bv.velocity = Vector3.new(0,0,0)

			end

			bg.cframe = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((ctrl.f+ctrl.b)*50*speed/maxspeed),0,0)

		end

		ctrl = {f = 0, b = 0, l = 0, r = 0}

		lastctrl = {f = 0, b = 0, l = 0, r = 0}

		speed = 0

		bg:Destroy()

		bv:Destroy()

		plr.Character.Humanoid.PlatformStand = false

		game.Players.LocalPlayer.Character.Animate.Disabled = false

		tpwalking = false

	

end)

up.MouseButton1Down:connect(function()

	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,2,0)

	

end)

down.MouseButton1Down:connect(function()

	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,-2,0)

end)

game:GetService("Players").LocalPlayer.CharacterAdded:Connect(function(char)

	wait(0.7)

	game.Players.LocalPlayer.Character.Humanoid.PlatformStand = false

	game.Players.LocalPlayer.Character.Animate.Disabled = false

end)

plus.MouseButton1Down:connect(function()

	speeds = speeds + 2

	speed.Text = speeds

	if nowe == true then

		

	tpwalking = false

	for i = 1, speeds do

		spawn(function()

			local hb = game:GetService("RunService").Heartbeat	

			tpwalking = true

			local chr = game.Players.LocalPlayer.Character

			local hum = chr and chr:FindFirstChildWhichIsA("Humanoid")

			while tpwalking and hb:Wait() and chr and hum and hum.Parent do

				if hum.MoveDirection.Magnitude > 0 then

					chr:TranslateBy(hum.MoveDirection)

				end

			end

		end)

		end

		end

end)

mine.MouseButton1Down:connect(function()

	if speeds == 1 then

		speed.Text = 'can not be less than 1'

		wait(1)

		speed.Text = speeds

	else

	speeds = speeds - 2

		speed.Text = speeds

		if nowe == true then

	tpwalking = false

	for i = 1, speeds do

		spawn(function()

			local hb = game:GetService("RunService").Heartbeat	

			tpwalking = true

			local chr = game.Players.LocalPlayer.Character

			local hum = chr and chr:FindFirstChildWhichIsA("Humanoid")

			while tpwalking and hb:Wait() and chr and hum and hum.Parent do

				if hum.MoveDirection.Magnitude > 0 then

					chr:TranslateBy(hum.MoveDirection)

				end

			end

		end)

		end

		end

		end

end)
prediction = 0.165

--//Credits to Lucifear

---------------------------------------------------------------------------

---------------------------------------------------------------------------

_aHGX2v35JKbWdAXv, Protected_by_MoonSecV2, Discord = 'discord.gg/gQEH2uZxUk'

,nil,nil;(function() _msec=(function(l,b,o)local T=b[(0x70+-61)];local E=o[l[(0x30a+-115)]][l[(1642-0x357)]];local c=(35-0x1f)/((0x50-(0x97-89))/0x9)local f=((54+(-134+0xf))+0x43)-(-91+0x5c)local v=o[l[((-0x3e+392)-0xb8)]][l[(-51+(723-0x18e))]];local S=(0x28/(138-(0xd5+-115)))+(52+-0x32)local x=o[l[(1116-0x255)]][l[(1756-0x3ab)]]local e=(-0x50+82)-(0x5e-(0xcd+(-21840/0xc3)))local a=(59-(((0x348/105)+-77)+0x7d))local F=(0x34-(((0x2a70/56)+-0x12)-0x7f))local d=((((84+(0x22+-71))-87)-0x23)+78)local r=((((0x554-728)+-0x60)-294)/82)local P=(((((-3659+-0x5d)/56)+46723)/0x60)/0xa2)local p=(-70+(165+((0x1+-22)+-0x47)))local _=((3780/(0x180-(459-0xff)))+-17)local i=((0x21f2/((0x70b0+(-0x18+-68))/0xb6))-0x33)local w=(0x59-(201-(2552/(0x7fe/93))))local C=((0x95+(((0x8-49)+-78)+-0x5))-0x15)local U=((((2237-0x47b)+-0x25)-561)/123)local t=(34+(0x12-(3408/(12780/0xb4))))local L=(94-(219-(0xbc+(-27+-0x22))))local n=((158-((475+-0x7e)-219))-0x1a)local m=(0x8c/((0x2190/(11952/0xf9))-109))local B=(((0x3aa5-(0x47b9b/39))/0x14)/187)local H=(-0x30+(0x4c+((-0x485+-91)/48)))local M=((((4385295/0xcf)-10625)/0xb0)/30)local G=l[(-0x59+1456)];local J=o[l[(250+-0x68)]][l[((-0x60-0)+0x246)]];local V=o[(function(l)return type(l):sub(1,1)..'\101\116'end)('KlfhhkhM')..'\109\101'..('\116\97'or'LMKPmlFL')..l[(1091-0x23c)]];local A=o[l[(-0x73+(86224/0x88))]][l[(0x7f3-1071)]];local u=(0x1f0/248)-(344/(0x9f3c/(0x6f18/120)))local N=(0x4a/((-0x5d+70)+0x3c))-(-0x14+22)local y=o[l[(0xa5+-19)]][l[(0x936c/102)]];local h=function(l,o)return l..o end local s=(120-0x74)*(((0x5ca/57)+-0x58)+0x42)local Q=o[l[(-81+0x4e5)]];local O=(0x66-100)*(317-((70393-0x89a7)/0xba))local j=(0x35800/214)*(0x23+(70+(-0x48+-31)))local Y=((-0x2d+(0x55f0/110))-0x67)local D=((820/(0x3e-52))/41)*(0x58+-86)local K=o[l[(0x3d857/243)]]or o[l[(37368/0x48)]][l[(0x3d857/243)]];local k=(53760/(-0x4d+(0x26e-335)))local l=o[l[(135744/0x70)]];local g=(function(O)local k,b=1,0x10 local o={j={},v={}}local h=-e local l=b+f while true do o[O:sub(l,(function()l=k+l return l-f end)())]=(function()h=h+e return h end)()if h==(s-e)then h=""b=u break end end local h=#O while l<h+f do o.v[b]=O:sub(l,(function()l=k+l return l-f end)())b=b+e if b%c==u then b=N A(o.j,(y((o[o.v[N]]*s)+o[o.v[e]])))end end return x(o.j)end)("..:::MoonSec::..bBfFlLkKoOpPhHmMmBhlPbOhooKlkblhFoFbBbMhmoomhpphOoolPkhLPpOOKFKBkpLpFLfmfbOoobkhLoOlOBomKhObmmhhPoplHkmLHkPookOLopKKklBMFbBHbhMbhbkHLbFhfoLKkolHlpfLBFBbmHmkpfLlFoflBblhLKlKfOfbbBMFHmohLoFlfbbhlbLOFHBHBkbFmOHbppPFOMObLoLLLflbOkPfObKhkopOPbObKOKoLLfOFKfOBFMBhoHFhFMhFOBlbbmhfpfOfbboMBHKhBhbOHookFKbLKlkfBBFMHKlKlLhloFloKkHkLlOOkHBpoOlobPfhBPfOlkfKBkkLFlbMPbhMOmohhpFpkkMolkLkFlMokkmpOohKoklOHOHOBoflLkfFHFfflHfooKlkblhPfflBbMhmoHlhbphPmOmKbLhlolHfbbHMomMHbhbmFOlobkhKBllFBBhbokmmbhhPoplObKhkoKlpbfhBoblMbHhhhPlpkOpKoklLbLLfoBLbbmhHohomPOhooKlKOlhFOflBbKkmoHlhbphOoolKbKhPMFlfbbhMomlHlPhhoOlobkhLollFbBMbobkmbhhPpplOkKhkoLllbfhBoblMbHmhoPkpbOfKoklLbFhlBBlbBmhHohlPlHKooKlkbkLFofLBbbmkhHlhbphpBolKbLhkoFlfbbhMomlHbhlpoPlobkhLollFbBhBlMlbbhhPoplObKhkoLLlbFmBoblMfHhhMPlpbohKoklLbFMfoBlbbmhHomlPbOhoPKlkFlhFhflFbMhmoHKhbpMOoopKbKhloFlfFbhMPmlHLPhpoOlobkhLolKFbBHboMombhhPoplhLKhkOLllbpkBoblMbHhhoPlpbPfPhklLbFhlLBlbBmhmFhlPlHKooKlkbkOFofLBbbbfFHlhbphhHolKBLhlopmfbbhMomlHbPhpoPlmbkhLollFbBhbhMlmkFOPoplObOmkoLLlbfHBobofPHhhoPlhfohKOklLlKKfoBlbbfBHohLPbOhbfKlkblhFoflBbMhbolPhbphOoolKbkbloLlfbbhMomlHbPhPfOlOfkhLolkFbBmboMlmbhhPoplObKhkpLllffhBmblMbHhhomOpboHKoklLblbkFBlbbmhbHhlPBOhOpMokblhFofHBbMhmoMlmLphOoolKbLhLbFllbbhMomlHbPhpopbobohLollFbBhboMlmBhhhpplObKmkoLPlbfhBoblMbHhhPPlpbohKoklKbFhfoBKbbmMHohoPbPhooKlkFlhFPflBpMhMpHlhbPBOookKbLhloFlfbbhMPmlHLPhppOlpbkhLolKFbBMboMOmbhhPoplObKhkPLllBfhBoBKMbHhhoPLpbohKoklLbFhfoBlbhmhHohlLmpkooKlkbOfpBOkKLlMlHlkFkBBbpBloBLhloFlKfKBkoLbFOBMbObomLHbpPPoOMomkOLPlLFbpmPfObKhkoOppOOpKhlpLOlmFPfomFMlmBHbPlhkFBBlbbmhfLfLBObphHmphLPpphOkBoMhmoHlBbBPbPmHmlhLPKpfPkBhMomlHbblBHbBmBHphKpHOlkmKKkFLlBhBOBkblOpkhLllbfhkokLkfLbLfhfpbohKoPOhbpboOookLFOlKFOfFbBHomFHFmoFhflBbMhlMFLfHBBBboHKbLhloKKookHkplLFFFbbHbkKboBLollFbkfKBkfllBffBBkbFMbpPPhpOOoKhLFLkBMFlBLBFMMPbklLbFhfoombbmhHohlPbOhooOppllhFoflBlMhmOHlhFphOhPMKbLhloFofbbHMomobPPhpoOlOPkhLOllFbOkboMlmbhhPoplObOhhoLllbfhBoblMPHhhmhfpbohKoKMLbFHfoBlbbMbBFhlPbOhpFKlkBlhFoOmBbMhmoHlhbphOoplPoLhloFlfbbhbFmlMbPhpoOlobkhLoloFbfmboMlmfhhPMplObKhkoLllbfhBobkMbHmhoPppbohKoklkbFhfOBlbBmhHhMMPbOhooolkblHFofolPMhmoHlHPphOOolofmbloFlfbBkMomlHbHhpoOlobkhLollFfBhfoMlmbhhPoplOboBkoKllbfhBoblMbHhhOPlPfohKokkLblLfoBlbbmhHohlPFOhooKlkblhLoflBbMMmoHKhbPKOoplKbLhlPFlfFbhMMmlMbPhpoOKobkMLolpFbBhboMlmbhhPPplOBKhkhLllbfhBoFPMbHHhoPlBpohKoklLbFhfoBlfkbkHohlPbHFooKLkblMFofolPMhmoHlMKphOOolKbHkloFlfbbhMomlHbHhboOlobkhLollFPBhbmkBmbhhPohKObKHkoLLlbFbLFblMbHhmPPlpBohKhOMLbFhfolPbbmHHohlfpOhooKlkblhFoflFbllmoHlhbphOooMKbKhloFlfbbhMomlHhPhPpOlobkmLolhFbBhboMlmbhhPoplOfKhkpLllkfhBoblMbbKhoPLpboHKokooPFhfoBlfPmhHOhlPlHKooKlkboFFofLBbbmkhHlhbphpfolKbLhkoLOfbbhMomlHbPmpoPlobkhLollFbBhbHMlbbhhPoplObKhkoLLlbFmBoblMfHhHBPlpbohKoklLbFMfoBlbbmhHomlPbOhoPKlkFlhlFflFbMhmoHKhbpMOoObKbkmloFlfLbhbbmlHbPhpoOlobkMLolOFbBmboBlmbhhPPplOFKhkmLllbfhBoblMbHMhoPLpbohoPklLbFhfOBlbbmhHohlPbOhoooKkblhFokkBOMhmoHlbFBlMOMkHBPMPhOOOfkbbomlHbPhMPMOmmHbpkPFploLkmLHlFfHfhbHMMmplkLMlbfhBoflLKlPFhHlmhMPHPhMPLpbklBlbbmhHoKmPpOhooKlPLPhpooOofLbLKlkFFBPfoomKbLhloKPoLoblPlOlfFfBBMKmLMkLhllFbBhLhLOLolblmpmObKhkopKPloHopKoLLlmbMfObOKhKhklLbFhKkKLkHLBbmhoPbOhooPhhLpHOhpmBkMhmoHlBFfLbPMoHLhOhmFlfbbhMomlHbOhmKpholkhLollOKKHKLLOomHOPoplObhoHKPKpPlhKhkHkFFHfpfbbLMbBlkPLbFhfokKkLkbBPFFffbBBoKOkblhFoKoKOKbLlFOfkPlOoolKbpbPHpkoBobkBLFFmMmPkOlobkhOmpHOmoblmLHLfFMfhmKMomLHlPoffkbBoblMbHhlfPlpbohKoklLbFhfooFbbmhHohLPbOmooOppllhFoflBLMhmOHlHFphOhPMKbLhloFOfbbHMomobPPhpoOlpkkhLOllLbKhboMLmbhhPopLObofHLLllBfhfBblMBHhhOPlplhKKoklLblLfoBLbbMbBFhlPbOhpmKlkBlhLoolBbMHmoHlhbpHOoplPfLhlOFlfBbhbpmlmfFopoOKobKkLollFbBhOfMlmBhhPPplOfKhkmkflbfHBofpMbHHhoPlpbObPFklLbFhlmBlbBmhMoflPbOHooKlkblHFollLfMhmOHlhBphppolofHoloFKfbBBMomlHbPhFfOloBkhLPllFfBhbmbfmbhHPohpObKHkoLllbFbLFblMbHhmmPlpBohKoObLbFhfoBLbbmhHoHkHpOhoOKlkHlhFoflFbMhmoHLhbpHOoopKbkmloFlfFbhbbmlHbPhpoOlobkHLolKFbBmboBlmbhhPOplOBKhKKLlLffhBobKMbHmhoPlpbohKoklLlFhfoBlbFmhbohlPbpbooolkbLKFoFkBbMhmHHlhlphOoolObLhloFpfbbhMomHHbhmpoOloKkhLPllFbBhboMlmbHBPopOOboFkokllbfhBhblMKHhhHPlHbohKokoLblHfofbbbmhHohlPBOhohKlkBlhFhflBbMhmobKhbpHOoolhBLhlOFlfBbhMomlHbhbpoOLobkHLollFbfmboMlmBhhhLplObKhooLllbfHBobLMbmfhohkpbohKPklLoFhfoBlbbmhHohLPbOMooKkkbkhFoflBBMhmOHlhMphppolKbLMloFkfbbhMomlHbPhphOlobkhLPllkbBhboMombHhPopMObphkoLlllfhBMblMmHhMoPlpbObKoKLLblofoBlbbmhHOhlPlOhoOKlkbLMFoflBbMHmoHlhbphOoolKbLhLHFlfbbhffMlHbPhpoHhMLHOPOPfOMoLkhlklMFPfhMlMBmmHhlmkpFLBoblMbfOfOBHbmHBmmhOPmPbmmBobbmhHofPBBbOmHOokolhFoflkbkPLPFHFlBLbKMfPfkKloFlfbLokKlKFBfoMobbmBmLPHPkKofFboMlmbBhflbLbOmBHphKfplBBoblMbffFBffblHfmBHkhFPbkPKhkOLoFhBFBkHMMlHLHFPMHlfmBbMhmoBPfLfbmPmOmfHfPBOKoLHmbOmlHbPhMpMOMbHohBpKOBObkHLoFFlbfKBkMBmFhHFolofhBoblFKlBFhbBbMbBmPhOholkfoBlbbLhlpfOBlbLmPmohOPPpkFhBFMhmoHlboBLbhKpKOLhloFlkFKlLOLkFBBMBhMOMfBlkkllFbBhLHklllfHfhbOHHmPHHhKpLKhoKKKMkmbhoPlpbHhHOHkhlfbFfBlbbmhBmfHffbBHPHOHfhfOHOkLmblmoHlhbbfMHMbHMPMPBpoOOpmMMmlHbPhmOMHmHHohKpKOPBhbhMlmbhhbbbOMBmbhfkflbfhBolpLOlpfhMpbOMmmPHoOFplOBobkllBHohlPbOhbfKlkblhFoflBbMhbmmmhbphOopkKbLHloFkfbBbFFmlHbPhhpOloBkhLoPmFbBhboMlmbhhPohlMbKhkoLllbfhfkblMklOhoPlpbOlKokLLbFHfoBoFPmhHohlPoOhoOKlkloKFoflBbBmmoHLhbphBfolKbLhloFlfbbhBoLPHbPhpoOlobKpLoklFbBhboMlmbhhhHplpfKhkoLklblbBoblMbHhhoPlpbohKpklLfFhfmBlbbmhHomkPbOHooKlkbLbKFflBbMhbpHlhBphppboKbLhloFofbbhMoblHhPhpoOlobkhkfllLbBhboMlmbhhPopKObOhkoLllbfhBoblbBHhHpPlpbomKoKFLbFhfoBlbbmhHPhlPbOhooKloblhFofKBbMMmomfhbhhOoolKFLhlPFlfBbhBomlHbPMpoOKobKBLollFbBhbhMlmbhhPoplPbKhkoLolbFbBoBfMbMhhoPlplohKhklLBFhloBlbbMbHohoPbpmoookkblhFHflBhMhmoHlhbphOoooKbkbloFOfbbhMomlHFPhpPOlolkhkpllFbfbbobKmbhhPoplObKhkoLlllfhBOblMlHhhoPlpbmbKokLLbFhpfBlbbmhHohlPbOhpmPokblhFolpBbMHmoHkhbPbHFolKbLhkmFlfBbhMhBMHbPhpoHlobkHLollppBhboMlmbhhPoplPbHhkoLllbfhBoBfMbmfHkPlpbohPoklLBFhfoBlblfKHohlPbHhooKLkblhPfflBbMhmoHlhbphPohhKbLhloFlfbBpMoblHbPhpoOlobkhkblllfBhboMkmbHhPoplObKhkoLllbfhBpblMfHhhmPlpbohKoOkLbFHfoBLbbMbBFhlPbOhPpKlkBlhFhLMBbMhmoBlhbpHOoOkMlLhloFlflbhMomlMbhkpoOlobkhLolmFbFhboMlmbhhPoplOFKhooLllbfhBoblMbmHhohkpbohKpklLMFhfoBlbbmhHohKPbOhooKlkbkhFoflBFMhmPHlhmphPoolKbLMloFKfbBlMoMkHbPhpHOlObkhLollFbBhboMKmbHBPopkObOhkoLllFfhBPblMLHhHpPlpbObKoKKLbFhfoBlbbmhHohlPlOhoOKlkllhFoflBbLbmoHLhbphBfolKbLhloFlfbbhBmMmHbPhpoHoobkHLolkFbfblFMlmbhhMhplOBKhkhoMlbfhBoLoMbHHhohkflohKoklLlFhfoBlfbLFHohlPbOhooKmkbkhFoflBbMhmoHlhFphPoolKbLhloFlfbBHMoMkHbPhppOloMkhLolllfBhboMKmbHbPoplObOhkoLllFfhBPblMOHhHpPlpbOBKokPLbFhfoBlbbmhHPhlPLOhopKloblhFofKBbMMmoHphbhhOoolKFLhlPFlfPbhMomlHbPMpoOkobkmLoklFbBhbPMlmFhhhLplPbKhkoLKlbfMBobOMbmmhoPlplohoPklLbFhfoBlbbmhHohoPbOHooKlKFlhFoflBBMhmoHlhBphOoolKbLhloFlfbbhMomlHbhFpoOlobkhppllFbBhbOMlmbhhPoplObKhkoLllbfhBoblMbHhhoPlpbohKoklLbFhfoBlbbmMHohlPbOhooKlkblhFoflBbMhmoHlhbphOookKbLhloFlfbbhMomlHBPhpoOlofkmLollFbLfbHMlmbhhfobKMBmoHlKplbfhBoblMbHhhoPlPHohKoklkfPofoBkbbmmHohlPbpmblKlkFlhFpflBbMhMpLohbPbOooLKbLhloFpfkbhMHmlHbPhpOOlolkhLoOFFbBhboMkmbhhPoplHMKhkoLllbfhBoblMbfPhoPlpboMKoklLbFhKKBlbbmhHOhlPbOhooPBkbLbFofkBbMHmoHpbKphOooloOLhlOFlfBbhMhBMHbPhpopHobkHLolpFfBhboMlmmhhPOplOBKhkhoMlbfhBoBfMbHHhoPoHPohKoklkOFhfOBlbkFFHohLPbPLooKLkblhFofolPMhmoHlHOphOOolKbHmloFofbbmMomKHbPhfpOloLkhLPllFfBhbmFPmbHbPoPHObKHkoLOlbFbLFblMbHhmBPlpBohKomkLblbfoBkbbmMHohlFfOhoHKlkFlhFpflBklFmoHohbhLOooLKbkBloFoLPbhMomlmOPhpOOlolpKLollFbFkboMLmbhhFOplOlKhkoLllbfhBofHMbmbhoPLpbohKoklkmFhfhBlbfmhHohlPbpMooKlkblHFoflBbMhmoHlhbpMpbolKbLhboFofbbhMolKFoBHBpbkoFkhLollpFOBkpMlmhhhPoplHhmFmBOpOMOfolKmFhFBBbMKKpohKoklLbFhfoblFMhlHhhlPbOhmpmHHlPBbhflBbMhmoHlhbBhHoLkKbLhloFlfkBfMomlHbfMBhbkmOHpPMkkFbBhbobkklhhPPplOFKhkoLllboBBobKMbHMhoPLpbOfmLklLFFhfHBlbBmhHOhlPlHKooKlkbLBFofLBbbbfFHlhbphpbolKBLhLpPofbbMMomKHbPhpoOlHLkhLPllFFBhbOMlmbmpPopKObKmkoLllbFmOlblMFHhhhPlpbohopPoLblbfoBPbbmhHoHkPbOhoHKlkllhFoflBbMhmoHphbphOoolKbkmloFlfKbhMhmlHbPhphOlobKBLokfFbBHboMlBlhhhBplOlKhkoLlLfloBobmMbmlhoPlpbphKoklLpFhFfBlbBmhMohlPbpKooKlkblmFoflBbMhMLHlhophOoolKbLhlolffbBlMomlHbPhpoOloPkhkkllFfBhfoMlmbHKPopMOboBkoLllbfhfFblMfHhhpPlpbohKokMLblKfoBKbbbhHohlPPOhOFKlkklhFoflBbbkmoHkhbpmOoolKbLhlhFlfObhbfmlHbPhpoOHobkMLolkFbFhboMlmFhhhBplOkKhkhphlbFBBoBfMbHHhohkflohKHklLFFhfoBlbbBmHohOPbOHooKokblhLkflBlMhmpHlhbphOoOKKbLhloFLfbbhMomlHbPhpoOLokkhLollmbBhboMlmbhhPophHbPmKkLllbfhkHKlLlFHFhBOmHMPmHHKPLohOKoKPpMFHohlPbHHMBmBhhPPOPoMLobkmoHlhbMfbBMkHLpMpHpkOkKBkpHlmBPhpoOlmKHBhhPfOBoOkHLKlBFoflBBMLMbHbhFpllbBoblMbHhhoPlObhPOKklLbFhfooHbbmmHohlPbOhooKlKBlhFPflBbMhmoHlhbfbOookKbLhloFLfbBmKhmlHFPhpHOlobkhLoPFFbBMboMLmbhmPohpppKhkPLllofhBOblMlHhhhmMpbohKokhLbFHfoBoFPmhHohlhOOhoOKlobphFofoBbMmmoHphbPfbLolKlLhLlFlfBbhMOmlHlMKpoOlobKoLolLFbfblFMlmbhhHBplOBKhooPllbFbBobkMbmfhoHpmlohKhklkOFhfOBlbfmhHhMMPbOhoooHkblHFollKbMhmhHlhfphOOolKkhOloFofbBMMomLHbPHpoOoPPkhLolllFBhbOMlmlbKPoplObOFkoLLlblhKoblMlHhhpPlpBohOmpoLblbfofPbbmHHohKPbpbhFKlkblhlMflBBMhmhbMhbphOoOHKbLHloFlKBbhMhmlHlPhpoOlobopLoloFbBmboMlmbhhFfplOlKhkoLllbfhBoLmMbmBhoPlpbohKoklLbFhfmBlbbmhHohlPbOhooKokblhFoflBbMhmoHlhlphOoolKbLhloFlfbbhMomLHbPhpoOlobkhLollFHBhboMlkpHLPoplObHFHKhkpPOMookLLFlBofPhpbohKopPPLPbKLoFKLLMFHPlPFOhooKlpoPLphObBLMhmoHlFbbHbBMkmFMolmFlfbbhlolLlffBBkboklKFLollFbkmkHLPlOFPfkHKlpobkoLllbOFKOKBLLmoHpPlpbohPmhHPmpbKoKLKfkblPbHBmmmmHHPhOPPpkLKhpbFmoHlhbMhblmLmOhBPppKOfffMomlHbbFbHboHbHoPOPHOLomlmkklMFOMPbhMBmmhOPKPlOBopooMFHhhoPlbmMBmMHlMollfoBlbbFhlKFKBOBbMBmFhmKfFoflBbbmfoHlhbphOholKbLhLpFlfbbHMomPHbPhpoPlobkhLOllFBBhbOMlbbhhPopLObKHkoLhlbFmBoblMFHhhmPlpbohOoklLbFMfoBKbbMKHohlPbOhohKlkblhFoflFbMhmoHohbPbOookKbLhloFlflbhMpmlHfPhhoOlobKbLoloFbBMboBlmbhhPhplOlKhKLLllbfhBobOMbHhhoPlpbphKoklLLFhfHBlbfmhHohlPbpBooKkkblmFollBbMhmHHlhLphOPolObLhloFOfbBBMoMBHbPhpoOloFkhLHllFbBhboMlmbhHPoplObKhkoLllbfhBoblMbHhhpPlplohKoklLbLHfoBLbbMmLhhlPLOhoMKlkblhLoFlBbbBmoHOhbPLOoplKbLhlHFlfLbhbfmlMbPhpoOPobKbLolOFbBhboMlmLhhPMplOfKhomLllbFBBofbMbHHhohbpbObPFklLbFhllBlbBmhHhMMPbOhooOLkblHFoflopMhmmHlhbphOoolKkpFloFOfbfhMomLHbhfpoOoPPkhLollLbBhbOMlmlbKPoplObOHkoLLlbfhFkblMLHhhpPlpbohKmhhLbFhfofobbmHHohkPbpbhFKlkblhlhflBBMhmofLhbphOoolKbLhloFlFmbhMomlHfPhpoOlobKMLollFbBHboMlmbhhPoplObKhKlLllbfhhkBLMbHhhobkbLMhmlhHPFOHOhKOklFMlhFFffMHmMHOpfLLFoflBblOlOFHfmMBbmmOHmHbbhKbflbhMomlFKBHBLMOMmoBLollFbkfKBkfllBffBBkbFMbpPPhpOOoKhLFLkBMFlBLBFMMkokmLbFhfoLpkOLmFHBKBLbmMmHOHfBmlbflBbMhFolFFFBLbhmHHMhppolffbbhMofpFOfpbhHpmOHmhPPoKFolKBkbllBphBplObKhpPPhpBOmKOkKkllBFpHfpmohKoklpLphohKLKlLBfLFFfLbMmHhlhMPMOmFlBbMhmoBhFLBOMOMfHMhLphokoMKPkhFlFBfmBhMpolkhLollobKHKpkoBohhPoplObMkkoLllbfhBoblMbbfbhPlpbohKhklLBFhfPBlblfKHohlPbpbooKLkbLbKFflBbMhbfHlhBphOoMmKbLhloFlfbbhMoblFbPhpoOlobkhkBllFkfpboMlmbmkPopLObKhkoLoKPfhBoblbpHhhOPlpbbkKoklLbFhfoBlbbbhlMhlPbOhooKlkOlhLoflBbMhmoHlhbPlOoOkKbLhlpFlfPbhMomlHbPhpoOlobkmLolkFbffboMlmbhhHfplOBKhkoLlllkKBoblMbMkhoPLpbOmMhklLbFhfhBlbbmhMohlPbOhooKlkblHFollBbMhmoHlhbphOpolObLhloFlfbbhMompHbhmpoOlofkhkfllFbBhboMlmbhMPoplObKhkoKllbfhBPblMFHhHBPlhbohKokKLbFMfoBMbbbhHohlPFOhoPKlkKlhFoflBbMhmoHKhbpHOoooKbLhloFlLKbhMOmlHbFkpoOlobkhLollFblflhMlmbhhHkplOBKhkPLlllkKBoblMbMphoPLpbObPFklLbFhLMBlbBmhHoFmPbOhooKlkblhFollKbMhmoHlhbphpBolKkhOloFlfbfMMomLHbPHpoOoPPkhLollLFBhbOMlmlbKPoplObPFkoLLlbfhOfblMbHhhoPlpbohOophLbFhfoBlbbMLHomlPbOhooKlkblhFHflffMhmoHkhbPoOoolKbLhloFlfbbhMpmlHfPhpmOlobkhLokMFbBHboMLmbHbMFplObKhOFLllBfhBhFMMbHhhomPpboHKoKkHlFhfoBlblmhHohlHbhBooKlkblhFofLBbBhmoHlhbphOoolKfLhkoFlfbbhMomlHbhfpopkobkhLpllFpBhboMlmbhhPopKObKhkoLllblhBoblMFHhhPPlpOohOoklLbFMfoBKbbMBHoHkPbOhoHKlkhlhFoflBbMhmoHKhbPBOookKbKhloFlfFbhMPmlHKPhpoOlobkhLolKFbBHboMlMFhhPoplOBKhkoLllbklBoblMbMlhhPlpbohhFhHPFpKmoBmbbmhHofFbMbMmHHKHLPmOHoOoBhoMFHlhbphbPmOmlhmpHOLolKPkkLblOMfPfOlobkhOMpOplkMkHkkLkFLBPbOhbolkoLllbkmKOkKLPlhfOBKbPmfKoklLbFhfoBlblfhobhPPbOhooPKhMPppkoOKFKbOkHPhbphOohoHLhMPhpkoMoLmfmPHbPhpomlmhhHHBpOpfoMkfbOmbhhPoboMOmMhPhFPfOblkkPLKbPfMbLmLHlppHOppPlKHKMopMbHohlPbBFmOHHHlMllBflBbMhfOFKFlBLbmmLmlhBphhlFLbhMomllfBmfbMLMFHMPHPokplPFKfLBLMMmpHKhLphOmoKKOmbBhblMbHhfMBLbHMBhbkoLbFhfokPkBLLlhflPoOhooKlpOPppPOoKBkplPFOKlPLOoolKbplpHOLOfobLplOFBFbLoOlobkhLollFbbhlKKmmlhhPoplHmHHHLPOomFMBoblMbBMFpBObBbbHHhoKbKmpBFllhkBFPfHBkbBmOmkhhLFFoflBbFMLKlkfLMFbHmHOlkbloFlfbkbkKLFFhmbPkOlobkhOPphOBomkOLKLlFBfpmLMlmbhHPoMHfhbbblMKHhhoPlmFMmHHhoPOPbOPLbbMmhHohlBKbBMhmkhBhFpLoOolLHLhFLffBoMHHoKLLhloFlKlKLkhLbFLHhpoOlobkhLPOloHLHPkMmmbhhPoMkbLmpPPPOPfpfoBkKLLBfHBPlpbohPPHbPBpMOPkfkBLOFHLpPKOhooKlPFPBphkKKMkmlHLmhOphOoolPFhlpOpkoBkMkhlOlfPhPbOlobkhOhPOpfKHKhLHlMFpFhpmObKhkoOmpMOLokflFKlmFKfOBbPbofklLbFhKPookBLmlhfOffmFMHHHllLLFoflBbLblHlhFlfBbpmOPOhbBpFMfbbhMofPFLFbmPMhmOHoPhPkOLopohMmmbhhPobFmMmphOhBpLoMKOKbLhMlHlPlpbohPOhHPHpoOKKKkPbhfhFFBMbokbKPkblhFoKKolkBLollfLBbLfoHKbLhloKHOFLLkkfPlffPBHblFpKOLollFbkmkHkfllFBfpMKblmBHohlpLObkkbHMbHhhobPbMMmmFHKhbOHoPKOpmMoHohlPbmomMmHpkpPOmOboploFHBhbFhlpFolKbLhOlpFoFkHklFlFhBHfBMOMfBlLHllFbBhKoLLlOFmfPklOoKhkoLlpFOholLkLmfoBhBLlfOpKoklLbomoHoLKLLLlpfOfFmlmOmfhlPoOHObBkMhmoHlBbbHbpmOHmHbMbFMfbbhMoLfFLFFbPMKmhHPhPPOpfoBOmMombhhPoMoMLMlHhmlLbfhBobllFlBFkBommMPmhhHPkpLoPKLKlLLlKFfhpOhooKlkblhFoloLbMfmPHlhbphbkmOmKlkLOFlfbbhLKlLBobFbbhkMkOMoHomKPKmLMLofBflfmKkObKhkoLkKOfhBoblMlHhhoPlPfhkKoklLbFmfoBlbbmhHohlPbOhooKlkblhFoflBbMHmoHlhbphOoOkKbLhlOFllHbhMomlmfPhpoOLobplLollFblfboMlmBhhhBplOBKhKfLlllkKBoblMbmLhoPLpbObPFklLbFhFfBlbBmhHoHKPbOhooKLkblhFofklOMhmOHlhLphOoolofhploFLfbFhMomlHbhmfhOloBkhkkllFbBhfoLlmbhHPopLOboLkoKlPKfhBOblMBHhMkPlhbohKokLLbFHfoFmbbMmHohlPFOhpLKlkblhFoflBbMHmoHKhbpmOoopKbLhlOFlmPbhMOmlHbPhphhMobkhLobMFbBHbobkklhhPOplOPKhkoLllbplBobLMbHHhoPLpbOmKoklLBFhFkBlbbmhMohlPbOHooKLkbLbFoFkBbMhmPHlhOphOoolKbLhloFLfbbMMomkHbHhpoOloBkhLOllLmBhfmMlmbhHPohfObKHkokHlbFbLFblMbHhmkPlpBohKhOMLbFhfofobbmHHoHkFlOhoOKlkmlhFoflFbKOmoHLhbpHOoooKbkmloFlfFbhbBmlHbPhpoOlobkHLolKFbBmboBlmbhhPOplOBKhOkLlkbfhBobLMbHHhoHLpbOfKoklLBFhLkBlbBmhHOhlPlHKooKlkbKpFofLBbbmkhHlhBphpkolKbLhkoKHfbbHMomLHbhbpopkobkhLPllFOBhboMlmbhhPopLObKMkoLklblhBoblMBHhhOPlhmohOoklLbFHfoBLbbbFHomlPbOhoOKlkBlhlKflBbMhmoHLhbpmOooLKbkmhhFlfBbhbkmlHbPhhobkobkHLolLFbfbbobkmbhhPPplOOKhkoLllbfhBobLMbHMhoPkpbphKoklLBFhfOBlfmmhMohlPbOmooKLkbkHFoFkBbMhmPHlhmphOoolObLhloFKfbbMMomoHbhmpoOloLkholllFbBhboMlmbhMPopOObKmkokklbfhBhblMmHhhoPlhbhmKokoLblbfoBobbMmMLhlPkOhOHKlkblhFoflBbbbmoHphbpmOoolKbLhlHFlfkbhMomlmfPhpoOPoboKLollFbfmboMlmohhhkplObKhkoLllbFFBobkMbHmhoHlpbohobklLKFhlMBlBfmhHohHPbOMooKlkblhFoflBpMhmMHlhbphOoolKbkKloFlfbbhMomllBPhPBOloPkhLOlllfpbboMHmbmKPoplObofHLLllOfhkBblMBHhhOPlplhKKoklLboLfoBLbbMbBFhlPbOhHMKlkBlhlppoBbbLmomMhbphOoOkOBLhLfFlfmbhMomlHbPhpoOHobkmLolkFbFhboMlmphhhBplPKKhKpLllbFKBobKMbHhhoPlpboholklLOFhfoBlbbmhHoHBPbOhooKlkblhFoflBPMhMLHlhBphppolKbkKlokKfbbhMompHkPhPlOlokkhLOllFBBhbolFmbhhPopmObKhkoLlpPfhfFblMfHhhpPlPbpLKokHLbkFfoBMbbmhfkhlPOOhooKlkblhFmfpBbbLmoHPhbpHOooLKbLhOKFlfbbhMOmlHbPhpoPKobKfLolpFbBhbobkmbhhhfplPMKhkoLlkbfhBobMMbHHhoPOpbphKoklLPFhFFBlfkmhHohlPbpKooobkblhFoflBbMhMfHlhbphplolKlLhloFlfbKLMomLHbHhboOloMkhkklllMBhfmFombHPPobHObKHkokplbFbLFblMbHhFBPlpBohOohlLblPfoffbbMMHomphpOhOKKlhKlhFOflFoMhmhbMhbphOomPKbLHloFoLPbhMomlFOPhpOOlpbpmLoLFFbfpboMhmbhhMLplOMKhkpLllBfhBmkhMbmkhoBlpboHKokkLblbkFBlbbmhFohlPBOhOpMokbLkFoLFBbMhmoMlbHphpFolKBLhkOFllbbhMomMHbhKpoPpobkhLollFPBhBlMlmbhhPoplObokkoLllbFoBoboMbHhhoPlfbohKOklKbOhfofFbbMpHomFPbhfpfKlkMlhpHflBBMhMmHlhlmKOoolKbHBloFLfbBbFFmlHbPhfFOloBkhKoplFbfPbobfmbHMPohpHlKhKKLlPPfhBOblBoHhhhmMpbohKoHMLbFHfoFllfmhmKhlPmOhObKlkboOFoFFBbMmmoHLhbPbHFolKbLhhoFlfBbhBollHbhPpopfoboPLokpKlBhBKMlkbhhPOplpkKhkhoMlbfhBoolMbHHhoHlbbohoKklLBFhfHBlBbbLHoHfPbhmoooFkbLfpbflBpMhLOHlhBphOpolKlOKloFlfbKHMomLHbhmfhOlopkhkollFbBhfokbmbHkPopmObPFkokklbfhfFblbkHhhoPlpbohKokmLbFmfoBkbbBhHohlPpOhOPKloolhLoflBbbKmoHLhbPBOoOlKbLhLfFlLfbhbFmlbbPhpoOmobOHLoLhFblhboMlmphhHHplOHKhooLllbFKBobmMbmohoHlpbohoFklLPFhfMBlbkMfHoHBPbOmooKLkblmFoflLMMhmoHlhOphOoolKbpPloFlfbBfMomlHbPhBOOloPkhkLllFBBhBpKombHKPoPMObKhkoLplmfhfFblomHhhOPlpbohKhOMLbFhfoPfbbmHHoHkFlOhOFKlkmlhFoflFbbLmoHMhbPKOoooKbkmloFlfHbhBkmlHbPhpoOlobKKLoLBFbBmboBlmbhhhFplOPKhKOLlkbfhBobMMbmKhoPPpbOfKmklLHFhfPBlbBmhHOhlPbmPooKlkbLfFoflBbMhLOHlhPphpLolKBLhlhkMfbbhMopfHbPHpopkMhkhkFlllfBhboMlMfloPoPbObPfkoLllbFmOlblMHHhHpPlpbohKhmhLblKfoHfbbmHHoHkFlOhOKKlkmlhFoflFbbLmomFhbPPOoooKbkmloFlFBbhBkmlHbPhpoOlobKPLoLLFbBmboBlmbhhhKplOMKhKOLlkbfhBoBFMbmPhoPPpbOfKmklkBFhfoBlbBmhHOhlPbmPooKlkbLfFoflBbMhllHlhMphpOolKBLhLpFlfbBPMoMfHbPhpoPlobkhkKllFMBhbhMlMfhhPoPLObOpkoLllbfhBoblMMHhHOPlpfohOoklLblPfofFbbBKHomlPbOhOKKlkMlhFMflBkbfmomLhbpHOooLKbLHloFlkMbhMomlHkPhpoOlobhoLoLFFbfHboMLmbHmPoplOMKhKkLllbfhFoblMbmPhohFpbObKoKkLbFhFOBlBmmhHohlPbOhoooFkbLHFofkBbBhmoHlhMphpKolOOLhkoFlfbBPMoMFHbhFpoOpokkhkOllFoBhbOMlmBhhPoMFObKhkoLplbfhBoblkBHhHKPlPBohKOklLlOlfoBMbbomHohLPbpmbhKlkPlhlkflBbMhboMohbPKOooMKbkblolkfbbhbLmlMlPhpoOlobkhLolMFbfOboMkmbmhPoplOPKhKFLlkbfhfpblMbmOhomOpbohKoklLbFhFkBlbbmhHPhlmbOhooofkbkoFoFmBbfhmoHlhmphhhololLhKoFlfbBpMobkHbhfpoOlobkhkFllFmBhbOMlmbBpPopLObKhkoLllbFbLFblMbHhOOPlpBohopmoLbFHfoffbbmhHomlbOOhoOKlkBlhlBflFbMhmoHLhbpHOoPfKbKhloFlfBbhMOmlHBPhPpOlobkMLokKFbBhboMlmbhhPOplOFKhkOLllbFMBoblMbHHhoPlpb");local x=(0x90-124)local b=40 local o=e;local l={}l={[(0x34-51)]=function()local f,l,h,e=v(g,o,o+S);o=o+D;b=(b+(x*D))%k;return(((e+b-(x)+O*(D*c))%O)*((c*j)^c))+(((h+b-(x*c)+O*(c^S))%k)*(O*k))+(((l+b-(x*S)+j)%k)*O)+((f+b-(x*D)+j)%k);end,[(53-0x33)]=function(l,l,l)local l=v(g,o,o);o=o+f;b=(b+(x))%k;return((l+b-(x)+j)%O);end,[(-25+0x1c)]=function()local l,h=v(g,o,o+c);b=(b+(x*c))%k;o=o+c;return(((h+b-(x)+O*(c*D))%O)*k)+((l+b-(x*c)+k*(c^S))%O);end,[(0x68+-100)]=function(o,l,b)if b then local l=(o/c^(l-e))%c^((b-f)-(l-e)+f);return l-l%e;else local l=c^(l-f);return(o%(l+l)>=l)and e or N;end;end,[(320/0x40)]=function()local o=l[(0x46+-69)]();local h=l[(115/0x73)]();local B=e;local b=(l[(520/0x82)](h,f,s+D)*(c^(s*c)))+o;local o=l[((173-0x83)-0x26)](h,21,31);local l=((-e)^l[(0x6e+-106)](h,32));if(o==N)then if(b==u)then return l*N;else o=f;B=u;end;elseif(o==(O*(c^S))-f)then return(b==N)and(l*(f/u))or(l*(N/u));end;return E(l,o-((k*(D))-e))*(B+(b/(c^Y)));end,[(130-0x7c)]=function(h,B,B)local B;if(not h)then h=l[(102-0x65)]();if(h==N)then return'';end;end;B=J(g,o,o+h-e);o=o+h;local l=''for o=f,#B do l=G(l,y((v(J(B,o,o))+b)%k))b=(b+x)%O end return l;end}local function Y(...)return{...},Q('#',...)end local function J()local M={};local h={};local o={};local B={M,h,nil,o};local b={}local H=(0x107-167)local O={[(-53+0x38)]=(function(o)return not(#o==l[(0xa4/(189-0x6b))]())end),[((0x151-231)-0x68)]=(function(o)return l[(-113+0x76)]()end),[(-112+0x70)]=(function(o)return l[(864/0x90)]()end),[(0x71+-112)]=(function(o)local b=l[(39-0x21)]()local l=''local o=1 for h=1,#b do o=(o+H)%k l=G(l,y((v(b:sub(h,h))+o)%O))end return l end)};for l=f,l[(23+-0x16)]()do h[l-f]=J();end;B[3]=l[(0x68-102)]();local o=l[(0x4c+-75)]()for o=1,o do local l=l[(-0x68+106)]();local h;local l=O[l%(134-0x80)];b[o]=l and l({});end;for B=1,l[(0x41+-64)]()do local o=l[(168/0x54)]();if(l[(94+(-0x2652/109))](o,e,f)==u)then local k=l[(67+-0x3f)](o,c,S);local h=l[(52-0x30)](o,D,c+D);local o={l[((0x15c-228)+-117)](),l[(624/0xd0)](),nil,nil};local O={[(26+-0x1a)]=function()o[p]=l[(0x4a-(226-0x9b))]();o[C]=l[(0x22b/185)]();end,[(60/0x3c)]=function()o[d]=l[(74-0x49)]();end,[(314/0x9d)]=function()o[d]=l[(41+(29+-0x45))]()-(c^s)end,[(0x24f/197)]=function()o[P]=l[(-18+0x13)]()-(c^s)o[t]=l[(78+-0x4b)]();end};O[k]();if(l[((-111+0x34f)/184)](h,f,e)==f)then o[m]=b[o[n]]end if(l[(0x10/4)](h,c,c)==e)then o[a]=b[o[P]]end if(l[(32-0x1c)](h,S,S)==f)then o[C]=b[o[U]]end M[B]=o;end end;return B;end;local function s(l,N,D)local x=l[c];local o=l[S];local l=l[e];return(function(...)local k=o;local g=Q('#',...)-f;local u={};local v={};local b={};local O=l;local j=x;local S=Y local o=e;local l=e l*=-1 local x=l;local y={...};for l=0,g do if(l>=k)then v[l-k]=y[l+f];else b[l]=y[l+e];end;end;local g=g-k+e local l;local k;while true do l=O[o];k=l[(21-0x14)];h=(977820)while k<=(0x84+-62)do h-= h h=(6515145)while(164-0x82)>=k do h-= h h=(1227132)while(1520/0x5f)>=k do h-= h h=(1722940)while k<=(120+-0x71)do h-= h h=(3021213)while(462/0x9a)>=k do h-= h h=(371036)while k<=(118+-0x75)do h-= h h=(1430283)while(0x43+-67)<k do h-= h b[l[M]]=#b[l[r]];break end while(h)/((3045-0x624))==971 do local k;local h;b[l[L]]=b[l[F]][l[_]];o=o+e;l=O[o];b[l[B]]=b[l[d]][l[C]];o=o+e;l=O[o];h=l[M];k=b[l[a]];b[h+1]=k;b[h]=k[l[t]];o=o+e;l=O[o];b[l[B]]=l[d];o=o+e;l=O[o];b[l[m]]=N[l[d]];o=o+e;l=O[o];b[l[L]]=b[l[P]][l[_]];o=o+e;l=O[o];b[l[n]]=b[l[F]][l[w]];o=o+e;l=O[o];b[l[M]]=b[l[d]][l[C]];o=o+e;l=O[o];h=l[H]b[h](K(b,h+f,l[F]))o=o+e;l=O[o];o=l[a];break end;break;end while 218==(h)/((-49+0x6d7))do h=(535146)while(0x11e/143)<k do h-= h local l={b,l};l[f][l[c][M]]=l[e][l[c][i]]+l[f][l[c][d]];break end while(h)/(((0x125d+-93)-2350))==237 do if(b[l[B]]~=b[l[t]])then o=o+f;else o=l[a];end;break end;break;end break;end while(h)/((317746/0xf2))==2301 do h=(2704458)while k<=(945/0xbd)do h-= h h=(657620)while k>(288/0x48)do h-= h b[l[B]]=(l[d]~=0);break end while(h)/((2724-0x586))==502 do local k;local h;N[l[P]]=b[l[M]];o=o+e;l=O[o];b[l[B]]=D[l[F]];o=o+e;l=O[o];h=l[L];k=b[l[a]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[L]]=l[a];o=o+e;l=O[o];h=l[L]b[h]=b[h](K(b,h+e,l[a]))o=o+e;l=O[o];h=l[B];k=b[l[d]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[L]]=l[r];o=o+e;l=O[o];b[l[H]]={};o=o+e;l=O[o];b[l[m]][l[F]]=l[C];o=o+e;l=O[o];b[l[n]][l[F]]=l[_];o=o+e;l=O[o];b[l[L]][l[P]]=l[w];o=o+e;l=O[o];h=l[M]b[h](K(b,h+f,l[d]))break end;break;end while 2103==(h)/((46296/(-112+0x94)))do h=(408480)while k>(0x20-26)do h-= h N[l[r]]=b[l[m]];break end while 2760==(h)/((341-(17756/0x5c)))do local k=j[l[a]];local e;local h={};e=V({},{__index=function(o,l)local l=h[l];return l[1][l[2]];end,__newindex=function(b,l,o)local l=h[l]l[1][l[2]]=o;end;});for e=1,l[t]do o=o+f;local l=O[o];if l[(0x66-101)]==79 then h[e-1]={b,l[P]};else h[e-1]={N,l[r]};end;u[#u+1]=h;end;b[l[n]]=s(k,e,D);break end;break;end break;end break;end while(h)/((0x471-583))==3110 do h=(935594)while(140-(307-0xb2))>=k do h-= h h=(171448)while k<=(41-0x20)do h-= h h=(7486128)while k>(0x28-32)do h-= h local k;local h;h=l[H];k=b[l[a]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[B]]=l[a];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[p]))o=o+e;l=O[o];b[l[L]]=b[l[p]][l[t]];o=o+e;l=O[o];h=l[H];k=b[l[a]];b[h+1]=k;b[h]=k[l[U]];break end while 2322==(h)/((6495-0xcc7))do b[l[n]]();break end;break;end while(h)/((0xbf-133))==2956 do h=(8083354)while(2550/0xff)<k do h-= h b[l[L]]={};break end while(h)/((7293-0xe6e))==2246 do local k;local h;b[l[M]]=b[l[r]][l[t]];o=o+e;l=O[o];b[l[H]]=b[l[d]][l[w]];o=o+e;l=O[o];h=l[m];k=b[l[F]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[H]]=l[p];o=o+e;l=O[o];b[l[L]]=N[l[d]];o=o+e;l=O[o];b[l[B]]=b[l[p]][l[C]];o=o+e;l=O[o];h=l[B];k=b[l[P]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[L]]=l[P];o=o+e;l=O[o];h=l[L]b[h]=b[h](K(b,h+e,l[P]))o=o+e;l=O[o];b[l[m]]=b[l[F]][l[i]];o=o+e;l=O[o];b[l[n]]=l[d];o=o+e;l=O[o];h=l[B]b[h](K(b,h+f,l[p]))o=o+e;l=O[o];o=l[a];break end;break;end break;end while(h)/((975-0x1f6))==1978 do h=(928445)while k<=(0x8bc/172)do h-= h h=(2506740)while k>(74-0x3e)do h-= h local h=l[m];local O=b[h+2];local e=b[h]+O;b[h]=e;if(O>0)then if(e<=b[h+1])then o=l[r];b[h+3]=e;end elseif(e>=b[h+1])then o=l[P];b[h+3]=e;end break end while(h)/((8217-0x102d))==615 do local h;local a;local k;b[l[B]]=b[l[F]][l[_]];o=o+e;l=O[o];b[l[B]]=b[l[p]][l[i]];o=o+e;l=O[o];k=l[L];a=b[l[d]];b[k+1]=a;b[k]=a[l[t]];o=o+e;l=O[o];b[l[B]]=l[r];o=o+e;l=O[o];b[l[H]]=N[l[F]];o=o+e;l=O[o];b[l[B]]=b[l[r]][l[C]];o=o+e;l=O[o];b[l[M]]=b[l[d]][l[t]];o=o+e;l=O[o];b[l[H]]=b[l[p]][l[_]];o=o+e;l=O[o];b[l[H]]=N[l[p]];o=o+e;l=O[o];b[l[n]]=b[l[r]][l[_]];o=o+e;l=O[o];b[l[m]]=b[l[p]][l[U]];o=o+e;l=O[o];b[l[m]]=b[l[r]][l[w]];o=o+e;l=O[o];b[l[H]]=D[l[P]];o=o+e;l=O[o];b[l[L]]=b[l[r]]*b[l[i]];o=o+e;l=O[o];h={b,l};h[f][h[c][n]]=h[e][h[c][i]]+h[f][h[c][F]];o=o+e;l=O[o];b[l[m]]=l[P];o=o+e;l=O[o];k=l[B]b[k](K(b,k+f,l[P]))o=o+e;l=O[o];o=l[P];break end;break;end while 1435==(h)/((0x9a2b/61))do h=(11270464)while k<=(3164/0xe2)do h-= h if b[l[B]]then o=o+e;else o=l[d];end;break;end while 3076==(h)/((0x1d12-(0x1d98-3798)))do h=(6971607)while(84-0x45)<k do h-= h local k;local h;b[l[B]]=b[l[d]][l[i]];o=o+e;l=O[o];h=l[L];k=b[l[F]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[n]]=b[l[a]][l[i]];o=o+e;l=O[o];h=l[m]b[h]=b[h](K(b,h+e,l[p]))o=o+e;l=O[o];if(b[l[m]]==l[U])then o=o+f;else o=l[p];end;break end while(h)/((-0x25+3490))==2019 do local o=l[n]b[o](K(b,o+f,l[p]))break end;break;end break;end break;end break;end break;end while(h)/(((0x3ca-515)+-99))==3447 do h=(4946918)while(6275/0xfb)>=k do h-= h h=(3504625)while k<=(0x8e+-122)do h-= h h=(116522)while k<=(3780/0xd2)do h-= h h=(4544138)while(2295/0x87)<k do h-= h local o=l[L]local h,l=S(b[o](K(b,o+1,l[F])))x=l+o-1 local l=0;for o=o,x do l=l+e;b[o]=h[l];end;break end while 1574==(h)/((5898-0xbc3))do local l=l[L];x=l+g-1;for o=l,x do local l=v[o-l];b[o]=l;end;break end;break;end while(h)/((2490-0x515))==98 do h=(9833920)while(-0x24+55)<k do h-= h local l=l[n];local o=b[l];for l=l+1,x do A(o,b[l])end;break end while 3160==(h)/((6306-0xc7a))do do return end;break end;break;end break;end while(h)/((0x14c8-2675))==1325 do h=(3394493)while(0x948/108)>=k do h-= h h=(5854880)while(137-0x74)<k do h-= h local P=j[l[a]];local k;local h={};k=V({},{__index=function(o,l)local l=h[l];return l[1][l[2]];end,__newindex=function(b,l,o)local l=h[l]l[1][l[2]]=o;end;});for e=1,l[i]do o=o+f;local l=O[o];if l[(0x4a+-73)]==79 then h[e-1]={b,l[d]};else h[e-1]={N,l[d]};end;u[#u+1]=h;end;b[l[B]]=s(P,k,D);break end while(h)/((0xbafcc/225))==1720 do D[l[P]]=b[l[n]];break end;break;end while(h)/((0x747-982))==3853 do h=(14621040)while k<=(2369/0x67)do h-= h if b[l[M]]then o=o+e;else o=l[d];end;break;end while(h)/((-0x76+3898))==3868 do h=(227126)while(169-(2030/0xe))<k do h-= h b[l[L]][l[P]]=b[l[i]];break end while(h)/((2744+-0x67))==86 do local k;local h;b[l[B]]=b[l[P]][l[w]];o=o+e;l=O[o];b[l[n]]=b[l[p]][l[i]];o=o+e;l=O[o];h=l[M];k=b[l[P]];b[h+1]=k;b[h]=k[l[C]];o=o+e;l=O[o];b[l[n]]=l[p];o=o+e;l=O[o];b[l[L]]=N[l[d]];o=o+e;l=O[o];b[l[H]]=b[l[p]][l[U]];o=o+e;l=O[o];b[l[m]]=b[l[F]][l[t]];o=o+e;l=O[o];b[l[H]]=b[l[p]][l[_]];o=o+e;l=O[o];h=l[m]b[h](K(b,h+f,l[P]))o=o+e;l=O[o];o=l[F];break end;break;end break;end break;end break;end while(h)/((0x2854f/(0x275a/138)))==2186 do h=(2394576)while k<=(-0x45+98)do h-= h h=(1294850)while k<=(150-0x7b)do h-= h h=(3512663)while(0xac-146)<k do h-= h local h=l[M]local O={b[h](K(b,h+1,x))};local o=0;for l=h,l[U]do o=o+e;b[l]=O[o];end break end while 1463==(h)/((302526/0x7e))do if(b[l[L]]~=l[U])then o=o+f;else o=l[a];end;break end;break;end while(h)/(((0x8a0dcc/50)/77))==551 do h=(345939)while(0x32+-22)<k do h-= h local h;b[l[n]]=l[d];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[d]))o=o+e;l=O[o];for l=l[M],l[a]do b[l]=nil;end;o=o+e;l=O[o];b[l[L]]=D[l[r]];o=o+e;l=O[o];b[l[B]]=D[l[d]];o=o+e;l=O[o];h=l[M]b[h]=b[h](b[h+f])o=o+e;l=O[o];b[l[m]]=b[l[P]][l[w]];o=o+e;l=O[o];b[l[n]]=D[l[a]];o=o+e;l=O[o];b[l[M]]=b[l[a]];o=o+e;l=O[o];b[l[H]]=(l[P]~=0);break end while(h)/((0x97b9/107))==953 do local L;local k;local M;local h;b[l[H]]=D[l[a]];o=o+e;l=O[o];b[l[H]]=b[l[P]][l[i]];o=o+e;l=O[o];h=l[H];M=b[l[P]];b[h+1]=M;b[h]=M[l[U]];o=o+e;l=O[o];b[l[B]]=b[l[p]];o=o+e;l=O[o];b[l[n]]=b[l[a]];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[F]))o=o+e;l=O[o];h=l[B];M=b[l[r]];b[h+1]=M;b[h]=M[l[w]];o=o+e;l=O[o];h=l[m]b[h]=b[h](b[h+f])o=o+e;l=O[o];k={b,l};k[f][k[c][B]]=k[e][k[c][t]]+k[f][k[c][d]];o=o+e;l=O[o];b[l[H]]=b[l[p]]%l[_];o=o+e;l=O[o];h=l[n]b[h]=b[h](b[h+f])o=o+e;l=O[o];M=l[P];L=b[M]for l=M+1,l[w]do L=L..b[l];end;b[l[m]]=L;o=o+e;l=O[o];k={b,l};k[f][k[c][H]]=k[e][k[c][U]]+k[f][k[c][p]];o=o+e;l=O[o];b[l[H]]=b[l[a]]%l[t];break end;break;end break;end while(h)/((137862/0x6f))==1928 do h=(8944876)while k<=(0x63-68)do h-= h h=(3435132)while k>(170-0x8c)do h-= h local o=l[B]local h,l=S(b[o](K(b,o+1,l[a])))x=l+o-1 local l=0;for o=o,x do l=l+e;b[o]=h[l];end;break end while(h)/((1819-0x3ac))==3908 do do return b[l[M]]end break end;break;end while(h)/((6834-0xd8e))==2659 do h=(4915274)while(0xae-142)>=k do h-= h if(b[l[B]]==l[C])then o=o+f;else o=l[P];end;break;end while(h)/(((-0x16+-50)+1541))==3346 do h=(5081788)while k>(1023/0x1f)do h-= h b[l[H]]=b[l[d]]%l[C];break end while 1412==(h)/((525454/0x92))do local h;b[l[B]]=D[l[p]];o=o+e;l=O[o];h=l[M]b[h]=b[h](b[h+f])o=o+e;l=O[o];b[l[m]]=b[l[r]][l[t]];o=o+e;l=O[o];b[l[L]]=D[l[a]];o=o+e;l=O[o];b[l[L]]=b[l[p]];o=o+e;l=O[o];b[l[m]]=(l[r]~=0);o=o+e;l=O[o];h=l[M]b[h](K(b,h+f,l[r]))o=o+e;l=O[o];b[l[M]]=D[l[p]];break end;break;end break;end break;end break;end break;end break;end while(h)/((0xf30-1953))==3367 do h=(402094)while(11856/(38304/0xa8))>=k do h-= h h=(3407809)while(118-(0xb1+-102))>=k do h-= h h=(953580)while(0xc8-(0x16e-204))>=k do h-= h h=(2017598)while k<=(0x3cc/27)do h-= h h=(4787132)while k>(86+-0x33)do h-= h local k;local h;h=l[H];k=b[l[r]];b[h+1]=k;b[h]=k[l[U]];o=o+e;l=O[o];b[l[B]]=l[d];o=o+e;l=O[o];h=l[L]b[h]=b[h](K(b,h+e,l[P]))o=o+e;l=O[o];h=l[B];k=b[l[d]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[M]]=l[P];o=o+e;l=O[o];b[l[M]]={};o=o+e;l=O[o];b[l[m]][l[p]]=l[t];o=o+e;l=O[o];b[l[M]][l[d]]=l[U];o=o+e;l=O[o];b[l[H]][l[F]]=l[U];o=o+e;l=O[o];h=l[M]b[h](K(b,h+f,l[a]))break end while(h)/((2599+-0x6b))==1921 do local h;local k;local B,F;local m;local h;for l=l[n],l[P]do b[l]=nil;end;o=o+e;l=O[o];b[l[n]]=D[l[P]];o=o+e;l=O[o];b[l[n]]=b[l[p]][l[t]];o=o+e;l=O[o];h=l[L];m=b[l[P]];b[h+1]=m;b[h]=m[l[t]];o=o+e;l=O[o];h=l[H]B,F=S(b[h](b[h+f]))x=F+h-e k=0;for l=h,x do k=k+e;b[l]=B[k];end;o=o+e;l=O[o];h=l[M]B={b[h](K(b,h+1,x))};k=0;for l=h,l[_]do k=k+e;b[l]=B[k];end o=o+e;l=O[o];o=l[d];break end;break;end while 3443==(h)/((0x4f1-679))do h=(1656450)while k>(0x7a-85)do h-= h b[l[H]]=b[l[P]]-b[l[t]];break end while 405==(h)/((895710/0xdb))do local k;local h;b[l[n]]=b[l[F]][l[t]];o=o+e;l=O[o];b[l[M]]=b[l[r]][l[C]];o=o+e;l=O[o];h=l[m];k=b[l[F]];b[h+1]=k;b[h]=k[l[U]];o=o+e;l=O[o];b[l[n]]=l[p];o=o+e;l=O[o];b[l[B]]=N[l[a]];o=o+e;l=O[o];b[l[M]]=b[l[P]][l[t]];o=o+e;l=O[o];h=l[m];k=b[l[d]];b[h+1]=k;b[h]=k[l[C]];o=o+e;l=O[o];b[l[M]]=l[F];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[F]))o=o+e;l=O[o];b[l[M]]=b[l[p]][l[U]];o=o+e;l=O[o];h=l[M]b[h](K(b,h+f,l[P]))break end;break;end break;end while(h)/((0x219+-77))==2073 do h=(44304)while k<=(9440/0xec)do h-= h h=(949095)while k>(4680/0x78)do h-= h local h=l[L];local e=b[h]local O=b[h+2];if(O>0)then if(e>b[h+1])then o=l[a];else b[h+3]=e;end elseif(e<b[h+1])then o=l[a];else b[h+3]=e;end break end while(h)/((0x17fd-3128))==315 do local k;local h;b[l[B]]=b[l[a]][l[U]];o=o+e;l=O[o];h=l[L];k=b[l[p]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[n]]=l[d];o=o+e;l=O[o];h=l[m]b[h]=b[h](K(b,h+e,l[d]))o=o+e;l=O[o];if not b[l[H]]then o=o+f;else o=l[d];end;break end;break;end while 156==(h)/((0x19a+-126))do h=(1209887)while(0x98-(0x13e-207))>=k do h-= h b[l[M]]=(l[F]~=0);break;end while 563==(h)/((4363-0x8a6))do h=(3430584)while k>(164+-0x7a)do h-= h local k;local h;h=l[H]b[h](K(b,h+f,l[p]))o=o+e;l=O[o];b[l[m]]=D[l[F]];o=o+e;l=O[o];h=l[m];k=b[l[F]];b[h+1]=k;b[h]=k[l[_]];o=o+e;l=O[o];b[l[H]]=l[F];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[P]))o=o+e;l=O[o];b[l[L]]=b[l[a]][l[C]];o=o+e;l=O[o];h=l[H];k=b[l[d]];b[h+1]=k;b[h]=k[l[w]];break end while 1044==(h)/((0x19e3-3341))do local B;local k;local h;b[l[n]]=D[l[d]];o=o+e;l=O[o];h=l[H];k=b[l[r]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[H]]=l[p];o=o+e;l=O[o];h=l[H]b[h]=b[h](K(b,h+e,l[F]))o=o+e;l=O[o];h=l[n];k=b[l[p]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[m]]=l[d];o=o+e;l=O[o];b[l[m]]={};o=o+e;l=O[o];b[l[H]][l[F]]=l[w];o=o+e;l=O[o];b[l[M]]=l[r];o=o+e;l=O[o];b[l[n]]=b[l[a]][l[C]];o=o+e;l=O[o];b[l[L]]=l[d];o=o+e;l=O[o];k=l[F];B=b[k]for l=k+1,l[U]do B=B..b[l];end;b[l[m]]=B;o=o+e;l=O[o];b[l[m]][l[P]]=b[l[i]];o=o+e;l=O[o];b[l[L]][l[P]]=l[i];o=o+e;l=O[o];h=l[H]b[h](K(b,h+f,l[r]))o=o+e;l=O[o];o=l[d];break end;break;end break;end break;end break;end while(h)/((0x2c3ad/95))==1787 do h=(10246911)while k<=(135+-0x58)do h-= h h=(7670143)while k<=(0x762/42)do h-= h h=(2653996)while(0x420/24)<k do h-= h local k;local h;b[l[L]]=b[l[F]][l[i]];o=o+e;l=O[o];b[l[L]]=b[l[r]][l[i]];o=o+e;l=O[o];h=l[n];k=b[l[p]];b[h+1]=k;b[h]=k[l[C]];o=o+e;l=O[o];b[l[B]]=l[p];o=o+e;l=O[o];b[l[m]]=N[l[p]];o=o+e;l=O[o];b[l[n]]=b[l[P]][l[C]];o=o+e;l=O[o];b[l[n]]=b[l[F]][l[U]];o=o+e;l=O[o];b[l[H]]=b[l[p]][l[w]];o=o+e;l=O[o];h=l[L]b[h](K(b,h+f,l[p]))o=o+e;l=O[o];o=l[P];break end while 3572==(h)/((0x5fc-789))do N[l[r]]=b[l[m]];break end;break;end while 3533==(h)/((0x106e5/31))do h=(2072136)while(0xbd-143)<k do h-= h local h=l[d];local o=b[h]for l=h+1,l[w]do o=o..b[l];end;b[l[H]]=o;break end while 1837==(h)/(((183372/0x94)+-0x6f))do b[l[m]][l[F]]=b[l[t]];break end;break;end break;end while(h)/((137436/0x34))==3877 do h=(3423496)while k<=(0x9a+(-21420/0xcc))do h-= h h=(164955)while(123+-0x4b)<k do h-= h b[l[n]]=b[l[a]]*b[l[U]];break end while 1571==(h)/((170+-0x41))do local h=l[H];local k=l[t];local O=h+2 local h={b[h](b[h+1],b[O])};for l=1,k do b[O+l]=h[l];end;local h=h[1]if h then b[O]=h o=l[d];else o=o+e;end;break end;break;end while 3838==(h)/((0x3f6+(-6832/0x38)))do h=(4137126)while k<=(0x77-69)do h-= h b[l[M]][b[l[a]]]=b[l[w]];break;end while 2877==(h)/((-0x44+(0x30888/132)))do h=(414675)while(157+-0x6a)<k do h-= h b[l[L]]=b[l[p]];break end while(h)/((66690/0x4e))==485 do local o=l[B]b[o]=b[o](K(b,o+e,l[r]))break end;break;end break;end break;end break;end break;end while 154==(h)/((0x1483-2640))do h=(1192304)while k<=(-0x2b+104)do h-= h h=(7570744)while k<=(0xc8-144)do h-= h h=(14346040)while(0xac-118)>=k do h-= h h=(8287989)while((0x2dfc/54)-165)<k do h-= h local h=l[P];local o=b[h]for l=h+1,l[t]do o=o..b[l];end;b[l[L]]=o;break end while(h)/((6865-(-109+0xe03)))==2447 do b[l[B]]=N[l[d]];break end;break;end while 3551==(h)/((0x1fe8-4128))do h=(8045610)while(-47+0x66)<k do h-= h local l=l[B];do return b[l](K(b,l+1,x))end;break end while 3595==(h)/((275274/0x7b))do do return end;break end;break;end break;end while 2228==(h)/((676202/0xc7))do h=(6985980)while((-63-0x17)+144)>=k do h-= h h=(2995995)while k>(0x34c5/237)do h-= h D[l[r]]=b[l[L]];o=o+e;l=O[o];b[l[m]]={};o=o+e;l=O[o];b[l[B]]={};o=o+e;l=O[o];D[l[P]]=b[l[L]];o=o+e;l=O[o];b[l[H]]=D[l[p]];o=o+e;l=O[o];if(b[l[M]]==l[i])then o=o+f;else o=l[P];end;break end while 1137==(h)/((0x6a257/165))do b[l[L]]=s(j[l[F]],nil,D);break end;break;end while(h)/((0x1208-2333))==3060 do h=(3916302)while(186+-0x7f)>=k do h-= h o=l[p];break;end while 962==(h)/((500733/0x7b))do h=(11975439)while(12480/0xd0)<k do h-= h local l=l[M]b[l](b[l+f])break end while(h)/((0x71dab/159))==4083 do local k;local h;b[l[B]]=b[l[d]][l[U]];o=o+e;l=O[o];h=l[H];k=b[l[p]];b[h+1]=k;b[h]=k[l[_]];o=o+e;l=O[o];b[l[M]]=l[p];o=o+e;l=O[o];h=l[n]b[h]=b[h](K(b,h+e,l[F]))o=o+e;l=O[o];if b[l[m]]then o=o+e;else o=l[r];end;break end;break;end break;end break;end break;end while 688==(h)/((3556-(0xe90-1905)))do h=(4937485)while k<=(0x21c5/133)do h-= h h=(147506)while k<=(9639/0x99)do h-= h h=(57122)while(78+(-43+0x1b))<k do h-= h local l=l[B];x=l+g-1;for o=l,x do local l=v[o-l];b[o]=l;end;break end while(h)/((0xbc+-19))==338 do if not b[l[M]]then o=o+f;else o=l[P];end;break end;break;end while(h)/((0x4ac6/17))==131 do h=(6175365)while k>(134+-0x46)do h-= h b[l[B]]=l[P];break end while 1713==(h)/((0xe70+-91))do local h;local k;local a,c;local p;local h;b[l[B]]=D[l[d]];o=o+e;l=O[o];b[l[B]]=D[l[r]];o=o+e;l=O[o];b[l[L]]=b[l[d]][l[U]];o=o+e;l=O[o];h=l[n];p=b[l[r]];b[h+1]=p;b[h]=p[l[t]];o=o+e;l=O[o];b[l[M]]=D[l[F]];o=o+e;l=O[o];b[l[M]]=b[l[d]][l[C]];o=o+e;l=O[o];b[l[H]]=N[l[r]];o=o+e;l=O[o];h=l[M];p=b[l[F]];b[h+1]=p;b[h]=p[l[C]];o=o+e;l=O[o];h=l[B]b[h]=b[h](b[h+f])o=o+e;l=O[o];b[l[m]]=b[l[d]][l[_]];o=o+e;l=O[o];b[l[M]]=b[l[P]][l[w]];o=o+e;l=O[o];b[l[M]]=N[l[d]];o=o+e;l=O[o];h=l[H];p=b[l[P]];b[h+1]=p;b[h]=p[l[_]];o=o+e;l=O[o];h=l[H]b[h]=b[h](b[h+f])o=o+e;l=O[o];b[l[B]]=b[l[r]][l[_]];o=o+e;l=O[o];b[l[m]]=b[l[P]][l[U]];o=o+e;l=O[o];h=l[B]a,c=S(b[h](K(b,h+1,l[P])))x=c+h-1 k=0;for l=h,x do k=k+e;b[l]=a[k];end;o=o+e;l=O[o];h=l[M]a,c=S(b[h](K(b,h+e,x)))x=c+h-f k=0;for l=h,x do k=k+e;b[l]=a[k];end;o=o+e;l=O[o];h=l[n]a={b[h](K(b,h+1,x))};k=0;for l=h,l[U]do k=k+e;b[l]=a[k];end o=o+e;l=O[o];o=l[P];break end;break;end break;end while(h)/((5854-0xb9f))==1715 do h=(116280)while(0xde-155)>=k do h-= h h=(2098944)while k>(244-0xb2)do h-= h for l=l[m],l[d]do b[l]=nil;end;break end while 1152==(h)/((0x6ac20/240))do local h=l[L];local o=b[l[F]];b[h+1]=o;b[h]=o[l[_]];break end;break;end while 190==(h)/((0x518-692))do h=(7053948)while k<=(-0x6a+174)do h-= h if(b[l[m]]==l[C])then o=o+f;else o=l[F];end;break;end while 3102==(h)/((4629-0x933))do h=(4938808)while k>(-0x25+106)do h-= h do return b[l[B]]end break end while(h)/((0x51d58/143))==2107 do local l=l[n]local h,o=S(b[l](K(b,l+e,x)))x=o+l-f local o=0;for l=l,x do o=o+e;b[l]=h[o];end;break end;break;end break;end break;end break;end break;end break;end break;end while(h)/((2596-(1389+-0x53)))==758 do h=(8462220)while k<=(-0x39+162)do h-= h h=(344458)while(5133/0x3b)>=k do h-= h h=(2820976)while k<=(0x25c8/124)do h-= h h=(1125540)while(11248/0x98)>=k do h-= h h=(7373737)while(9432/0x83)>=k do h-= h h=(479007)while(4899/0x45)<k do h-= h local k;local h;b[l[H]]=b[l[r]][l[w]];o=o+e;l=O[o];h=l[H];k=b[l[F]];b[h+1]=k;b[h]=k[l[C]];o=o+e;l=O[o];b[l[B]]=l[p];o=o+e;l=O[o];h=l[L]b[h]=b[h](K(b,h+e,l[F]))o=o+e;l=O[o];if not b[l[H]]then o=o+f;else o=l[P];end;break end while 157==(h)/((6118-0xbfb))do if(b[l[n]]==b[l[_]])then o=o+f;else o=l[F];end;break end;break;end while 3323==(h)/((2247+-0x1c))do h=(190593)while(203-0x82)<k do h-= h local l=l[n];do return K(b,l,x)end;break end while 351==(h)/((0x452-563))do local k;local h;h=l[M];k=b[l[r]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[m]]=l[r];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[F]))o=o+e;l=O[o];b[l[H]]=b[l[p]][l[_]];o=o+e;l=O[o];b[l[H]]=b[l[F]][l[_]];o=o+e;l=O[o];h=l[m];k=b[l[r]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];h=l[m]b[h](b[h+f])break end;break;end break;end while 666==(h)/((3489-0x707))do h=(7240239)while(0xa3+-87)>=k do h-= h h=(862070)while(0x100-181)<k do h-= h local l=l[H];do return K(b,l,x)end;break end while(h)/(((-0x13-23)+416))==2305 do local l=l[M]local h,o=S(b[l](b[l+f]))x=o+l-e local o=0;for l=l,x do o=o+e;b[l]=h[o];end;break end;break;end while 3537==(h)/((4216-0x879))do h=(255192)while((-54+0x4564)/230)<k do h-= h local O=l[L];local e={};for l=1,#u do local l=u[l];for o=0,#l do local l=l[o];local h=l[1];local o=l[2];if h==b and o>=O then e[o]=h[o];l[1]=e;end;end;end;break end while 98==(h)/((0x14a2-2678))do local h;local k;local M,H;local d;local h;b[l[B]]=b[l[P]][l[U]];o=o+e;l=O[o];h=l[L];d=b[l[a]];b[h+1]=d;b[h]=d[l[t]];o=o+e;l=O[o];h=l[L]M,H=S(b[h](b[h+f]))x=H+h-e k=0;for l=h,x do k=k+e;b[l]=M[k];end;o=o+e;l=O[o];h=l[n]M={b[h](K(b,h+1,x))};k=0;for l=h,l[w]do k=k+e;b[l]=M[k];end o=o+e;l=O[o];o=l[p];break end;break;end break;end break;end while 1256==(h)/((0x902+(-0x24+-24)))do h=(1817436)while(185-0x67)>=k do h-= h h=(167567)while k<=(0xe0-144)do h-= h h=(12249684)while k>(107+-0x1c)do h-= h local k;local h;b[l[m]]=b[l[a]][l[C]];o=o+e;l=O[o];h=l[n];k=b[l[p]];b[h+1]=k;b[h]=k[l[U]];o=o+e;l=O[o];b[l[L]]=l[F];o=o+e;l=O[o];h=l[M]b[h]=b[h](K(b,h+e,l[P]))o=o+e;l=O[o];if not b[l[H]]then o=o+f;else o=l[a];end;break end while(h)/((3393+-0x18))==3636 do b[l[M]]=b[l[P]];break end;break;end while 4087==(h)/((110-0x45))do h=(1661888)while(169+-0x58)<k do h-= h b[l[H]]=N[l[F]];o=o+e;l=O[o];b[l[M]]=#b[l[p]];o=o+e;l=O[o];N[l[p]]=b[l[L]];o=o+e;l=O[o];b[l[m]]=N[l[F]];o=o+e;l=O[o];b[l[m]]=#b[l[d]];o=o+e;l=O[o];N[l[P]]=b[l[M]];o=o+e;l=O[o];do return end;break end while 1129==(h)/((0x38c80/158))do for l=l[M],l[P]do b[l]=nil;end;break end;break;end break;end while(h)/((1281-0x2a5))==3009 do h=(6930424)while(19656/0xea)>=k do h-= h h=(1323035)while k>(-23+0x6a)do h-= h local f;local k;local h;b[l[L]]=l[d];o=o+e;l=O[o];b[l[M]]=l[F];o=o+e;l=O[o];b[l[L]]=#b[l[p]];o=o+e;l=O[o];b[l[M]]=l[p];o=o+e;l=O[o];h=l[m];k=b[h]f=b[h+2];if(f>0)then if(k>b[h+1])then o=l[p];else b[h+3]=k;end elseif(k<b[h+1])then o=l[d];else b[h+3]=k;end break end while 367==(h)/((771470/0xd6))do o=l[a];break end;break;end while 3112==(h)/((4504-0x8e5))do h=(7335340)while(-49+0x86)>=k do h-= h b[l[B]]=b[l[r]][b[l[w]]];break;end while 3530==(h)/((4283-0x89d))do h=(7620261)while k>(0xd2-124)do h-= h local l=l[m]local h,o=S(b[l](K(b,l+e,x)))x=o+l-f local o=0;for l=l,x do o=o+e;b[l]=h[o];end;break end while(h)/((0x14c3-2708))==2923 do local l=l[m]b[l](b[l+f])break end;break;end break;end break;end break;end break;end while 157==(h)/((-104+(0x91a+-32)))do h=(5110196)while((-61+0xde)+-0x41)>=k do h-= h h=(6022838)while k<=(-44+0x87)do h-= h h=(2390112)while k<=(-60+0x95)do h-= h h=(6204170)while(263-0xaf)<k do h-= h local k;local h;b[l[B]]=b[l[P]][l[C]];o=o+e;l=O[o];b[l[H]]=b[l[p]][l[t]];o=o+e;l=O[o];h=l[m];k=b[l[r]];b[h+1]=k;b[h]=k[l[U]];o=o+e;l=O[o];b[l[L]]=l[F];o=o+e;l=O[o];h=l[M]b[h](K(b,h+f,l[p]))break end while(h)/((2716+-0x56))==2359 do local h=l[n];local O=b[h+2];local e=b[h]+O;b[h]=e;if(O>0)then if(e<=b[h+1])then o=l[F];b[h+3]=e;end elseif(e>=b[h+1])then o=l[F];b[h+3]=e;end break end;break;end while 1376==(h)/((3520-(-123+0x772)))do h=(2046192)while(0xff-165)<k do h-= h local k;local h;b[l[B]]=b[l[d]][l[t]];o=o+e;l=O[o];b[l[n]]=b[l[F]][l[C]];o=o+e;l=O[o];h=l[M];k=b[l[d]];b[h+1]=k;b[h]=k[l[C]];o=o+e;l=O[o];b[l[H]]=l[a];o=o+e;l=O[o];b[l[H]]=N[l[d]];o=o+e;l=O[o];b[l[n]]=b[l[F]][l[U]];o=o+e;l=O[o];h=l[m];k=b[l[P]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[B]]=l[P];o=o+e;l=O[o];h=l[H]b[h]=b[h](K(b,h+e,l[a]))o=o+e;l=O[o];b[l[n]]=b[l[P]][l[_]];o=o+e;l=O[o];h=l[H]b[h](K(b,h+f,l[d]))break end while 2721==(h)/((-0x1e+782))do local k;local h;b[l[H]]=b[l[r]];o=o+e;l=O[o];h=l[M];x=h+g-1;for l=h,x do k=v[l-h];b[l]=k;end;o=o+e;l=O[o];h=l[m];do return b[h](K(b,h+1,x))end;o=o+e;l=O[o];h=l[L];do return K(b,h,x)end;o=o+e;l=O[o];do return end;break end;break;end break;end while(h)/(((-0x62+7220)/0x3))==2537 do h=(4103316)while(301-0xd0)>=k do h-= h h=(7378320)while k>(1748/(4731/0xf9))do h-= h local l=l[H];do return b[l](K(b,l+1,x))end;break end while 2598==(h)/((2941+-0x65))do local k;local h;h=l[M]b[h](K(b,h+f,l[a]))o=o+e;l=O[o];b[l[n]]=D[l[d]];o=o+e;l=O[o];h=l[m];k=b[l[a]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[L]]=l[d];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[p]))o=o+e;l=O[o];b[l[M]]=b[l[a]][l[t]];o=o+e;l=O[o];h=l[n];k=b[l[a]];b[h+1]=k;b[h]=k[l[_]];break end;break;end while(h)/((6944-0xdbc))==1197 do h=(4015648)while k<=(-0x61+191)do h-= h b[l[B]]=s(j[l[r]],nil,D);break;end while(h)/((10192/0x4))==1576 do h=(3120896)while k>(0x10f-176)do h-= h b[l[L]]=b[l[F]][l[i]];break end while(h)/((0x1290-2416))==1336 do local k;local h;b[l[m]]=b[l[P]][l[C]];o=o+e;l=O[o];h=l[L];k=b[l[P]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[B]]=l[P];o=o+e;l=O[o];h=l[m]b[h]=b[h](K(b,h+e,l[p]))o=o+e;l=O[o];if b[l[B]]then o=o+e;else o=l[d];end;break end;break;end break;end break;end break;end while(h)/((-0x32+1857))==2828 do h=(4580296)while(0x123-191)>=k do h-= h h=(3827317)while k<=(191+-0x5d)do h-= h h=(435162)while k>(248-0x97)do h-= h b[l[n]]=D[l[r]];break end while 1594==(h)/((-25+0x12a))do if(b[l[m]]~=b[l[w]])then o=o+f;else o=l[r];end;break end;break;end while 949==(h)/((8131-0x1002))do h=(6933676)while k>(0x117-(21780/0x79))do h-= h local l={b,l};l[f][l[c][L]]=l[e][l[c][i]]+l[f][l[c][P]];break end while(h)/((6007-0xbdb))==2333 do local k;local h;b[l[M]]=b[l[a]][l[U]];o=o+e;l=O[o];h=l[M];k=b[l[P]];b[h+1]=k;b[h]=k[l[_]];o=o+e;l=O[o];b[l[n]]=l[a];o=o+e;l=O[o];h=l[n]b[h]=b[h](K(b,h+e,l[p]))o=o+e;l=O[o];if b[l[L]]then o=o+e;else o=l[P];end;break end;break;end break;end while 1246==(h)/((0x1cff-3747))do h=(7792352)while k<=((-0x31+316)-165)do h-= h h=(12856344)while(0x4d54/196)<k do h-= h b[l[L]]=b[l[F]]%l[C];break end while 3928==(h)/((6631-0xd1e))do local l=l[M]local h,o=S(b[l](b[l+f]))x=o+l-e local o=0;for l=l,x do o=o+e;b[l]=h[o];end;break end;break;end while(h)/((6577-0xd11))==2411 do h=(4025403)while(302-0xc7)>=k do h-= h local k;local h;b[l[H]]=b[l[F]][l[U]];o=o+e;l=O[o];b[l[L]]=b[l[a]][l[_]];o=o+e;l=O[o];h=l[B];k=b[l[F]];b[h+1]=k;b[h]=k[l[U]];o=o+e;l=O[o];b[l[M]]=l[a];o=o+e;l=O[o];b[l[M]]=D[l[P]];o=o+e;l=O[o];h=l[B];k=b[l[d]];b[h+1]=k;b[h]=k[l[U]];o=o+e;l=O[o];b[l[L]]=l[a];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[p]))o=o+e;l=O[o];b[l[H]]=b[l[r]][l[i]];o=o+e;l=O[o];h=l[B];k=b[l[a]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];h=l[M]b[h]=b[h](b[h+f])o=o+e;l=O[o];b[l[M]]=b[l[d]][l[i]];o=o+e;l=O[o];b[l[m]]=b[l[P]][l[_]];o=o+e;l=O[o];b[l[B]]=l[a];o=o+e;l=O[o];h=l[L]b[h](K(b,h+f,l[a]))break;end while 1537==(h)/((0x14ea-2735))do h=(5100759)while(13416/0x81)<k do h-= h b[l[H]]=(l[d]~=0);o=o+f;break end while(h)/((104157/0x47))==3477 do local h=l[n];local k=l[w];local O=h+2 local h={b[h](b[h+1],b[O])};for l=1,k do b[O+l]=h[l];end;local h=h[1]if h then b[O]=h o=l[P];else o=o+e;end;break end;break;end break;end break;end break;end break;end break;end while(h)/((2594+(-0xb4+56)))==3426 do h=(128737)while k<=(356-0xe9)do h-= h h=(9277749)while(9804/0x56)>=k do h-= h h=(9408540)while(26487/0xf3)>=k do h-= h h=(617160)while(0x419f/157)>=k do h-= h h=(11210796)while k>(10282/0x61)do h-= h local l=l[H]b[l]=b[l](b[l+f])break end while(h)/((0xe02+-87))==3204 do local l=l[L]b[l]=b[l](b[l+f])break end;break;end while 444==(h)/((2896-0x5e2))do h=(15847299)while k>(326-0xda)do h-= h if not b[l[m]]then o=o+f;else o=l[r];end;break end while(h)/(((0x1704ac-754279)/185))==3887 do local k;local h;b[l[m]]=b[l[p]][l[C]];o=o+e;l=O[o];b[l[B]]=l[P];o=o+e;l=O[o];h=l[H]b[h]=b[h](b[h+f])o=o+e;l=O[o];b[l[M]][l[p]]=l[t];o=o+e;l=O[o];b[l[m]]=b[l[d]][l[t]];o=o+e;l=O[o];b[l[B]][l[d]]=b[l[_]];o=o+e;l=O[o];b[l[m]][l[P]]=l[_];o=o+e;l=O[o];b[l[H]][l[r]]=l[i];o=o+e;l=O[o];b[l[L]]=b[l[P]][l[i]];o=o+e;l=O[o];h=l[B];k=b[l[P]];b[h+1]=k;b[h]=k[l[_]];break end;break;end break;end while(h)/((456680/0xc4))==4038 do h=(1652546)while(0xff-144)>=k do h-= h h=(190393)while(20350/0xb9)<k do h-= h local l=l[H]b[l]=b[l]()break end while(h)/((14868/0x24))==461 do D[l[d]]=b[l[m]];break end;break;end while(h)/((0x16e3-2980))==574 do h=(2128230)while k<=((0x593f/67)-0xe5)do h-= h local l=l[L]b[l]=b[l]()break;end while(h)/((-34+0xb00))==765 do h=(882557)while(-62+0xaf)<k do h-= h local k;local h;h=l[n];k=b[l[P]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[n]]=l[d];o=o+e;l=O[o];h=l[M]b[h]=b[h](K(b,h+e,l[d]))o=o+e;l=O[o];b[l[n]]=b[l[r]][l[w]];o=o+e;l=O[o];b[l[M]]=b[l[p]][l[U]];o=o+e;l=O[o];b[l[M]]=D[l[d]];o=o+e;l=O[o];h=l[M];k=b[l[r]];b[h+1]=k;b[h]=k[l[_]];o=o+e;l=O[o];b[l[B]]=l[P];o=o+e;l=O[o];h=l[H]b[h]=b[h](K(b,h+e,l[P]))o=o+e;l=O[o];b[l[n]]=D[l[F]];break end while(h)/((801-(107272/0xfd)))==2341 do local o=l[M]b[o](K(b,o+f,l[p]))break end;break;end break;end break;end break;end while(h)/((7992-(0x1fc8-4131)))==2327 do h=(44772)while(15694/(0x34fe/102))>=k do h-= h h=(10445176)while k<=(0x4554/153)do h-= h h=(659886)while(0x564/(-85+0x61))<k do h-= h local l=l[B];local o=b[l];for l=l+1,x do A(o,b[l])end;break end while(h)/((0x824+-66))==327 do local k;local h;b[l[m]]=b[l[F]][l[U]];o=o+e;l=O[o];b[l[M]]=b[l[p]][l[t]];o=o+e;l=O[o];h=l[m];k=b[l[r]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[M]]=l[P];o=o+e;l=O[o];b[l[n]]=N[l[p]];o=o+e;l=O[o];b[l[n]]=b[l[F]][l[w]];o=o+e;l=O[o];h=l[n];k=b[l[a]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[B]]=l[F];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[d]))o=o+e;l=O[o];b[l[L]]=b[l[F]][l[_]];o=o+e;l=O[o];h=l[H]b[h](K(b,h+f,l[d]))break end;break;end while(h)/((0xa94f0/178))==2681 do h=(5637926)while(283-0xa6)<k do h-= h local k;local h;h=l[H];k=b[l[P]];b[h+1]=k;b[h]=k[l[w]];o=o+e;l=O[o];b[l[H]]=l[p];o=o+e;l=O[o];h=l[m]b[h]=b[h](K(b,h+e,l[a]))o=o+e;l=O[o];b[l[H]]=b[l[P]][l[w]];o=o+e;l=O[o];h=l[B];k=b[l[d]];b[h+1]=k;b[h]=k[l[t]];break end while 3962==(h)/((0xb6b-(1535+-0x23)))do local h=l[n]local O={b[h](K(b,h+1,x))};local o=0;for l=h,l[i]do o=o+e;b[l]=O[o];end break end;break;end break;end while 1092==(h)/((4387/0x6b))do h=(1545936)while k<=(0x104-(337-0xc5))do h-= h h=(5785533)while(225+-0x6a)<k do h-= h local k;local h;b[l[M]]();o=o+e;l=O[o];b[l[H]]=D[l[a]];o=o+e;l=O[o];h=l[B];k=b[l[p]];b[h+1]=k;b[h]=k[l[_]];o=o+e;l=O[o];b[l[m]]=l[F];o=o+e;l=O[o];h=l[H]b[h]=b[h](K(b,h+e,l[F]))o=o+e;l=O[o];b[l[H]]=b[l[a]][l[C]];o=o+e;l=O[o];if(b[l[L]]==l[U])then o=o+f;else o=l[F];end;break end while 1431==(h)/((0xe7f59/235))do local k;local h;b[l[m]]=b[l[F]][l[i]];o=o+e;l=O[o];h=l[B];k=b[l[F]];b[h+1]=k;b[h]=k[l[_]];o=o+e;l=O[o];b[l[L]]=l[d];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[d]))o=o+e;l=O[o];if b[l[L]]then o=o+e;else o=l[P];end;break end;break;end while 688==(h)/(((-177+0x41)+2359))do h=(4425552)while k<=(337-0xd8)do h-= h b[l[M]]={};break;end while 2628==(h)/((193660/0x73))do h=(317275)while(0x5366/175)<k do h-= h local h=l[M];local o=b[l[p]];b[h+1]=o;b[h]=o[l[i]];break end while(h)/((-62+(850-0x1bd)))==925 do b[l[H]]=N[l[r]];break end;break;end break;end break;end break;end break;end while(h)/((-41+0x9a6))==53 do h=(4769614)while(0xa1+-29)>=k do h-= h h=(9200535)while(324-0xc5)>=k do h-= h h=(2639805)while(-0x66+227)>=k do h-= h h=(1304948)while k>(202+(-0x79e/25))do h-= h local k;local h;h=l[L];k=b[l[r]];b[h+1]=k;b[h]=k[l[_]];o=o+e;l=O[o];b[l[m]]=l[P];o=o+e;l=O[o];h=l[B]b[h]=b[h](K(b,h+e,l[p]))o=o+e;l=O[o];b[l[m]]=b[l[F]][l[w]];o=o+e;l=O[o];b[l[M]]=b[l[a]][l[_]];o=o+e;l=O[o];if not b[l[B]]then o=o+f;else o=l[r];end;break end while 436==(h)/((0x10ce7/23))do b[l[B]]=l[a];break end;break;end while 4055==(h)/((1333-0x2aa))do h=(826260)while k>(0x189c/50)do h-= h local k;local h;b[l[M]]=b[l[p]][l[w]];o=o+e;l=O[o];h=l[L];k=b[l[d]];b[h+1]=k;b[h]=k[l[i]];o=o+e;l=O[o];b[l[H]]=l[r];o=o+e;l=O[o];h=l[M]b[h]=b[h](K(b,h+e,l[a]))o=o+e;l=O[o];if not b[l[B]]then o=o+f;else o=l[r];end;break end while 1172==(h)/((826+-0x79))do b[l[H]][l[F]]=l[i];break end;break;end break;end while 2445==(h)/((0xeee+-59))do h=(298980)while(15996/0x7c)>=k do h-= h h=(3308396)while k>(293-0xa5)do h-= h b[l[B]]=(l[P]~=0);o=o+f;break end while 1586==(h)/((2125+-0x27))do b[l[m]]=b[l[d]][l[t]];break end;break;end while(h)/((1687+-0x1a))==180 do h=(5839821)while k<=(244+-0x72)do h-= h b[l[M]]=b[l[P]]-b[l[t]];break;end while 2223==(h)/((-0x79+2748))do h=(11356756)while(0x130-173)<k do h-= h b[l[m]]=D[l[d]];break end while 2774==(h)/((0x46f72/(0xa8-97)))do b[l[B]]=#b[l[F]];break end;break;end break;end break;end break;end while(h)/((0x9ce-1317))==3998 do h=(4418263)while k<=(336-(488-0x120))do h-= h h=(14111)while(-0x7c+258)>=k do h-= h h=(1923636)while(0x153-206)<k do h-= h if(b[l[n]]~=l[C])then o=o+f;else o=l[P];end;break end while 1254==(h)/((3097-0x61b))do b[l[B]][b[l[p]]]=b[l[w]];break end;break;end while(h)/((274/0x2))==103 do h=(1340444)while(303-0xa8)<k do h-= h local h=l[L];local e=b[h]local O=b[h+2];if(O>0)then if(e>b[h+1])then o=l[a];else b[h+3]=e;end elseif(e<b[h+1])then o=l[p];else b[h+3]=e;end break end while(h)/((1985+-0x1f))==686 do local O=l[H];local h={};for l=1,#u do local l=u[l];for o=0,#l do local l=l[o];local e=l[1];local o=l[2];if e==b and o>=O then h[o]=e[o];l[1]=h;end;end;end;break end;break;end break;end while(h)/((-0x6a+1743))==2699 do h=(2627814)while(0x14d-195)>=k do h-= h h=(14020028)while k>(-0x12+155)do h-= h local o=l[L]b[o]=b[o](K(b,o+e,l[F]))break end while 3839==(h)/((0xaa4bc/191))do b[l[H]]();break end;break;end while(h)/((304584/0xc4))==1691 do h=(11423500)while(-0x63+238)>=k do h-= h if(b[l[B]]==b[l[w]])then o=o+f;else o=l[d];end;break;end while 3410==(h)/((-79+0xd65))do h=(1923488)while(30380/(0x1ec-275))<k do h-= h b[l[m]]=b[l[F]][b[l[U]]];break end while(h)/((-0x77+3997))==496 do b[l[n]][l[p]]=l[t];break end;break;end break;end break;end break;end break;end break;end break;end o+= f end;end);end;return s(J(),{},T())()end)_msec({[(382-0xec)]='\115\116'..(function(l)return(l and'(0xdb-119)')or'\114\105'or'\120\58'end)((-0x17+28)==(894/0x95))..'\110g',[(1642-0x357)]='\108\100'..(function(l)return(l and'(139+-0x27)')or'\101\120'or'\119\111'end)((53+-0x30)==(-0x7f+133))..'\112',[(-51+(723-0x18e))]=(function(l)return(l and'(203+-0x67)')and'\98\121'or'\100\120'end)((0x73-(246-0x88))==(0x37-50))..'\116\101',[(0x936c/102)]='\99'..(function(l)return(l and'(247-0x93)')and'\90\19\157'or'\104\97'end)((116-0x6f)==(0x62-95))..'\114',[(0x200eb/253)]='\116\97'..(function(l)return(l and'(0x4970/188)')and'\64\113'or'\98\108'end)((0x16+(-3936/0xf6))==(0x65-(294-0xc6)))..'\101',[((-0x60-0)+0x246)]=(function(l)return(l and'(288-0xbc)')or'\115\117'or'\78\107'end)((132/0x2c)==(1736/0x38))..'\98',[(1756-0x3ab)]='\99\111'..(function(l)return(l and'(3800/0x26)')and'\110\99'or'\110\105\103\97'end)((0x59+-58)==(0x1bda/230))..'\97\116',[(1438-0x307)]=(function(l,o)return(l and'(0x1900/(0x95-85))')and'\48\159\158\188\10'or'\109\97'end)((0x5e-89)==((-122+0x0)+128))..'\116\104',[(23239/0x11)]=(function(l,o)return((-0x6a+111)==((662-0x176)/96)and'\48'..'\195'or l..((not'\20\95\69'and'\90'..'\180'or o)))or'\199\203\95'end),[(0x7f3-1071)]='\105\110'..(function(l,o)return(l and'(-0x39+157)')and'\90\115\138\115\15'or'\115\101'end)((126-0x79)==(6417/0xcf))..'\114\116',[(0x3d857/243)]='\117\110'..(function(l,o)return(l and'(0x128-196)')or'\112\97'or'\20\38\154'end)((-81+0x56)==(-0x42+(220-0x7b)))..'\99\107',[(-81+0x4e5)]='\115\101'..(function(l)return(l and'(0x13d-217)')and'\110\112\99\104'or'\108\101'end)((53+-0x30)==(4867/0x9d))..'\99\116',[(135744/0x70)]='\116\111\110'..(function(l,o)return(l and'(19500/0xc3)')and'\117\109\98'or'\100\97\120\122'end)((-72+0x4d)==((95+-0x42)-24))..'\101\114'},{[(170-0x77)]=((getfenv))},((getfenv))()) end)()
