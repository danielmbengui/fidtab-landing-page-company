# FidTab — Site vitrine

Site marketing **Next.js** pour présenter **FidTab** aux tabacs et commerces de proximité indépendants : boutique en ligne personnalisée, carte de fidélité digitale et outils de gestion, sans compétence technique requise.

---

## Pages du site

| Route | Rôle |
|-------|------|
| `/` | Page d’accueil — argumentaire commercial complet |
| `/request-demo` | Formulaire de demande de démo |
| `/contact` | Coordonnées (e-mail, WhatsApp) |
| `/legal-notice` | Mentions légales |
| `/terms` | Conditions générales d’utilisation (CGU) |
| `/privacy` | Politique de confidentialité |

Toutes les pages secondaires partagent la même navigation, le sélecteur de langue et le pied de page. Les textes sont centralisés dans `src/i18n/messages.js` (français par défaut, avec **en**, **de**, **it**).

---

## Page d’accueil (`/`)

Landing page en une seule page défilante, avec ancres dans le menu : Fonctionnalités, Fidélité, Comment ça marche, Tarifs, puis CTA vers la démo.

### Hero

- **Positionnement** : solution clé en main pour tabacs indépendants.
- **Message** : « Votre commerce, dans la poche de vos clients » — boutique en ligne, carte de fidélité et tableau de bord, sans effort technique.
- **Chiffres mis en avant** : +38 % de clients récurrents, mise en ligne en 2 semaines, 0 CHF de frais cachés.
- **Visuel** : mockup téléphone (app fictive *Vaakai Store*) avec commandes, points fidélité et notifications.
- **Actions** : lancer le tabac en ligne → `/request-demo` ; lien vers la section « Comment ça marche ».

### Bandeau partenaires

- Défilement des noms de tabacs partenaires (données statiques + complément possible via **Firebase** / collection commerces).
- Accroche : des tabacs indépendants qui font confiance à FidTab.

### Fonctionnalités (`#fonctionnalites`)

Grille de **7 blocs** :

| Fonctionnalité | Contenu |
|----------------|---------|
| Boutique en ligne | Nom, logo, couleurs du commerce ; commande 24h/24 |
| Carte de fidélité digitale | Points automatiques, récompenses au choix du commerçant |
| Tableau de bord | Ventes, clients fidèles, meilleures ventes en temps réel |
| Click & Collect | Commande en ligne, retrait au comptoir — *bientôt disponible* |
| Notifications push | Promotions ciblées sur le téléphone du client |
| Gestion des stocks | Catalogue produits, ruptures, modifications rapides |
| Mise en ligne rapide | Boutique prête en moins de 2 semaines (design, paramétrage, formation) |

### Carte de fidélité (`#fidelite`)

- **Promesse** : la carte qui fait revenir les clients — points à chaque achat, visibles sur mobile.
- **4 points forts** : points automatiques, récompenses personnalisées, carte utilisable chez plusieurs tabacs partenaires, rappels proches d’une récompense.
- **Démo visuelle** : carrousel de cartes exemple (Vaakai Store, Tabac Rhein, Swiss Tabac) avec barre de progression et récompenses en CHF.
- **Statistiques animées** : taux de retour et cartes actives.

### Comment ça marche (`#comment`)

Trois étapes :

1. **Personnalisation** — logo, couleurs, catalogue ; validation par le commerçant.
2. **Lancement** — mise en ligne, configuration fidélité, formation équipe (~1 h).
3. **Croissance** — commandes, points, suivi via le tableau de bord.

### Vitrine multi-tabacs (`#stores`)

