---
name: seo
description: Audit et optimisation SEO pour le projet Tykode (Next.js App Router). Use when asked to "audit SEO", "optimiser le SEO", "vérifier les métadonnées", "améliorer le référencement", "ajouter structured data", "vérifier Open Graph", or "SEO d'une page".
metadata:
  author: tykode
  version: "1.0.0"
  argument-hint: <page-ou-composant>
---

# SEO Tykode — Next.js App Router

Skill d'audit et d'optimisation SEO pour le site Tykode, agence digitale en Guyane.

## Stack SEO du projet

- **Framework** : Next.js 15+ App Router
- **Metadata API** : `generateMetadata()` de Next.js (`Metadata` type)
- **Utilitaires** : `apps/web/src/lib/utils/metadata.ts`
  - `generateMetadata()` — métadonnées génériques
  - `generateServiceMetadata()` — pages de service
  - `generateOrganizationSchema()` — JSON-LD Organisation
  - `generateServiceSchema()` — JSON-LD Service
  - `generateBreadcrumbSchema()` — JSON-LD Breadcrumb
- **Config site** : `apps/web/src/lib/config/site.ts` → `siteConfig`
- **Marché cible** : Guyane française (973), Cayenne — locale `fr_GF`

## Ce que fait cette skill

1. Lire les fichiers indiqués (layout.tsx, page.tsx, ou autres)
2. Auditer chaque point de la checklist ci-dessous
3. Proposer des corrections concrètes en utilisant les utilitaires existants du projet
4. Signaler les problèmes au format `fichier:ligne — [CRITIQUE|MOYEN|FAIBLE] description`

---

## Checklist d'audit SEO

### 1. Métadonnées de base
- [ ] `title` : présent, unique par page, < 60 caractères, contient le mot-clé principal
- [ ] `description` : présente, unique, 120–160 caractères, call-to-action implicite
- [ ] `keywords` : pertinents pour la Guyane (ex: "guyane", "cayenne", "973")
- [ ] `canonical` : URL canonique définie via `alternates.canonical`
- [ ] `robots` : pas de `noIndex` involontaire sur les pages publiques
- [ ] Utilise `generateMetadata()` ou `generateServiceMetadata()` — NE PAS dupliquer la logique

### 2. Open Graph & Twitter Cards
- [ ] `og:title`, `og:description`, `og:image` présents
- [ ] `og:image` : 1200×630px, URL absolue, fichier existant dans `/public`
- [ ] `og:locale` : `fr_GF` pour les pages Guyane
- [ ] `og:type` : `website` (pages) ou `article` (blog)
- [ ] `twitter:card` : `summary_large_image`
- [ ] `twitter:site` : `@tykode`

### 3. JSON-LD Structured Data
- [ ] Page d'accueil : `Organization` schema via `generateOrganizationSchema()`
- [ ] Pages service : `Service` schema via `generateServiceSchema()`
- [ ] Navigation imbriquée : `BreadcrumbList` via `generateBreadcrumbSchema()`
- [ ] JSON-LD injecté avec `<script type="application/ld+json">` dans le JSX
- [ ] Pas de données JSON-LD en doublon entre layout et page

### 4. SEO local — Guyane
- [ ] Mots-clés locaux présents : "guyane", "cayenne", "97300", "973", "antilles-guyane"
- [ ] `areaServed: "GF"` dans les schémas Organization et Service
- [ ] Adresse physique cohérente avec `siteConfig.contact.address`
- [ ] Numéro de téléphone au format E.164 dans les schémas (`+594...`)
- [ ] `lang="fr"` sur `<html>` (déjà présent dans layout.tsx)

### 5. Sitemap & Robots
- [ ] `sitemap.ts` présent dans `apps/web/src/app/` (Next.js MetadataRoute.Sitemap)
- [ ] Toutes les pages publiques incluses dans le sitemap
- [ ] `robots.ts` présent avec `Allow: /` et `Sitemap:` pointer
- [ ] Pas de pages `/dashboard`, `/admin`, `/api` dans le sitemap

### 6. Performance & Core Web Vitals
- [ ] Images : `next/image` utilisé avec `width`, `height` et `alt` descriptif
- [ ] Fonts : chargées via `next/font` (déjà Geist dans layout.tsx)
- [ ] Pas de `layout shift` causé par des images sans dimensions
- [ ] LCP < 2.5s : image hero avec `priority` prop si above-the-fold
- [ ] CLS < 0.1 : skeleton loaders ou dimensions fixes sur les éléments dynamiques

### 7. Balises sémantiques
- [ ] Un seul `<h1>` par page, contenant le mot-clé principal
- [ ] Hiérarchie h1 > h2 > h3 respectée (pas de sauts)
- [ ] `<main>`, `<nav>`, `<footer>`, `<article>`, `<section>` utilisés correctement
- [ ] Liens avec texte descriptif (pas "cliquez ici")
- [ ] Images décoratives avec `alt=""`, images informatives avec alt descriptif

### 8. Maillage interne
- [ ] Pages de service se lient mutuellement (`/services/sites-web` → `/services/e-commerce`)
- [ ] Page d'accueil pointe vers toutes les pages de service
- [ ] Breadcrumb visible et cohérent avec le JSON-LD

---

## Patterns de correction

### Ajouter les métadonnées à une page
```tsx
// apps/web/src/app/services/mon-service/page.tsx
import { generateServiceMetadata } from "@/lib/utils/metadata";

export const metadata = generateServiceMetadata(
  "Nom du Service",
  "Description 120-160 chars avec mots-clés Guyane.",
  "mon-service"
);
```

### Injecter du JSON-LD
```tsx
import { generateServiceSchema, generateBreadcrumbSchema } from "@/lib/utils/metadata";

export default function Page() {
  const serviceSchema = generateServiceSchema({
    name: "Nom du Service",
    description: "Description du service",
    priceFrom: 500,
  });

  const breadcrumb = generateBreadcrumbSchema([
    { name: "Accueil", url: "/" },
    { name: "Services", url: "/services" },
    { name: "Nom du Service", url: "/services/mon-service" },
  ]);

  return (
    <>
      <script
        type="application/ld+json"
        dangerouslySetInnerHTML={{ __html: JSON.stringify(serviceSchema) }}
      />
      <script
        type="application/ld+json"
        dangerouslySetInnerHTML={{ __html: JSON.stringify(breadcrumb) }}
      />
      {/* contenu de la page */}
    </>
  );
}
```

### Sitemap Next.js
```ts
// apps/web/src/app/sitemap.ts
import { MetadataRoute } from "next";
import { siteConfig } from "@/lib/config/site";

export default function sitemap(): MetadataRoute.Sitemap {
  const base = siteConfig.url;
  return [
    { url: base, lastModified: new Date(), changeFrequency: "weekly", priority: 1 },
    { url: `${base}/services`, lastModified: new Date(), changeFrequency: "monthly", priority: 0.9 },
    { url: `${base}/services/sites-web`, lastModified: new Date(), changeFrequency: "monthly", priority: 0.8 },
    // ... autres pages
    { url: `${base}/contact`, lastModified: new Date(), changeFrequency: "yearly", priority: 0.7 },
  ];
}
```

---

## Usage

Si l'utilisateur donne un fichier ou pattern :
1. Lire le fichier
2. Appliquer la checklist complète
3. Sortir les findings par ordre de priorité (CRITIQUE > MOYEN > FAIBLE)
4. Proposer les corrections avec le code exact à utiliser

Si aucun fichier précisé, demander : "Quelle page ou section veux-tu auditer ? (ex: page d'accueil, /services/sites-web, toutes les pages de service)"