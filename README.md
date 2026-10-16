# Travaux Software Engineering — livraison complète

Cette archive contient deux **projets Python locaux complets**, prêts à ouvrir dans VS Code.

1. **TP3_Integration/** : solution TP1 complétée, unités TP2, intégrations TP3, Ruff et pre-commit.
2. **TP4_FastAPI/** : même base conservée, plus entraînement ML, modèle sauvegardé et API REST.

Ouvrir le README du dossier souhaité ; toutes les commandes partent de sa racine.
Les environnements .venv doivent être créés localement, ils ne sont pas inclus.
Les dossiers docs/ contiennent les réponses aux étapes, justifications et choix techniques.
Les dossiers output/ contiennent les rapports réellement produits à la vérification.
Les historiques Git locaux, commits et tags sont inclus ; réinstaller les hooks après extraction.
Aucun notebook Colab n'est requis ni inclus.

Sources examinées : ZIP TP1_Clean_Code, PDF TP2_pytest, TP3_Test_intégration,
TP4_Exposer un modèle ML avec FastAPI, Bloc3_Soft_Engineering et Bloc4_Soft_Engineering.
Le ZIP TP1 contient un squelette, pas une correction ni des tests TP2 déjà écrits.
La solution complète ces éléments à partir des consignes reçues.
Le guide PDF mentionné par le README TP1 est absent du ZIP fourni.

## Ce qui est vérifié
- intégrité d'initial.py et du CSV TP1 ;
- maintien du code et des tests hérités entre TP3 et TP4 ;
- tests unitaires, intégrations, API et seuil historique de couverture ;
- profil Ruff strict d'origine, formatage et hooks pre-commit ;
- refus d'un vrai commit avec un test faux puis restauration ;
- refactoring avec tests avant/après et patch enregistré ;
- modèle réellement entraîné, chargé et interrogé ;
- Uvicorn et routes interrogées sur un port HTTP local lors de la livraison.

Les preuves détaillées et limites figurent dans RAPPORT_VALIDATION.md et chaque dossier output/.
Les erreurs volontaires du rapport git_gate.txt sont attendues : aucun faux test ne subsiste.
