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

## Campaign Turn persistence of generated and reference art

Canonical campaign art follows the same Campaign Turn staging, Final Review, approval, reconciliation, verification, and reset workflow as every other persistent Campaign Turn result. Do not create a separate out-of-Turn art save path.

When an image is generated or reference art is adopted during an active Campaign Turn:

1. ChatGPT asks `Make image? Yes / No` under the Image decision workflow above when generation is appropriate.
2. If the player says `Yes`, ChatGPT generates the image, but the image binary remains player-managed.
3. The player saves the generated image and uploads it to the campaign repository as a `.png` or another supported image file.
4. ChatGPT verifies that the repository image path actually exists before recording it as a campaign reference.
5. Record the verified image in `turn_save.md` as a compact Turn entry such as `Art: <verified-image-path>.png`, with a note to follow this rule and the campaign's `art/art_log.md` instructions when preparing the permanent visual-reference details.
6. Stage any continuity-relevant visual metadata in `turn_save.md`, including which visible features match established textual canon, which are inspiration only, and which are accidental or known to be inaccurate when relevant.
7. If the underlying textual appearance actually changes through play, stage the corresponding textual state owner in `Pending Permanent Transfers` as well.
8. Include `art/art_log.md` in `Pending Permanent Transfers` only when the Turn contains new or changed visual-reference metadata that is not already recorded there.
9. At the Campaign Turn Final Review, compare the proposed art transfer against the existing `art/art_log.md` and textual appearance owners. Remove any unchanged or already-established detail from the planned merge so the permanent files are not duplicated.
10. Show the art transfer as part of the same **Exact Planned Permanent Transfers** presented for the Campaign Turn save confirmation.
11. Only after the player confirms the Campaign Turn save may the approved new or changed visual-reference metadata be written to `art/art_log.md` and any approved textual appearance change be written to its proper owner.
12. Verify the permanent art/reference update together with the rest of the approved Campaign Turn save before requesting Turn reset.

The uploaded image file may physically exist in the repository before the Campaign Turn ends, but its canonical visual-reference metadata is not transferred into `art/art_log.md` merely because the file exists. The normal Campaign Turn Final Review and confirmation gate still control the permanent metadata update.

Campaign Turn staging and save behavior are defined in `CAMPAIGN_TURNS_AND_STEPS.md` and `SAVES_VERIFICATION_AND_RECOVERY.md`. The campaign copy of `art/art_log.md` defines the fill-out structure for the permanent visual-reference record.
