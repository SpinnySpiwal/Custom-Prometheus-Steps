# Welcome to my custom [Prometheus](https://github.com/prometheus-lua/prometheus) steps!

## What is Prometheus?
Prometheus is an open source Lua Obfuscator that can be used to obfuscate lua code.
But, it isn't exactly 'secure', so to speak.

I've gotten steps created for it that:
* Decrypt the string encryption (Not public)
* Reverse the ConstantArray step (Not public)
* [Disable the AntiTamper](Prometheus-AntiTamper-Bypass.lua) (Closed-Source step. Will not open source, or it will be patched.)

## Key
* 🔴 = I'm never going to open source this. People will just reverse engineer it.
* 🟡 = I'm thinking about opening source this.

## Steps I created myself *for* obfuscation
* Dynamic String Encryption 🔴
* ConstantArray V2 🔴
* NumbersToExpressions V2 🔴
* NumTransform 🟡

## Examples

### NumbersToExpressions V2

**Before:**
```
local arr = {}
for i = 1, 100 do
	local x;
	x = (x or 1) + i;
	arr[i] = function()
		return x;
	end
end

for i, func in ipairs(arr) do
	print(func())
end
```


**After:**
```
local arr = {}
for i = math.deg(0.01745329251994329547437168059786927187815308570862), math.deg(1.74532925199432953355938025197247043251991271972656), (math.rad(1.90985931710274403627636274904944002628326416015625)) * 30 do
	local x
	x = (x or 0.022222222222222223 * 45) + i;
	(arr)[i] = function()
		return x
	end
end
for i, func in ipairs(arr) do
	print(func())
end
```

### NumTransform

**Before:**

```
local arr = {}
for i = 1, 100 do
	local x;
	x = (x or 1) + i;
	arr[i] = function()
		return x;
	end
end

for i, func in ipairs(arr) do
	print(func())
end
```


**After:**

```
local arr = {};
for i = 0x1, 0b1100100, 0b1 do
	local x;
	x = ((x or 0b1))+(((i)));
	(arr)[(((((((i)))))))] = function()
			return x;
		end;
end;
for i, func in ipairs(arr) do
	print(func());
end;
```


## How to use?

To use my obfuscator, you need to contact me via discord.
Discord is `spinnyspiwal`, the obfuscator is private only because of skids.