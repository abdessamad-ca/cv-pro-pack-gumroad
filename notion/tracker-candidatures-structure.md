# Tracker Candidatures Notion - Structure Complète

Ce fichier définit la structure exacte du template Notion à créer pour le bonus du bundle.

---

## VUE D'ENSEMBLE

Le Tracker Candidatures est un **template Notion all-in-one** qui permet de :
- Suivre 50+ candidatures simultanées
- Tracker les statuts et relances
- Analyser les performances (taux de réponse, conversion)
- Gérer les préparations d'entretiens
- Stocker les contacts recruteurs

---

## ARCHITECTURE BASES DE DONNÉES

### Database 1 : Candidatures (principale)

**Propriétés :**

1. **Titre** (Title) : [Poste] @ [Entreprise]
   - Exemple : "Développeur Full-Stack @ Startup ABC"

2. **Statut** (Select)
   - 📝 Brouillon
   - 📤 Envoyée
   - 👀 Vue par le recruteur
   - 📞 Entretien RH
   - 💼 Entretien technique
   - ✅ Offre reçue
   - ❌ Refusée
   - 🚫 Sans réponse

3. **Entreprise** (Text)

4. **Poste** (Text)

5. **Plateforme** (Select)
   - LinkedIn
   - Indeed
   - Welcome to the Jungle
   - Site entreprise
   - Recommandation
   - Autre

6. **Date de candidature** (Date)

7. **Date de dernière relance** (Date)

8. **Prochaine relance** (Date)
   - Formule : Date candidature + 7 jours (si pas de réponse)

9. **Priorité** (Select)
   - 🔥 Haute
   - ⭐ Moyenne
   - 💤 Basse

10. **Salaire proposé** (Number) - Format : €

11. **Lien offre** (URL)

12. **Contact recruteur** (Relation → Database Contacts)

13. **Documents envoyés** (Multi-select)
    - CV
    - Lettre de motivation
    - Portfolio
    - Références

14. **Notes** (Text long)

15. **Entretiens** (Relation → Database Entretiens)

16. **Score match** (Number) - Auto-évaluation 1-10

17. **Tags** (Multi-select)
    - Remote
    - Hybrid
    - On-site
    - CDI
    - CDD
    - Freelance
    - Startup
    - Grand groupe

---

### Database 2 : Contacts Recruteurs

**Propriétés :**

1. **Nom** (Title)
2. **Poste** (Text) - Exemple : "Talent Acquisition Manager"
3. **Entreprise** (Text)
4. **Email** (Email)
5. **Téléphone** (Phone)
6. **LinkedIn** (URL)
7. **Candidatures liées** (Relation → Candidatures)
8. **Dernière interaction** (Date)
9. **Notes** (Text long)

---

### Database 3 : Entretiens

**Propriétés :**

1. **Titre** (Title) : [Type] - [Entreprise]
   - Exemple : "Entretien RH - Startup ABC"

2. **Type** (Select)
   - 📞 Téléphone
   - 💻 Visio
   - 🏢 Sur place
   - 🧪 Test technique

3. **Candidature** (Relation → Candidatures)

4. **Date & Heure** (Date avec heure)

5. **Durée** (Text) - Exemple : "45 min"

6. **Participants** (Text) - Noms des interviewers

7. **Lien visio** (URL)

8. **Préparation** (Checkbox)

9. **Notes préparation** (Text long)
   - Questions à poser
   - Points à mentionner
   - Recherches sur l'entreprise

10. **Compte-rendu** (Text long)
    - Ce qui s'est bien passé
    - Points d'amélioration
    - Prochaines étapes

11. **Feedback reçu** (Text)

---

### Database 4 : Relances

**Propriétés :**

1. **Candidature** (Relation → Candidatures)
2. **Date de relance** (Date)
3. **Type** (Select)
   - Email
   - LinkedIn
   - Téléphone
4. **Message envoyé** (Text long)
5. **Réponse reçue** (Checkbox)
6. **Notes** (Text)

---

## VUES (VIEWS) PAR DATABASE

### Candidatures - Vues

#### Vue 1 : 📊 Dashboard (Table)
- Toutes les candidatures
- Groupé par : Statut
- Trié par : Date de candidature (décroissant)
- Filtres : Aucun

#### Vue 2 : 📤 En cours (Board/Kanban)
- Colonnes : Statuts (sauf Refusée, Sans réponse)
- Carte affiche : Entreprise, Poste, Date, Priorité
- Filtre : Statut ≠ Refusée ET Statut ≠ Sans réponse

