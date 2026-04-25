# AgentFlow Documentation

Mintlify-powered documentation source for AgentFlow.

This repo holds the MDX files, configuration, and assets that compile into the public docs site at `docs.agentflow.website` (or whichever subdomain you bind).

## Layout

```
.
├── docs.json                # Mintlify config (theme, navigation, branding)
├── introduction.mdx
├── quickstart.mdx
├── concepts/                # Conceptual overviews
├── launchpad/               # Launchpad surface
├── marketplace/             # Marketplace surface
├── flow/                    # FLOW credits, subscriptions, payouts
├── api/                     # API reference
├── guides/                  # Task-oriented guides
├── self-host/               # Self-hosting docs
└── images/                  # Logos, favicon, OG images
```

## Local preview

Install the Mintlify CLI:

```bash
npm i -g mintlify
```

From the repo root:

```bash
mintlify dev
```

The CLI starts a local server (default `http://localhost:3000`) with hot reload on MDX edits.

## Deploying

Mintlify builds and serves the site from a connected GitHub repo. Owner action:

1. Push this repo to GitHub.
2. Go to [mintlify.com](https://mintlify.com) and sign in.
3. Click **New project** → **Connect GitHub** and select this repo.
4. Mintlify auto-deploys to `<workspace>.mintlify.app`.
5. (Optional) In the Mintlify dashboard, add a custom domain — for example `docs.agentflow.website`. Mintlify shows the CNAME target; create the CNAME in your DNS provider.
6. Every subsequent `git push` to the default branch redeploys.

No build step or CI configuration is required on this repo. Mintlify handles everything.

## Editing

- All content is `.mdx` (Markdown + JSX components).
- Available components are documented at https://mintlify.com/docs/components — every component used here (`Card`, `CardGroup`, `Steps`, `Step`, `Tabs`, `Tab`, `Note`, `Warning`, `Tip`, `CodeGroup`, `ParamField`, `ResponseField`) is part of the standard Mintlify set, no extra installation needed.
- Each page starts with frontmatter:

  ```mdx
  ---
  title: "Page Title"
  description: "One-line meta description"
  ---
  ```

- Internal links use absolute paths without the `.mdx` extension: `/api/auth`, not `./auth.mdx`.

## Navigation

Edit `docs.json` to add, reorder, or rename pages. The `navigation.tabs[*].groups[*].pages` arrays drive the sidebar.

## Branding

- Accent color is set in `docs.json` → `colors.primary` (`#d4ff00`).
- Logos live in `images/logo/{light,dark}.svg`.
- Favicon is `images/favicon.svg`.
- Default appearance is `dark`; users can switch.

## Contributing

Open a PR against the default branch. Mintlify previews the changes on a per-PR URL so reviewers can see the rendered output.

## License

Documentation is licensed under CC-BY-4.0. Code samples in this repo are MIT-licensed unless noted otherwise.
