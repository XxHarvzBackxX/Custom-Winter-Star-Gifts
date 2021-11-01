← [README](README.md)
This document helps mod authors create a content pack for Custom Winter Star Gifts.

**See the [main README](README.md) for other info**.

# Content Packs

## How-to
In your `manifest.json` file, specify that this is a content pack for CWSG by placing CWSG's unique ID inside the `ContentPackFor` field (`harvz.CWSG`).
Next, create a `content.json` file. It should look similar to this:
```js
{
  "NPCGifts": [
    {
      "NameOfNPC": "...",
      "ItemNames": {
        "...": 1
      },
      "Mode": "...",
      "Priority": 100
    }
  ]
}
```

## Fields

Field                | Valid Entries                        
-------------------- | ------------------------------- 
NameOfNPC            | (string) The internal name of the NPC you are targeting.<small>(Can also put 'All' if you want to apply to every NPC)</small>
ItemNames            | (Dictionary<string, int>) Names of the items you wish to add for this target, accompanied by the quantity of items you wish to add.  
Mode                 | (string) Which mode to use. Accepts "Add" <small>(adds to existing list for this target)</small> or "Overwrite" <small>(overwrites existing list for this target).</small>
Priority             | (int) The order in the stack of which this should be patched (carries over to multiple content packs). This should be any number above 0, but you usually won't need to go much higher than 200.

An example content pack can be found on the [Nexus page under files tab](https://www.nexusmods.com/stardewvalley/mods/10024?tab=files).

### Multiple Targets
To add multiple targets, simply add multiple 'NPCGifts' entries. Copy and paste the first one, adding a comma to the end, and fill in the appropriate info. Example:
```js
{
  "NPCGifts": [
    {
      "NameOfNPC": "All",
      "ItemNames": {
        "Parsnip": 1
      },
      "Mode": "Overwrite",
      "Priority": 250
    }
    {
      "NameOfNPC": "Robin",
      "ItemNames": {
        "Apple": 1
      },
      "Mode": "Add",
      "Priority": 100
    }
  ]
}
```

## Variety
Have a combination of many modes, items, quantities and NPCs to make a fun collection of items, ideal for your vision. Example:
```js
{
  "NPCGifts": [
    {
      "NameOfNPC": "All",
      "ItemNames": {
        "Parsnip": 10,
        "Apple": 5,
        "Prismatic Shard": 1
      },
      "Mode": "Overwrite",
      "Priority": 250
    }
    {
      "NameOfNPC": "Robin",
      "ItemNames": {
        "Iridium Bar": 1
      },
      "Mode": "Add",
      "Priority": 100
    }
  ]
}
```
This setup would make everyone give either 10 parsnips, 5 apples, or 1 prismatic shard, except Robin, who could give 10 parsnips, 5 apples, 1 prismatic shard, or 1 iridium bar.
Make sure to combine many factors for some real variety!


# Questions
If you have any questions, feel free to open an issue on the Github, leave a comment on Nexus, or DM me on Discord at `XxHarvzBackxX#3665`!
-Harvz
