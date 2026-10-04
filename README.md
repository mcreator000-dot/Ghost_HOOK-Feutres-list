# GHOST_HOOK Cheat Features


## 🎯 Combat — Aimbot Tab
| Feature | Description |
|---|---|
| **Silent Aim** | Redirects bullets/raycasts at target without moving your view. Toggle + keybind. |
| **Silent Aim Method** | `Ghost hook old` (spoofs AimPart CFrame) vs `new` (fake_part + Bullet stack-checked Raycast redirect + `ProjectileInflict` seed-timing fix). |
| **Aim Part** | Chooses which body part to target (Head, FaceHitBox, Torso, limbs, etc.). |
| **Aim Assist** | Smoothly steers camera toward silent-aim target (camera-based, not mouse-based). |
| **Target Players** | Allows silent aim to target other players. |
| **Target AI** | Allows silent aim to target NPCs in `AiZones`. |
| **Target Helicopters** | Allows targeting `MI24V` / `BTR80` vehicles via `CollisionPilot`. |
| **Team Check** | Skips teammates (compares `Journey.Clan.CurrentClan`). |
| **Wallbang** | Sets `testwallbang` flag — shoots through obstructed targets. |
| **Wallbang TP** | Teleports you past the wall for one window; fires only after `UAC.LastVerifiedPos` converges. |
| **Corner Shoot** | Auto-finds a nearby origin (corner peek) with line-of-sight to target. |
| **Random Hit Part** | Randomly picks a body part each shot (evades hitbox checks). |
| **Lift Hitboxes** | Physically shifts target characters up by N studs to desync hitboxes. |
| **Target Chams** | Highlights current silent-aim target with a colored Highlight. |
| **Hit Chance (Triggerbot)** | Sets probability % that a trigger pull actually fires. |

### Rage Bot Sub-tab
| Feature | Description |
|---|---|
| **Rage Bot** | Full auto-fire rage bot — ignores FOV, auto-fires on lock. |
| **Rage Max Distance** | Maximum range for rage targeting (up to 4000m). |
| **Hit Chance (%)** | Probability each shot is allowed to fire. |
| **Min Damage** | Only fire if target's health ≥ this value. |
| **Target Priority** | Distance / Health / FOV sorting. |
| **Auto Fire** | Automatically discharges when locked. |
| **Head Only** | Restricts targeting to Head part. |
| **Velocity Prediction** | Leads moving targets. |
| **Prediction Multiplier** | Scales the lead amount. |
| **Backtrack** | Rewinds target position using `AssemblyLinearVelocity`. |
| **Backtrack MS** | How far back (in ms) to rewind. |
| **Auto Wallbang** | Fires through thin walls (validated against wall thickness). |
| **Max Wall Thickness** | Thickness threshold for wallbangable geometry. |
| **Auto Scope** | Auto-zooms camera FOV while rage is active. |
| **Shot Delay** | Minimum time between shots. |

### Trigger Bot Sub-tab
| Feature | Description |
|---|---|
| **Triggerbot** | Auto-fires when crosshair is on a triggerable target. |
| **Shoot on Manipulated** | Fires when a manipulated origin is found (even if hidden). |
| **Hit Chance (%)** | Probability per trigger pull. |
| **Peek Blink** | Freezes replicated position while peeking; snaps back the instant you shoot. |

### Bullet Tracers Sub-tab
| Feature | Description |
|---|---|
| **Bullet Tracer** | Draws a visual tracer from origin to target. |
| **Tracer Style** | Tracer 1 / Tracer 2 / Beam / Dark Beam Lines / Bent. |
| **Tracer Thickness / Lifetime** | Visual tuning sliders. |

