# 🚀 Dinevio — Super App Multi-Services

> Plateforme de mobilité et livraison multi-services (Courses, Livraisons, Marketplace)  
> Inspirée du modèle Uber / Glovo — Flutter + Firebase + Next.js

---

## 👨‍💻 Développeur

| | |
|---|---|
| **Développeur** | Marouan Bahtit |
| **Entreprise** | Bestcrea LLC |
| **GitHub** | [github.com/Bestcrea](https://github.com/Bestcrea) |
| **Site Web** | [bestcrea.com](https://bestcrea.com) |
| **Email** | bahtitmarouan@gmail.com / contact@bestcrea.com |
| **Téléphone** | +212 636 499 140 |

---

## 📱 Aperçu du Projet

Dinevio est une **super-app** de mobilité et de livraison qui repose sur **Firebase** comme backend unique partagé entre plusieurs applications :

| Application | Technologie | Version | Statut |
|---|---|---|---|
| Customer App | Flutter (Android / iOS) | 2.0.1+5 | ✅ 80–85% prêt |
| Driver App | Flutter (Android / iOS) | 1.0.0+2 | ✅ Fonctionnel |
| Admin Panel | Flutter Web | 1.0.0+1 | ✅ Opérationnel (41 modules) |
| Cloud Functions | Node.js / Firebase | — | ✅ Stripe + Assignation |
| Dinevio Web | Next.js 16 | 0.1.0 | ⚠️ En cours |
| Landing Page | Statique | — | ✅ Présent |

---

## 📁 Structure du Dépôt

```
dinevio/
├── customer/           ← App client Flutter (55 modules)  — PRIORITÉ
│   └── lib/features/       auth · rides · food · grocery · wallet · chat
│
├── driver/             ← App chauffeur Flutter (45 modules)
│   └── lib/features/       courses · intercity · colis · wallet · abonnements
│
├── admin/              ← Panel admin Flutter Web (41 modules)
│   └── lib/features/       dashboard · clients · chauffeurs · paiements · support
│
├── dinevio-web/        ← Site public Next.js 16 (WIP)
├── dinevio-web-static/ ← Site statique
├── function/           ← Cloud Functions (Stripe + assignation courses)
├── firestore_index/    ← Index Firestore
├── Database/           ← Schéma et données
├── landing_page/       ← Landing marketing
└── docs/               ← Rapports internes et documentation
```

---

## 🏗️ Architecture Globale

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   Customer App  │     │   Driver App    │     │  Admin Panel    │
│  Flutter Mobile │     │ Flutter Mobile  │     │  Flutter Web    │
└────────┬────────┘     └────────┬────────┘     └────────┬────────┘
         │                       │                        │
         └───────────────────────┼────────────────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │     Firebase Backend     │
                    │  ┌─────────────────────┐│
                    │  │   Firebase Auth     ││
                    │  │   Cloud Firestore   ││
                    │  │   Firebase FCM      ││
                    │  │   Firebase Storage  ││
                    │  │   Cloud Functions   ││
                    │  └─────────────────────┘│
                    └────────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │       Stripe API         │
                    │  (Paiements en ligne)    │
                    └─────────────────────────┘

         ┌─────────────────────────────────────┐
         │      Dinevio Web (Next.js 16)        │
         │         Non connecté ⚠️              │
         └─────────────────────────────────────┘
```

---

## 🔧 Stack Technique

| Couche | Technologies |
|---|---|
| **Mobile** | Flutter ≥ 3.2.6, Dart ≥ 3.2.6 |
| **State Management** | GetX (principal), Provider, Riverpod |
| **Backend** | Firebase Auth, Firestore, Storage, FCM |
| **Maps** | Google Maps Flutter, Geolocator, GeoFlutterFire2 |
| **Paiements** | Stripe, Razorpay, PayPal, Flutterwave |
| **IA** | Gemini (chatbot support client) |
| **Admin** | Flutter Web |
| **Web Public** | Next.js 16, React 19, Tailwind 4 |
| **Cloud** | Node.js Firebase Functions v2 |

---

## 📊 Statut des Fonctionnalités

| Fonctionnalité | Frontend | Backend | Prêt prod |
|---|---|---|---|
| Auth (Phone/Google/Apple) | ✅ | ✅ | ✅ |
| Courses Taxi | ✅ | ✅ | ✅ |
| Intercity | ✅ | ✅ | ⚠️ |
| Livraison Colis | ✅ | ✅ | ✅ |
| Food Delivery | ✅ | ✅ | ✅ |
| Grocery | ✅ | ❌ mock | ❌ |
| Parapharmacie | ✅ | ⚠️ mock | ⚠️ |
| Wallet / Stripe | ✅ | ✅ | ✅ |
| Chat | ✅ | ✅ | ✅ |
| Notifications FCM | ✅ | ✅ | ✅ |
| Admin Back-office | ✅ | ✅ | ✅ |
| Site Web Next.js | ⚠️ | ❌ | ❌ |

---

## 🚀 Démarrage Rapide

### Customer App
```bash
cd customer
flutter pub get
flutter run
```

### Driver App
```bash
cd driver
flutter pub get
flutter run
```

### Admin Panel
```bash
cd admin
flutter pub get
flutter run -d chrome
```

### Dinevio Web
```bash
cd dinevio-web
npm install
npm run dev
```

### Cloud Functions
```bash
cd function/functions
npm install
firebase deploy --only functions
```

---

## 🗺️ Roadmap

### Phase 1 — MVP (2–4 semaines)
- [x] Courses taxi (flux principal)
- [x] Food delivery
- [ ] Activer règles Firestore production
- [ ] Nettoyer .gitignore

### Phase 2 — Complétion (4–8 semaines)
- [ ] Nouveau module Rides → brancher backend
- [ ] Grocery → migrer vers Firestore
- [ ] Parapharmacie → catalogue réel
- [ ] Livraisons marketplace côté Driver

### Phase 3 — Écosystème (8+ semaines)
- [ ] Connecter Dinevio Web à Firebase
- [ ] Analytics + monitoring
- [ ] CI/CD
- [ ] Tests automatisés

---

## 📬 Contact

| | |
|---|---|
| 👤 **Marouan Bahtit** | Développeur Full-Stack & Mobile |
| 📧 **Email** | bahtitmarouan@gmail.com |
| 📧 **Pro** | contact@bestcrea.com |
| 📞 **Téléphone** | +212 636 499 140 |
| 🌐 **Site Web** | [bestcrea.com](https://bestcrea.com) |
| 💻 **GitHub** | [github.com/Bestcrea](https://github.com/Bestcrea) |

---

*Built with ❤️ by [Bestcrea LLC](https://bestcrea.com)*
