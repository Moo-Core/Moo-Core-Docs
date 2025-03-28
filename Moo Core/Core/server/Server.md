---
title: Core Functions
nav_order: 3
parent: Server
layout: home
---

# 📃Core Functions
<hr>
This file contains the core server-side functions for player and character management in the Emerald RP framework. These functions handle player connections, state management, character data operations, and routing bucket assignments. All functions are stored in the Core.Functions table.

<br>

# 📃Core.Functions.PlayerFullyJoined
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID

Core.Functions.PlayerFullyJoined = function(source)
{% endhighlight %}

Initializes a player's state bags with default values when they fully join the server. Sets up player data, character states, UI states, and camera settings.

<br>

# 📃Core.Functions.GetPlayer
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID

--| :: Returns:
{ 
  Success = <true/false>,
  Message = <status message>,
  PlayerObject = <player state data if successful>
}

Core.Functions.GetPlayer = function(source)
{% endhighlight %}

Retrieves a player's state data if it exists, returning a status object with the player data or an error message.

<br>

# 📃Core.Functions.UpdatePlayer
<hr>

{% highlight lua %}
--| :: Parameters:
source       - The player source ID
playerObject - Table containing state data to update

--| :: Returns:
{ 
  Success = <true/false>,
  Message = <status message>
}

Core.Functions.UpdatePlayer = function(source, playerObject)
{% endhighlight %}

Updates a player's state bags with new data provided in the playerObject table.

<br>

# 📃Core.Functions.DoesPlayerExist
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID

--| :: Returns:
<boolean> - True if player exists, false otherwise

Core.Functions.DoesPlayerExist = function(source)
{% endhighlight %}

Checks if a player has existing state data.

<br>

# 📃Core.Functions.GetPlayerIdentifier
<hr>

{% highlight lua %}
--| :: Parameters:
source     - The player source ID
identifier - String identifier type to search for (e.g., "steam", "discord")

--| :: Returns:
{ 
  Success = <true/false>,
  Message = <status message>,
  Identifier = <identifier value if successful>
}

Core.Functions.GetPlayerIdentifier = function(source, identifier)
{% endhighlight %}

Retrieves a specific identifier for a player from their CFX identifiers.

<br>

# 📃Core.Functions.SaveSettings
<hr>

{% highlight lua %}
--| :: Parameters:
source    - The player source ID
settings  - Table containing player settings
playerId  - The player's unique ID

--| :: Returns:
{ 
  Success = <true/false>,
  Message = <status message>
}

Core.Functions.SaveSettings = function(source, settings, playerId)
{% endhighlight %}

Saves player settings to the database and updates the player's state bag.

<br>

# 📃Core.Functions.GetPlayerIdentifiers
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID

--| :: Returns:
{ 
  Success = <true/false>,
  Message = <status message>,
  [identifierType] = <identifier value>
}

Core.Functions.GetPlayerIdentifiers = function(source)
{% endhighlight %}

Returns all CFX identifiers for a player in a table format.

<br>

# 📃Core.Functions.InsertCharacterData
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID
data   - Table containing character data

Core.Functions.InsertCharacterData = function(source, data)
{% endhighlight %}

Inserts new character data into the database and updates the player's character state.

<br>

# 📃Core.Functions.GetCharacterData
<hr>

{% highlight lua %}
--| :: Parameters:
source         - The player source ID
returnResource - Resource name to return data to

Core.Functions.GetCharacterData = function(source, returnResource)
{% endhighlight %}

Retrieves character data from the database and updates the player's state bag.

<br>

# 📃Core.Functions.DeleteCharacterData
<hr>

{% highlight lua %}
--| :: Parameters:
source      - The player source ID
characterId - The character ID to delete

Core.Functions.DeleteCharacterData = function(source, characterId)
{% endhighlight %}

Deletes a character's data from the database and refreshes the player's character state.

<br>

# 📃Core.Functions.UpdateCharacterCoords
<hr>

{% highlight lua %}
--| :: Parameters:
id    - The player source ID
value - New coordinates value

Core.Functions.UpdateCharacterCoords = function(id, value)
{% endhighlight %}

Updates a selected character's coordinates in the database and state bag.

<br>

# 📃Core.Functions.UpdateCharacterThirst
<hr>

{% highlight lua %}
--| :: Parameters:
id    - The player source ID
value - New thirst value

Core.Functions.UpdateCharacterThirst = function(id, value)
{% endhighlight %}

Updates a selected character's thirst level in the database and state bag.

<br>

# 📃Core.Functions.UpdateCharacterHunger
<hr>

{% highlight lua %}
--| :: Parameters:
id    - The player source ID
value - New hunger value

Core.Functions.UpdateCharacterHunger = function(id, value)
{% endhighlight %}

Updates a selected character's hunger level in the database and state bag.

<br>

# 📃Core.Functions.UpdateCharacterHP
<hr>

{% highlight lua %}
--| :: Parameters:
id    - The player source ID
value - New HP value

Core.Functions.UpdateCharacterHP = function(id, value)
{% endhighlight %}

Updates a selected character's health points in the database and state bag.

<br>

# 📃Core.Functions.UpdateCharacterOutfit
<hr>

{% highlight lua %}
--| :: Parameters:
id    - The player source ID
value - New outfit data

Core.Functions.UpdateCharacterOutfit = function(id, value)
{% endhighlight %}

Updates a selected character's outfit data in the database and state bag.

<br>

# 📃buildConnectionCard
<hr>

{% highlight lua %}
--| :: Parameters:
waitingMessage - String message to display

--| :: Returns:
<string> - JSON-encoded AdaptiveCard

function buildConnectionCard(waitingMessage)
{% endhighlight %}

Builds an AdaptiveCard for connection deferrals with social media links and custom message.

<br>

# 📃Core.Functions.PlayerConnecting
<hr>

{% highlight lua %}
--| :: Parameters:
name         - Player name
setKickReason - Callback to set kick reason
deferrals    - Deferral object for connection handling

Core.Functions.PlayerConnecting = function(name, setKickReason, deferrals)
{% endhighlight %}

Handles the player connection process, including identifier checks, whitelist verification, ban checks, and data initialization.

<br>

# 📃Core.Functions.PlayerDropped
<hr>

{% highlight lua %}
--| :: Parameters:
source - The player source ID
reason - Drop reason string

Core.Functions.PlayerDropped = function(source, reason)
{% endhighlight %}

Cleans up player data when they disconnect from the server.

<br>

# 📃Core.Functions.SetRoutingBucket
<hr>

{% highlight lua %}
--| :: Parameters:
source           - The player source ID
bucket           - Routing bucket ID
enablePopulation - Boolean for population control
lockDownMode     - Lockdown mode setting

Core.Functions.SetRoutingBucket = function(source, bucket, enablePopulation, lockDownMode)
{% endhighlight %}

Assigns a player to a specific routing bucket with population and lockdown options.