### Gun Mods Sub-tab
| Feature | Description |
|---|---|
| **Rapid Fire** | Forces `FireRate` to a custom delay (up to 3000 RPM). |
| **Force Hit** | 3 methods: `instant hit` (back-dates timestamp), `Silent force-hit` (fabricates RaycastResult), `validation override` (swaps hit part on `ProjectileInflict`). |
| **No Recoil** | Nullifies spring `shove` calls. |
| **Magic Bullet** | Fabricates the RaycastResult the Bullet module asks for. |
| **No Spread** | Returns `AccuracyDeviation = 0` on GetAttribute. |
| **No Gun Bob** | Zeros the spring `update` return (viewmodel bob). |
| **Instant Aim** | Sets `AimInSpeed` / `AimOutSpeed = 0`. |
| **Unlock Firemodes** | Forces `FireModes = {"Auto","Semi"}`. |
| **One Tap** | Fires 10 rounds in a single shot (no charge ramp). |
| **Instant Reload** | Hooks `fps_reloadtypes.magazine` / `loadByHand` for one-frame reloads. |
| **Auto Reload** | Watchdog that invokes `Reload` remote when mag ≤ threshold. |
| **Auto Reload At** | Reload threshold (0 = only when empty). |
| **Auto Refill Mag** | Background loop loads magazines from compatible ammo via `InventoryMove`. |
| **Instant Equip** | Speeds up equip animation to 15×. |

### FOV Sub-tab
| Feature | Description |
|---|---|
| **Use FOV** | Restricts silent aim to FOV circle. |
| **Show FOV** | Renders FOV circle. |
| **FOV Outline** | Renders glow ring around FOV. |
| **FOV Radius / Glow Intensity** | Visual tuning. |

### Status Bar Sub-tab
| Feature | Description |
|---|---|
| **Crosshair Status Bar** | Shows target visibility/manipulation state. |
| **Force Status Bar** | Always visible (not just when SA active). |
| **Width / Height / Offset** | Layout sliders. |

---

## 👁 Visuals — Player ESP
| Feature | Description |
|---|---|
| **ESP Master Switch** | Master toggle for all player ESP. |
| **Infinite Range** | Shows ESP beyond streamed distance using `UAC.LastVerifiedPos`. |
| **Max Distance Limit** | Culls ESP beyond N studs. |
| **Name ESP** | Shows real name above head. |
| **Display Name ESP** | Shows display name. |
| **Health ESP** | Neon gradient health bar with glow. |
| **Distance ESP** | Distance in meters. |
| **Weapon ESP** | Shows currently equipped weapon. |
| **Skeleton ESP** | Draws bone lines between joints. |
| **Chams** | Highlight-based wall-visible chams (`AlwaysOnTop` or Occluded). |
| **Highlight High KD** | Marks players with K/D > 5 as `[CHEATER]` and colors chams. |

### Object ESP Sub-tab
| Feature | Description |
|---|---|
| **Dropped Items ESP** | Labels dropped loot with name + amount. |
| **Corpse ESP** | Labels corpses with distance. |
| **Container ESP** | Labels whitelisted containers. |
| **Container Whitelist** | Multi-select list of container types. |
| **Exit ESP** | Labels extraction points. |
| **Quest Item ESP** | Labels quest items. |
| **Vehicle ESP** | Labels vehicles. |
| **AI Chams ESP** | Highlights NPCs. |
| **AI Nametag ESP** | Name above NPCs. |

### Minecraft Sub-tab
| Feature | Description |
|---|---|
| **Minecraft UI** | Full Minecraft-style inventory/hotbar/health/food/water bar overlay. |

---

## 🏃 Movement
### Character Sub-tab
| Feature | Description |
|---|---|
| **Omni Sprint** | Always sprints when moving (forces WalkSpeed 18). |
| **Speed Hack** | Forces `WalkSpeed` to custom value every frame (10–22 sps). |
| **Noclip (Door Spam)** | Disables collision + spams door remote + slow diagonal movement. |
| **Walk on Water (Jesus)** | Spawns a collidable part under you when on water. |

### Third Person Sub-tab
| Feature | Description |
|---|---|
| **Third Person** | Forces third-person camera with adjustable distance. |
| **Lock Body to Camera** | Rotates HRP to camera look direction. |
| **Zoom Fade** | Fades character out while aiming/scoping. |

### Flyhack Tab
| Feature | Description |
|---|---|
| **Flyhack** | WASD + Space/Ctrl free flight. |
| **Fly Speed / Vertical Speed** | Speed sliders. |

### DESYNC Tab
| Feature | Description |
|---|---|
| **Desync Enabled** | Offset/rotate your replicated position from real position. |
| **Visualize Character** | Shows a ghost clone at the real position (neon BoxHandleAdornment). |
| **X/Y/Z Offset** | Positional desync sliders (−10 to 10). |
| **X/Y/Z Rotate** | Rotational desync sliders. |
| **Random Rotation / Position** | Randomizes desync each frame. |
| **Velocity Desync** | Sets `AssemblyLinearVelocity` to a spoofed value. |
| **Look Vector Spoof** | Spoofs pitch via `UpdateTilt` remote (Up/Down/Straight/Custom). |

