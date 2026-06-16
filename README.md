# skills-djibril

Ma collection personnelle de skills [Claude Code](https://docs.claude.com/en/docs/claude-code) — orientée stack **Angular** (front + back) et **Java / Spring Boot**, avec PostgreSQL et Docker, plus des packs généralistes (docs, web, design, déploiement).

Un skill est un dossier contenant un fichier `SKILL.md` que Claude Code (et les agents compatibles) détecte automatiquement.

## Structure du dépôt

- **Skills curés** — dossiers au premier niveau : [`find-skills`](./find-skills/), [`frontend-design`](./frontend-design/), [`teach-impeccable`](./teach-impeccable/) et la collection [`koda-stack`](./koda-stack/).
- **Skills installés via [skills.sh](https://skills.sh)** — sous [`.claude/skills/`](./.claude/skills/). Le fichier [`skills-lock.json`](./skills-lock.json) permet de restaurer exactement la même liste.

## Angular

| Skill | Description |
| --- | --- |
| [`angular-developer`](./.claude/skills/angular-developer/) | Guidance et génération de code Angular v20+ (officiel). |
| [`angular-new-app`](./.claude/skills/angular-new-app/) | Création d'une nouvelle app via Angular CLI. |
| [`angular-signals`](./.claude/skills/angular-signals/) | État réactif avec `signal()`, `computed()`, `effect()`. |
| [`angular-forms`](./.claude/skills/angular-forms/) | Signal Forms (Angular v21+). |
| [`angular-http`](./.claude/skills/angular-http/) | `resource()`, `httpResource()`, `HttpClient`, interceptors. |
| [`angular-routing`](./.claude/skills/angular-routing/) | Lazy loading, guards fonctionnels, resolvers. |
| [`angular-di`](./.claude/skills/angular-di/) | `inject()`, injection tokens, providers. |
| [`angular-component`](./.claude/skills/angular-component/) | Composants standalone, OnPush, content projection. |
| [`angular-directives`](./.claude/skills/angular-directives/) | Directives custom (attribut, structurelles, host). |
| [`angular-ssr`](./.claude/skills/angular-ssr/) | SSR / hydration avec `@angular/ssr`. |
| [`angular-testing`](./.claude/skills/angular-testing/) | Tests unitaires/intégration (Vitest/Jasmine, TestBed). |
| [`angular-tooling`](./.claude/skills/angular-tooling/) | Angular CLI, génération, build, config. |

## Java / Spring Boot

| Skill | Description |
| --- | --- |
| [`spring-boot-skill`](./.claude/skills/spring-boot-skill/) | Best practices Spring Boot 4.x (MVC, JPA, Modulith, Security, tests, ArchUnit). |
| [`jspecify-skill`](./.claude/skills/jspecify-skill/) | Null-safety via JSpecify (Maven/Gradle). |
| [`dr-jskill`](./.claude/skills/dr-jskill/) | Scaffolding Java + Spring Boot full-stack (Angular, PostgreSQL, REST, Docker). |

## Base de données & Infra

| Skill | Description |
| --- | --- |
| [`supabase-postgres-best-practices`](./.claude/skills/supabase-postgres-best-practices/) | Optimisation Postgres : requêtes, schémas, index, RLS. |
| [`docker-development`](./.claude/skills/docker-development/) | Dockerfiles, docker-compose, multi-stage, sécurité, CI. |

## React / Vercel / Déploiement

| Skill | Description |
| --- | --- |
| [`vercel-react-best-practices`](./.claude/skills/vercel-react-best-practices/) | Perf React / Next.js (Vercel Engineering). |
| [`vercel-composition-patterns`](./.claude/skills/vercel-composition-patterns/) | Patterns de composition React. |
| [`vercel-react-view-transitions`](./.claude/skills/vercel-react-view-transitions/) | View Transitions API React. |
| [`vercel-react-native-skills`](./.claude/skills/vercel-react-native-skills/) | Best practices React Native / Expo. |
| [`vercel-optimize`](./.claude/skills/vercel-optimize/) | Optimisation coût/perf de projets déployés sur Vercel. |
| [`vercel-cli-with-tokens`](./.claude/skills/vercel-cli-with-tokens/) | Déploiement Vercel via tokens. |
| [`deploy-to-vercel`](./.claude/skills/deploy-to-vercel/) | Déployer une app/un site sur Vercel. |

## Design & Frontend

| Skill | Description |
| --- | --- |
| [`frontend-design`](./.claude/skills/frontend-design/) | Direction visuelle distinctive pour de nouvelles UI. |
| [`web-design-guidelines`](./.claude/skills/web-design-guidelines/) | Revue UI/accessibilité contre les Web Interface Guidelines. |
| [`theme-factory`](./.claude/skills/theme-factory/) | Thèmes (couleurs/typo) appliqués aux artefacts. |
| [`brand-guidelines`](./.claude/skills/brand-guidelines/) | Application d'une charte de marque. |
| [`canvas-design`](./.claude/skills/canvas-design/) | Création d'art visuel en .png/.pdf. |
| [`algorithmic-art`](./.claude/skills/algorithmic-art/) | Art génératif en p5.js. |

## Documents & Bureautique

| Skill | Description |
| --- | --- |
| [`docx`](./.claude/skills/docx/) | Créer/lire/éditer des documents Word. |
| [`pdf`](./.claude/skills/pdf/) | Manipuler des PDF (fusion, split, OCR, formulaires…). |
| [`pptx`](./.claude/skills/pptx/) | Créer/éditer des présentations PowerPoint. |
| [`xlsx`](./.claude/skills/xlsx/) | Tableurs Excel/CSV (lecture, édition, formules, charts). |

## Rédaction & Communication

| Skill | Description |
| --- | --- |
| [`doc-coauthoring`](./.claude/skills/doc-coauthoring/) | Co-rédaction structurée de docs/specs/propositions. |
| [`writing-guidelines`](./.claude/skills/writing-guidelines/) | Revue de prose contre un guide d'écriture. |
| [`internal-comms`](./.claude/skills/internal-comms/) | Communications internes (statuts, updates, FAQ…). |
| [`slack-gif-creator`](./.claude/skills/slack-gif-creator/) | GIFs animés optimisés pour Slack. |

## Web & Test

| Skill | Description |
| --- | --- |
| [`agent-browser`](./.claude/skills/agent-browser/) | Automatisation navigateur pour agents. |
| [`webapp-testing`](./.claude/skills/webapp-testing/) | Test d'apps web locales via Playwright. |
| [`web-artifacts-builder`](./.claude/skills/web-artifacts-builder/) | Artefacts HTML élaborés (React, Tailwind, shadcn/ui). |

## Méta & Agents

| Skill | Description |
| --- | --- |
| [`find-skills`](./find-skills/) | Découvrir et installer des skills. |
| [`skill-creator`](./.claude/skills/skill-creator/) | Créer / améliorer / évaluer des skills. |
| [`mcp-builder`](./.claude/skills/mcp-builder/) | Construire des serveurs MCP (Python/TypeScript). |
| [`claude-api`](./.claude/skills/claude-api/) | Référence API Claude / SDK Anthropic. |
| [`teach-impeccable`](./teach-impeccable/) | Setup one-shot du contexte design d'un projet. |
| [`template-skill`](./.claude/skills/template-skill/) | Squelette de skill à dupliquer. |

## koda-stack — 10 agents créatifs

Collection de 10 skills créatifs : `brief`, `trends`, `concept`, `script`, `art-direction`, `storyboard`, `generate`, `assemble`, `publish`, `repurpose`. Voir [`koda-stack/`](./koda-stack/).

## Installation

```bash
git clone https://github.com/djibril1212/skills-djibril.git

# Option A — restaurer toute la liste via la CLI skills.sh
cd skills-djibril && npx skills experimental_install

# Option B — copier un skill manuellement (niveau projet)
cp -r skills-djibril/.claude/skills/angular-developer .claude/skills/

# koda-stack au niveau utilisateur (disponible partout)
cp -r skills-djibril/koda-stack ~/.claude/skills/
```

## Attribution & licences

La plupart de ces skills sont l'œuvre de leurs auteurs respectifs et restent sous leur licence d'origine :

- **Anthropic** — [`anthropics/skills`](https://github.com/anthropics/skills) : docx, pdf, pptx, xlsx, claude-api, frontend-design, mcp-builder, skill-creator, brand-guidelines, canvas-design, algorithmic-art, theme-factory, doc-coauthoring, internal-comms, slack-gif-creator, web-artifacts-builder, webapp-testing, template-skill.
- **Vercel Labs** — [`vercel-labs/skills`](https://github.com/vercel-labs/skills), [`agent-skills`](https://github.com/vercel-labs/agent-skills), [`agent-browser`](https://github.com/vercel-labs/agent-browser) : find-skills, agent-browser, vercel-*, web-design-guidelines, writing-guidelines, deploy-to-vercel.
- **Angular Team** — [`angular/skills`](https://github.com/angular/skills) : angular-developer, angular-new-app.
- **AnalogJS** — [`analogjs/angular-skills`](https://github.com/analogjs/angular-skills) : angular-component, -di, -directives, -forms, -http, -routing, -signals, -ssr, -testing, -tooling.
- **SivaLabs** — [`sivaprasadreddy/sivalabs-agent-skills`](https://github.com/sivaprasadreddy/sivalabs-agent-skills) : spring-boot-skill, jspecify-skill.
- **Julien Dubois** — [`jdubois/dr-jskill`](https://github.com/jdubois/dr-jskill) : dr-jskill.
- **Supabase** — [`supabase/agent-skills`](https://github.com/supabase/agent-skills) : supabase-postgres-best-practices.
- **Netresearch** — [`netresearch/docker-development-skill`](https://github.com/netresearch/docker-development-skill) : docker-development.
- **Tim Koda** — [`koda-stack`](https://github.com/timkoda/koda-stack), licence MIT conservée dans [`koda-stack/LICENSE`](./koda-stack/LICENSE).
