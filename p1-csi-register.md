# Partie 1 — CSI Register

## 1. Diagnostic selon les 4 dimensions

### Organisations & personnes

Le service helpdesk présente des difficultés de traitement qui se traduisent par une **lenteur de traitement**, des **tickets perdus** et des **utilisateurs qui rappellent plusieurs fois pour un même problème**. Ces symptômes indiquent un problème d'organisation du traitement et de suivi : les rôles, la répartition de la charge ou les compétences nécessaires au suivi des tickets doivent être clarifiés.

### Information & technologie

Le symptôme « tickets perdus » montre que les informations relatives aux demandes ne sont pas suffisamment fiables ou suivies dans l'outillage actuel. Le service doit disposer d'un système permettant d'enregistrer chaque demande, d'en suivre le statut et de conserver un historique exploitable par les techniciens.

### Partenaires & fournisseurs

Le contexte ne fournit pas d'élément indiquant qu'un fournisseur externe est directement responsable des dysfonctionnements. Cette dimension reste donc à vérifier avant d'attribuer une cause externe au problème. Les éventuelles dépendances à un éditeur de l'outil helpdesk, à un opérateur réseau ou à un prestataire doivent être identifiées dans un diagnostic réel.

### Value Streams & processus

Le flux de traitement d'un ticket semble présenter des ruptures : certaines demandes sont perdues et certains utilisateurs doivent rappeler plusieurs fois. Le processus doit donc être rendu visible et traçable, depuis la création du ticket jusqu'à sa résolution et sa clôture. Des règles de priorité et de suivi doivent également être définies.

## 2. CSI Register

| Priorité | Amélioration | Effort | Impact | Justification |
|---|---|---|---|---|
| 1 | Mettre en place un workflow helpdesk unique avec création obligatoire, attribution, priorité, statut et clôture des tickets | Moyen | Fort | Traite directement les tickets perdus et améliore la traçabilité de bout en bout. |
| 2 | Définir des SLA/SLO et un tableau de suivi des délais | Moyen | Fort | Permet de mesurer la lenteur de traitement et de détecter rapidement les écarts. |
| 3 | Créer une base de connaissance pour les incidents et demandes récurrents | Faible | Moyen | Réduit les rappels et accélère le traitement des problèmes connus. |

### Priorisation

La priorité 1 est donnée à la traçabilité du workflow : tant qu'une demande peut être perdue ou rester sans responsable, les autres améliorations sont difficiles à mesurer efficacement. La priorité 2 permet ensuite de piloter objectivement la qualité du service. La base de connaissance vient compléter le dispositif en réduisant les traitements répétitifs.

## 3. Principe directeur mobilisé

Le principe **« Collaborer et promouvoir la visibilité »** a le plus guidé la priorisation.

Le problème central est notamment l'absence de visibilité sur le parcours des demandes : un ticket perdu ou un utilisateur obligé de rappeler plusieurs fois montre que l'information sur l'état du traitement n'est pas suffisamment visible. Le workflow unique rend les responsabilités, les statuts et les délais observables par les personnes concernées.

La démarche reste également cohérente avec **« Progresser de manière itérative avec du feedback »** : les améliorations peuvent être déployées progressivement puis évaluées à partir des résultats des SLA/SLO et des retours utilisateurs.
