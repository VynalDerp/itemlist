---
title: Info
layout: page
permalink: /info
---

{%- assign utils = false -%}
{%- assign lootboxes = false -%}
{%- assign puppeteer = false -%}
{%- for mod in site.data.modlist -%}
    {%- case mod.name -%}
        {%- when 'ToolkitUtils' %}
            {%- assign utils = true -%}
        {%- when 'ToolkitUtils - Testing' -%}
            {%- assign utils = true -%}
        {%- when 'Puppeteer' -%}
            {%- assign puppeteer = true -%}
        {%- when 'TwitchToolkit - Lootboxes' -%}
            {%- assign lootboxes = true -%}
    {%- endcase -%}
{%- endfor -%}


{%- assign bal = '!bal' -%}
{%- assign buy = '!buy' -%}
{%- for command in site.data.commands -%}
    {%- if command.data.isBal -%}
        {%- assign bal = command.usage -%}
        {%- continue -%}
    {%- endif -%}

    {%- if command.data.isBuy -%}
        {%- assign buy = command.usage -%}
        {%- continue -%}
    {%- endif -%}
{%- endfor -%}

# Welcome

Welcome to [{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }})'s stream.
This stream uses the mod
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) to provide an
interactive experience. There's a lot to the mod that may seem complicated to even more experienced
users, but this short guide will help you get the hang of things.

## What is Twitch Toolkit?

Twitch Toolkit is a mod by hodlhodl that allows viewers to affect the game in a number of ways. The
most prominent is its [store]({{- "/" | relative_url -}}), which allows you to purchase a number of
things the streamer curated. Depending on the purchase, these things appear in-game or affect the
game in some way. Another way viewers can interact with the game is through the mod's polls. The
choices in these polls depend heavily on what's enabled in the mod.

## What Are Coins?

Coins are the mod's currency. You can view your balance by using the `{{ bal }}` command. 

{% if utils == true %}
You'll notice the balance command may have some new emojis. If that's the case, here is an overview
of the emojis as follows:

- 💰 represents the amount of coins you current have.
- ⚖ represents your current karma.
- 📈 represents the amount of coins you gain everytime the mod awards coins.
- 📉 represents the amount of coins you lose everytime to mod awards coins.

{% endif %}


{%- if lootboxes == true -%}
You'll also notice that you'll get a message from the bot about a lootbox. You can open this lootbox
by using the `!openlootbox` command, as well as check the number of lootboxes you have with `!lootboxes`.
You'll always get a new lootbox everyday.
{%- endif -%}


<br/>
## What is Karma?

Karma is a system in the mod that tries to limit the amount of negative events a viewer can purchase at
one time. This system works by directly modifying that amount of coins viewers get everytime the mod
awards coins. This means that the lower you karma is, the lower your coin gain is. The hope is that
negative events get spread out more so the colony can recover.

## How Do I Use Twitch Toolkit?

You can use Twitch Toolkit in a number of ways -- the most prominent way is through its
[commands]({{- "/commands" | relative_url -}}). The more important command is the `{{- buy -}}`
command, which is the mods entry point into purchasing things from the store. Other notable commands
are the `!mypawn` commands, which allow you see various information about your pawn. We won't cover
every command here, but most commands should generally be self-descriptive or have a description of
what they do on the [commands]({{- "/commands" | relative_url -}}) page.

<br/>

# FAQ

## What is the best gear?

The best gear varies from playthrough to playthrough, but the current best gear set is:

Format: Layer \ Coverage - itemname[materialtype,quality]

ONLY COPY itemane[materialtype,quality]. No spaces.

- Outer (Head) \ full - ironhelm[solar-forgedsteel,legendary]
- Strapped (Head) \ eyes - nightvisiongoggles (any)
- Strapped (Head) \ head, ears - gunlink (any)
- Strapped (Head) \ jaw - facemask[milirafeather,legendary]
- Skin (Head) \ neck, jaw - stealthmask[milirafeather,legendary]
- Middle\ full - ironhide[solar-forgedsteel,legendary]
- Skin \ full - fragsuit[milirafeather,legendary] OR uniformepischica[legendary] OR orassanflightsuit[legendary] *1
- Outer \ full - gorkacombatbodysuit[milirafeather,legendary]
- Webbing \ shoulders - aternitignianimperialarmysuspenders[legendary]
- Webbing \ utility slot - any *2
- Utility \ utility slot - any *3
- Utility \ legs - chemlightlegpack (any)
- Backpack \ shoulder - molle2rucksack(ucp) (any) OR closedoxygencylinder (any) *4

*1 Fragsuit for protection, Uniforme for psychic sensitivity, Flight Suit for 50% bleed factor <br/>
*2 Rimmu-nation belts are identical in cost and stats. <br/>
*3 Check next section for details <br/>
*4 MOLLE for bulk/mass increase, Closed Oxygen Cylinder for pain shock/move speed <br/>

## Utility Items

Pick one, based on your character build. Torso slots do not conflict with utility slots.

- Utility Slot - jumppack[awful]
- Utility Slot - medicbag[awful] (surgery success, tend quality)
- Utility Slot - portableassistantcomputer (work speed, learning factor, research speed, hack speed, aim time, ranged cooldown, melee cooldown)
- Utility Slot - rangedshieldbelt[legendary]
- Utility Slot - shieldbelt[legendary]
- Utility Slot - toolbelt[awful] (repair success, construction speed, construct success)
- Torso - sashimonobanner[awful] (pain shock, suppressability)
- Torso - quiver[awful] (reload speed, ranged cooldown)



## What are the best materials?

Best materials also change from playthrough to playthrough. Currently, the best materials are, in this order:

Cloths:
- Milira Feather
- Hyperweave
- Blue Cat Lily
- Aramid Cloth
- Araneron

Metals:
- Solar-Forged Steel
- Plasteel OR Tungsteel
- Amorphous Polymer

{%- if puppeteer -%}
<br/>
## What is Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) is a mod by Brrainz that
allows viewers to directly control their pawns, and even view a number of information about your pawn in
a graphical way. It also redirects some of the responses from Twitch Toolkit to its website to clean up
chat a bit. So, if you're logged into Puppeeter and you're wondering why the bot isn't responding to you,
you should check the `TT` tab on the website first.
{%- endif -%}
