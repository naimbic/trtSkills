# Plan — Application POS Poissonnerie (B2B/B2C)

## Résumé du projet
Développement d'une application web POS (Point de Vente) complète pour une poissonnerie marocaine, avec support B2B et B2C, mode offline-first, gestion de stock avec traçabilité FIFO, et architecture générique réutilisable pour d'autres commerces.

## Stack technique
- **Frontend**: Next.js 14+ (App Router), TypeScript, Tailwind CSS
- **Offline-first**: Service Worker + IndexedDB via Dexie.js
- **Backend**: Next.js API Routes + PostgreSQL + Prisma ORM
- **Auth**: NextAuth.js (Auth.js) avec RBAC
- **Impression**: ESC/POS via Web USB/Bluetooth + fallback navigateur
- **Scan**: HID USB + html5-qrcode pour caméra
- **Déploiement**: Hetzner VPS + EasyEngine + nginx-proxy + PM2

## Stages d'exécution

### Stage 1 — Fondations & Architecture
- Initialiser le projet Next.js avec TypeScript, Tailwind
- Configurer Prisma avec schéma de base de données complet (multi-table)
- Configurer NextAuth.js avec RBAC (admin, manager, cashier, stock_manager)
- Mettre en place Dexie.js pour IndexedDB local (offline-first)
- Structure de dossiers modulaire
- Configuration PWA (manifest + service worker)

### Stage 2 — Catalogue Produits & Stock
- CRUD produits avec catégories
- Génération de codes-barres internes (Code128)
- Gestion des lots/traçabilité (DLC, origine, fournisseur)
- Stock mouvements avec FIFO
- Alertes péremption et stock bas

### Stage 3 — Module POS (cœur)
- Interface tactile/tablette optimisée
- Grille produits par catégories
- Scan code-barres (HID + caméra)
- Mode pesée (saisie manuelle, prêt pour balance)
- Bascule B2C/B2B avec prix adaptés
- Gestion des remises
- Paiement multi-mode (espèces, carte, crédit B2B, mixte)
- Calcul de monnaie

### Stage 4 — Offline-First & Synchronisation
- Queue d'opérations IndexedDB
- Synchronisation auto dès retour connexion
- Résolution de conflits (stock)
- Indicateur visuel état connexion

### Stage 5 — Clients B2B & Crédit
- Fiches clients B2B (ICE, crédit_limit, payment_terms)
- Clients B2C anonymes
- Encours de crédit, relances
- Historique d'achats

### Stage 6 — Rapports & Dashboard
- CA jour/semaine/mois, par produit/catégorie
- Marge brute
- Pertes/casse
- Export PDF/Excel
- Graphiques avec recharts

### Stage 7 — Impression & Finalisation
- Impression tickets thermiques (ESC/POS)
- Factures PDF avec mentions légales marocaines
- Polish UI/UX responsive
- Tests et optimisation

### Stage 8 — Déploiement
- README complet
- Guide de déploiement (Hetzner + EasyEngine)
- Scripts de build et démarrage

## Livrables
- Code source complet Next.js TypeScript
- Schema Prisma
- Application déployable en local
- Documentation
