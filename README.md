# 🚀 FinanceAI Pro — Site Complet Prêt à Déployer

**Site de blog sur la Finance Automatique, Revenus Passifs & Business IA**

> ✅ Google AdSense connecté : `ca-pub-3022790927047442`

---

## ✅ Ce qui est déjà configuré

| Élément | Statut | Détail |
|---------|--------|--------|
| AdSense Publisher ID | ✅ Connecté | `ca-pub-3022790927047442` |
| ads.txt | ✅ Créé | `/public/ads.txt` |
| Script AdSense | ✅ Actif | Dans `layout.tsx` |
| Unités d'annonces | 🔧 À compléter | Voir étape 3 |
| Toutes pages légales | ✅ Présentes | Privacy, Terms, Cookies, Legal, Disclaimer |
| SEO technique | ✅ Complet | Sitemap, Robots, JSON-LD, OpenGraph |
| Articles de blog | ✅ 10+ articles | À compléter avec vos articles |

---

## 🔧 ÉTAPE 1 — Installation locale

```bash
# Cloner / copier le projet dans un dossier
cd financeai-pro

# Installer les dépendances
npm install

# Lancer en développement
npm run dev
# → Ouvrir http://localhost:3000
```

---

## 🌐 ÉTAPE 2 — Déploiement sur Vercel (5 minutes)

### Méthode A : Via GitHub (recommandée)
1. Créez un repo GitHub (github.com/new)
2. Poussez le code :
```bash
git init
git add .
git commit -m "Initial commit — FinanceAI Pro"
git remote add origin https://github.com/VOTRE-USERNAME/financeai-pro.git
git push -u origin main
```
3. Allez sur **vercel.com** → "New Project"
4. Importez votre repo GitHub
5. Cliquez **Deploy** — c'est tout !

### Méthode B : Via Vercel CLI
```bash
npm install -g vercel
vercel login
vercel --prod
```

---

## 💰 ÉTAPE 3 — Créer vos Unités d'Annonces AdSense

Votre compte AdSense est déjà connecté (`ca-pub-3022790927047442`). Il faut maintenant créer les unités d'annonces :

### 3.1 Connexion AdSense
1. Allez sur **adsense.google.com**
2. Connectez-vous avec votre compte Google

### 3.2 Créer les unités (si pas encore fait)
**Annonces → Par unité → Créer une annonce**

Créez ces 5 unités :

| Nom à donner | Format | Taille |
|-------------|--------|--------|
| `FAP-Leaderboard` | Display | 728×90 ou adaptatif |
| `FAP-Rectangle` | Display | 300×250 ou adaptatif |
| `FAP-InFeed` | In-feed | Adaptatif |
| `FAP-Article` | In-article | Adaptatif |
| `FAP-Sidebar` | Display | 300×600 ou adaptatif |

### 3.3 Copier les Slot IDs
Pour chaque unité créée, notez le **data-ad-slot** (ex: `1234567890`)

### 3.4 Mettre à jour le code
Ouvrez `src/lib/config.ts` et remplacez :
```typescript
slots: {
  headerBanner: 'VOTRE_SLOT_1',   // ← ID de FAP-Leaderboard
  articleTop:   'VOTRE_SLOT_2',   // ← ID de FAP-Article
  articleMid:   'VOTRE_SLOT_3',   // ← ID de FAP-InFeed
  articleBottom:'VOTRE_SLOT_4',   // ← ID de FAP-Rectangle
  sidebar:      'VOTRE_SLOT_5',   // ← ID de FAP-Sidebar
  inFeed:       'VOTRE_SLOT_6',   // ← ID supplémentaire
}
```

Puis dans `src/components/ui/AdSlot.tsx`, remplacez aussi les numéros de slot dans les composants.

---

## 🌍 ÉTAPE 4 — Connecter votre Domaine

### Sur Vercel
1. Tableau de bord Vercel → votre projet → **Settings → Domains**
2. Ajoutez votre domaine (ex: `financeaipro.com`)
3. Copiez les DNS records affichés

### Chez votre Registrar (OVH, Namecheap, etc.)
Ajoutez ces enregistrements DNS :
```
Type A    → 76.76.19.61        (Vercel IP)
Type CNAME → www → cname.vercel-dns.com
```

### Mettre à jour la config
Dans `src/lib/config.ts`, mettez à jour :
```typescript
url: 'https://www.VOTRE-DOMAINE.com',
```

---

## 📊 ÉTAPE 5 — Google Search Console & Analytics

### Google Search Console
1. Allez sur **search.google.com/search-console**
2. Ajoutez votre propriété (domaine)
3. Vérifiez via DNS TXT record
4. Soumettez le sitemap : `https://votre-domaine.com/sitemap.xml`

