# v2 – Filtrage inter-VLAN avec des ACL 🚧 *(en cours)*

Suite du lab [v1 – VLAN et routage inter-VLAN](../README.md).

---

## 🎯 Objectif

Dans la v1, le routage inter-VLAN laisse **tout passer** : un poste du VLAN CLIENT peut joindre le VLAN GESTION_IT et les serveurs.
L'objectif de cette v2 est d'ajouter des **listes de contrôle d'accès (ACL)** sur RT1 pour appliquer le principe du **moindre privilège** : chaque VLAN n'accède qu'à ce dont il a besoin.

---

## 📋 Règles prévues

| # | Source | Destination | Action | Pourquoi |
|---|---|---|---|---|
| 1 | VLAN 10 – CLIENT | VLAN 50 – GESTION_IT | ❌ Bloquer | Un poste client n'a pas à joindre le réseau d'administration |
| 2 | Tous les VLAN sauf 50 | SSH vers SW0 et RT1 | ❌ Bloquer | Seule l'équipe IT administre les équipements |
| 3 | Tous les VLAN | Serveurs DNS / DHCP (VLAN 40) | ✅ Autoriser les services nécessaires | Les postes ont besoin du DNS et du DHCP |

*Règles susceptibles d'évoluer pendant la réalisation.*

---

## ⚙️ Configuration

*À compléter : ACL créées, interfaces et sens d'application.*

📁 Configurations : `configs/` *(à venir)*

---

## ✅ Tests

| Test | Résultat attendu | Résultat obtenu |
|---|---|---|
| PC1 (CLIENT) → PC7 (GESTION_IT) | ❌ Bloqué | *à tester* |
| PC7 (GESTION_IT) → RT1 en SSH | ✅ Autorisé | *à tester* |
| PC1 (CLIENT) → RT1 en SSH | ❌ Bloqué | *à tester* |
| PC1 → serveur DNS | ✅ Autorisé | *à tester* |
| PC1 → 8.8.8.8 | ✅ Autorisé | *à tester* |

📷 Captures : `captures/` *(à venir)*

---

## 🐞 Difficultés rencontrées

*À compléter.*

---

## 🔐 Analyse sécurité

*À compléter : risques couverts par les ACL et limites restantes.*
