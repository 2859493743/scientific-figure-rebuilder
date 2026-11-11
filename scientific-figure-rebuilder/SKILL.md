---
name: scientific-figure-rebuilder
description: Rebuild or edit research diagrams and flowcharts as editable Visio or PowerPoint shapes from reference images or existing documents. Use for scientific architecture, model, and process diagrams; not for statistical plots derived from data or complete presentation design.
---

# Scientific figure rebuilder

Turn a reference or an existing Office diagram into a useful editable figure. Follow the user's requested format and preserve the meaning of the figure. A visually plausible picture is not sufficient if it changes labels, relationships, or data.

## Choose the deliverable

- For editable Visio, build a `.vsdx` with native shapes and text, using connectors that remain attached when relevant nodes move.
- For editable PowerPoint, build a `.pptx` using PowerPoint shapes, text, and connectors. An exported page inserted as a single image is not an editable PowerPoint diagram.
- If both are requested, build and verify both separately against the same component and relationship inventory. Do not assume that converting a rendered page preserves editability.
- If the user only requests an image or PDF, say whether the result has an editable source; do not claim editability for a flattened export.

Simple boxes, labels and relationships should remain independently editable. Discuss or disclose exceptions for intricate artwork that cannot reasonably be reconstructed as shapes: a small replaceable image asset may be appropriate, but never present a whole-page image as an editable diagram. Do not invent missing experimental results or architecture connections.

## Workflow

1. Inspect the supplied source and requested output. Identify the figure, text, objects, nesting, arrows, dimensions and any ambiguous relationships. When source documents are supplied, prefer their original embedded image to a screenshot. Ask about ambiguity that could change scientific meaning.
2. Record the main panels, components and connections before drawing. Establish page size and panel bounds, then place large elements before details. Preserve an existing figure's content and styling unless the user asks for changes.
3. Use the available editing application or an appropriate library. On Windows, Office COM automation may be used if the relevant application is installed and accessible; do not assume it works over a noninteractive SSH session. For existing files, save a separate copy or obtain permission before overwriting.
4. Draw shapes, editable text and meaningful groups. Use attached connectors where supported, and preserve arrow direction and routing. Use fonts available in the environment and disclose substitutions that affect the result.
5. Save and reopen the result when possible. Render a preview and compare it to the reference, including labels, arrow endpoints, overlap and clipping. Test representative objects and connectors by moving them in a disposable copy. Check each requested file exists and is nonempty. Report unverified behavior or unsupported automation rather than claiming a pass.

Use a script to generate reproducible diagrams when it is useful; inspect and test that script before running it on existing documents. Never install software, overwrite unrelated work, or terminate an existing Office session without appropriate permission. Do not infer values for charts from their appearance: request the underlying data or clearly label a reconstruction as approximate.
