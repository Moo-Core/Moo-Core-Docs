---
title: Databases
nav_order: 1
parent: Server
layout: home
---

# 📃Databases
<hr>
The db.lua file contains all of the database interactions done for player and character data (for the most part). The functions are held within the Core.DB table and are called strictly within the core file structures. No other resource should be calling these functions, but other resources are just fine to interact with the databases that are made by the core.

<br>

# 📃Core.DB.GetPlayerData
<hr>

{% highlight lua %}

--| :: Parameters:
discord         - The attached discord ID for the player.
steam           - The attached steam ID for the player.
license         - The CFX/R* License key for the player.

--| :: Returns the following:
{ 
  Success = < True/False >,
  Message = < A message to inform >,
  Data = < The data you are wanting to use/see >
}

{% endhighlight %}


# 📃Core.DB.InsertPlayerdata
<hr>

{% highlight lua %}

--| :: Parameters:
name          - The player's name
discord       - The attached discord ID for the player.
steam         - The attached steam ID for the player.
license       - The CFX/R* License key for the player.
tokens        - The tokens for the player to be available to use.

--| :: Returns the following:
{ 
  Success = < True/False >,
  Message = < A message to inform >,
  Data = < The data you are wanting to use/see >
}

{% endhighlight %}


# 📃Core.DB.CheckBans
<hr>

{% highlight lua %}

--| :: Parameters:
identifiers   - The identifiers for the player.

--| :: Returns the following:
{ 
  Success = < True/False >,
  Message = < A message to inform >,
  Data = < The data you are wanting to use/see >
}

{% endhighlight %}
