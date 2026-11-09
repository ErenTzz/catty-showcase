[← Showcase](../README.md) · [Türkçe](engineering.tr.md)

# Catty engineering case study

Catty combines a persistent pet-care hub with short arcade sessions. The central design question was how to let each activity have its own controls and rules while keeping rewards and pet progression coherent across scenes.

```mermaid
flowchart LR
    Hub["Pet-care hub"] --> Care["Care activities"]
    Hub --> Arcade["Arcade mini-games"]
    Care --> Progress["Shared rewards and progression"]
    Arcade --> Progress
    Progress --> Hub
    Progress --> Save["Local persistence"]
    Hub --> Save
```

## Turning touch input into bath progress

Bath Time gives the player three tools in sequence. Each touch stroke contributes coverage to a region of the cat. The session checks whether the tool matches the current stage and whether the input applies to an active region. Coverage drives stage completion. The presentation layer shows dirt, foam, water, and progress as the session changes.

Separating coverage from presentation lets the visuals change while the completion rules stay consistent. The reward can be claimed only after the final stage, and the session tracks whether it has already been claimed. [See the interaction in motion.](../media/bath-gameplay.gif)

## Bringing mini-game rewards back to the hub

Each mini-game owns its playfield, input, and scoring. Session coins and pending XP are tracked during play and applied to shared progression through the result flow. The hub can use the resulting balances without knowing how a given mini-game scored the run. Mobile lifecycle handling also matters here because a player can pause the app or leave a scene while a session is in progress.

The tap-to-fly and platforming scenes recycle obstacle pairs and platforms using object pools. The pools can grow when the active playfield needs more objects. The reward flow and spawning logic serve different parts of the game and can be adjusted independently.

## Teaching actions in context

The tutorial represents onboarding as configurable steps. A step can show dialogue, highlight a control, or wait for a gameplay event. Event-driven completion keeps the instruction visible until the player performs the relevant action. Local progress records which parts of onboarding the player has completed.

Dialogue placement uses the highlighted control's screen bounds. This addressed a concrete tablet issue where the instruction card could cover a food recipe the player was being asked to select. The layout was checked on phone and tablet views after the change.
