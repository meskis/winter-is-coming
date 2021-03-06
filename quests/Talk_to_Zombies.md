# Talk to Zombies. Game "Winter is coming"

Hey, Backend Engineer, we'd like you to build a simple game engine! :)

## Requirements
Build a Server which hosts a [game](../README.md#game-rules) and game participant (Client) can play via bidirectional Communication Channel 

- Fulfill specification - implement game engine by [Communication Channel specification](#communication-channel-specification) 
- Concentration - only solve the problems scoped in the requirements (task difficulty is max for 1-2 days)
- Language agnostic - choose a language for this problem solving (we love Golang or any other it's readable code)
- Clean code - demonstrate your most readable code
- Design patterns - demonstrate your design skills (SOLID, KISS, DRY etc.)
- Testing - demonstrate creepy love for tests, it's totally ok
- We can easily start your game Server and play
- Share code on VCS and send a link to jobs@mysterium.network

### Communication Channel specification
- As a Client I can join and interact with Server through Communication Channel
- Dont create a Client yet. Anyway your chosen protocol will be testable with *telnet*, *curl*, *Postman* etc.
and start a game after joining
- As a Client I can start a game
- When game is started Server creates new board and spawns new zombie
- When game is started Server announces Zombie’s coordinates every 2 seconds
- As a Client I can send coordinates of the Archer's shot
- As a Client I would like to know if my shot was accurate

### Communication Channel example
```
# Client send Archer's name
START john
```

```
# Server announces coordinates
WALK night-king 0 0
WALK night-king 0 1
WALK night-king 1 1
WALK night-king 1 2
WALK night-king 1 3
...
```

```
# Client sends Archer's coordinates
SHOOT 0 0
# Server responds with Archer's result
BOOM john 0
BOOM john 1 night-king
```

### Bonus points for (only when requirements fulfilled)
- Parallelism problem - unlimited Clients can play simultaneous games at once
- Concurrency problem - several Clients can join same game, first good shoot wins
- Cross-platform problem - your friends are able to host a Server on their personal machines
- Peer-to-peer problem - You can connect to your friend's server and play from your home
- Critical thinking - pick a solution/library for bidirectional Communication Channel so that it fits game requirements. Or implement any creative solution for messaging
