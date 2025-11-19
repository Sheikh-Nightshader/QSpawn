
           
           
           .,o'       `o,.
         ,o8'           `8o.
        o8'               `8o
       o8:                 ;8o
      .88                   88.
      :88.                 ,88:
      `888                 888'
       888o   `888 888'   o888
       `888o,. `88 88' .,o888'
        `8888888888888888888'
          `888888888888888'
             `::88⛧88;:'
                88 88
                88 88
                `8 8'
           ⛧     ` '     ⛧

QSpawn Quake MAP Creator Beta 1.1 - Sheikh Nightshader

QSpawn - Quake MAP Creator (CLI)

Description:
QSpawn is a command-line tool for creating and editing Quake 1 .MAP files.
It supports:
- Adding rooms, boxes, lights, players, and custom entities
- Using default textures or any custom texture names
- Placing items and monsters with custom coordinates
- Exporting fully valid Quake .MAP files

Usage:
1. Run the script:
   python3 qspawn.py

2. Commands:
   NEW                       - Create a new map
   ROOM cx cy cz w d h [WALL=wall_tex FLOOR=floor_tex CEIL=ceil_tex]
                             - Add a room
   BOX cx cy cz sx sy sz TEXTURE=tex
                             - Add a brush box
   LIGHT x y z [intensity]  - Add a light
   PLAYER x y z [angle]     - Place a player start
   ENTITY classname key=value ...
                             - Add a custom entity
   ITEM classname x y z [key=value ...]
                             - Add a custom item or monster
   TEXTURES                  - List example textures
   ITEMS                     - List example items/entities
   EXPORT filename.map       - Save the map
   HELP                      - Show commands
   EXIT                      - Quit the editor

Simple Usage:

quake> NEW
New map created with worldspawn.

quake> ROOM 0 0 0 1024 1024 256 WALL=bricka2_2 FLOOR=woodflr1_5 CEIL=sky1

Room added at (0,0,0) size=(1024,1024,256)

quake> PLAYER 0 0 0

Entity 'info_player_start' added with properties: {'origin': '0 0 0', 'angle': '0'}

quake> ITEM weapon_shotgun 100 0 0

Entity 'weapon_shotgun' added with properties: {'origin': '100 0 0'}

quake> LIGHT 0 0 128 300

Entity 'light' added with properties: {'origin': '0 0 128', 'light': '300', 'angle': '360'}

quake> EXPORT mymap.map
Map exported -> mymap.map

quake> EXIT

After exporting a map:

  1. Compile map with QBSP:
       qbsp yourmap.map

  2. Run VIS for visibility:
       vis yourmap.bsp

  3. Run LIGHT to bake lighting:
       light yourmap.bsp

  Then your map is ready to play in Quake.
  
Notes:
- Any texture or entity name can be used; defaults are just suggestions. You need a texture wad named tex.wad which contains the source textures. If you mapped quake before you would know. I have it in the .map header under worldspawn, the default directory to it. "C:\quake\TEX.WAD"
- Coordinates for items and monsters are added automatically in the map file.
- Fully CLI-based, no GUI required.
- Need Tools for compiling .map files qbsp, vis, map etc.
- Finally and important to mention this is only in Beta!!! There may be issues. It works and I made test maps with it.

License:
MIT
