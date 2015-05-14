# SAGA system API documentation

Uses [Netty-Socket.IO](https://github.com/mrniko/netty-socketio)  for Java implementation of [Socket.IO](http://socket.io/) server.

Socket API Events
================================

### onWorldList

Send to client on socket connection. 

```json
{
    "worlds": [
        {
            "id": 1,
            "name": "NEWWORLD"
        }
    ]
}
```

Contains a list of all the SAGA worlds.

## createWorld

Returns the initial world state

###### Arguments
- 'String name' — Name of the world that is to be loaded
  
###### Response:

```json
{
    "entities": [
        {
            "name": "RAPUNZEL",
            "type": "Character"
        },
        {
            "name": "GOLD_BALL",
            "type": "Article"
        },
        {
            "name": "TOWER",
            "type": "Location"
        }
    ],
    "relations": [
        {
            "name": "IS_AT",
            "entity1": "PRINCESS",
            "entity2": "PALACE",
            "entity3": "",
            "intensity": 0
        },
        {
            "name": "IS_AT",
            "entity1": "FROG",
            "entity2": "FOUNTAIN",
            "entity3": "",
            "intensity": 0
        }
    ]
}
```

