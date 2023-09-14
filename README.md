# kibot-cfg

A cfg.yaml file for structuring Kibot fab pack exports. 

# How do I install this?

Once you've cloned the repo, just symlink to the config file in whatever Kicad repo you're working in. 

Clone the repo to your local machine, and in any kicad directory, run:

```
ln -s ~/kibot-cfg/cfg.kibot.yaml cfg.kibot.yaml
```

Make any edits you wish in `~/kibot-cfg/cfg.kibot.yaml`, and they'll be applied to all repos in which you've linked to the YAML file - no manual updates required!

# How do I use this?
If you have kibot installed, you can quickly create a fabpack for a board manufacturer by navigating to the top level driectory and running:

```
user@kicad:~/my_board$ kibot -e cad/my_board/my_board.kicad_sch
```

This will generate a directory, `fab/`, along with a subdirectory tree, and populate it with all info needed for board fab (gerbers, drill, PNP, BOM, etc).

It will also zip contents of that directory into two fabpacks:

* `turnkey`, which includes PCB fab info, a BOM, and assembly information
* `bareboard`, which includes only PCB fab info (gerbers and drill)

You can find these fabpacks under the `releases/staging` directoy. (Kibot will create this for you if it does not exist.)


