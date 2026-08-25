Within each campaign, persistent NPCs receive stable campaign-local IDs such as `NPC-0001` in that campaign's `NPC-state.md`. Cross-file references use the stable NPC ID plus the NPC's current name for readability; names and Markdown headings are not identity keys.

## Campaign-local identity

Each campaign assigns persistent NPCs stable campaign-local IDs such as `NPC-0001` in its own `NPC-state.md`. NPC IDs are never reused within that campaign, and cross-file references use the stable NPC ID plus the NPC's current name instead of relying on name-derived Markdown headings or anchors.

The two required core PCs are defined through that campaign's `character_sheet.md` and `active_game.json` advancement state under the repository-wide core-party rules. The ChatGPT-controlled core PC is a PC, not an NPC.

Detailed NPC ownership, party-membership reconciliation, vendor state, and cross-file behavior are defined in this directory's `GAME_MASTER_RULES.md`.