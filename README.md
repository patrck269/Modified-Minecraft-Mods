# Modified Minecraft Mods

Patched Minecraft mods used in **Airships For Free** (Technic slug `airships-for-free` / working tree `jazz`).

Each mod is its own git repo, forked from upstream, with Patrick’s changes on `main`.

## Repos

| Mod | Upstream | This fork |
|-----|----------|-----------|
| Eureka (Valkyrien Skies ships) | [ValkyrienSkies/Eureka](https://github.com/ValkyrienSkies/Eureka) | [patrck269/Eureka](https://github.com/patrck269/Eureka) |
| c2meF (chunk threading) | [sj-hub9796/c2meF](https://github.com/sj-hub9796/c2meF) | [patrck269/c2meF](https://github.com/patrck269/c2meF) |
| Immersive Aircraft | [Luke100000/ImmersiveAircraft](https://github.com/Luke100000/ImmersiveAircraft) | [patrck269/ImmersiveAircraft](https://github.com/patrck269/ImmersiveAircraft) |

Clone with submodules:

```
git clone --recurse-submodules https://github.com/patrck269/Modified-Minecraft-Mods.git
```

## What changed

**Eureka**

- Immersive Aircraft / Simple Planes land on VS ship decks without world-space backflip glue.
- Parked planes ride with the ship; taxi and takeoff keep relative speed like solid ground.
- Mixin presence uses `ClassLoader.getResource` so dedicated Forge does not re-enter the transformer.
- Simple Planes / IA `tick` injects both `tick()V` and Forge SRG `m_8119_()V`.

**c2meF**

- Mixin presence via `getResource` (same dedicated-server re-entry crash).
- `VsShipCompatGate` serializes concurrent chunk IO/worldgen in the VS shipyard.

Immersive Aircraft and Valkyrien Skies 2 were cloned for reference only and were not patched.

## Pack

Technic Solder: `https://solder.idontliveinthe.uk/api/` — pack `airships-for-free`.
