# kanibal-studio/.github

Dépôt spécial de l'organisation [Kanibal Studio](https://github.com/kanibal-studio) : il
porte le profil public de l'organisation, les fichiers communautaires appliqués par
défaut à tous ses dépôts, et les workflows GitHub Actions réutilisables.

Le profil affiché sur la page de l'organisation est
[`profile/README.md`](profile/README.md) ; ce README décrit le dépôt lui-même.

## Contenu

| Chemin | Rôle | Portée |
| --- | --- | --- |
| `profile/README.md` | Profil public de l'organisation | Page de l'organisation |
| `CODE_OF_CONDUCT.md` | Code de conduite (Contributor Covenant 2.1, français) | Tous les dépôts sans fichier propre |
| `CONTRIBUTING.md` | Guide de contribution | Tous les dépôts sans fichier propre |
| `SECURITY.md` | Politique de signalement des vulnérabilités | Tous les dépôts sans fichier propre |
| `SUPPORT.md` | Où obtenir de l'aide | Tous les dépôts sans fichier propre |
| `.github/ISSUE_TEMPLATE/` | Formulaires d'issues (bug, fonctionnalité, question) et `config.yml` | Tous les dépôts sans modèles propres |
| `.github/PULL_REQUEST_TEMPLATE.md` | Modèle de pull request | Tous les dépôts sans modèle propre |
| `.github/workflows/docs-quality.yml` | Workflow réutilisable : markdownlint, yamllint, actionlint, lychee | Sur appel (`workflow_call`) |
| `.github/workflows/ci.yml` | CI de ce dépôt, qui appelle `docs-quality.yml` | Ce dépôt |
| `workflow-templates/` | Modèle proposé dans l'onglet Actions des dépôts de l'organisation | Tous les dépôts |
| `.markdownlint-cli2.yaml`, `.yamllint.yml`, `lychee.toml` | Configurations de lint par défaut, servies aux dépôts appelants qui n'ont pas les leurs | Ce dépôt et sur appel |
| `.github/dependabot.yml` | Mise à jour hebdomadaire groupée des actions | Ce dépôt |
| `LICENSE` | MIT, pour le contenu de ce dépôt | Ce dépôt |

Règles GitHub à connaître, d'après la
[documentation officielle](https://docs.github.com/fr/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) :

- un dépôt qui possède son propre fichier (à la racine, dans `.github/` ou `docs/`)
  l'emporte sur le défaut ;
- les formulaires d'issues doivent vivre dans `.github/ISSUE_TEMPLATE/` ;
- une licence ne peut pas être fournie par défaut : chaque dépôt porte la sienne ;
- les labels posés par les formulaires (`bug`, `enhancement`, `question`) sont ceux que
  GitHub crée dans tout nouveau dépôt.

## Utiliser le workflow réutilisable dans un dépôt

```yaml
# .github/workflows/docs-quality.yml
name: Qualité documentaire
on:
  push:
    branches: [main]
  pull_request:
permissions:
  contents: read
jobs:
  docs-quality:
    uses: kanibal-studio/.github/.github/workflows/docs-quality.yml@main
    # with:
    #   check-links: false   # chaque vérification est désactivable
```

Le même modèle est proposé dans l'onglet **Actions** de chaque dépôt de l'organisation
(« Qualité documentaire (Kanibal Studio) »). Un dépôt sans configuration de lint hérite
de celles de ce dépôt ; pour les adapter, il suffit d'ajouter son propre
`.markdownlint-cli2.yaml`, `.yamllint.yml` ou `lychee.toml`.

## Vérifier localement

Les mêmes outils que la CI :

```bash
npx markdownlint-cli2 "**/*.md"
pipx run yamllint --strict .
actionlint                        # https://github.com/rhysd/actionlint
actionlint workflow-templates/*.yml
lychee './**/*.md'                # https://lychee.cli.rs
```

## État réel

| Capacité | État |
| --- | --- |
| Profil public de l'organisation | Réel, affiché sur la page de l'organisation |
| Fichiers communautaires par défaut | Réels ; GitHub les applique aux dépôts sans fichier propre |
| Formulaires d'issues et modèle de PR | Réels, YAML validé ; rendu à contrôler à la première utilisation |
| CI de ce dépôt (`ci.yml`) | Réel, testé localement avec les mêmes outils, exécuté à chaque pull request |
| Workflow réutilisable `docs-quality.yml` | Réel, exercé par `ci.yml` ; le repli sur la configuration de l'organisation n'est validé que par lecture jusqu'au premier appel depuis un autre dépôt |
| Modèle de workflow (`workflow-templates/`) | Implémenté, non testé : visible seulement depuis l'onglet Actions d'un autre dépôt de l'organisation |
| Signalement privé de vulnérabilités | Dépend d'un réglage GitHub à activer par l'organisation (voir `SECURITY.md`) |
| Dependabot (actions) | Réel dès la fusion sur `main` |

## Retour arrière

Chaque changement de ce dépôt est un commit ordinaire : `git revert` suffit. Un défaut
retiré cesse immédiatement de s'appliquer aux autres dépôts, sans autre action.
