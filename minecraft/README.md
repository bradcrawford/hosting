# Server setup

1. Ensure docker & docker-compose are installed and working
2. Access via ssh and copy `server/docker-compose.yml` into `minecraft-server`
3. Make any changes in `docker-compose.yml`
4. Run `docker-compose up --build -d` to start the server as a daemon

# Setting game rules

1. Run `docker attach minecraft`
2. Run `gamerule <name> <value>` to configure game rules e.g. `gamerule showCoordinates true`
3. Type `ctrl+p ctrl+q` to quit

```
gamerule showCoordinates true
gamerule doDaylightCycle false
gamerule doLimitedCrafting false
gamerule keepInventory true
gamerule recipesUnlock false
```
