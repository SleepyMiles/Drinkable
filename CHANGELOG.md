## 1.3.2
- Fixed: without FrailtyPlus installed, the game's input system broke on startup (the "Could not load file or assembly 'Frailty'" error), so you couldn't drink, the Burp key didn't work and the game showed a save data error. FrailtyPlus is optional again, as it should be.
- Fixed: without StaticNetcodeLib you couldn't drink ("Drink: NullReferenceException"). Drinking ran on BepInEx' own object, which the game can remove when it loads a scene; now it runs on its own object.
- StaticNetcodeLib is no longer needed (Drinkable never used it).
- Fixed: typing part of a drink's name in the terminal bought the wrong thing ("belch" bought a Belt bag). The first word of a drink's name, or its name written together ("belchcola"), now finds the drink. Typing the first two words of the name ("belch cola 3") always finds it too, even when the game has its own command for the first word.
- Fixed: after leaving a lobby and hosting or joining another one, the others no longer saw or heard your drinks (and the machines stopped syncing) until you restarted the game.
- Fixed: without EladsHUD+, the buff icons could sit on top of FrailtyPlus' injury icons, and drifted a little further off with every icon before them. They now line up along the same tilted line as FrailtyPlus' icons.
- Fixed: on some setups (where BepInEx' own object is removed when the game loads a scene) the mod lost track of the other mods: EladsHUD+'s status row, AdvancedCompany's terminal and TerminalFormatter weren't found.
- Fixed: when Lucky got you out of a Forest Giant's grab, the giant kept playing its eating animation and slid after you. Its eating animation is now cut off and it's stunned for 5 s (new setting "Lucky Forest Giant stun"); it can't grab you again until 3 s after the stun, so you can get away.
- Fixed: We'll Make It (Buddy Spritz, 15%) didn't come near a dead teammate's body, only while carrying one (30%): the body counted from the spot where the player died, not where it really lies. Crew Sense's compass shows bodies where they really are too.
- **Speed Balance** (new setting in General, off by default): on = only your fastest speed buff counts, speed buffs don't stack. Slowdowns always count.
- Buff icons without EladsHUD+: the frame moves like FrailtyPlus' icons (its dashes change a few times a second), and debuff pictures slowly pulse red, like FrailtyPlus' injuries.
- **Cleaner settings:** no numbers in front of the sections any more, and fewer of them, in this order: General (now with finding drinks as scrap), Drinkable, Store price, Machine (the Soda Machine and the Drink Machine together; their prices are now "Soda Machine price" / "Drink Machine price"), Sodas Buff 1 to 4 (every drink's buffs, grouped by drink), Display. The Debug section is gone. Your settings are moved over once.

## 1.3.1
- Fixed an error that make player cannot drink any drink at all, StaticNetcodeLib (by Xilophor) is now a required dependency.

## 1.3.0

### New
- **10 new drinks**, found as scrap, sold in the store and in the new Drink Machine, each can in its own style:
  - **Hush Soda** ($120): **Silent**. Your footsteps, landings and dropped items are half as loud, and monsters hear them from only half as far. Opening and drinking it makes a sound, but never alerts monsters.
  - **Craft Beer** ($80): **Cold One** while you drink (stamina refills fast, full when you finish), then **Tipsy** + **Wobbly**. A second beer while Tipsy: **Drunk** + **Staggering**. Faster, higher jumps, weight slows you less, your voice carries further, less damage, slower paranoia, Hoarding Bugs don't mind you, a deeper voice and hiccups (everyone hears them, and you flinch); you slip when you walk.
  - **Belch Cola** ($60): **Big Burp**, 3 burps on **[R]** (setting "Burp key"). Hoarding Bugs back off, Spore Lizards run, a Snare Flea lets go.
  - **Rocket Fizz** ($80): **Fizz Jump**, one more jump in mid-air.
  - **Lucky Lemonade** ($150): **Lucky**, 25% of hits miss you, and you survive one thing that would kill you: a Bracken, Forest Giant, Masked or Old Bird grab lets go of you, an Eyeless Dog's lunge goes past you. Works with SnatchinBrackenFORK's drag.
  - **Hunch Soda** ($100): **Danger Sense**, a ping every few seconds marks monsters and traps within 50 m through walls.
  - **Buddy Spritz** ($70): **Crew Sense**, teammates and dead teammates' bodies on the game's compass with their names. Near a teammate: **Chill** (calmer, a bit more stamina refill, slow healing up to 50 HP, not while bleeding). Near a dead teammate's body: **We'll Make It** (15% less damage, 30% while carrying the body).
  - **Focus Fizz** ($60): **Locked In**, longer scanner reach (its wave goes further and stays bright longer), faster hands and ladder climbing; turrets, landmines and spike traps don't notice you.
  - **Party Pop** ($80): confetti and a party horn; **Party** for you and everyone near you. The more of your crew within 15 m, the better: alone or 1 teammate 7% faster and 15% quicker stamina refill, 2 teammates 12% / 35%, 3 or more 20% / 50%. The slime dances for you and never hurts you.
  - **Ghost Pepper Pop** ($120): **Hot Stuff**, a monster that hits you gets stunned for 2 s with the Zap Gun's lightning (and maybe burned), its hit hurts less, spider webs burn away, steam out of your ears.
- **Drink Machine** (ship upgrade, $500, needs LethalLib): the Soda Machine's blue sibling, "Company After Hours", with the 10 new drinks. It prices and stocks drinks the same way as the Soda Machine. One free random drink per player per day from each machine.
- **High value drinks** cost a set price in the machines (not the "Drink price %"): Lucky Lemonade $100, Hunch Soda $70 and Ghost Pepper Pop $90 in the Drink Machine; Climate Soda $80, Cheesy Soda $90 and Kosher Soda $100 in the Soda Machine. Each has its own setting in its machine's config section.
- **DRINKS store section**: all drinks now have their own section in the store (works with AdvancedCompany's terminal too), not CONSUMABLES. With FrailtyMedical, its MEDICAL section comes first.
- New sounds: hiccups, burps and Fizz Jump.
- With EladsHUD+'s colours on, the game's own stamina meter is tinted too (setting "Tint stamina bar"), not only EladsHUD+'s bar.
- New config sections 11 to 15. The compass settings (at the top, offset) count for Crew Sense too.

### Balance changes
| What | Before | Now |
|---|---|---|
| Red soda: Sugar Rush | 45 s | 60 s |
| Peach Soda: price | $50 | $70 |
| Peach Soda: Sugar Mend | 50 HP | 35 HP over 90 s |
| Climate / Cheesy / Kosher Soda in the Soda Machine | 50% of the store price | set price $80 / $90 / $100 |

Settings still at their old default are moved to the new default once; changed settings are kept.

### Icon changes
<img src="https://raw.githubusercontent.com/SleepyMiles/Drinkable/main/images/changes_1_3_0_icons.png" width="720">

- New mod icon: the Red soda and a Craft Beer, poster style, "DRINKABLE".
- Buddy Spritz has a new can.
- Buff colours: Sugar Mend green to pink (its health and stamina bar colour too), Sharp Sight pink to cyan, Silent purple to gold, Danger Sense purple to gold, Party green to purple.
- New icons for the 16 new buffs and debuffs.
- Chill shows no timer while you're near your crew; the 3 s countdown shows once you walk away. We'll Make It shows its damage reduction (15% or 30%) instead of a timer.

### Tooltip changes
- **Chill**: "Your crew is close: you calm down, your stamina refills a little faster and you slowly heal up to half health (not while you bleed)."
- **We'll Make It**: "Not leaving them behind: near a fallen teammate's body you take less damage, and even less while you carry them."
- **Crew Sense**: "...your compass shows your teammates and the bodies of the ones who didn't make it. Near a teammate you Chill; near a fallen one, We'll Make It."
- **Party**: now ends with "The more of your crew around you, the better."
- **Tipsy / Drunk**: list everything they do (speed, jumps, weight, damage, paranoia, voice, Hoarding Bugs).

## 1.2.0
- **Kosher Soda reworked.** Equilibrium no longer gives damage reduction: it makes **Adrenaline** and **Equivalence** possible.
  - **Adrenaline** (was Borrowed Time): getting hit makes you faster and sprinting free for a moment. The damage adds up while it lasts, in 4 tiers (I: +15% for 1.5 s ... IV: +45% for 3 s); the icon shows the tier.
  - **Equivalence**: now starts when you get a FrailtyPlus injury or the Cadaver infection (60%+). It halves your injuries' time left (and every new one's while it lasts), the infection grows half as fast, you take 10% less damage and heal 2 HP every 5 s, even while bleeding. It lasts as long as your injuries (for the infection: as long as Equilibrium). Its injuries no longer pause.
- **Cheese Sense** uses the game's own compass: it lights up and shows the nearest scrap and the nearest exit (main entrance or fire exit, whichever is nearest), with distance and above / below. New settings: compass at the top of the screen, compass offset X / Y (the old compass bar settings are gone).
- **Grounded** is now called **Adapted** (Climate Soda).
- New icons for every buff (Adrenaline has one per tier), and new tooltips.
- The **Pill bottle is removed** (FrailtyMedical has the pills now): it's plain scrap again, not in the store or the Soda Machine. Numb and Regeneration are gone with it.
- Fixed: a store-bought drink's "Drink : [LMB]" tip stayed on screen after drinking it until you scrolled.
- Renamed inside too (no more "DrinkableSoda" anywhere): the config is now `Miles.Drinkable.cfg`. Your old settings and save data (empty cans, Soda Machine) are moved over once. FrailtyPlus must be 1.2.0 or newer for its parts.

## 1.1.1
- Fixed healing over time giving 1 HP less than it should (Peach Soda's Sugar Mend, the pills' Regeneration).
- README: every buff / debuff icon with what it does.

## 1.1.0
- Renamed from **DrinkableSoda** to **Drinkable**, so it can hold more than sodas. Your config (`Miles.DrinkableSoda.cfg`), saves and bought items carry over. Remove the old DrinkableSoda before installing.
- README: works with TZPPlus, FrailtyPlus, FrailtyMedical and EladsHUD+.

## 1.0.1
- With FrailtyMedical installed, the Pill bottle belongs to it (as Painkillers): Drinkable leaves the pills alone (not in the store, not a free drink). All of FrailtyMedical's items (its pills too) join the CONSUMABLES section, and both mods keep their bought items when everyone dies.
- Buff icons are the same size as FrailtyPlus' by default (new setting "Buff icon scale").

## 1.0.0
- First release: Red soda and Pill bottle can be used, plus 9 new sodas (Bolt Cola, Peach Soda, Sparkle Soda, ACE Soda, Vanilla Soda, Cheesy Soda, Climate Soda, Kosher Soda, Mystery Soda) with their own labels, each with its own buff. The pills give Numb (less damage) and Regeneration (healing), clear TZP's dizziness and (with FrailtyPlus) cure broken limbs and concussion.
- FrailtyPlus and EladsHUD+ are optional: without EladsHUD+ the buff icons show in the bottom-left corner.
- All of them can be bought in the store ($30 to $200; store sales take at most 20% off them). Scrap ones become empty cans / bottles that keep their value.
- Found drinks: pricier ones are rarer and worth more.
- Soda Machine ship upgrade (needs LethalLib, $500): one free random drink per player per day (same odds as finding them; can be a Pill bottle), then buy the drink you pick (press its button twice) at 50% of the store price, 2 to 5 of each drink a day (Climate, Cheesy and Kosher Soda: 0 to 3, higher amounts rarer), then sold out. Its flap tips open when a drink comes out, with the game's own sounds.