### Google Analytics 4
1. **analytics.google.com** → Créer une propriété GA4
2. Copiez votre **Measurement ID** (ex: G-XXXXXXXXXX)
3. Dans `src/app/layout.tsx`, décommentez et complétez :
```javascript
// Remplacez G-XXXXXXXXXX par votre vrai ID
gtag('config', 'G-XXXXXXXXXX');
```

---

## 📋 ÉTAPE 6 — Vérification ads.txt

Après déploiement, vérifiez que ads.txt est accessible :
```
https://votre-domaine.com/ads.txt
```
Le contenu doit être :
```
google.com, pub-3022790927047442, DIRECT, f08c47fec0942fa0
```

---

## 📝 ÉTAPE 7 — Ajouter des Articles

### Option A : Modifier `src/lib/articles.ts`
Ajoutez vos articles dans le tableau `articles` avec ce format :
```typescript
{
  slug: 'mon-titre-article',
  title: 'Mon Titre d\'Article Optimisé SEO',
  excerpt: 'Description courte de 150-160 caractères...',
  content: `## Introduction\n\nVotre contenu ici...`,
  category: 'Revenus Passifs',
  categorySlug: 'revenus-passifs',
  author: 'FinanceAI Pro',
  publishedAt: '2025-05-20',
  updatedAt: '2025-05-20',
  readTime: 8,
  tags: ['tag1', 'tag2', 'tag3'],
  featured: false,
  views: 0,
}
```

---

## ✅ Checklist avant soumission AdSense

- [ ] Site déployé sur domaine personnalisé (pas .vercel.app)
- [ ] `ads.txt` accessible et correct
- [ ] Page À propos complète et professionnelle
- [ ] Page Contact avec formulaire fonctionnel
- [ ] Politique de Confidentialité mentionnant AdSense
- [ ] Mentions légales présentes
- [ ] Disclaimer financier présent
- [ ] Minimum 20-30 articles de contenu original
- [ ] Pas de contenu dupliqué ou spam
- [ ] Site en HTTPS
- [ ] Core Web Vitals au vert (PageSpeed Insights)
- [ ] Newsletter fonctionnelle
- [ ] Sitemap soumis à Google Search Console
- [ ] Trafic organique visible (attendre 1-3 mois de contenu)

---

## 📁 Structure du Projet

```
financeai-pro/
├── public/
│   ├── ads.txt              ← ✅ OBLIGATOIRE AdSense
│   ├── app-ads.txt
│   └── favicon.svg
├── src/
│   ├── app/
│   │   ├── layout.tsx       ← Script AdSense intégré
│   │   ├── page.tsx         ← Homepage
│   │   ├── sitemap.ts       ← SEO sitemap auto
│   │   ├── robots.ts        ← Robots.txt
│   │   ├── blog/
│   │   │   ├── page.tsx     ← Liste articles
│   │   │   └── [slug]/      ← Article individuel (ads intégrées)
│   │   ├── categories/[slug]/
│   │   ├── about/           ← Page À propos (E-E-A-T)
│   │   ├── contact/         ← Formulaire contact
│   │   ├── privacy/         ← ✅ Requis AdSense
│   │   ├── terms/           ← ✅ Requis AdSense
│   │   ├── cookies/         ← ✅ Requis AdSense
│   │   ├── legal/           ← Mentions légales
│   │   ├── disclaimer/      ← Disclaimer financier
│   │   └── newsletter/
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Header.tsx
│   │   │   ├── Footer.tsx
│   │   │   └── TickerBar.tsx
│   │   ├── blog/
│   │   │   └── ArticleCard.tsx
│   │   └── ui/
│   │       ├── AdSlot.tsx   ← ✅ Unités AdSense
│   │       ├── Newsletter.tsx
│   │       ├── ShareButtons.tsx
│   │       └── CookieBanner.tsx
│   ├── lib/
│   │   ├── articles.ts      ← Base de données articles
│   │   └── config.ts        ← ✅ Config avec pub ID
│   └── styles/
│       └── globals.css
├── next.config.js           ← Headers CSP compatibles AdSense
├── package.json
└── README.md
```

---

## 🎯 Optimisation RPM AdSense

Pour maximiser vos revenus publicitaires :

1. **Ciblez le trafic USA/Europe** (RPM 2-5× plus élevé)
2. **Articles longs 1500-3000 mots** (plus d'annonces)
3. **Format auto AdSense** activé
4. **Placement stratégique** : après le titre, milieu article, fin d'article, sidebar
5. **Core Web Vitals** au vert (vitesse = plus de clics)
6. **Trafic organique SEO** (plus qualifié = meilleur CTR)

---

## 🆘 Support

- Email : contact@financeaipro.com
- Documentation Next.js : https://nextjs.org/docs
- Documentation AdSense : https://support.google.com/adsense
