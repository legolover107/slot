<div align="center">

<img src=".github/resources/banner.png" width="100%" alt="slot. A bespoke, Game Boy-centric frontend for the Anbernic RG SP.">

<a href="LICENSE"><img src="https://img.shields.io/github/license/slot-cfw/slot?style=for-the-badge&labelColor=242429&color=4d4d57" height="36" alt="License"></a>
<a href="https://github.com/slot-cfw/slot/stargazers"><img src="https://img.shields.io/github/stars/slot-cfw/slot?style=for-the-badge&labelColor=242429&color=4d4d57" height="36" alt="Stars"></a>
<a href="https://github.com/slot-cfw/slot/releases"><img src="https://img.shields.io/github/downloads/slot-cfw/slot/total?style=for-the-badge&labelColor=242429&color=4d4d57" height="36" alt="Downloads"></a>
<a href="https://slot-cfw.fyi"><img src="https://img.shields.io/badge/Guide-slot--cfw.fyi-4d4d57?style=for-the-badge&labelColor=242429" height="36" alt="Docs"></a>
<a href="https://discord.gg/NYRWsSuPUu"><img src="https://img.shields.io/badge/Discord-4d4d57?style=for-the-badge&labelColor=242429&logo=discord&logoColor=white" height="36" alt="Discord"></a>

</div>

---

# What is slot?

A bespoke, Game Boy-centric frontend for the Anbernic RG SP.

Has support for GBA, GBC, and GB titles only.

> [!IMPORTANT]
> ROMs must be unzipped. slot does not read `.zip` or `.7z` files.

A full user guide can be found at [slot-cfw.fyi](https://slot-cfw.fyi).

---

# What does it look like?

<p align="center">
<img src=".github/resources/screenshots/carousel.gif" width="48%" alt="Scrolling the cart carousel across the Game Boy Advance, Game Boy and Game Boy Color shelves">
<img src=".github/resources/screenshots/core-picker.gif" width="48%" alt="Flipping a cart to its circuit board to choose mGBA or gpSP">
</p>

<p align="center">
<img src=".github/resources/screenshots/link.gif" width="96.5%" alt="Two SPs racing in Mario Kart over the emulated link">
</p>

---

# Added in this fork

This fork, **slot-blow**, adds three features that make your carts behave like real, decades-old cartridges.
They all live under **Quick Menu > Gameplay > Experimental**, and you can turn each one on or off there.

<p align="center">
<img src=".github/resources/screenshots/fork/experimental-menu.png" width="60%" alt="The Experimental page of the quick menu with Dusty Carts, Label Wear and Dry Batteries">
</p>

## Dusty Carts: blow on the cart

One cart in ten fails to boot. Instead of the game, the screen shows scrambled tiles and the emulator stays paused.
Hold or mash **B** to blow on the cart. When the breath meter fills, the cart pops back out to the shelf,
slides back in, and gets a new roll of the dice.

- The glitch looks different on each platform: a garbled logo on GB, garish tiles on GBC, stripes on GBA.
- It tears harder the more you blow.
- A cart resumed at boot never comes up dusty.

<p align="center">
<img src=".github/resources/screenshots/fork/dusty-carts.gif" width="96.5%" alt="A cart boots to scrambled tiles, B is held to blow on it, and the cart is ejected and slides back in">
</p>

## Dry Batteries: solder in a new cell

One cart in ten that boots clean shows the notice from the Pokémon games instead:
*"The internal battery has run dry. The game can be played."* Reading on does not start the game. It opens
the cart on a soldering bench:

1. **Desolder** the old cell: hold **A** on each tab until the solder melts.
2. **Solder** the new cell: hold **A** to heat the iron and let go while the gauge is in the green.
   Let go too early and you get a dull cold joint. Hold too long and the pad burns, and you have to wait for it to cool.
3. Once both joints shine, the notice comes back to say clock-based events will occur again, and the game starts.

The bench is drawn in the game's own style, with a Gen 3 text box on GBA, a Gen 2 text box on GB/GBC and four greys on GB.
Dusty Carts rolls first, so a cart you just blew on can still have a dry battery.

<p align="center">
<img src=".github/resources/screenshots/fork/dry-battery.gif" width="96.5%" alt="The dry battery notice, desoldering the old cell, a cold joint, two good joints, then the fixed notice">
</p>

## Label Wear: carts age as you play

Play time is tracked per cart (in `Config/play_time.txt`), and the label wears down as the hours add up.
It fades and yellows, then gathers scratches, a thumb smudge and frayed edges, and finally two or three
dog-eared or torn corners. Each cart keeps its own damage in the same places. Wear goes up in steps from
1 hour to 100 hours of play.

<p align="center">
<img src=".github/resources/screenshots/fork/label-wear-steps.png" width="96.5%" alt="The same label after 0, 5, 20, 50 and 100 hours of play">
<br>
<sub>The same label after 0 h, 5 h, 20 h, 50 h and 100 h of play.</sub>
</p>

<p align="center">
<img src=".github/resources/screenshots/fork/label-wear.gif" width="96.5%" alt="Scrolling along the shelf from a new cart to one played for 100 hours">
</p>

## Testing

To skip the dice roll, set these environment variables:

| Variable    | Values             | Effect                                           |
|-------------|--------------------|--------------------------------------------------|
| `SLOT_DUST` | `always` \| `off`  | Every cart comes up dusty, or none does          |
| `SLOT_DRY`  | `always` \| `off`  | Every clean boot has a dry battery, or none does |

---

# Supported Devices

| Device                | Supported | Since Version |
|-----------------------|-----------|---------------|
| Anbernic RG SP        | **Yes**   | Always        |
| Anbernic RG 34XX      | **Yes**   | 1.4.0         |
| Anbernic RG 34XXSP    | **Yes**   | 1.4.0         |
| Anbernic RG 35XXSP    | **Yes**   | 1.5.0         |
| Anbernic RG 35XX Plus | **Yes**   | 1.5.0         |
| Anbernic RG 35XX-H    | **Yes**   | 1.7.0         |
| Anbernic RG 35XX Pro  | **Yes**   | 1.15.0        |
| Anbernic RG 28XX      | **Yes**   | 1.6.0         |

If you have one of the untested devices, or have tried slot on a device not listed,
please [open an issue on GitHub](https://github.com/slot-cfw/slot/issues) and let me know how it went.

---

# Discord Community

slot has a [Discord server](https://discord.gg/NYRWsSuPUu) for questions, sharing setups, and talking about the project.

It is open to everyone in the slot universe. That includes folks running or building forks of slot.

There is no reason for this community to be fragmented so long as we are having fun!

---

# AI Disclosure

The Rust frontend, and the SVGs on [slot-cfw.fyi](https://slot-cfw.fyi), were put together by Claude.
I reviewed everything that was produced. All documentation is 100% free-range, meatbag prose.

My goal with this project was to recreate the feeling of playing my GBA SP in the back seat as a kid,
but with a few modern creature comforts.

Nothing about this project is exciting or groundbreaking from a technological perspective, and as a
result, I delegated the glue code. mGBA, gpSP and Gambatte have been around forever and are the true stars of
this show. The incredible skeuomorphic art is the work of [Markus](https://github.com/MarkusMaribu), an
artist who saw the bare-bones version and offered to dress it up.

I understand if my use of AI is a dealbreaker for you. Just know it's the least interesting part of
what's here.

Figured I should share the end result of all the wasted water. ✌🏻

---

# Spread Joy!

I've spent a lot of time building slot.

If you enjoy using it and feel inclined to pay it forward, go do something nice for someone! ❤️
