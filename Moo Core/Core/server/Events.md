---
title: Events
nav_order: 2
parent: Server
layout: home
---

# 📃Events
<hr>
This file contains server-side event handlers for player connections and character management. It includes functions for handling player connections, disconnections, and various character data operations. All functions are part of the Core.Functions table and are triggered through registered network events.

<br>

# 📃Player Connecting
<hr>

{% highlight lua %}
AddEventHandler('playerConnecting', function(name, setKickReason, deferrals)
    Core.Functions.PlayerConnecting(name, setKickReason, deferrals)
end)
{% endhighlight %}

Handles the initial player connection process before joining the server. Passes player name, kick reason callback, and deferrals to the core function.

<br>

# 📃Player Dropped
<hr>

{% highlight lua %}
AddEventHandler('playerDropped', function(reason)
    Core.Functions.PlayerDropped(source, reason)
end)
{% endhighlight %}

Manages player disconnection events, passing the source ID and drop reason to the core function.

<br>

# 📃Core.Functions.PlayerFullyJoined
<hr>

{% highlight lua %}
RegisterNetEvent('Player::OnPlayerFullyJoined', function()
    Core.Functions.PlayerFullyJoined(source)
end)
{% endhighlight %}

Triggered when a player has fully joined the server, sending their complete player data to the client.

<br>

# 📃Core.Functions.SetRoutingBucket
<hr>

{% highlight lua %}
--| :: Parameters:
source           - The player source ID
bucket           - The routing bucket ID to set
enablePopulation - Boolean to enable/disable population
lockDownMode     - Boolean for lockdown mode

RegisterNetEvent('Player::SetRoutingBucket', function(source, bucket, enablePopulation, lockDownMode)
    Core.Functions.SetRoutingBucket(source, bucket, enablePopulation, lockDownMode)
end)
{% endhighlight %}

Sets a player's routing bucket with options for population control and lockdown mode.

<br>

# 📃Core.Functions.SaveSettings
<hr>

{% highlight lua %}
--| :: Parameters:
source    - The player source ID
settings  - The settings data to save
playerId  - The player's unique ID

RegisterNetEvent('Player::SaveSettings', function(source, settings, playerId)
    Core.Functions.SaveSettings(source, settings, playerId)
end)
{% endhighlight %}

Saves player settings to the database using their source and player ID.

<br>

# 📃Core.Functions.InsertCharacterData
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID
data   - The character data to insert

RegisterNetEvent('Characters::InsertCharacterData', function(source, data)
    Core.Functions.InsertCharacterData(source, data)
end)
{% endhighlight %}

Inserts new character data for a player into the database.

<br>

# 📃Core.Functions.GetCharacterData
<hr>

{% highlight lua %}
--| :: Parameters:
source         - The player source ID
returnResource - The resource to return data to

RegisterNetEvent('Characters::GetCharacterData', function(source, returnResource)
    Core.Functions.GetCharacterData(source, returnResource)
end)
{% endhighlight %}

Retrieves character data for a player and sends it to the specified resource.

<br>

# 📃Core.Functions.UpdateCharacterCoords
<hr>

{% highlight lua %}
--| :: Parameters:
id    - The character ID
value - The new coordinates to set

RegisterNetEvent('Characters::UpdateCharacterCoords', function(id, value)
    Core.Functions.UpdateCharacterCoords(id, value)
end)
{% endhighlight %}

Updates a character's coordinates in the database.

<br>

# 📃Core.Functions.DeleteCharacterData
<hr>

{% highlight lua %}
--| :: Parameters:
source      - The player source ID
characterId - The ID of character to delete

RegisterNetEvent('Characters::DeleteCharacterData', function(source, characterId)
    Core.Functions.DeleteCharacterData(source, characterId)
end)
{% endhighlight %}

Deletes a character's data from the database.

<br>

# 📃Core.Functions.UpdateCharacterThirst
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID
value  - The new thirst value

RegisterNetEvent('Characters::UpdateCharacterThirst', function(source, value)
    Core.Functions.UpdateCharacterThirst(source, value)
end)
{% endhighlight %}

Updates a character's thirst level in the database.

<br>

# 📃Core.Functions.UpdateCharacterHunger
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID
value  - The new hunger value

RegisterNetEvent('Characters::UpdateCharacterHunger', function(source, value)
    Core.Functions.UpdateCharacterHunger(source, value)
end)
{% endhighlight %}

Updates a character's hunger level in the database.

<br>

# 📃Core.Functions.UpdateCharacterHP
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID
value  - The new HP value

RegisterNetEvent('Characters::UpdateCharacterHP', function(source, value)
    Core.Functions.UpdateCharacterHP(source, value)
end)
{% endhighlight %}

Updates a character's health points in the database.

<br>

# 📃Core.Functions.UpdateCharacterOutfit
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID
value  - The new outfit data

RegisterNetEvent('Characters::UpdateCharacterOutfit', function(source, value)
    Core.Functions.UpdateCharacterOutfit(source, value)
end)
{% endhighlight %}

Updates a character's outfit data in the database.
