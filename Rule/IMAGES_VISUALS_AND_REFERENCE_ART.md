# Images, Visuals, and Reference Art

## Image generation

Scene art is optional. Do not ask for an image after every scene.

Good image candidates include:

- major character introductions
- dramatic reveals
- transformations
- important romantic or sensual moments
- visually striking adult intimacy where image generation is permitted
- spectacular locations
- major monsters or boss encounters
- important outfits, equipment, scars, tattoos, or other visual changes
- any scene the player explicitly asks to see

Adult image boundaries are governed by `ADULT_CONTENT_AND_CONSENT.md`.

## Generated image files

Generated image binaries are player-managed.

ChatGPT must not commit, upload, create, replace, rename, or delete generated image files in the repository. The player handles image-file persistence manually.

ChatGPT may update textual art-continuity metadata and may record a repository image path only after the player has added the file and that path is verified to exist.

File existence alone does not make an image canonical.

## Image decision workflow

1. Narrate the scene normally and present any relevant gameplay choices first.
2. If the scene genuinely deserves an image, end the text with `Make image? Yes / No`.
3. If the player answers `Yes`, generate the image **before resolving any gameplay choice for that scene**.
4. After the generated image is shown, stop and wait for the player's gameplay choice or freeform action. Do not advance the scene merely because the image was generated.
5. If the player answers `No`, do not generate an image.
6. When `No` is followed by other text in the same message, immediately parse the remaining text as gameplay input. Example: `No, A, 1, E) ...`.
7. Before generating a recurring character, established location, important item, transformation, outfit, scar, tattoo, or other continuity-sensitive visual, consult the active campaign's textual appearance owner and visual-reference log.
8. Generated images must be as accurate as possible to established visual canon to avoid unnecessary remakes.
9. Textual canon overrides accidental visual inconsistencies unless the player explicitly adopts the new visual detail.

## Textual appearance authority

Textual appearance canon belongs to the state file that owns the entity:

- `character_sheet.md` owns the core PCs' textual appearance canon
- `NPC-state.md` owns persistent NPC textual appearance canon
- `world_state.md` owns established location and world-object appearance where applicable
- `inventory.md` owns mechanically or visually relevant owned-item state where applicable

`art/art_log.md` is the campaign's canonical **visual-reference index**, not a competing textual appearance owner.

It owns verified reference-image paths, visual-reference continuity metadata, provenance notes, and notes identifying which visible features are canonical, inspirational, accidental, or known to be inaccurate.

When an image conflicts with established textual canon, the textual state owner wins unless the player explicitly adopts the image difference as new canon.

## Reference art

When the player supplies reference art or manually adds images to the repository:

- record a repository path only after it actually exists
- record which visible features match canonical textual state
- record which features are inspiration only
- record known accidental or incorrect visual details when relevant
- prefer written canonical traits over accidental image differences
- never assume an unverified image path exists

## Persistence of visual-reference metadata

When continuity-critical visual-reference information is established during an active Campaign Turn:

1. stage the change in `turn_save.md`
2. include `art/art_log.md` in the planned permanent transfers
3. if the underlying textual appearance also changes, stage the appropriate textual state owner too
4. add the reference metadata to `art/art_log.md` only during approved Campaign Turn reconciliation

Outside an active Campaign Turn, persist new visual-reference metadata through the normal completed-save workflow.

If reference art is supplied or adopted during an active Campaign Turn, the image file may exist immediately, but canonical reference metadata remains staged until approved reconciliation. File existence does not bypass save approval.

Campaign Turn staging and save behavior are defined in `CAMPAIGN_TURNS_AND_STEPS.md` and `SAVES_VERIFICATION_AND_RECOVERY.md`.