### Anti-Aim Sub-tab
| Feature | Description |
|---|---|
| **Anti Aim** | Flips or spins your character model to desync hitboxes. |
| **Resolve Desync** | Positions enemies at their `UAC.LastVerifiedPos`. |
| **Position Offset** | Custom offset for AA. |
| **UG Resolver (Hold X)** | Teleports you underground for 0.10s repeatedly. |
| **Anti Drown** | Blocks `Drowning` FireServer + resets attribute. |

### TP Kill Sub-tab
| Feature | Description |
|---|---|
| **TP Kill** | Teleports ~200 studs above silent-aim target and auto-fires. |
| **Height Offset** | Teleport height. |
| **Show Charge Bar** | 5s cooldown bar. |
| **Auto Look at Target** | Camera snaps to target. |
| **Auto Triggerbot** | Fires automatically once verified. |
| **Glow Size** | Visual tuning. |

### Movement Extras Sub-tab
| Feature | Description |
|---|---|
| **Bunny Hop** | Auto-jumps with custom power when on ground. |
| **No Fall Damage** | Forces `Landed` state below −12.5 Y velocity. |
| **Car Speedhack** | Multiplies vehicle velocity (1×–10×, capped at 320). |
| **Underworld Walk** | Walks underground with AlignPosition/Orientation and free-look camera. |
| **Teleport Vehicle To Me** | Pivots nearest vehicle with a `VehicleSeat` to your position. |

---

## 🧑 Player
### ViewModel Sub-tab
| Feature | Description |
|---|---|
| **ViewModel Changer** | Offsets arms/weapon via Motor6D C0. |
| **Arm / Body / Gun Chams** | Recolors viewmodel/body parts with material override. |
| **Remove Arms** | Hides viewmodel arms. |
| **Always Suit Arms** | Clones `CivilianShirt` + Blackout `CombatGloves` onto viewmodel. |

### Anti Aim Tab
(covered above in Movement)

### Camera Sub-tab
| Feature | Description |
|---|---|
| **FOV Changer** | Writes `GameplaySettings.DefaultFOV`. |
| **Zoom** | Hold/toggle key to zoom FOV down. |
| **Hit Effect (Stars)** | Particle burst on hit. |
| **Damage Numbers** | Floating `-N` damage text with drift/gravity. |
| **No Muzzle Flash** | Disables muzzle flash emitters/lights. |

---

## 🌍 World
### Environment Sub-tab
| Feature | Description |
|---|---|
| **Time Changer** | Sets `Lighting.ClockTime` (1–24). |
| **Ambient Changer** | Sets `Lighting.Ambient` / `OutdoorAmbient`. |
| **No Fog** | Zeros `Atmosphere.Haze` / `Density`. |
| **No Grass** | Sets `Terrain.Decoration = false`. |
| **No Shadows** | `Lighting.GlobalShadows = false`. |
| **No Leafs** | Hides foliage with SurfaceAppearance. |
| **No Clouds** | Disables Clouds instances. |
| **No Screen Effects** | Hides visor/mask/flashbang effects. |
| **Xray** | Sets world parts to 0.5 transparency. |
| **No Landmines** | Destroys PMN2/MON50/GrenadeTrap models. |
| **Custom Skybox** | 7 presets with brightness + X/Z rotation. |
| **Custom Muzzle Flash** | Recolors muzzle flash lights/particles. |

### Radar Sub-tab
| Feature | Description |
|---|---|
| **Radar** | External 2D radar with markers, cardinal lines, offscreen indicators. |

### Performance Sub-tab
| Feature | Description |
|---|---|
| **Force Render All (3k)** | Streams content around all players within 12000 studs. |
| **Lite Mode (FPS Saver)** | One-click disable of heavy visuals. |
| **Extreme Potato Mode** | Strips materials, shadows, decals, post-effects. |

### Inventory / Finder Sub-tab
| Feature | Description |
|---|---|
| **Inventory Checker** | Shows targeted player's inventory (hotbar + full grid). |
| **Item Finder** | Scans other players' inventories for whitelisted items. |
| **Autosort** | 14-tier vault categorization + `InventoryMove` replay. |

