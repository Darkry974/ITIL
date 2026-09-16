# Partie 2 — Service Level Management & Event Management

## 1. SLA et SLO

### SLA 1 — Délai de première réponse

Le helpdesk s'engage à fournir une première réponse à toute demande enregistrée selon sa priorité.

| Priorité | SLO de première réponse |
|---|---|
| P1 — Critique | 95 % des tickets répondus en moins de 1 h |
| P2 — Haute | 95 % des tickets répondus en moins de 4 h |
| P3 — Normale | 90 % des tickets répondus en moins de 1 jour ouvré |
| P4 — Faible | 90 % des tickets répondus en moins de 2 jours ouvrés |

**Mesure :** temps entre la création du ticket et la première réponse humaine enregistrée dans l'outil.

### SLA 2 — Délai de résolution

Le helpdesk s'engage à respecter des objectifs de résolution adaptés à la priorité.

| Priorité | SLO de résolution |
|---|---|
| P1 — Critique | 90 % des tickets résolus en moins de 4 h |
| P2 — Haute | 90 % des tickets résolus en moins de 1 jour ouvré |
| P3 — Normale | 90 % des tickets résolus en moins de 3 jours ouvrés |
| P4 — Faible | 90 % des tickets résolus en moins de 5 jours ouvrés |

**Mesure :** temps entre la création du ticket et son passage à l'état résolu, hors éventuel temps d'attente explicitement défini par les règles du service.

Les SLA devront être réévalués après une période d'utilisation afin de vérifier qu'ils correspondent aux capacités réelles du helpdesk.

## 2. Classification Event Management

| Log | Classification | Justification | Action |
|---|---|---|---|
| `AUTH user=jdupont action=login status=success host=WKS-042` | Informational | Connexion utilisateur réussie : événement normal. | Aucune action immédiate. |
| `DISK host=SRV-FILE01 usage=82% threshold=80%` | Warning | L'utilisation disque dépasse le seuil configuré de 80 %. Le risque de saturation est identifié mais la saturation n'est pas encore avérée. | Vérifier l'évolution de l'espace disque, identifier les gros consommateurs et planifier un nettoyage ou une extension si nécessaire. |
| `SVC name=helpdesk-portal status=unreachable duration=00:04:12` | Exception | Le portail helpdesk est explicitement inaccessible pendant 4 min 12 s : anomalie avérée sur un service utilisé par le helpdesk. | Ouvrir immédiatement un Incident, vérifier la disponibilité du portail, les services associés et les journaux, puis restaurer le service. |
| `BACKUP job=nightly-backup host=SRV-DB01 status=completed size=45GB` | Informational | La sauvegarde nocturne est terminée avec succès. | Aucune action immédiate. |
| `NET link=switch-3F-port12 status=down flapping=true count=6/10min` | Exception | Le lien est en panne et « flapping » 6 fois en 10 minutes : anomalie réseau avérée et répétitive. | Ouvrir un Incident réseau, contrôler le port, le câblage et l'équipement connecté, puis stabiliser le lien. |

## 3. Règle de pilotage

Les événements Warning servent à déclencher une action préventive avant qu'un incident ne survienne. Les événements Exception déclenchent une prise en charge immédiate, généralement sous forme d'Incident lorsque le service est effectivement dégradé ou indisponible.
