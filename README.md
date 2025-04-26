#### (1.0.11)

**Fixes & Changes:**

- Adapted Sword and Abilities fixes.  
- Removed a few redundant items.
- Fixed crash caused by double knockback; issue with being unremovable and not saved is now resolved.  
- Fixed `SmartLeft/RightMagSet` only affecting magazine size after reloading.  
- TI items that were limited to specific unit bases are now unlimited.  
- Fixed `SmartProjSet` not working properly.  
- On-hit effect damage now scales with the unit’s damage multiplier.  
- Converted `summonRider` item to `SmartSummonRider`.  
- `TransformAddDelay` removed; all transformed items are now Smart.  
- Fixed transformation to rider on death not working due to an unticked variable.  
- Fixed knockback items not functioning correctly.  
- Fixed `MeleeAddStick` crashing the game.  
- `SmartOnHit` items now include additional modifiers defined by position:  
  - **X** = Delay per spawn  
  - **Y** = Damage Multiplier
  - **Z** = Random position offset  
- `MeleeAddDash` is now a *Smart* item with scale adjustment:  
  - **X** = Force Multiplier
  - **Y** = Delay Multiplier
  - **Z** = Swing Range Multiplier  
- `SmartProjSet` includes additional scale modifiers defined by position:  
  - **X** = Block power needed  
  - **Y** = Allowed hits  
  - **Z** = Screen shake  
- `SmartRangedSet` includes additional scale modifiers defined by position:  
  - **X** = Recoil
  - **Y** = Projectiles Amount  
  - **Z** = Shoot Delay 
- `SmartMeleeSet` includes additional scale modifiers defined by position:  
  - **X** = Screenshake Multiplier
  - **Y** = Required Power To Parry  
  - **Z** = Self Damage Multiplier  
- `SmartOnHit` with X = -1 now randomly spawns explosion index.  
- Split `SmartOnHit` into three item types:  
  - For all weapons  
  - For all projectiles  
  - For all units  
- All halved/nulify/doubled items and custom transformations are now Smart items.  
- Some smart items changed into multiplier instead of actual value from their modified components for easier implementation. Affected usually those whose value is like 1000+ like SmartMeleeSet.

**New Items:**

- `SmartRangeDistance`
  - **X** = Unit Attack Distance
  - **Y** = Weapon Distance 
  - **Z** = Always Attack (0 = false, 1 = true)  
- `AdaptiveArrowVolley`  
- `UnitDisableFriendlyFire`  
- `SmartUnitBalanceModifier`  
  - **X** = Static Force Multiplier
  - **Y** = Overall Multiplier 
  - **Z** = Gravity
- `SmartSFXManager`
  - **X** = Pitch
  - **Y** = Volume
  - **Z** = Category
  - **Position X** = Effect
- `SmartUnitVocalManager`  
  - **X** = Pitch
  - **Y** = Volume
  - **Z** = Category
  - **Position X** = Effect
- `SmartUnitWeaponSoundManager`  
  - **X** = Pitch
  - **Y** = Volume
  - **Z** = Category
  - **Position X** = Effect
- `SmartUnitRigidbodyLimiter`  
  - **X** = Max velocity
  - **Y** = Max angular velocity
- `SmartUnitRigidbody`  
  - **X** = Mass  
  - **Y** = Drag  
  - **Z** = Angular drag  
- `SmartUnitDupe`  
  - **X** = Spawn amount  
  - **Y** = Expiration time (0 = does not expire)  
  - **Z** = Spawn interval (0 = spawn once)  
- `SmartWeaponHoldableRight/Left`  
  - **X** = Proportional force  
  - **Y** = Joint angular drive  
  - **Z** = Joint limit  
- `SmartHealingItem`  
  - **X** = Heal amount  
  - **Y** = Heal rate (seconds)  
  - **Z** = Healing type (Brawl Star Style = 0 / Constant = 1 / Percentage-Based = 2)  
- `SmartMovingProp`  
  - **X** = Index Object To Move (0 is first, 1 is second, test from 0 to upward)  
  - **Y** = Add Speed Per Second 
  - **Z** = Keep Moving After Death (0 = false, 1 = true)  
  - **Position Offset** affects rotation axis, speed, and uses Euler angles. Only affects `MeshRenderer`, even outside of props.   
- `SmartConditionalEventManager`  
  - **X** = Cooldown multiplier (affects min/max)  
  - **Y** = Min Unit distance to target
  - **Z** = Max Unit distance to target 
