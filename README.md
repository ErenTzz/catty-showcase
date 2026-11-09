<div align="center">

[English](README.md) · [Türkçe](README.tr.md)

# Catty: Virtual Cat&Mini Games

**A virtual pet game for Android, built with Unity and C#.**

Care for a cat, play short arcade mini-games, and use what you earn to look after your pet and unlock new rooms.

[**Play on Google Play**](https://play.google.com/store/apps/details?id=com.thehookgames.catty) · [**Watch gameplay**](#gameplay-demo) · [**Read the engineering case study**](docs/engineering.md)

<img src="media/care.jpg" alt="Catty's home and pet care interface" width="225" /> <img src="media/mini-game.jpg" alt="A tap-to-fly mini-game with yarn obstacles and a coin pickup" width="225" /> <img src="media/rooms.jpg" alt="Catty in the greenhouse room" width="225" />

</div>

## My role

I'm **Eren Toksöz**, the Unity developer behind Catty. My work spans C# gameplay, mobile UI and touch interaction, progression and save flows, onboarding, and the Android release. The game is published on Google Play under **theHookGames**.

## Gameplay demo

<table>
<tr>
<th align="center" width="25%">Bath Time</th>
<th align="center" width="25%">Paw Tap</th>
<th align="center" width="25%">Tap to Fly</th>
<th align="center" width="25%">Item Collection</th>
</tr>
<tr>
<td align="center" valign="top">
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/bath-gameplay.mp4"><img src="media/bath-gameplay.gif" width="175" alt="Soap, rinse, and dry Catty." /></a><br />
Soap, rinse, and dry Catty.<br />
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/bath-gameplay.mp4"><strong>Watch video (MP4)</strong></a>
</td>
<td align="center" valign="top">
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/paw-tap.mp4"><img src="media/paw-tap.gif" width="175" alt="Tap targets in time to build a combo." /></a><br />
Tap targets in time to build a combo.<br />
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/paw-tap.mp4"><strong>Watch video (MP4)</strong></a>
</td>
<td align="center" valign="top">
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/tap-to-fly.mp4"><img src="media/tap-to-fly.gif" width="175" alt="Fly through gaps between yarn obstacles." /></a><br />
Fly through gaps between yarn obstacles.<br />
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/tap-to-fly.mp4"><strong>Watch video (MP4)</strong></a>
</td>
<td align="center" valign="top">
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/item-collection.mp4"><img src="media/item-collection.gif" width="175" alt="Move the basket to catch falling supplies." /></a><br />
Move the basket to catch falling supplies.<br />
<a href="https://raw.githubusercontent.com/ErenTzz/catty-showcase/main/media/item-collection.mp4"><strong>Watch video (MP4)</strong></a>
</td>
</tr>
</table>

The mini-game clips were captured in Unity with automated inputs. All MP4 clips are silent.

## Engineering highlights

| Area | What I built |
| --- | --- |
| Touch gameplay | A staged bath interaction that tracks cleaning coverage separately from its visual feedback. Each stage accepts its matching tool, and a completed session can grant its reward once. |
| Arcade sessions | Separate scenes for tap-to-fly, platforming, item collection, and Paw Tap. Scrolling obstacles and platforms use object pools to reuse spawned objects. |
| Progression | Mini-game results feed shared coin and XP progression. Local saves preserve pet state, supplies, and onboarding progress between sessions. |
| Onboarding and mobile UI | Configurable tutorial steps wait for gameplay events before advancing. Contextual highlights and dialogue guide the player through the relevant controls, with layout checks on phone and tablet aspect ratios. |

[**Read the engineering case study**](docs/engineering.md) for the decisions behind the bath interaction, reward flow, and tutorial.

## More from the game

<div align="center">

<a href="media/progression.jpg"><img src="media/progression.jpg" width="160" alt="Catty's level-up celebration" /></a>
<a href="media/platforming.jpg"><img src="media/platforming.jpg" width="160" alt="Cloud platforming mini-game" /></a>
<a href="media/chests.jpg"><img src="media/chests.jpg" width="160" alt="Chest reward screen" /></a>
<a href="media/shop.jpg"><img src="media/shop.jpg" width="160" alt="Room customization shop" /></a>

</div>

Store screenshots are from the [Google Play listing](https://play.google.com/store/apps/details?id=com.thehookgames.catty). This portfolio repository contains gameplay media and a technical case study. The Unity project is private.

**Eren Toksöz** · [GitHub profile](https://github.com/ErenTzz)
