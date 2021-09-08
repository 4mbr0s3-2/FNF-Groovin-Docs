# How to Make an Actually Decent Modchart (WIP...)
*Authored by 4mbr0s3 2*

*Note: This is NOT a tutorial on how to modchart in Schmovin', Kade Engine, ProjectFNF, Psych Engine, etc. This is also not a guide for making a modchart in NotITG, since it's for people familiar with Friday Night Funkin's Haxe codebase and not StepMania's Lua scripts.*

This guide assumes that you already know how to make a modchart with any of the engines (or that you're epic enough of a programmer to make one from the vanilla game out of sheer willpower).

## The "Sine Wave" Syndrome

Before getting into the actual nitty-gritty, let's first learn about what to (try to) avoid.

Have you ever heard of the [*Whitty Syndrome*](https://www.urbandictionary.com/define.php?term=Whitty%20syndrome)? 
There's something similar to that for modcharts, especially Lua modcharts. I call it the "Sine Wave" Syndrome.
Here's a brief history of it.

With Kade Engine's new Lua bindings, [*TaroNuke*](https://twitter.com/TaroNuke), a rhythm game developer and StepMania modder (best known for UKSRT and NotITG... please check his work out), created some example code for the system. 

```lua
local currentBeat = (songPos / 1000)*(bpm/60)
for i=0,7,1 do
    local receptor = _G['receptor_'..i]
    receptor.angle = (spinLength / 7) * -math.sin((currentBeat + i*0.25) * math.pi)
    -- Wow, sine (and sine with a phase shift of 3*pi/2) waves!
    receptor.x = receptor.defaultX + spinLength * math.sin((currentBeat + i*0.25) * math.pi)
    receptor.y = receptor.defaultY + spinLength * math.cos((currentBeat + i*0.25) * math.pi)
    end
```

*...That was the only modchart code example for Kade Engine for the longest time.*

So, naturally, other mods used it as a basis for modcharting. 
Here's a list of mods that use this sine wave effect:

- V.S. Agoti
- V.S Zardy - Foolhardy RetroSpecter Remix...
- Smoke Em Out Struggle - Release RetroSpecter Remix
- Custom Roses Modchart! (this one's actually pretty neat)
- V.S Shaggy - God Eater RetroSpecter Remix
- VS Trollface/Trollge
- Vs. RetroSpecter
- Friday Night Funkin': Neo

Using sine waves in modcharts isn't necessarily bad (it's what the *tipsy* and *drunk* mods in the original DDR game are, after all), but slapping it onto a chart and calling it a modchart can feel pretty bland and uncreative, especially when it has been used so much in other mods.

## Readability

OK, now it's time that we actually start talking about FNF modcharts.
It's important that modchart creators understand how players would approach sightreading a modchart.
There are a few things to address with regards to making a chart readable.

### Note coloring

Friday Night Funkin's notes only show one thing: direction. Each note direction has a corresponding color associated with it, which means that the appearance of FNF's notes can only give players the same piece of information.
However, StepMania uses timing colors, or quantization colors, which means that StepMania's notes give players both the direction and the time to hit them.

When applying modchart effects that can affect the player's conception of note timings in FNF, the player can clearly see what arrow to press, but not *when*. Therefore, *timing colors are important for conveying this missing piece of information.*

### Memorization

Memorization is an *incredible* game design mechanic to train players on.

*One of the best ways of taking advantage of this mechanic with modcharting is to give the player a brief glimpse into a section of the chart and to hide or distract the player from that particular section in any creative way.*

Think of it like [object permanence](https://en.wikipedia.org/wiki/Object_permanence), but for rhythm game arrows.

Let's do some case studies to see how other mods use the mechanic of memorization.

#### FNF Mod Case Study: [*Kastimagina* from "In The Galaxy Mod" by Allen98637](https://www.youtube.com/watch?v=_dNohf8Yaik)

Additionally, this particular way of adding memorization can be considered the cornerstone of many *NotITG* modfiles.
So, let's disect some NotITG modfiles.

#### Non-FNF Case Study: [*Sakuramichi Overdrive (ARM Remix) / rizuna* from UKSRT LAGC15 by taro4012 / TaroNuke](https://www.youtube.com/watch?v=RDWKedOHitU)



### Eye movement

Eye movement is another important aspect to consider when making modcharts.
*It's important to consider where the player is looking at all times of a modchart.* It might be useful to give the player hints for where to look on-screen as well.
