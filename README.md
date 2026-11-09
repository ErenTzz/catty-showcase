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
| Touch gameplay | A three-stage bath session that measures cleaning coverage independently of the effects and allows one reward claim after completion. |
| Arcade mechanics | Four mini-games with distinct controls and scoring. Scrolling obstacles, platforms, and Paw Tap targets are reused through object pools. |
| Persistent pet simulation | The game saves pet needs when it goes into the background and accounts for elapsed time when the player returns. Soap and litter have persistent usage counts shared by the shop, inventory, and care activities. |
| Progression and economy | Mini-game coins and XP feed shared progression. Missions, daily rewards, and room-specific chests give players different ways to earn items and customize their pet's home. |
| Onboarding and adaptive UI | Configurable steps advance in response to gameplay events. Dialogue placement uses the highlighted control's bounds to keep it accessible on phones and tablets. |
| Localization | Unity Localization supports English, Turkish, German, Spanish, and French. Editor tooling migrates existing UI text into tables, and Play Mode checks cover both fixed labels and text generated at runtime. |
| Mobile lifecycle and rewarded ads | Connectivity changes update the game selection flow. The rewarded-ad flow handles pause and resume, and distinguishes a confirmed reward from dismissal or failure. |
| Seasonal content and build size | A Unity build step bakes the active seasonal artwork into scenes, prefabs, and animation references, excludes unused sprite atlases, and restores editable assets after the build. |
| Validation and release workflow | Unity Editor checks cover tutorial content, localization, and chest behavior. A Git pre-commit hook blocks generated files and local tooling artifacts from being committed. |

[**Read the engineering case study**](docs/engineering.md) for the decisions behind these systems.

## More from the game

<div align="center">

<a href="media/progression.jpg"><img src="media/progression.jpg" width="160" alt="Catty's level-up celebration" /></a>
<a href="media/platforming.jpg"><img src="media/platforming.jpg" width="160" alt="Cloud platforming mini-game" /></a>
<a href="media/chests.jpg"><img src="media/chests.jpg" width="160" alt="Chest reward screen" /></a>
<a href="media/shop.jpg"><img src="media/shop.jpg" width="160" alt="Room customization shop" /></a>

</div>

Store screenshots are from the [Google Play listing](https://play.google.com/store/apps/details?id=com.thehookgames.catty). This portfolio repository contains gameplay media and a technical case study. The Unity project is private.

**Eren Toksöz** · [GitHub profile](https://github.com/ErenTzz)
