# PS2 Saves

PCSX2 memory card backups maintained in [velrino/ps2](https://github.com/velrino/ps2).

## Memory cards

All versioned memory card images live in `saves/`.

| File | Game | Save ID |
|------|------|---------|
| `Burnout3-USA.ps2` | Burnout 3: Takedown | `BASLUS-21050` |
| `MortalKombat-ShaolinMonks-USA.ps2` | Mortal Kombat: Shaolin Monks | `BASLUS-21087` |
| `NFS-Carbon-USA.ps2` | Need for Speed: Carbon | `BASLUS-21494` |
| `NFS-MostWanted-USA.ps2` | Need for Speed: Most Wanted | `BASLUS-21351` |
| `NFS-Underground2-USA.ps2` | Need for Speed: Underground 2 | `BASLUS-21065` |

The cards were moved from the repository root without changing their contents.

## Use with PCSX2

The local save folder is:

```text
/Users/velrino/Documents/Projects/ps2/saves
```

In PCSX2, open **Settings → Memory Cards**, choose this folder and assign the
appropriate card to a slot. Use a card that matches the game's region.
Changing the folder does not migrate cards from PCSX2's previous folder;
back up existing progress before switching cards.

## Back up changes

Close PCSX2 before copying or committing cards so they are no longer being written.
Place memory card images in `saves/`, then review and commit only the intended files:

```bash
git status --short
git add saves/GameName-USA.ps2
git diff --cached --stat
git commit -m "Update GameName memory card"
```

The ignore rules allow only this README, `.gitignore` and `saves/*.ps2`.
The PCSX2 application, downloaded installers, BIOS, games, save states, logs,
caches and macOS metadata stay local and are not included in new commits.
