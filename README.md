# skills-djibril

Mes skills [Claude Code](https://docs.claude.com/en/docs/claude-code) — collection personnelle de skills réutilisables.

## Skills disponibles

| Skill | Description |
| --- | --- |
| [`seo`](./seo/SKILL.md) | Audit et optimisation SEO pour un projet Next.js App Router (métadonnées, Open Graph, JSON-LD, sitemap, Core Web Vitals). |

## Installation

Cloner un skill dans le dossier des skills de ton projet (ou au niveau utilisateur) :

```bash
# Au niveau d'un projet
git clone https://github.com/djibril1212/skills-djibril.git
cp -r skills-djibril/seo .claude/skills/

# Ou au niveau utilisateur (disponible partout)
cp -r skills-djibril/seo ~/.claude/skills/
```

Chaque skill est un dossier contenant un fichier `SKILL.md`. Claude Code le détecte automatiquement et l'expose comme commande déclenchable.
