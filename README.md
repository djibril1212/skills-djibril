# skills-djibril

Mes skills [Claude Code](https://docs.claude.com/en/docs/claude-code) — collection personnelle de skills réutilisables.

## Mes skills

| Skill | Description |
| --- | --- |
| [`seo`](./seo/SKILL.md) | Audit et optimisation SEO pour un projet Next.js App Router (métadonnées, Open Graph, JSON-LD, sitemap, Core Web Vitals). |

## Skills tiers inclus

### [`koda-stack`](./koda-stack/) — 10 agents créatifs

Set de 10 skills créatifs (brief, trends, concept, script, art-direction, storyboard, generate, assemble, publish, repurpose).

> **Attribution** — `koda-stack` est l'œuvre de **Tim Koda**, distribué sous licence MIT.
> Source : https://github.com/timkoda/koda-stack — la licence d'origine est conservée dans [`koda-stack/LICENSE`](./koda-stack/LICENSE).

## Installation

Chaque skill est un dossier contenant un fichier `SKILL.md`. Claude Code le détecte automatiquement.

```bash
git clone https://github.com/djibril1212/skills-djibril.git

# Skill seo (niveau projet)
cp -r skills-djibril/seo .claude/skills/

# koda-stack (niveau utilisateur, disponible partout)
cp -r skills-djibril/koda-stack ~/.claude/skills/
```
