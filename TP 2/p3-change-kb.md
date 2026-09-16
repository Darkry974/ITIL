# Partie 3 — Change Enablement, Knowledge Management & Product and Service Lifecycle

## 1. RFC — Mise en place d'un workflow helpdesk traçable

### Informations générales

- **Titre :** Mise en place d'un workflow unique de gestion des tickets helpdesk
- **Type de changement :** Normal
- **Demandeur :** Responsable du service helpdesk
- **Approbrateur proposé :** CAB / responsable habilité à approuver le changement
- **Priorité :** Haute
- **Motif :** Lenteur de traitement, tickets perdus et rappels répétés des utilisateurs.

### Description

Le changement consiste à configurer le portail helpdesk afin que chaque demande soit obligatoirement enregistrée et suive un workflow comprenant au minimum :

1. création du ticket ;
2. qualification et attribution d'une priorité ;
3. attribution à un technicien ou une file ;
4. traitement ;
5. résolution ;
6. clôture.

Chaque étape doit conserver un historique permettant de connaître le responsable et l'état du ticket.

### Justification du type de changement

Le changement est classé **normal** car il modifie le fonctionnement du service existant et peut avoir un impact sur les utilisateurs et les techniciens. Il nécessite donc une évaluation, un test et une validation avant généralisation.

Il n'est pas considéré comme standard puisque la modification du workflow n'est pas décrite comme pré-approuvée dans le contexte. Il n'est pas urgent car le contexte ne signale pas une situation nécessitant une procédure accélérée de changement à risque élevé.

## 2. Analyse d'impact

### Personnes affectées

- Utilisateurs du helpdesk : création et consultation des demandes selon le nouveau workflow.
- Techniciens : qualification, attribution, traitement et clôture des tickets.
- Responsable helpdesk : suivi des files, priorités et indicateurs.
- Éventuel administrateur de l'outil : configuration technique du workflow.

### Risques de régression

- Tickets existants pouvant être mal classés lors de la migration vers les nouveaux statuts.
- Notifications pouvant être mal configurées.
- Techniciens pouvant ne pas maîtriser immédiatement le nouveau workflow.
- Blocage d'une demande si une étape obligatoire est configurée incorrectement.

### Mesures de réduction du risque

- Tester le workflow sur un environnement de test ou avec un périmètre pilote.
- Vérifier la conservation des tickets existants.
- Tester les notifications et les droits.
- Former rapidement les techniciens aux nouveaux statuts.
- Conserver une procédure de retour arrière.

## 3. Plan de mise en œuvre

1. Sauvegarder la configuration et les données nécessaires de l'outil.
2. Configurer les statuts, files, règles d'attribution et notifications.
3. Créer quelques tickets de test représentant plusieurs priorités.
4. Vérifier le parcours création → attribution → traitement → résolution → clôture.
5. Faire valider le résultat par le responsable helpdesk.
6. Déployer le workflow.
7. Surveiller les premiers tickets et relever les anomalies.
8. Mesurer les résultats à l'aide des SLA/SLO définis en Partie 2.

## 4. Plan de rollback

En cas de régression :

1. Désactiver le nouveau workflow.
2. Restaurer la configuration précédente sauvegardée.
3. Vérifier que les tickets existants sont de nouveau accessibles et que leurs historiques sont conservés.
4. Désactiver temporairement les règles de notification nouvellement créées si elles génèrent des erreurs.
5. Informer les techniciens et le responsable helpdesk du retour à l'ancien fonctionnement.
6. Analyser la cause de l'échec avant une nouvelle tentative de déploiement.

## 5. Simulation CAB

### Position du demandeur

Le demandeur recommande l'approbation car le changement répond directement aux trois symptômes observés : tickets perdus, lenteur et rappels répétés. La traçabilité permettra également de mesurer les délais et d'améliorer le pilotage du service.

### Position de l'approbateur

L'approbateur accepte le principe du changement sous réserve que les tests soient concluants, qu'une sauvegarde soit disponible et qu'un rollback puisse être réalisé. Le changement est approuvé pour un déploiement progressif afin de limiter le risque.

**Décision simulée : APPROUVÉ sous conditions.**

## 6. Article de base de connaissance

### Symptôme

Un utilisateur signale qu'une demande au helpdesk n'a pas été traitée ou qu'il doit rappeler plusieurs fois pour obtenir un suivi.

### Cause

La demande n'est pas suffisamment tracée dans un workflow unique : elle peut ne pas être correctement enregistrée, attribuée, suivie ou clôturée.

### Résolution

1. Vérifier que la demande possède un numéro de ticket.
2. Vérifier son statut.
3. Vérifier la file ou le technicien auquel elle est attribuée.
4. Vérifier la priorité et les délais associés.
5. Si le ticket existe, poursuivre son traitement et mettre à jour son statut.
6. Si aucune trace n'existe, créer un nouveau ticket en indiquant le problème initial et le contexte fourni par l'utilisateur.
7. Ne pas clôturer le ticket tant que la résolution n'est pas enregistrée.

### Mots-clés

`helpdesk`, `ticket`, `ticket perdu`, `suivi`, `attribution`, `workflow`, `SLA`, `résolution`

## 7. Positionnement dans le Product and Service Lifecycle

Le changement mobilise principalement les étapes suivantes :

### Design

Le workflow doit être conçu ou repensé : statuts, responsabilités, règles d'attribution, priorités et notifications doivent être définis pour obtenir le résultat attendu.

### Build

La configuration du workflow dans l'outil helpdesk constitue la mise en œuvre concrète du changement.

### Transition

Le changement doit être testé, validé puis introduit dans le service opérationnel avec une gestion du risque et un plan de rollback.

### Operate / Deliver / Support

Après la mise en production, le nouveau fonctionnement est utilisé dans l'activité quotidienne du helpdesk. Les tickets sont traités et les performances sont suivies.

Le modèle n'est pas un enchaînement strictement linéaire : une modification constatée pendant les tests ou l'exploitation peut conduire à revenir à la conception, à reconstruire une configuration ou à relancer une transition. Les étapes peuvent donc se chevaucher selon le contexte.

## 8. Remarque sur les données GLPI

Le sujet demande en Partie 4 de copier les champs clés d'une demande GLPI, mais aucun ticket GLPI ni ses champs (titre, description, statut, dates) n'est fourni dans le fichier du TP. Ces informations ne peuvent donc pas être inventées de manière fiable.
