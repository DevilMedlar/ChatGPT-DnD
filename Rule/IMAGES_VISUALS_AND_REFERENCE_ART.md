## Images

The repository-wide image play loop and player-managed generated-image-binary rule are owned by root `GAME_MASTER_RULES.md`.

Textual appearance canon remains in the state file that owns the character, NPC, location, or item. Each campaign's `art/art_log.md` owns verified reference-image paths and visual-reference continuity metadata rather than duplicating textual appearance authority. Image-path and reference-metadata staging during Campaign Turns follows `campaigns/GAME_MASTER_RULES.md`.

## Image generation

Scene art is optional. Do not ask for an image after every scene.

Good image candidates include major character introductions, dramatic reveals, transformations, important romantic or sensual moments, visually striking adult intimacy where image generation is permitted, spectacular locations, major monsters, boss encounters, important outfits/equipment/scars/tattoos/visual changes, or any scene the player explicitly asks to see.

Generated image binaries are player-managed. ChatGPT must not commit, upload, create, replace, rename, or delete generated image files in the repository. The player handles image-file persistence manually. ChatGPT may update textual art-continuity metadata and may record a repository image path only after the player has added the file and that path is verified to exist.

### Image decision workflow

1. Narrate the scene normally and present any relevant gameplay choices first.
2. If the scene genuinely deserves an image, end the text with `Make image? Yes / No`.
3. If the player answers `Yes`, generate the image **before resolving any gameplay choice for that scene**.
4. After the generated image is shown, stop and wait for the player's gameplay choice or freeform action. Do not advance the scene merely because the image was generated.
5. If the player answers `No`, do not generate an image.
6. When `No` is followed by other text in the same message, immediately parse the remaining text as gameplay input. Example: `No, A, 1, E) ...`.
7. Before generating a recurring character, established location, important item, transformation, outfit, scar, tattoo, or other continuity-sensitive visual, consult the active campaign's textual appearance owner and visual-reference log.
8. Generated images must be as accurate as possible to avoid having to remake them unnecessarily.
9. Textual canon overrides accidental visual inconsistencies unless the player explicitly adopts the new visual detail.

Campaign-specific staging and persistence of visual-reference metadata live in `campaigns/GAME_MASTER_RULES.md`.

## Reference art

When the player supplies reference art or manually adds images to the repository:

- Record a repository path only after it actually exists.
- Record which features are canonical and which are inspiration only.
- Prefer written canonical traits over accidental differences in generated images.
- Never assume an unverified image path exists.

The active campaign's assigned textual state files own appearance canon. The campaign's `art/art_log.md` owns verified reference-image paths and visual-reference metadata that point back to that textual canon.

## Image and reference-art persistence

Textual appearance canon belongs to the state file that owns the entity:

- `character_sheet.md` owns the core PCs' textual appearance canon
- `NPC-state.md` owns persistent NPC textual appearance canon
- `world_state.md` owns established location and world-object appearance where applicable
- `inventory.md` owns mechanically or visually relevant owned-item state where applicable

`art/art_log.md` is the campaign's canonical **visual-reference index**, not a competing textual appearance owner. It owns verified reference-image paths, generated/reference-art continuity metadata, provenance notes, and notes identifying which visible features are canonical, inspirational, or accidental. When an image conflicts with established textual canon, the textual state owner wins unless the player explicitly adopts the image difference as new canon.

Generated image binaries remain player-managed under the repository-wide image rules. File existence does not itself make an image canonical.

When newly established continuity-critical visual-reference information occurs during an active Campaign Turn, stage it in `turn_save.md` and include `art/art_log.md` in the Exact Planned Permanent Transfers. If the underlying textual appearance also changes, stage the appropriate textual state owner too. Add the reference metadata to `art/art_log.md` only during approved Campaign Turn reconciliation. Outside an active Campaign Turn, persist it through the normal completed-save workflow.

When the player supplies reference art or manually adds images to the repository:

- record the repository path only after it actually exists
- record which features are canonical and which are inspiration only
- prefer written canonical traits over accidental differences in generated images
- never assume an unverified image path exists

If reference art is supplied or adopted during an active Campaign Turn, the image file may exist immediately, but canonical reference metadata remains staged in `turn_save.md` until approved Campaign Turn reconciliation. File existence does not bypass Confirmation Gate 1.