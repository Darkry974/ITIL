# TP ITIL 5 — Amélioration d'un service Helpdesk interne

## Objectif

Ce dépôt présente une démarche d'amélioration du service helpdesk interne en utilisant les pratiques et modèles demandés par le sujet : Continual Improvement, Service Level Management, Event Management, Change Enablement, Knowledge Management, Service Request Management et Product and Service Lifecycle.

## Tableau récapitulatif

| Partie | Pratiques / modèles ITIL 5 mobilisés |
|---|---|
| Partie 1 — Diagnostic | Continual Improvement + 4 dimensions du service |
| Partie 2 — Pilotage | Service Level Management + Event Management |
| Partie 3 — Changement | Change Enablement + Knowledge Management + Product and Service Lifecycle |
| Partie 4 — Clôture | Service Request Management + synthèse |

## Principe directeur structurant

Le principe directeur le plus structurant est **« Collaborer et promouvoir la visibilité »**.

Exemple concret : le problème initial comprend des tickets perdus et des utilisateurs qui rappellent plusieurs fois. La priorité donnée à un workflow unique rend visible le statut, le responsable et le parcours de chaque ticket. Cette visibilité facilite ensuite la mesure des SLA/SLO et la réduction des demandes répétitives.

## AI Governance et modèle 6C

Dans ce cas précis, le module **AI Governance** et le modèle **6C** ne sont pas nécessaires pour résoudre le problème principal.

Le TP décrit un dysfonctionnement de processus et de traçabilité du helpdesk, sans usage d'un système d'intelligence artificielle. La première amélioration consiste donc à structurer le workflow des tickets, à définir des niveaux de service et à améliorer le suivi.

Une IA pourrait éventuellement être envisagée plus tard pour assister le tri ou la suggestion de réponses, mais cela constituerait un nouveau périmètre. Dans le cas fourni, introduire une gouvernance IA ou un référentiel de capacités IA ne permettrait pas de résoudre directement les tickets perdus et le manque de visibilité du processus.

Si une IA était ajoutée ultérieurement, une analyse de gouvernance deviendrait pertinente pour traiter notamment les données utilisées, les responsabilités, la sécurité, la qualité des réponses et les risques liés aux décisions automatisées. Aucun de ces éléments n'est actuellement fourni dans le contexte du TP.

## Partie 4 — Demande de service GLPI

Le sujet demande de traiter une demande de service GLPI liée au changement et de recopier :

- titre ;
- description ;
- statut ;
- dates.

Aucun ticket GLPI n'est présent dans le fichier fourni. Il serait incorrect d'inventer ces champs.

### À compléter avec le ticket GLPI réel

```text
Titre :
Description :
Statut :
Date de création :
Date de dernière modification :
Date de résolution / clôture :
```

La demande doit être traitée comme une **Service Request** lorsqu'elle correspond à une demande planifiée liée au changement, et non comme un Incident : un Incident correspond à une interruption ou dégradation non planifiée d'un service, tandis qu'une demande de service correspond à une demande planifiée et standardisée.

## Résultats attendus

La démarche proposée vise à :

1. empêcher la perte des tickets ;
2. rendre les responsabilités et statuts visibles ;
3. mesurer les délais de traitement ;
4. détecter certaines anomalies avant qu'elles ne deviennent des incidents ;
5. documenter les résolutions récurrentes ;
6. transformer l'amélioration en changement contrôlé ;
7. mesurer ensuite l'efficacité du nouveau fonctionnement.

## Historique Git demandé

Le sujet demande au minimum deux commits par partie, avec des messages de type `pN: <action>`.

Exemple :

```text
p1: diagnostic et CSI register
p1: finalisation de la priorisation
p2: définition des SLA et SLO
p2: classification des événements
p3: rédaction de la RFC
p3: ajout de la base de connaissance
p4: synthèse et README
p4: finalisation de la clôture
```

## Fichiers

- `p1-csi-register.md`
- `p2-slm-events.md`
- `p3-change-kb.md`
- `README.md`