- `SmartConnectedTransform`  
  - **X** = Transform delay  
  - **Y** = Range to target  
  - **Z** = Damage required  
  - Allows team-linked transformations — if one unit transforms, all linked ones do as well (only if they have this ability). Does not stack with other transformation abilities.  
- `DisableUnitOutline`  
- `SmartSummonRider`  
  - **X** = Spawn amount  
  - **Y** = Expiration time (0 = does not expire)  
  - **Z** = Spawn interval (0 = spawn once)  
- `MoreRider`:
  - **Position** defines mount offset; duplicates rider if one exists.
- `UnitTargetSelf`
- `SmartMeleeKnockback`
  - **X** = On Impact Force Multiplier  
  - **Y** = Impact Multiplier 
  - **Z** = Enemy Mass Pow

#### (1.0.10)

- Fixed ice explosion particle now showing up.
- Fixed the SmartOnHitEffect causing the weapon to be wonky.
- Fixed some explosions not doing damage properly.

#### (1.0.9)

- Fixed ColorableProjModel and ColorableProjParticle doesn't works properly.

#### (1.0.8)

**Changes**

- Removes sound during weapon swaps.
- Removed all previous manual weapon scaling and replaced with new *SmartWeaponScaling*.
- Added check for *WeaponDoublesRange* so if possessed wont attack auto.
- Fixed *transform to rider 10 seconds ability* still transforms after unit death.
- *DupesRiderToRider* item has been renamed to *DoublesUnitSpawning.* 

**Items**

- TransformAddDelay
- ColorableProjModel
- ColorableProjParticle
- SummonRider
- UnbindVehicleHealth
- UnbindRiderHealth
- BindVehicleHealth
- BindRiderHealth 
- MultiplyRangedDelay
- HalvesRangedDelay
- NullifyAllDelay
- SmartWeaponScalingRight
- SmartWeaponScalingLeft
- SmartProjSetRight
- SmartProjSetLeft
- SmartMeleeSet
- SmartRangedSet
- AbilityRemoveSound
- SmartRight/LeftMagSet
- SmartOnHitEffect
- ForcePointAddReaperScytheEffect
- SetProjHoming 
- KeepNormalUnitColorInstance
- AddPlaceholderBoxProps
- RigScale
- WeaponPlaceholderBoxRight/WeaponPlaceholderBoxLeft
- AdaptiveOrbCasting
- AdaptiveSwordCasting
- SmartWeaponWeighting
- WeaponHoldingUpRotation
- WeaponHoldingForwardRotation
- WeaponHoldingRelativePosition

#### (1.0.7)

**Changes**

- Uses custom items for most of the items instead of pre-existing items.
- Instead of using bat transformation, have custom particles via AssetBundling.
- Changes the *EyeKeepOpenedItem* to affect eyes instead of making new eyes.

**Item**

- TransformToRiderWhenDies
- Nulify/Doubles/HalvesWeaponRecoil(Affect both hand)
- Nulify/Doubles/HalvesWeaponSwingforce(Affect both hand)
- HideAbilityModel
- WeaponHalvedRange (same with weaponDoubleRange but reversed)
- Doubles/HalvesProjectile(affect all spawned projectile)
- TornadoDisables
- NulifyRightHand/LeftHand/Head(Turns a body parts into 0.0001 in scale, for hands they applied to both arm and elbow)
- ForceSkinChange
- DupesRiderToRider
- DoublesMeleeKnockback
- HalvesMeleeKnockback
- DoublesMeleeScreenshake
- HalvesMeleeScreenshake

#### (1.0.6)

- Added more items addition.
- SkinChange Optimization (3 changes).
- Custom category for all items.
- **WeaponDoubledRange** fix.

#### (1.0.5)

- Added more items addition.

#### (1.0.4)

- Added melee Blink addition ability.
- Added weapon-swapping abilities.

#### (1.0.3)

- All weapon scaling now has its specific XYZ.
- Added an item called *AlwaysTansferHP*.
- Added eye clothing that always opens.
- Added an item called *Remove Healthbar*, which is self-explanatory.

#### (1.0.2)

- Added transformation for when the unit health is below 50% and 25% health condition, and also new Pirate Queen's adaptive ability.
- Improved Sensei's adaptive throw to have better adaptive particle color.

#### (1.0.1)

- Fixed items were not saved properly due to a delay in loading.
