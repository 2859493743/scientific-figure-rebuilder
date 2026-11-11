# Scientific Figure Rebuilder

A Codex-compatible skill for rebuilding research architecture diagrams and flowcharts as editable Microsoft Visio or PowerPoint figures.

## What it does

- Reconstructs diagrams from reference images or edits existing Office diagrams.
- Distinguishes editable Visio output from a separately editable PowerPoint output.
- Guides verification of labels, layout, connectors and exports.

This is an instruction skill, not a turnkey converter. The agent must select and implement appropriate drawing tools for each task. Visio and PowerPoint automation depends on locally available applications, licenses and a suitable interactive Windows environment. It does not promise fully automatic reconstruction or support for every drawing format. Statistical charts should be produced from the actual data with appropriate plotting tools.

## Install

Copy the `scientific-figure-rebuilder` folder into your Codex skills directory, for example on Windows:

```powershell
Copy-Item -Recurse .\scientific-figure-rebuilder "$env:USERPROFILE\.codex\skills\scientific-figure-rebuilder"
```

Restart or reload the agent if required. Do not overwrite an existing skill without checking it first.

Example request: “Rebuild this model diagram as an editable Visio file and a separate editable PowerPoint slide. Preserve the arrow directions and provide previews.”

## License

MIT; see [LICENSE](LICENSE). Microsoft Visio and PowerPoint are separate proprietary products and are not distributed by this repository.
