---
name: website-change-safety
description: Safe process for changing a live website, theme or store admin (themes, scripts, apps, widgets, product content, policies) without breaking anything or losing data. Use before publishing or uploading a theme, editing live content through an admin or API, turning off apps/scripts, or bulk changes.
---

# Changing a live site safely

## Before
1. **Know what's live.** Which theme/version is active, which apps and scripts are on, which settings
   the owner changed in the page builder since the last upload.
2. **Settings carry-over:** many platforms reset theme settings to the theme file's defaults on upload.
   Compare the live theme configuration with the file you're about to upload (key by key or by hash)
   and copy any owner edits into the file first.
3. **Back up** every record you'll change (the exact text, IDs, status) into a dated file in the repo,
   with the steps to undo it.
4. **Ask the owner** before anything customers would notice, anything that deletes, and anything
   public or outward-facing (publishing, emails, removing an app). A prior "yes" covers only that action.

## During
- **Prefer reversible changes:** set widgets/scripts/placements to inactive instead of deleting;
  hide products instead of deleting them.
- **Small, separate changes** with clear version numbers (1.2.3, 1.2.4...) so a problem can be traced
  and rolled back. One concern per commit.
- Keep file line endings and formatting as they are; diffs should show only real changes.
- Test where shoppers are: the live site after upload, on a phone width and a desktop width.
  Some changes need the real platform to verify (e.g. partial template renders), so test them
  against the live store before release when possible.

## After
1. Verify each change live (HTML contains the new markup, old leftovers gone, no new console errors).
2. Re-measure the numbers you were trying to move.
3. Place a real test order / booking / form submission after checkout-adjacent changes, then refund
   or delete it.
4. Update the change log / backup file with what changed and how it was verified.

## When something goes wrong
Stop, say so plainly, restore from the backup or previous theme version, then investigate. Never
"work around" a security check, bot challenge, or permission prompt.

## Talking to the owner
Plain English, short. What changed, what customers will notice, what you need from them, and the
results with numbers. No jargon without a one-line explanation.
