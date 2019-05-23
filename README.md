# Running auditor node
Running auditor node is as simple as generating one seed and calling a `docker-compose up -d` command.
## Preparing all data
### Generate
Generate `NODE_SEED` by running following command:
```
docker run --rm --entrypoint=core tokend/core:3.3.1 gen-seed
```
You should see the following output:
```
Secret seed: SAXK2YCEHV3DLLFQ2N4NHC36C4VISRFIRM4WAX475SHX6WFUFZ373K2X
Public: GAO5AAU4QK2BJAMLAD6EBR4X2KVFV54U6M3CV6USSLLE76ITCEA5V6VB
```
Save secret seed, you'll need it later.

## Configuring
Please open the configs/core.ini file in the editor of your choice and tune its content following provided instructions.

Set `NODE_SEED` to the value you've generated + " self":
```
NODE_SEED="SAXK2YCEHV3DLLFQ2N4NHC36C4VISRFIRM4WAX475SHX6WFUFZ373K2X self"
```
___
*Do not change other configs unless you know what you are doing*

## Running
When configs are filled with correct values running the node is quite easy.
Go to the directory with docker-compose.yaml file and run:
```
docker-compose up -d
```

After running this command you'll get core peer port at 8090 and API port at 8080.

## Removing
To remove node just run in the directory with docker-compose.yaml:
```
docker-compose down -v
```
