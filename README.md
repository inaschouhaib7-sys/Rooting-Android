# Rooting-Android
executer l emulateur
<img width="1351" height="634" alt="image" src="https://github.com/user-attachments/assets/b3d5cb97-4588-49bf-9f75-1f6ac71a4bf4" />
Rooter l'AVD
<img width="942" height="640" alt="image" src="https://github.com/user-attachments/assets/eb2e1ea1-e182-4a8e-addb-93ef4b730e58" />
Vérifications :
<img width="950" height="602" alt="image" src="https://github.com/user-attachments/assets/bafaba7d-23cc-4e72-bbff-ace9f80b6690" />
Option permissive :
<img width="940" height="175" alt="image" src="https://github.com/user-attachments/assets/6e3ad7f2-54c2-4d47-b5ea-b1cecb10c2b7" />

<img width="901" height="369" alt="image" src="https://github.com/user-attachments/assets/185e1f01-07e6-46a1-b0fa-ee262e255d37" />
Journalisation :
<img width="952" height="125" alt="image" src="https://github.com/user-attachments/assets/84fd551f-561f-4174-8a85-8d97d00240cf" />

Fiche périmètre:
App + version : RootExplorer Pro v3.2.1
Support (AVD / device labo) : AVD — Android Virtual Device (Pixel 6)
Objectif : Comprendre le rooting et ses impacts
Données : Fictives (aucune donnée réelle)
Réseau : Test — environnement isolé

Démarrer un AVD propre
Android Studio → Device Manager → Start (ou créer un AVD simple avec API récente)

<img width="306" height="662" alt="p" src="https://github.com/user-attachments/assets/383eea26-532a-4039-85ee-9889ddfc8060" />

Vérifier : écran d'accueil Android, aucun compte personnel
Commande de vérification : adb devices

<img width="1170" height="146" alt="image" src="https://github.com/user-attachments/assets/a766ac42-9aeb-4086-880a-6fe0b1cf0e31" />

Installer et lancer l'app de test

<img width="1167" height="385" alt="image" src="https://github.com/user-attachments/assets/3899b58a-9030-4919-849b-8f2049ca5ac6" />

 Définir 3 scénarios simples
Ouvrir l'écran d'accueil
Rechercher un item

<img width="506" height="1016" alt="image" src="https://github.com/user-attachments/assets/e347c801-1034-46ae-ae1b-bbc89f0e1c1e" />

Ouvrir un détail (fiche produit/profil)
<img width="502" height="1022" alt="image" src="https://github.com/user-attachments/assets/e7a2d116-626c-4b71-876c-511191ea9556" />

Lire Android Security (6 lignes max)
La sécurité Android repose sur plusieurs couches de protection.
Chaque application fonctionne dans une sandbox, isolée des autres.
Le modèle de permissions contrôle l’accès aux ressources sensibles (caméra, stockage, micro…).
Le système protège aussi l’intégrité globale, empêchant les modifications non autorisées.
Ces mécanismes limitent les risques liés aux applications malveillantes.
Le rooting peut contourner ces protections et compromettre la sécurité du système.

Verified Boot (idée générale + check AVD)
Verified Boot est un mécanisme de sécurité qui vérifie l’intégrité du système au démarrage.
Son objectif principal est de garantir que le système lancé est bien celui prévu par le fabricant, sans modification malveillante.
Il repose sur une chain of trust : chaque composant vérifie cryptographiquement l’authenticité du suivant avant de lui transmettre le contrôle.
Ainsi, la confiance se construit étape par étape dès le bootloader jusqu’au système Android.
L’intégrité au démarrage est critique, car si le boot est compromis, toutes les protections ultérieures peuvent être contournées.
Un système altéré dès le démarrage rend inefficaces le sandboxing, les permissions et les autres mécanismes de sécurité.
<img width="1319" height="117" alt="image" src="https://github.com/user-attachments/assets/44580937-effa-4717-a87f-57c2ed6deafc" />


Android Verified Boot (AVB) est l’évolution moderne de Verified Boot, offrant une vérification d’intégrité plus robuste et flexible des partitions système.
Il utilise des mécanismes cryptographiques avancés pour garantir que chaque composant chargé au démarrage est authentique et non modifié.
AVB intègre aussi une protection contre le rollback, empêchant l’installation d’anciennes versions vulnérables du système.

Protection anti-rollback :
Elle bloque le retour vers une version plus ancienne d’Android pouvant contenir des failles connues, afin d’éviter qu’un attaquant n’exploite une vulnérabilité corrigée dans les versions récentes.

<img width="985" height="722" alt="image" src="https://github.com/user-attachments/assets/98a8e4c4-cd35-4838-aacf-783ae7aa2611" />

