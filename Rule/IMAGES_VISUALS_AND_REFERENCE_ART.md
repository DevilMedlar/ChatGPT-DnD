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