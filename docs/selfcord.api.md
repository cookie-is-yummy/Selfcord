# selfcord.api package

## Submodules

## selfcord.api.errors module


### _exception_ selfcord.api.errors.DiscordException()
Bases: `Exception`


### _exception_ selfcord.api.errors.Funnu(\*args: object)
Bases: `DiscordException`


### _exception_ selfcord.api.errors.LoginFailure(message: dict, status: int)
Bases: `DiscordException`


### _exception_ selfcord.api.errors.ReconnectWebsocket(message: str)
Bases: `DiscordException`


### _exception_ selfcord.api.errors.RuntimeError(message: str)
Bases: `DiscordException`

## selfcord.api.events module


### _class_ selfcord.api.events.EventHandler(bot, http)
Bases: `object`

Used to handle discord events


#### _async_ handle_channel_create(channel, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when a channel is created


#### _async_ handle_channel_delete(data, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when a channel is deleted


#### _async_ handle_guild_create(data, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when a guild is created


#### _async_ handle_guild_member_list_update(data, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when member chunk payload is sent via gateway


#### _async_ handle_guild_role_create(role, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when a role is created


#### _async_ handle_guild_role_delete(role, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when a role is deleted


#### _async_ handle_message_create(data, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when a message is created


#### _async_ handle_message_delete(data, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles what happens when a message is created. Disclaimer: Only guild id, message id and channel id will be present if the message is not in bots cache.


#### _async_ handle_ready(data, user: [Client](selfcord.models.md#selfcord.models.client.Client), http)
Handles the ready event, what is executed when it appears

## selfcord.api.gateway module


### _class_ selfcord.api.gateway.Activity()
Bases: `object`


#### _static_ Game(name, details: str, state: str, buttons: dict, application_id: str, key: str)
Method to generate “Playing …” activity


#### _static_ Listen(name, details: str, state: str, buttons: dict, application_id: str, key: str)
Method to generate “Listening …” activity


#### _static_ Stream(name, details: str, state: str, url: str, buttons: dict, application_id: str, key: str)
Method to generate “Streaming …” activity


#### _static_ Watch(name, details: str, state: str, buttons: dict, application_id: str, key: str)
Method to generate “Watching …” activity


### _class_ selfcord.api.gateway.gateway(http, show_heartbeat=False)
Bases: `object`

OP CODES


#### DISPATCH(_ = _ )

#### GUILD_SYNC(_ = 1_ )

#### HEARTBEAT(_ = _ )

#### HEARTBEAT_ACK(_ = 1_ )

#### HELLO(_ = 1_ )

#### IDENTIFY(_ = _ )

#### INVALIDATE_SESSION(_ = _ )

#### PRESENCE(_ = _ )

#### RECONNECT(_ = _ )

#### REQUEST_MEMBERS(_ = _ )

#### RESUME(_ = _ )

#### VOICE_PING(_ = _ )

#### VOICE_STATE(_ = _ )

#### _async_ change_presence(status: str, afk: bool, activity: dict)
Change the clients current presence

Args:

    status (str): online, offline or dnd
    afk (bool): Whether client is set as AFK
    activity (Activity): Activity object


#### chunks(lst, n)

#### _async_ close()
Close the connection to discord gateway


#### _async_ connect()
Connect to discord gateway


#### _async_ heartbeat(interval)
Heartbeat for gateway to maintain connection

Args:

    interval (int): Interval between sends


#### _async_ heartbeat_ack()
Whenever heartbeat ack is sent, logs the time between last send of heartbeat json and receive of the ack


#### _async_ identify()
Identify to gateway, uses amazing mobile client spoof


#### _async_ lazy_chunk(guild_id: str, channel_id: str, amount: int)
Sends lazy guild request to gather current online members

Args:

    guild_id (str): The guild id specified
    channel_id (str): The channel id specified


#### _async_ leave_call()
Leaves a discord call


#### _async_ recv_msg()
Receives Message from gateway, encodes as json and does things depending on op code


#### _async_ ring(channel: str, guild=None)
Initiates a discord call

Args:

    channel (str): Channel ID
    guild (str, optional): Guild ID. Defaults to None.


#### roundup(n)

#### _async_ send_json(payload: dict)
Send json to the gateway

Args:

    payload (dict): Valid payload to send to the gateway


#### _async_ start(token: str, user: [Client](selfcord.models.md#selfcord.models.client.Client), bot)
Start discord gateway connection

Args:

    token (str): User token
    user (Client): User client
    bot (_type_): Bot class

## selfcord.api.http module


### _class_ selfcord.api.http.http()
Bases: `object`


#### _async_ encode_image(url)

#### _async_ get_cookie()

#### remove_dupes(dictionary: dict)

#### _async_ request(method: str, endpoint: str, \*args, \*\*kwargs)
Used to send requests

Args:

    method (str): HTTP method
    endpoint (str): Discord api endpoint

Raises:

    LoginFailure: If you suck

Returns:

    dict: Data, json data


#### _async_ static_login(token: str)
Used to retrieve basic token information

Args:

    token (str): User token

Returns:

    Client: A Client object

## Module contents

Discord API related modules, used to interact with discord