### Freecam Sub-tab
| Feature | Description |
|---|---|
| **Freecam** | Detached camera with WASD/E/Q flight + `ReplicationFocus` spoofing. |
| **Show Distance ESP** | Distance label from camera to character. |
| **Vis Check From Real Character** | Visibility checks use real character position. |

---

## 🔧 Misc
| Feature | Description |
|---|---|
| **Target Info Panel** | Draggable panel showing target name, K/D, visibility, weapons, health. |
| **Target Line** | Line from crosshair to target. |
| **All Equipment** | Restores map/compass/GPS/radio inventory entries. |
| **No Melee Cooldown** | Hooks `MeleeWeaponDefault` to clear `useDebounce`. |
| **Melee Reach** | Sets `RangeNormal` / `RangePower` on melee tool. |
| **Show Report Count** | Draggable counter showing total reports against you. |
| **Report Notifications** | Red notification when reported. |
| **Hit Logs** | On-screen valid/invalid hit feed. |
| **Whisper Timer HUD** | Predicts Whisper boss spawn from weather forecast. |
| **Cheaters Lobby** | Teleports whitelisted NPCs into a circle around you. |
| **Mod Detector** | Flags players with high premium level or invisible body parts. |
| **Cheater Detector** | Flags players with K/D > 5 or high HSR/flag counts. |

---

## 🔊 Misc Sounds
| Feature | Description |
|---|---|
| **Custom Hit Sound** | 14 preset hitmarker sounds. |
| **Custom Gun Sound** | 8 preset gunshot sounds. |
| **Gun Sounds Volume** | Volume scaler for gun sounds. |
| **Hitmarker Volume** | Volume scaler for hitmarker sounds. |
| **Mute Breathing** | Silences gas mask breathing loop. |
| **No Reapir Blur** | Hides `PrismScopeGui.Sight.StaticLCD`. |

### Grenade Sub-tab
| Feature | Description |
|---|---|
| **Predict Trajectory** | 3D neon beam + blast ring for thrown grenade. |
| **Target Lineup** | Solves optimal arc to hit targeted player. |
| **Target Arc Mode** | Auto / Low / High / Airburst. |
| **Auto Throw** | Rewrites `ServerProjectile` direction to hit target. |

---

## ⚙️ Settings
| Feature | Description |
|---|---|
| **Config Save/Load/Delete** | Full config management with autoload. |
| **Skin Changer** | Forces `Skin` attribute + repaints viewmodel. |
| **Unlock All Skins** | Populates `Purchases.Skins` folder with all skin entries. |
| **Knife Changer** | Swaps melee inventory ref + overlays model in viewmodel. |
| **Keybind Indicator** | On-screen list of active keybinds. |
| **Toggle Menu Key** | Rebindable menu key. |
| **Hide Server Info** | Hides `ServerInfo` GUI. |
| **Hide Name In Chat** | Replaces your name with "Hidden" in chat. |
| **Rejoin Server** | Teleports back to same JobId. |
| **NPC Teleport** | Teleports lobby NPCs to you. |
| **Custom Theme** | Accent color picker. |

---

## 🔌 Under-the-Hood Hooks (not UI-visible but active)
- **Enum.KeyCode `__index` hook** — prevents mouse-button keybind crash storms.
- **`game.__index` hook** — hides desync CFrame reads from game scripts.
- **`game.__newindex` hook** — blocks Lighting/Camera writes while features are active.
- **`game.__namecall` hook** — intercepts `Raycast`, `GetAttribute`, `Play`, `InvokeServer`, `FireServer`, `Create` (TweenService).
- **`fps_reloadtypes.magazine` / `loadByHand`** — instant reload.
- **`CreateBullet` hook** — silent aim redirect + One Tap burst + tracer.
- **`updateClient` hook** — Instant Aim, Force Auto, Unlock Firemodes, Rapid Fire.
- **Spring `shove` / `update` hooks** — No Recoil / No Gun Bob.
- **`MeleeWeaponDefault` hooks** — No Melee Cooldown.
- **Hitscan spoof** — teleports root for one frame past obstruction.
- **Wallbang TP** — gated on `UAC.LastVerifiedPos` convergence.
- **TP Kill verification** — waits for server to confirm teleport before firing.

---

**Total: ~120 individually toggleable gameplay-advantage features** across 30+ tabs, plus 7 low-level metamethod/function hooks.
