# BloodHound Neo4j DB wrapper

## Problem description

BloodHound is a fantastic tool. But if you want to switch between dataset (ex: htb prolabs) you have to clear and reimport the data losing your progression along the way (ex: owned nodes). The database behind BloodHound is Neo4j and their multi-database option is a paid feature.

## Solution

In the neo4j configuration, if you set the default database to something other then "neo4j", it will create a new folder and therefore a new database.

So with this little wrapper you can start neo4j with your desired database. You will keep your progress when switching between databases and can delete data when the project is finished.

I guess it can be used with something else then BloodHound, should work with any other tools that use neo4j databases.

## How to start

Notice: only been test/used on Kali Linux.

### Requirements

```bash
sudo apt update
sudo apt install jq moreutils tmux bloodhound neo4j -y
```

### Clone and setup

```bash
git clone <repo>
cd <repo>
./bh-neo4j-wrapper.sh setup
```

### Usage

```bash
# when setup is done, you can use the command from anywhere
bh-neo4j-wrapper.sh help
bh-neo4j-wrapper.sh list
bh-neo4j-wrapper.sh run offshore
bh-neo4j-wrapper.sh rm dante
```

### How to uninstall

```bash
# you can delete the repo
rm -rf <reponame>
# delete symlink
sudo rm /usr/local/bin/tool.sh
```