#### Vue 3 : 🔥 Priorité Haute (Table)
- Filtre : Priorité = Haute
- Trié par : Prochaine relance

#### Vue 4 : ⏰ À relancer (Table)
- Filtre : Prochaine relance ≤ Aujourd'hui + 3 jours
- Trié par : Prochaine relance
- Mise en évidence : Lignes avec date dépassée en rouge

#### Vue 5 : ✅ Succès (Gallery)
- Filtre : Statut = Offre reçue OU Entretien technique
- Affiche : Entreprise, Poste, Salaire

#### Vue 6 : 📈 Analytics (Timeline)
- Axe X : Date de candidature
- Groupé par : Plateforme
- Permet de voir la distribution temporelle

---

### Entretiens - Vues

#### Vue 1 : 📅 Calendrier (Calendar)
- Date : Date & Heure
- Affiche les entretiens à venir

#### Vue 2 : ⏭️ À venir (Table)
- Filtre : Date ≥ Aujourd'hui
- Trié par : Date (croissant)

#### Vue 3 : ✅ Passés (Table)
- Filtre : Date < Aujourd'hui
- Trié par : Date (décroissant)

---

## DASHBOARD PRINCIPAL

### Page d'accueil "🎯 Job Search Tracker"

**Sections :**

#### 1. Stats en Un Coup d'Œil (Callout boxes)

Utiliser des formules Notion pour calculer :

```
📊 STATISTIQUES CLÉS

📤 Candidatures envoyées : [Formule COUNT filtrée]
📞 Entretiens obtenus : [COUNT Entretiens]
✅ Taux de réponse : [% candidatures avec réponse]
⏱️ Temps moyen avant réponse : [AVG jours]
🎯 Candidatures en cours : [COUNT statut ≠ Refusée/Sans réponse]
```

**Formules Notion :**

**Total candidatures :**
```
prop("Statut").length()
```

**Taux de réponse :**
```
(prop("Statut").filter(s => s != "Sans réponse" && s != "Brouillon").length() / prop("Statut").length()) * 100
```

#### 2. Vue Kanban "En Cours"

Embed de la vue Board des candidatures.

#### 3. Section "⏰ Relances Urgentes"

Embed de la vue "À relancer" (filtrée : 7 jours sans réponse).

#### 4. Section "📅 Prochains Entretiens"

Embed de la vue Calendar des entretiens (semaine en cours).

#### 5. Graphique de Performance

Utiliser Notion Charts (ou embed Google Sheets) :

**Graphique 1 : Candidatures par Semaine**
- Axe X : Semaines
- Axe Y : Nombre de candidatures
- Type : Ligne

**Graphique 2 : Taux de Conversion par Plateforme**
- Axe X : Plateformes
- Axe Y : % d'entretiens obtenus
- Type : Barres

---

## TEMPLATES INTÉGRÉS

### Template 1 : Nouvelle Candidature

**Pré-rempli avec :**
```
📝 Titre : [À compléter] @ [Entreprise]
Statut : Brouillon
Date candidature : [Aujourd'hui]
Priorité : Moyenne
Documents : CV, Lettre
Notes :
  - Lien offre : 
  - Pourquoi cette entreprise :
  - Points à mentionner dans la lettre :
  - Mots-clés offre :
```

### Template 2 : Préparation Entretien

**Structure :**
```
🎤 PRÉPARATION ENTRETIEN

## 1. Recherches Entreprise
- Activité principale :
- Produits/services :
- Actualités récentes :
- Valeurs :

## 2. Analyse du Poste
- Missions principales :
- Compétences requises :
- Points de match avec mon profil :

## 3. Questions à Poser (5-7)
1. 
2. 
3. 

## 4. Exemples à Préparer
- Réalisation dont je suis fier :
- Difficulté surmontée :
- Travail en équipe :

## 5. Questions Attendues
- Parlez-moi de vous → [Réponse préparée]
- Pourquoi cette entreprise → [Réponse]
- Vos points forts/faibles → [Réponse]
```

### Template 3 : Email de Relance

**Templates copy-paste :**

**Relance J+7 :**
```
Objet : Suivi candidature - [Poste]

Bonjour [Prénom],

Je me permets de revenir vers vous concernant ma candidature 
au poste de [Poste] envoyée le [Date].

Je reste très intéressé(e) par cette opportunité et serais ravi(e) 
d'échanger avec vous sur mon profil.

Restant à votre disposition,
Cordialement,
[Prénom Nom]
```

