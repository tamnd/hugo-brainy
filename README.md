# hugo-brainy

A Hugo theme for personal knowledge bases and digital gardens. Built on top of [Hextra](https://github.com/imfing/hextra).

## What it includes

- Custom sidebar that shows only the nearest section tree, not the full site tree
- Feed layout for the home page (most recent notes, chronological)
- Tag index and tag term pages
- Knowledge graph view (D3.js force simulation, section color-coding, focus mode)
- Tree/mindmap view (collapsible horizontal D3 tree)
- Calendar view (month grid with day-by-day post listings)
- Breadcrumb navigation for doc pages
- Page actions (GitHub source link, raw Markdown link, copy to clipboard)
- Shadcn-inspired monochrome design: oklch color tokens, borders instead of shadows

## Requirements

- Hugo extended v0.126.0 or later
- Hugo modules enabled (`go.mod` in your site root)

## Installation

Add hugo-brainy to your site's `go.mod`:

```
hugo mod get github.com/tamnd/hugo-brainy@latest
```

Update your `hugo.toml`:

```toml
[module]
  [[module.imports]]
    path = "github.com/tamnd/hugo-brainy"
```

Hugo resolves Hextra transitively; you do not need to import it separately.

## Configuration

hugo-brainy reads the same params as Hextra. See [Hextra docs](https://imfing.github.io/hextra) for the full list.

The theme adds a few menu item types for the navbar:

```toml
[[menu.main]]
  name = "Graph"
  [menu.main.params]
    type = "graph"

[[menu.main]]
  name = "Tree"
  [menu.main.params]
    type = "tree"

[[menu.main]]
  name = "Calendar"
  [menu.main.params]
    type = "calendar"
```

## Content structure

Pages need `type = "docs"` (or cascade it from a section `_index.md`) to use the doc layouts:

```yaml
---
type: docs
cascade:
  type: docs
---
```

## License

MIT
