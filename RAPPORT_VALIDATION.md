# Rapport de validation de la livraison

## Vérifications réellement exécutées

| Contrôle | TP3 | TP4 |
|---|---:|---:|
| Tests/scénarios réussis | 44 | 64 |
| Échecs finaux | 0 | 0 |
| Couverture src.sales_processing | 100 % | 100 % |
| Tests d'intégration locaux | 13 | 13 conservés |
| Tests API | — | 20 |
| Ruff strict du TP1 | Validé | Validé |
| Formatage Ruff | Validé | Validé |
| pre-commit (Ruff + pytest rapide) | Validé | Validé |
| CSV/initial.py originaux, vérification SHA-256 | Identiques | Identiques |
| Code et tests hérités du TP3 | Base | Conservés à l'identique |
| Git local, commits et tags | Inclus | Inclus, avec historique TP3 |

Le seuil exigé est 80 % ; la couverture observée de 100 % concerne uniquement
le module historique sales_processing, pas l'ensemble du serveur ni toutes les
situations réelles possibles. Les rapports de tests et de couverture contiennent
les versions Python et paquets effectivement utilisés.

## API et modèle
Le script d'entraînement a été exécuté ; le pipeline entier a été sauvegardé.
L'évaluation hors entraînement est dans TP4_FastAPI/output/training.txt.
Un vrai processus Uvicorn a été lancé puis arrêté proprement. Des requêtes HTTP
locales réelles ont vérifié la santé (200), la prédiction valide (200), trois
entrées invalides (422), /docs (200), /redoc (200) et /openapi.json (200).
Les réponses JSON exactes sont dans output/api_http_examples.json.
Les cas 503 et 500 sont vérifiés via les tests isolés, pas par destruction du
modèle livré. Les pages de documentation sont servies ; leur interface navigateur
n'a pas fait l'objet d'une capture visuelle.

## Git, gate et refactoring
Le refus d'un commit avec un test volontairement faux est enregistré dans
TP3_Integration/output/git_gate.txt. Le retour du commit est non nul et HEAD est
resté inchangé. Le test temporaire a été supprimé, puis toute la suite finale est
repassée au vert. Aucun test faux ne figure dans l'archive.
L'extraction de DEFAULT_COUNTRY est documentée par docs/refactoring.patch et les
rapports avant/après. Les deux étapes passent les tests.
Les derniers états Git des deux projets sont propres lors de la validation.
Les hooks générés sont exclus de l'archive pour ne pas embarquer un chemin Python
propre à l'environnement de préparation : les réinstaller comme indiqué au README.

## Limites explicites des sources et du périmètre
- Le ZIP TP1 fournit un squelette et un CSV, pas une correction ni des tests TP2.
- Le guide PDF TP1 cité par son README ne figure pas dans le ZIP reçu.
- Le schéma à huit colonnes du TP1 est conservé ; les exemples simplifiés du TP3
  sont adaptés et la différence country/customer_country est expliquée.
- Les appels externes de taux de change sont mockés ; les tests ne valident pas
  la disponibilité future de ce service Internet.
- S3 est simulé avec Moto, sans compte AWS ni appel cloud réel.
- Le modèle est pédagogique, sa cible est déterministe et sa probabilité n'est
  pas une prévision commerciale fiable.
- Aucun déploiement distant, commit distant ni transmission à l'enseignant n'est effectué.

## Fichiers de preuve
Dans chaque dossier output/ : tests.txt, junit.xml, coverage.txt, coverage.json,
integration.txt, ruff.txt, format.txt, pre_commit.txt, pipeline.txt,
source_integrity.json, environment.json, git_history.txt et git_status.txt.
Le TP4 ajoute api_tests.txt, training.txt, http_smoke.txt, api_http_examples.json,
openapi.json et tp3_preservation.json. Les comptes rendus sont dans docs/.
