do
 
function pairsByKeys(t, f)
      local a = {}
      for n in pairs(t) do table.insert(a, n) end
      table.sort(a, f)
      local i = 0      -- iterator variable
      local iter = function ()   -- iterator function
        i = i + 1
        if a[i] == nil then return nil
        else return a[i], t[a[i]]
        end
      end
      return iter
    end
 
-- Returns true if is not empty
local function has_usage_data(dict)
  if (dict.usage == nil or dict.usage == '') then
    return false
  end
  return true
end
 
-- Get commands for that plugin
-- !help command
local function telegram_help()
  local i = 0
  local text = ""
  -- Plugins names
  for name in pairsByKeys(plugins) do
    if plugins[name].hidden then
      name = nil
    else
    
    text = text..'\n'..'Creed is Dead for ever .'
    end
  end
  text = text..'\n'..'Creed is Dead for ever.'
  return text
end
 
 
-- !help all command
local function help_all(requester)
  local ret = ""
  for name in pairsByKeys(plugins) do
    if plugins[name].hidden then
      name = nil
    else
      ret = ret .. plugin_help(name, nil, requester)
    end
  end
  return ret
end

local function run(msg, matches)
  if is_sudo(msg) then
      requester = "sudo"
  elseif is_admin(msg) then
      requester = "admin"
  elseif is_momod(msg) then
      requester = "moderator"
  else
      requester = "user"
  end
  if matches[1] == "Creed" then
    return telegram_help()
  elseif matches[1] == "Creed" then
    return help_all(requester)
  else
    local text = ""
    if tonumber(matches[1])  then
      text = plugin_help(nil, matches[1], requester)
    else
      text = plugin_help(matches[1], nil, requester)
    end
    if not text then
      text = telegram_help()
    end
    return text
  end
end
 
return {
  description = "For Funny.",
  
  patterns = {
    "^Creed$",
    "^CreeD$",
    "^creed_is_dead (.+)"
  },
  usage = {
    "!Creed: @creed's name is arsalan , he have 3 Guards with 700 Members and this bot is made by him . (Use With Out \'!\')",
  },
  run = run
}
 
end
