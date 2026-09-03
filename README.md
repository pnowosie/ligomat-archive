# ligomat-archive

Every finished tournament, as one PGN.

The table tells you who won. The games tell you *how* — and those outlive the season, the club, and
whatever website announced the results. So they get their own home here, in the most boring and most
durable format chess has.

**One file per event.** It opens with a chapter carrying the format, the dates and the final table,
then every board in round order — walkowers and byes included, so the file matches the pairing sheet
line for line.

Plain PGN. Open it in lichess, SCID, ChessBase, or a text editor.

## Where these come from

These files are an artifact of **game-notifier**, a side project of mine that runs club tournaments
played online. A cron watches chess.com and lichess for games between the paired players, records
each result the moment it finds one, announces it to Discord exactly once, and keeps the standings
page up to date. No one types in a result; nobody chases players for screenshots.

The whole state is plain JSON committed to git, so the tournament's history *is* the repository's
history. When an event ends, that data is rendered into the file you are looking at.

The first public version of the system is [**cebuliga**](https://github.com/pnowosie/cebuliga).

Files here are generated, never edited by hand. The `Fingerprint` tag on the first chapter records
which version of the tournament data produced the file.

I kept "exactly once" because it's the genuinely interesting property — announced_at is the dedup key, not result, so a failed webhook costs you nothing and no game is ever announced twice.

One thing I couldn't check: github.com/pnowosie/cebuliga isn't reachable from here, and your notes say that repo is slated to be archived. Worth confirming it's public before the link goes out.