- **Idée** : chaque tabac garde sa propre identité (URL, couleurs, clientèle).
- **Exemples** : cartes boutique (dont **Vaakai Store** — partenaire réel, Genève/Meyrin, lien vers [vaakai-store.vercel.app](https://vaakai-store.vercel.app)) ; autres vitrines type Tabac Rhein, Swiss Tabac.
- Données vitrine alimentées par **Firestore** quand la config Firebase est présente, sinon données de repli dans `src/config/partnerData.js`.

### Témoignages / partenaire (`#temoignages`)

- Mise en avant de **Vaakai Store** comme partenaire déjà en ligne.
- Bénéfices : identité propre (logo, couleurs, URL dédiée) et mise en ligne accompagnée.

### Tarifs (`#tarifs`)

- Facturation **mensuelle** ou **annuelle** (équivalent « −2 mois » sur l’annuel).
- **3 formules** (prix en CHF) :

| Plan | Mensuel | Annuel | Pour qui |
|------|---------|--------|----------|
| **Starter** | 49 | 490 | Démarrer : boutique, 50 produits max, fidélité basique, support e-mail |
| **Pro** *(populaire)* | 99 | 990 | Complet : boutique et produits illimités, fidélité avancée, push, analytics, support prioritaire |
| **Multi** | 149 | 1 490 | Jusqu’à 5 boutiques, fidélité multi-enseignes, dashboard central, formations, account manager |

- **Option à la carte** : site internet personnalisé — forfait unique **199 CHF** (en complément de l’abonnement).

### Appel à l’action final (`#demo`)

- **Titre** : prêt à digitaliser votre commerce ?
- **Promesses** : démo sans engagement, mise en ligne en 2 semaines, support inclus.
- **Liens** : demande de démo → `/request-demo` ; contact téléphonique / WhatsApp.

### Pied de page

Liens vers les sections de l’accueil, mentions légales, CGU, confidentialité, contact et CTA démo.

---

## Demande de démo (`/request-demo`)

Formulaire orienté **prise de contact commerciale** (envoi via `mailto:` vers `contact@fidtab.com`).

- **Titre** : Passons à l’action — rappel rapide pour présenter FidTab.
- **Champs obligatoires** : nom du commerce, nom du contact.
- **Canal de rappel** (au choix) : e-mail, téléphone (validation internationale), ou WhatsApp.
- **Champ optionnel** : message libre.
- Après envoi : écran de confirmation ; le client mail s’ouvre avec l’objet `[FidTab] Demande de démo — {commerce}`.

---

## Contact (`/contact`)

Page simple, sans formulaire intégré :

- **E-mail** : `contact@fidtab.com` (lien `mailto:` avec sujet « Contact FidTab »).
- **WhatsApp** : numéro défini dans `src/context/constants/constants_app.js` (`CONTACT_WHATSAPP`).

---

## Pages légales

Documents structurés par sections, avec liens croisés entre eux et date de mise à jour (**mai 2026**).

### Mentions légales (`/legal-notice`)

Éditeur (FidTab), hébergement, propriété intellectuelle, responsabilité — dont précision sur la fidélité (points et récompenses selon chaque tabac partenaire, contrôle d’âge en magasin).

### CGU (`/terms`)

Objet du service, description (boutique + fidélité + gestion), **règles détaillées de la carte de fidélité** (responsabilité du tabac partenaire pour l’inscription, le scan QR et l’âge légal), abonnements et tarifs, obligations des parties, renvoi vers la politique de confidentialité, droit applicable.

### Confidentialité (`/privacy`)

Responsable du traitement, données collectées (formulaires, données techniques), finalités, traitement dans le **programme de fidélité** (données côté commerçant partenaire), durée de conservation, droits RGPD, cookies.

---

## Langues

Interface et contenus marketing disponibles en **français**, **anglais**, **allemand** et **italien**. Le choix de langue est mémorisé côté client (`LanguageProvider`). Les traductions admin / back-office partagent le même fichier via `src/i18n/admin/translations.js`.

---

## Démarrage rapide

```bash
npm install
npm run dev
```

Ouvrir [http://localhost:3000](http://localhost:3000).

Pour la vitrine partenaires en temps réel, configurer Firebase dans `.env.local` (variables `NEXT_PUBLIC_*` — voir `src/lib/firebasePublicConfig.js`). Sans Firebase, le site fonctionne avec les données de démonstration.

```bash
npm run build   # production
npm run start   # serveur production
npm run lint    # ESLint
```

---

## Stack (aperçu)

- **Next.js 16** — App Router, React 19
- **Polices** — Syne (titres), DM Sans (corps)
- **CSS** — `src/app/globals.css` (variables, animations, responsive)
- **i18n** — `src/i18n/messages.js` + `LanguageProvider`
- **Firebase** (optionnel) — partenaires / vitrine depuis Firestore
- **MUI** — composants UI ponctuels (champs téléphone, etc.)

---

## Structure utile

```
src/
  app/
    page.js              # Accueil
    request-demo/        # Formulaire démo
    contact/             # Contact
    legal-notice/        # Mentions légales
    terms/               # CGU
    privacy/             # Confidentialité
  i18n/messages.js       # Textes des pages (FR, EN, DE, IT)
  context/constants/     # Nom de marque, e-mails, chemins
  config/partnerData.js  # Données Vaakai Store (repli)
  components/            # Nav, footer, mockup, pages secondaires
```

---

## Personnalisation du contenu

| Besoin | Fichier |
|--------|---------|
| Textes marketing et pages légales | `src/i18n/messages.js` |
| Nom de marque, e-mail, WhatsApp, chemins | `src/context/constants/constants_app.js` |
| Partenaire Vaakai (témoignage / vitrine) | `src/config/partnerData.js` |
| Couleurs et styles | `src/app/globals.css` |
| Tarifs affichés | section `pricing` dans `messages.js` |
