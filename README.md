# DUNGEONS COMMAND CENTRE

A **game pack** for [gamebrain](https://github.com/koozyapno1/gamebrain) — a
generic game intel assistant that answers questions about a game from a
knowledge base and can speak the answers aloud.

This pack teaches it about **Minecraft Dungeons - Jungle Awakens DLC**.

## Install

```bash
git clone https://github.com/koozyapno1/gamebrain.git
cd gamebrain

git clone https://github.com/koozyapno1/gamebrain-pack-minecraft-dugeons.git packs/minecraft-dugeons

echo "PACK_DIR=./packs/minecraft-dugeons" >> .env

docker compose up -d
```

Or with plain Python:

```bash
export PACK_DIR=./packs/minecraft-dugeons
python app.py
```

Full instructions: **[gamebrain INSTALL.md](https://github.com/koozyapno1/gamebrain/blob/main/docs/INSTALL.md)**

## What it knows

| Area | Detail |
|---|---|
| **Topics** | 8 researched topics — Getting Started, Classes, Weapons, Armor, Caves, Bosses, ... |
| **Tips** | 41 ordered, practical steps |
| **Videos** | 24 real YouTube guide videos, linked per topic |

Every topic has an ordered **tips** list that the assistant returns as
numbered steps, and a **videos** list of working guide links.

## Files

```
pack.json    the manifest - tools, prompt, UI copy, reference tabs
kb.json      the knowledge base - all the game facts
```

No code, no keys, no secrets. Content only.

## Try it

```bash
curl -s http://localhost:8095/health | python3 -m json.tool
curl -s http://localhost:8095/tools | python3 -m json.tool
curl -s -X POST http://localhost:8095/chat \
  -H 'Content-Type: application/json' \
  -d '{"message": "Which class should I pick as a beginner?"}' | python3 -m json.tool
```

Look for `tools_used` in the response. If it is empty the model answered from
memory instead of using the pack.

## Credits and sources

The game facts were compiled from public reference sources:

- minecraft.wiki
- game8.co (Minecraft Dungeons)

YouTube video links point to the original creators' channels. All game names,
locations and trademarks belong to their respective owners. This pack is an
unofficial community reference and is not affiliated with or endorsed by the
publisher.

## Licence

The pack's **code and manifest** are MIT (same as gamebrain). The **game facts
and video links** are community-sourced content — see `kb.json` → `sources`
for attribution.
