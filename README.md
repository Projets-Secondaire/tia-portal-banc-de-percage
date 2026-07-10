# Banc de perçage automatisé (SI3) – TIA Portal V16

Situation d'intégration 3 – 6ᵉ secondaire – Année scolaire 2023-2024

## Description

Automatisation d'un banc de perçage industriel, développée sur Siemens S7-1200 (CPU 1214C DC/DC/DC) sous TIA Portal V16. Le cycle est commandé par un programme en logique à contacts, obtenu à partir de la traduction du GRAFCET, avec gestion du perçage, du clamage/déclamage de la pièce, de l'éjection et de la sécurité (arrêt d'urgence, capot).

## Fonctionnement

1. Détection d'une pièce métallique et fermeture du capot
2. Clamage de la pièce (vérin B)
3. Perçage : descente puis remontée du vérin A, moteur actif
4. Déclamage de la pièce (vérin B)
5. Éjection de la pièce (vérin C)
6. Retour en position d'attente, prêt pour un nouveau cycle

Le cycle intègre aussi la gestion de l'arrêt d'urgence, du capot de sécurité et la signalisation par voyants (H1, H2, H3).

## Méthodologie

- **GRAFCET niveau 1** : cycle de fonctionnement (vue métier)
- **GRAFCET niveau 2** : équations logiques (conditions d'évolution selon les capteurs)
- **GRAFCET niveau 3** : adressage automate (%I, %Q, %M)
- Programmation en logique à contacts (CONT) sur TIA Portal V16 : blocs Transition (FC1), Sortie (FC2), Signalisation (FC3), Startup (OB100), Main (OB1)

## Matériel

- Automate Siemens S7-1200, CPU 1214C DC/DC/DC
- 3 vérins pneumatiques (A, B, C) avec capteurs de fin/début de course
- Moteur de perçage triphasé
- Capteur inductif de détection de pièce métallique
- Boutons poussoir, arrêt d'urgence, relais auxiliaires (Ka0-Ka9), contacteur KM1
- Voyants de signalisation (H1, H2, H3)

## Rapport complet

Le rapport complet est disponible dans [`rapport/rapport_banc_de_percage.pdf`](rapport/rapport_banc_de_percage.pdf).
