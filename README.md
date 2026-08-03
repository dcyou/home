# home — dcyou.co

Page d'accueil publique du portfolio **dcyou**, servie sur **https://dcyou.co**.

C'est une *project page* GitHub Pages, et c'est **délibéré**.

## Pourquoi un dépôt de projet et pas `dcyou.github.io`

Poser un domaine personnalisé sur le **site utilisateur** (`dcyou/dcyou.github.io`)
ferait basculer **tout** `dcyou.github.io` en 301 vers le domaine — y compris les
project pages. Or `https://dcyou.github.io/legal/letterscatch/` est l'URL de
confidentialité **déclarée à Apple et à Google**. Elle ne doit pas bouger.

Sur un dépôt de **projet**, la redirection est *scopée au préfixe du dépôt* : seul
`https://dcyou.github.io/home/` redirige vers `https://dcyou.co/`. Le site
utilisateur et `dcyou/legal` ne bougent pas d'un octet.

Vérifié sur des comptes réels ayant les deux configurations en même temps
(`google/jsonnet` → jsonnet.org, `Netflix/hollow` → hollow.how,
`nix-community/builtwithnix.org`, `uber/h3`, `microsoft/maker.js`, `pinterest/l10nmessages`) :
dans tous les cas `https://{owner}.github.io/` répond **200 sans redirection** et
les autres project pages aussi.

## DNS attendu chez Infomaniak (zone `dcyou.co`)

    A     @    185.199.108.153
    A     @    185.199.109.153
    A     @    185.199.110.153
    A     @    185.199.111.153
    AAAA  @    2606:50c0:8000::153
    AAAA  @    2606:50c0:8001::153
    AAAA  @    2606:50c0:8002::153
    AAAA  @    2606:50c0:8003::153
    CNAME www  dcyou.github.io.

Les sous-domaines existants (`letterscatch`, `duomatch`, `animalsoul`, …) ne sont
pas concernés : ils gardent leurs enregistrements actuels.

Une fois les A/AAAA en place et le certificat émis, activer **Enforce HTTPS**
dans Settings → Pages.

## Contenu

Identique à `dcyou/dcyou.github.io` (voir ce dépôt pour le détail des 30 langues).
Ce dépôt-ci est la **version canonique** ; le site utilisateur n'est qu'un miroir
temporaire, à remplacer par une redirection une fois `dcyou.co` en ligne.

- `index.html` — la page, un seul fichier, zéro dépendance
- `icons/` — icônes des apps **déjà sorties** uniquement (SVG autonomes)
- `CNAME` — porte le domaine `dcyou.co`

**Aucune application non lancée n'apparaît sur cette page** : ni son nom, ni son
sujet, ni le nom de fichier de son icône, ni même le nombre d'apps en cours (il
fuirait par différence à chaque sortie). La section « En préparation » ne contient
qu'une carte teaser anonyme. Une app n'y gagne son nom que le jour où elle est
publiquement accessible.

**Cette règle s'applique au commit, pas seulement à la page** : sur un dépôt
public, un commit reste servi par `raw.githubusercontent.com` même après que son
contenu a été retiré de la page. Retirer un nom dans un commit suivant ne
l'efface pas, ça le laisse une URL plus loin — la règle vaut donc **avant** le
commit.

Mentions légales par application : https://dcyou.github.io/legal/
Contact : support@dcyou.co
