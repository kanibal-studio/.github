# Contribuer aux outils de Kanibal Studio

Merci de votre intérêt. Ce guide s'applique à tous les dépôts de l'organisation
[Kanibal Studio](https://github.com/kanibal-studio), sauf indication contraire dans le
dépôt concerné. En participant, vous acceptez le [code de conduite](CODE_OF_CONDUCT.md).

## Ce que vous pouvez faire

- **Signaler un bug** avec le modèle « Rapport de bug » : version, étapes de
  reproduction, journaux.
- **Proposer une fonctionnalité** avec le modèle « Proposition de fonctionnalité » :
  problème, solution envisagée, alternatives.
- **Améliorer la documentation** : une faute, un exemple manquant, une explication
  confuse, tout compte.
- **Corriger ou implémenter** : pour un changement conséquent, ouvrez d'abord une issue
  afin d'en discuter avant d'y consacrer du temps.

Une vulnérabilité ne se signale jamais dans une issue publique : voir
[SECURITY.md](SECURITY.md).

## Proposer une modification

1. Forkez le dépôt et créez une branche depuis `main` (`fix/…`, `feat/…`, `docs/…`).
2. Faites un changement ciblé : une pull request traite un seul sujet.
3. Ajoutez ou adaptez les tests ; ils doivent passer localement. Chaque dépôt documente
   sa commande de test dans son README.
4. Mettez à jour la documentation concernée (README, changelog s'il existe, docstrings).
5. Ouvrez la pull request en suivant le modèle proposé ; la CI doit être verte.

### Messages de commit

- À l'impératif, en français ou en anglais, première ligne de 72 caractères au plus.
- Préfixe recommandé de type
  [Conventional Commits](https://www.conventionalcommits.org/fr/v1.0.0/) : `feat:`,
  `fix:`, `docs:`, `test:`, `ci:`, `refactor:`, `chore:`.
- Le corps explique le *pourquoi* ; le diff montre déjà le *quoi*.

### Qualité attendue

- Pas de code mort, de doublon ni de configuration inutilisée.
- Pas de secret, d'identifiant ni de donnée personnelle dans le code, les tests ou les
  journaux.
- Un changement de comportement visible est documenté ; s'il casse la compatibilité, il
  est signalé explicitement dans la pull request.
- Les dépôts peuvent réutiliser le workflow
  [`docs-quality`](.github/workflows/docs-quality.yml) de l'organisation pour vérifier
  Markdown, YAML, workflows GitHub Actions et liens.

## Revue et fusion

Un·e mainteneur·euse relit chaque pull request. Les demandes de changement sont des
questions, pas des reproches : répondez-y ou expliquez votre choix. Les décisions finales
reviennent aux mainteneur·euse·s d'Altavista360, qui priorisent selon l'usage réel des
outils.

## Licence des contributions

Sauf mention contraire dans le dépôt, les outils sont publiés sous licence MIT. Toute
contribution est réputée soumise sous la licence du dépôt qui la reçoit (principe
« inbound = outbound »). Aucun accord de contributeur (CLA) n'est demandé.
