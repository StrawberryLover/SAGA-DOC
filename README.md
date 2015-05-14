# SAGA system API documentation

Uses [Netty-Socket.IO](https://github.com/mrniko/netty-socketio)  for Java implementation of [Socket.IO](http://socket.io/) server.

Socket API Events
================================

## To client events

### onWorldList

Send to client on socket connection. 

###### Response:

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

    
## onAction

Send action to the SAGA system.

###### Arguments
- 'int id' — Actions id
- 'bool execute' - Tells the SAGA system if the action was executed
    
## To server events

## beginWorld

Begins the SAGA world

## endWorld

Ends the SAGA world
    
## resetWorld

Resets the SAGA world

## action

Get an action from the SAGA system

###### Response:

```json
{
    "id": 3277,
    "name": "MOVE",
    "planID": 1626,
    "parentPlanID": 1606,
    "lastAction": false,
    "entities": [
        {
            "name": "WITCH",
            "type": "Character"
        },
        {
            "name": "TOWER",
            "type": "Location"
        },
        {
            "name": "FOUNTAIN",
            "type": "Location"
        }
    ],
    "effects": [
        {
            "name": "IS_AT",
            "entity1": "WITCH",
            "entity2": "TOWER",
            "entity3": "",
            "intensity": 0,
            "operator": "REMOVE"
        },
        {
            "name": "IS_AT",
            "entity1": "WITCH",
            "entity2": "FOUNTAIN",
            "entity3": "",
            "intensity": 0,
            "operator": "ADD"
        }
    ],
    "priority": 0
}
```

