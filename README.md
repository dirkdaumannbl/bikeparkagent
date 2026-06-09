# bikeparkagent

A Claude Code project that researches MTB / downhill / gravity bike parks and
produces a single, self-contained, fully-cited HTML report (an overview
comparison table plus a detailed section per park).

The work is done by the **`bikepark-researcher`** subagent, which researches the
open web and only states facts it can back with a source. Distances are computed
by car from **Oskar-Helene-Park 7, 14195 Berlin**.

## Layout

```
.claude/agents/bikepark-researcher.md   the subagent definition (auto-discovered by Claude Code)
templates/report-template.html          the HTML report template the agent fills in
reports/                                 generated reports land here (bikepark-report-YYYY-MM-DD.html)
```

## Usage

From this project directory, launch Claude Code and ask it to research one or
more parks. The `bikepark-researcher` subagent is invoked automatically when you
give it park names or a file of names, e.g.:

- `Research Bikepark Geißkopf, Germany`
- `Research these parks: Bikepark Winterberg, Bikepark Albstadt, Leogang`
- `Research the parks listed in parks.txt` (one park per line; `.txt`/`.csv`)

You can also invoke it explicitly: `Use the bikepark-researcher subagent to research …`

## Output

The agent writes `reports/bikepark-report-YYYY-MM-DD.html` (appending `-2`, `-3`,
… if one already exists for today) and reports back the file path, the parks
covered, and any values it could not verify (marked **Not found** rather than
guessed).
