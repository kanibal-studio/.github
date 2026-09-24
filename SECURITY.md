# Politique de sécurité

Cette politique s'applique à tous les dépôts publics de l'organisation
[Kanibal Studio](https://github.com/kanibal-studio) (Altavista360), sauf politique
spécifique publiée dans le dépôt concerné.

## Versions prises en charge

Chaque outil est maintenu sur sa branche principale et sa dernière version publiée.
Les correctifs de sécurité ne sont pas rétroportés sur les versions antérieures :
mettez à jour vers la dernière version.

## Signaler une vulnérabilité

**Ne décrivez jamais une vulnérabilité dans une issue, une pull request ou une
discussion publique.**

1. **Signalement privé GitHub, canal privilégié.** Sur le dépôt concerné, onglet
   *Security* puis *Report a vulnerability* (« Signaler une vulnérabilité »). Le rapport
   n'est visible que des mainteneur·euse·s. Voir le
   [guide GitHub](https://docs.github.com/fr/code-security/how-tos/report-and-fix-vulnerabilities/report-privately).
2. **Si ce bouton n'est pas proposé** sur le dépôt, ouvrez une issue avec le modèle
   « Question », *sans aucun détail technique*, en demandant un canal privé : un·e
   mainteneur·euse vous répondra avec un moyen de contact confidentiel.

Indiquez : le dépôt et la version concernés, le type de vulnérabilité, les étapes de
reproduction ou une preuve de concept, et l'impact estimé.

## Ce que vous pouvez attendre

- un accusé de réception, puis la qualification du rapport ;
- des échanges sur la correction et sa date de publication ;
- un crédit dans l'avis de sécurité publié, si vous le souhaitez.

Nous pratiquons la divulgation coordonnée : merci de nous laisser un délai raisonnable,
jusqu'à 90 jours, pour corriger avant toute publication.

## Pour les mainteneur·euse·s

Le signalement privé doit être activé sur chaque dépôt, ou pour toute l'organisation
en une fois : voir
[activer le signalement privé](https://docs.github.com/fr/code-security/how-tos/report-and-fix-vulnerabilities/configure-vulnerability-reporting/configure-for-a-repository).
Tant qu'il ne l'est pas, seul le point 2 ci-dessus fonctionne.

## Périmètre

- **Couvert** : le code et la configuration des dépôts de l'organisation.
- **Non couvert** : les dépendances tierces (signalez-les à leurs mainteneurs), les
  attaques par déni de service et l'ingénierie sociale.
- Les sites web d'Altavista360 ne relèvent pas de cette politique GitHub ; un
  signalement les concernant reçu par ce canal sera transmis à l'équipe compétente.
