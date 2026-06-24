# Algae World - Gameplay Fact Card

## App Identity
- **App Name**: Algae World
- **Bundle ID**: com.rosewood.algaeworld.game
- **Version**: 1.0
- **Platform**: iOS (iPhone only)
- **Minimum iOS**: 15.0
- **Framework**: SpriteKit + Objective-C
- **Orientation**: Portrait only
- **Age Rating**: 4+
- **Network**: Fully offline, no ads, no IAP, no analytics, no tracking

## Core Gameplay Loop
1. **Drag the lamp** to illuminate the algae tank. Light intensity varies by zone (direct / refracted / filtered / dark).
2. **Tap nutrient capsules** (N / P / K) to feed algae. Each species prefers a different nutrient.
3. **Watch the HUD**: light state chip (GOOD / FED / OVER), oxygen bar, nutrient bars (N/P/K), order panel, timer ring.
4. **Complete the compound order** before the 30-second timer runs out.
5. **Keep algae alive**: HP below survival threshold = level failure.
6. **Earn stars** based on survival rate and total population.

## Algae Species (4 types)
| Species | Nutrient | Light Preference | Compound |
|---------|----------|------------------|----------|
| Green Algae (AWGreenAlgae) | N (Nitrogen) | Direct light | Chlorophyll |
| Cyanobacteria (AWCyanobacteria) | P (Phosphorus) | Refracted light | Phycocyanin |
| Rhodophyta / Red Algae (AWRhodophyta) | K (Potassium) | Filtered light | Phycoerythrin |
| Chrysophyta / Golden Algae (AWChrysophyta) | Balanced N/P/K | Moderate light | Carotenoid |

## Compound Orders (8 types)
- Chlorophyll (Phase 1)
- Phycocyanin (Phase 2)
- Phycoerythrin (Phase 3)
- Carotenoid (Phase 3)
- Omega-3 (Phase 3)
- Antioxidant (Phase 3-4)
- Biodiesel (Phase 4)
- SpaceNutrient (Phase 5 - ultimate)

## Level Progression (50 levels, 5 phases)
- **Phase 1 (L1-L10)**: Green algae + Chlorophyll orders. Tutorial: light direction, optimal zone, over-illumination.
- **Phase 2 (L11-L20)**: +Cyanobacteria + Phycocyanin orders. Introduces nutrient injection and competition.
- **Phase 3 (L21-L30)**: +Rhodophyta + Chrysophyta. Phycoerythrin, Carotenoid, Omega-3, Antioxidant orders.
- **Phase 4 (L31-L40)**: Day/Night cycle. Oxygen pressure mechanic. Biodiesel and Antioxidant orders.
- **Phase 5 (L41-L50)**: Space cultivator challenge. SpaceNutrient synthesis. All mechanisms combined.

## Star Rating System
- **3 stars**: survival rate >= 80% AND total population >= target
- **2 stars**: survival rate >= 50% AND total population >= target/2
- **1 star**: survival rate > 0
- **0 stars**: all algae dead (level failed)

## Nutrient Mechanics
- Nutrients (N/P/K) decay exponentially based on half-life constants (AW_NUTRIENT_HALFLIFE_N/P/K).
- Each capsule tap injects 0.30 nutrient units (capped at 1.0).
- Nutrient overload threshold triggers warning notification.
- Nutrient time-remaining is calculated via inverse half-life formula.

## Level Duration
- Every level lasts 30 seconds (AW_LEVEL_DURATION).

## HUD Elements
- Level label (top-left)
- Pause button (top-right)
- Phase chip
- Timer ring (counts down from 30s)
- Oxygen bar
- Nutrient bars (N / P / K)
- Order panel (target compound + progress)
- Light state chip per algae (GOOD / FED / OVER)

## Monetization
- None. No ads, no in-app purchases, no subscriptions.

## Data Collection
- None. All progress (level completion, stars) saved locally via AWDataManager.

## Template Residue Check
- No tw_*, game_01_*, Template, or other template residue found.
- All assets are original game-specific (AW* prefix).

## Debug UI
- showsFPS = NO
- showsNodeCount = NO
(Verified in SceneDelegate.m)