**Relance LinkedIn :**
```
Bonjour [Prénom],

J'ai postulé au poste de [Poste] chez [Entreprise] et souhaiterais 
me présenter brièvement :

[Pitch 2-3 lignes]

Seriez-vous disponible pour un échange rapide ?

Merci,
[Prénom]
```

---

## AUTOMATISATIONS (via Notion API ou Zapier)

### Auto 1 : Rappel Relance

**Trigger :** Date "Prochaine relance" = Aujourd'hui
**Action :** Envoyer notification ou email

### Auto 2 : Mise à jour Statut

**Trigger :** Entretien créé
**Action :** Statut candidature → "Entretien RH" ou "Entretien technique"

### Auto 3 : Calcul Prochaine Relance

**Formule automatique :**
```
if(prop("Statut") == "Envoyée", 
   dateAdd(prop("Date candidature"), 7, "days"),
   empty)
```

---

## PAGES ANNEXES

### Page 1 : 📚 Ressources Utiles

**Contenu :**
- Liste de jobboards recommandés
- Templates emails (relances, remerciements)
- Checklist préparation entretien
- Questions fréquentes + réponses types
- Liens vers outils (LinkedIn, Indeed, etc.)

### Page 2 : 🎯 Objectifs & Stratégie

**Contenu :**
```
## Objectif Mensuel
Nombre de candidatures : [20]
Entretiens souhaités : [5]
Offres espérées : [1]

## Stratégie
- Plateformes prioritaires : [LinkedIn, WTTJ]
- Secteurs cibles : [Tech, SaaS]
- Types d'entreprises : [Startups, Scale-ups]

## Suivi Hebdomadaire
Semaine 1 : [X candidatures]
Semaine 2 : 
Semaine 3 :
Semaine 4 :
```

### Page 3 : 💡 Notes & Apprentissages

Section libre pour noter :
- Ce qui fonctionne dans les candidatures
- Feedbacks reçus
- Points à améliorer
- Tendances observées

---

## WORKFLOW D'UTILISATION

### Étape 1 : Nouvelle Candidature

1. Créer nouvelle entrée dans "Candidatures"
2. Remplir : Poste, Entreprise, Plateforme, Lien offre
3. Statut → "Brouillon"
4. Copier mots-clés de l'offre dans Notes
5. Adapter CV et lettre
6. Une fois envoyée : Statut → "Envoyée"
7. Prochaine relance s'auto-remplit à J+7

### Étape 2 : Suivi Quotidien

1. Ouvrir Dashboard
2. Vérifier "Relances Urgentes"
3. Envoyer emails de relance si nécessaire
4. Mettre à jour statuts (si réponses reçues)
5. Checker "Prochains Entretiens"

### Étape 3 : Préparation Entretien

1. Créer entrée dans "Entretiens"
2. Utiliser template "Préparation Entretien"
3. Faire recherches entreprise
4. Préparer questions et exemples
5. Checkbox "Préparation" → ✅

### Étape 4 : Après Entretien

1. Remplir "Compte-rendu" dans Entretiens
2. Mettre à jour statut candidature
3. Programmer relance si besoin
4. Noter les feedbacks

---

## EXPORT & PARTAGE

### Export du Template

1. **Dupliquer** la page principale
2. **Vider** les données exemples (garder structure)
3. **Exporter** en Notion Template
4. Générer **lien de duplication** : "Share → Duplicate as template"

**Lien à inclure dans le Bundle :**
```
https://notion.so/templates/[ID-TEMPLATE]
```

### Instructions pour l'Acheteur

**Dans le README du Bundle :**

> ## 📋 Installer le Tracker Notion
>
> 1. Clique sur ce lien : [Tracker Candidatures]
> 2. Clique "Duplicate" en haut à droite
> 3. Choisis ton workspace Notion
> 4. Le template s'installe automatiquement !
>
> **Première utilisation :**
> - Explore le Dashboard principal
> - Crée ta première candidature (bouton "New")
> - Personnalise les vues selon tes besoins

---

## TEMPS DE CRÉATION

| Tâche | Durée |
|-------|-------|
| Créer databases | 20 min |
| Configurer propriétés | 15 min |
| Créer vues | 20 min |
| Designer Dashboard | 30 min |
| Ajouter formules/stats | 15 min |
| Créer templates | 15 min |
| Remplir exemples | 10 min |
| Test complet | 10 min |
| **TOTAL** | **2h15** |

---

**🎯 Template Notion 100% prêt à dupliquer et utiliser !**
