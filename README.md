# Custom Codex Skills

Private source repository for TheAOProject's custom Codex skills.

## Included

- `ao-product-capture`: capture a complete retailer product image, prepare a transparent cutout, and save the verified asset to Canva's AO Products folder.
- `ao-outfit-pin`: create Canva outfit designs from AO Products and publish verified Pinterest pins. Includes its two supporting guides and three reference images.
- Skill instructions and supporting files are preserved as supplied.

Codex's bundled `.system` skills, installed plugin caches, account settings, and credentials are excluded. The root `.gitignore` allows only explicitly listed custom skill folders.

## Mac mini

The working repository is `~/.agents/skills`. Its `main` branch tracks `origin/main` at `https://github.com/TheAOProject/Codex-Skills.git`.

The older `~/.codex/skills/ao-product-capture` location links to the same custom skill folder, so updates reach both existing locations. The bundled `~/.codex/skills/.system` directory is unchanged. Original custom skill copies were backed up outside this repository under `~/Documents/Codex/Skill-Backups` during setup.

Pull updates:

```sh
git -C "$HOME/.agents/skills" pull --ff-only
```

Publish an intentional skill edit:

```sh
cd "$HOME/.agents/skills"
git status --short
git diff
git add -- ao-product-capture/SKILL.md ao-product-capture/agents/openai.yaml
git commit -m "Update AO Product Capture"
git push
```

Commit and push changes on one Mac before pulling them on another. If a pull reports local changes or divergent history, preserve and review those changes; do not force-push or reset them away.

## AO Outfit Pin installation

The synced copy is `~/.agents/skills/ao-outfit-pin`, with a link at `~/.codex/skills/ao-outfit-pin`. Its original source folder at `~/Documents/ChatGPT/The AO Project Site/skills/ao-outfit-pin` is retained unchanged as a separate copy. Edit the synced copy when making changes intended for this repository; edits to the original project copy are not automatically mirrored.

The skill uses existing Canva AO Products assets, a model identity reference, and an editable seed design. It also references the established AO project path on the Mac mini. On another Mac, retain access to those Canva resources and resolve the local project path before running an outfit task. Syncing the skill does not copy project output history or authenticate Canva/Pinterest on another computer.

To publish an intentional edit, review `git diff`, then add the `ao-outfit-pin` folder explicitly, commit, and push. Installing or editing this skill alone does not create or publish a Pinterest post.

## Another Mac

Authenticate GitHub on that Mac using its own account access. Inspect and back up existing custom skills before changing their installed locations. Do not replace the entire `~/.codex/skills` directory or commit its `.system` contents.

If `~/.agents/skills` does not exist, clone directly:

```sh
git clone https://github.com/TheAOProject/Codex-Skills.git "$HOME/.agents/skills"
```

If it already exists, clone this repository into a separate folder, compare existing skill contents, and merge any differences before linking individual custom skill folders or connecting the existing directory. Never overwrite a different local skill copy without a backup.

Codex supports user skills in `~/.agents/skills` and symlinked skill folders. If a change does not appear, restart Codex. See [OpenAI's skill documentation](https://learn.chatgpt.com/docs/build-skills).

## Adding a custom skill

Create its own folder containing `SKILL.md`, inspect all included files for credentials and temporary artifacts, and explicitly allow the new root folder in `.gitignore`. Add only that folder and the `.gitignore` change. Keep system skills and machine-specific account configuration out of Git.
