# Prompts pour Générer les 24 Templates CV avec IA

Utilise ces prompts avec **ChatGPT + DALL-E** ou **Claude + Midjourney** pour créer les designs rapidement.

---

## STRATÉGIE DE GÉNÉRATION

### Approche Hybride Recommandée

**Étape 1** : Créer 1 template de base dans Canva/Figma (30 min)
**Étape 2** : Dupliquer et modifier pour créer 6 styles (1h30)
**Étape 3** : Générer 3 variations couleurs par style (45 min)
**Total** : 2h45 pour 24 fichiers

---

## PROMPT CHATGPT : GÉNÉRATION CONTENU CV

### Prompt Master (Copier-Coller)

```
Agis comme un expert en rédaction de CV. Je vais te donner un profil et tu vas générer le contenu complet d'un CV optimisé ATS.

Profil :
- Métier : [ex: Développeur Full-Stack]
- Années d'expérience : [ex: 5 ans]
- Secteur : [ex: SaaS/Fintech/Marketing]
- Compétences clés : [ex: Python, React, AWS]

Génère :

1. ACCROCHE (2-3 lignes)
   - Formule : [Rôle] + [Années] + [Spécialité] + [Résultat mesurable]

2. EXPÉRIENCE (3 postes)
   - Format : Titre | Entreprise | Dates
   - 3-4 bullet points par poste avec résultats chiffrés
   - Utiliser verbes d'action au passé

3. FORMATION (2 diplômes)
   - Diplôme | École | Année

4. COMPÉTENCES
   - Techniques (6-8)
   - Outils (4-6)
   - Langues (2)

Ton : Professionnel mais dynamique
Format : Markdown avec bullet points
Longueur : 1 page (700-900 mots)
```

---

## PROMPT DALL-E / MIDJOURNEY : DESIGN ÉLÉMENTS

### Pour Générer des Headers/Accents Visuels

**Prompt Midjourney** :
```
Minimalist professional CV header design, [color: blue corporate / emerald green / burgundy red], geometric shapes, clean lines, modern typography, high contrast, white background, vector style, --ar 16:9 --style raw --v 6
```

**Variations de Couleurs** :
- Bleu Corporate : `#2563EB, #1E40AF, #DBEAFE`
- Vert Émeraude : `#059669, #047857, #D1FAE5`
- Rouge Bordeaux : `#991B1B, #7F1D1D, #FEE2E2`

---

## TEMPLATES CANVA : GUIDE ÉTAPE PAR ÉTAPE

### Template 1 : Classic (Sobre et Pro)

**Canva Search** : "Professional Resume" → Choisir layout 1 colonne

**Modifications** :
1. **Header** :
   - Nom : Font **Poppins Bold 32pt**
   - Titre poste : **Poppins Regular 18pt**
   - Contact : **Inter Regular 11pt** (gris foncé #374151)

2. **Sections** :
   - Titres sections : **Poppins SemiBold 16pt** + ligne accent (3px, couleur primaire)
   - Corps texte : **Inter Regular 11pt**, interligne 1.4
   - Bullet points : • (puce ronde classique)

3. **Espacements** :
   - Marge document : 1.5cm tous côtés
   - Entre sections : 1cm
   - Entre bullet points : 0.3cm

4. **Couleurs** :
   - Texte principal : Noir #1F2937
   - Accent (titres, ligne) : Bleu #2563EB
   - Texte secondaire : Gris #6B7280

**Export** :
- Format : PDF (impression)
- Qualité : Standard
- Puis : Télécharger en DOCX (Canva Pro)

---

### Template 2 : Modern (Bande Latérale)

**Structure** :
```
┌──────────────────────────────────┐
│ Sidebar 30% │ Main Content 70%  │
│             │                    │
│ Photo       │ Nom + Accroche     │
│ Contact     │ Expérience         │
│ Compétences │ Formation          │
│ Langues     │ Projets            │
└──────────────────────────────────┘
```

**Sidebar** :
- Background : Couleur primaire (Bleu #2563EB)
- Texte : Blanc #FFFFFF
- Icônes : Feather Icons (mail, phone, location, linkedin)

**Main Content** :
- Background : Blanc
- Texte : Noir/Gris
- Sections avec titres en couleur primaire

---

### Template 3 : Infographics (Visuel)

**Éléments Graphiques** :
1. **Barres de compétences** :
   - Pas de % visible (ATS-unfriendly)
   - Utiliser : ●●●●○ (5 cercles, 4 remplis = niveau expert)

2. **Timeline Expérience** :
   - Ligne verticale avec points
   - Dates à gauche, contenu à droite

3. **Icons** :
   - Pack cohérent (Font Awesome ou Feather)
   - 1 icône par section

**Warning** : Version "Infographics Light" pour ATS
→ Variante sans graphiques complexes mais avec mise en page visuelle

---

### Template 4 : Sidebar (Colonne Gauche)

Similaire à Modern mais inversé :
- Sidebar 25% à gauche (gris clair #F3F4F6)
- Contenu principal 75% à droite
- Moins "agressif" que Modern

---

### Template 5 : Rows (Horizontal Sections)

**Structure** :
- Sections empilées horizontalement
- Chaque section a fond alternant (blanc / gris très clair)
- Headers de section en pleine largeur avec background couleur

**Avantage** : Très ATS-friendly (1 colonne pure)

---

### Template 6 : Two Column (Symétrique)

**Structure** :
```
┌──────────────────────────────────┐
│        Nom + Contact             │
├──────────────┬───────────────────┤
│ Col 1 (50%) │ Col 2 (50%)       │
│ Expérience  │ Compétences       │
│ Formation   │ Certifications    │
└──────────────┴───────────────────┘
```

**Usage** : Pour profils avec beaucoup de contenu latéral (compétences, certifications)

---

## VARIATIONS DE COULEURS (3 Palettes)

### Palette 1 : Bleu Corporate
```css
--primary: #2563EB;      /* Bleu vif */
--primary-dark: #1E40AF; /* Bleu foncé */
--primary-light: #DBEAFE; /* Bleu clair */
--text: #1F2937;         /* Gris anthracite */
--text-secondary: #6B7280; /* Gris moyen */
```

### Palette 2 : Vert Émeraude
```css
--primary: #059669;      /* Vert émeraude */
--primary-dark: #047857; /* Vert foncé */
--primary-light: #D1FAE5; /* Vert clair */
--text: #1F2937;
--text-secondary: #6B7280;
```

### Palette 3 : Rouge Bordeaux
```css
--primary: #991B1B;      /* Rouge bordeaux */
--primary-dark: #7F1D1D; /* Rouge foncé */
--primary-light: #FEE2E2; /* Rouge clair */
--text: #1F2937;
--text-secondary: #6B7280;
```

---

## WORKFLOW PRODUCTION (2h45 Total)

### Phase 1 : Design du Premier Template (30 min)

1. Ouvrir Canva Pro
2. Rechercher "Professional Resume"
3. Choisir template 1 colonne épuré
4. Modifier selon spécifications "Classic"
5. Remplir avec contenu généré par ChatGPT
6. Export PDF + DOCX

### Phase 2 : Duplication et Variations (1h30)

**Pour chaque template (2-4 min)** :
1. Dupliquer le Classic
2. Modifier la structure selon type (Sidebar, Modern, etc.)
3. Ajuster espacements et typographies
4. Export PDF + DOCX

**Répéter pour les 6 styles** : 6 × 15 min = 1h30

### Phase 3 : Variations Couleurs (45 min)

**Pour chaque template (2 min)** :
1. Dupliquer
2. Remplacer couleur primaire (Bleu → Vert ou Rouge)
3. Vérifier contraste texte
4. Export PDF + DOCX

**18 variations** (6 templates × 3 couleurs - originaux) : 18 × 2.5 min = 45 min

---

## CONVERSION DOCX DEPUIS PDF

### Option 1 : Canva Direct
- Canva Pro permet export direct en DOCX ✅

### Option 2 : Outils de Conversion
**Si pas Canva Pro** :
- **CloudConvert** : cloudconvert.com (gratuit 25 conversions/jour)
- **Zamzar** : zamzar.com (gratuit 2 fichiers/jour)
- **Adobe Acrobat** : Export PDF → Word (si abonnement)

**Workflow** :
1. Upload PDF
2. Convert to DOCX
3. Télécharger
4. Ouvrir dans Word et vérifier formatage
5. Ajuster si nécessaire (polices, espacements)

---

## PROMPT CHATGPT : GÉNÉRATION BULK (24 CVs)

### Automatiser avec Script Python + OpenAI API

```python
import openai
import json

openai.api_key = "YOUR_API_KEY"

profiles = [
    {"role": "Développeur Full-Stack", "years": 5, "skills": "Python, React, AWS"},
    {"role": "Data Scientist", "years": 3, "skills": "Python, ML, TensorFlow"},
    {"role": "Marketing Manager", "years": 7, "skills": "SEO, Growth, Analytics"},
    # ... 21 autres profils
]

for i, profile in enumerate(profiles):
    prompt = f"""
    Génère le contenu complet d'un CV pour :
    - Rôle : {profile['role']}
    - Expérience : {profile['years']} ans
    - Compétences : {profile['skills']}
    
    Format : Markdown avec sections Accroche, Expérience, Formation, Compétences.
    Inclure résultats chiffrés.
    """
    
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "user", "content": prompt}]
    )
    
    cv_content = response.choices[0].message.content
    
    with open(f"cv_content_{i+1}.md", "w") as f:
        f.write(cv_content)
    
    print(f"CV {i+1} généré : {profile['role']}")
```

**Coût** : ~24 CVs × $0.03 = **$0.72**

**Temps** : 10 minutes (automatique)

---

## CHECKLIST QUALITÉ (Par Template)

### Avant Export

- [ ] **ATS-Friendly** :
  - [ ] 1 colonne ou 2 colonnes simples max
  - [ ] Pas de zones de texte flottantes
  - [ ] Police standard (Arial, Calibri, Inter, Poppins)
  - [ ] Pas de tableaux complexes
  - [ ] Sections clairement titrées

- [ ] **Contenu** :
  - [ ] Placeholders [NOM], [EMAIL], [TÉLÉPHONE]
  - [ ] 3-4 expériences avec bullet points
  - [ ] 2 diplômes
  - [ ] Section compétences complète
  - [ ] Accroche de 2-3 lignes

- [ ] **Design** :
  - [ ] Marges 1-2cm
  - [ ] Contraste texte suffisant (4.5:1 minimum)
  - [ ] Alignements propres
  - [ ] Espacements cohérents
  - [ ] 1 page (ou 2 pages si senior)

- [ ] **Export** :
  - [ ] PDF 300 DPI
  - [ ] DOCX modifiable
  - [ ] Nom de fichier : `[Style]-[Couleur].pdf` (ex: `Classic-Bleu.pdf`)

---

## TEMPLATES PRÊTS À L'EMPLOI (Canva)

### Recherches Canva Recommandées

**Templates de base à adapter** :
1. "Minimalist Resume" → Classic
2. "Modern CV with Sidebar" → Modern
3. "Creative Resume" → Infographics
4. "Professional CV" → Rows
5. "Two Column Resume" → Two Column

**Filtres** :
- Style : Professional
- Couleur : [Selon palette]
- Layout : 1 page

---

## GÉNÉRATION AVEC FIGMA (Alternative Pro)

### Plugin Figma : "Content Reel"

1. Installer Content Reel plugin
2. Créer 1 template avec placeholders
3. Connecter CSV avec données (24 lignes)
4. Générer les 24 variations automatiquement
5. Export bulk PDF + PNG

**Avantage** : Design ultra-cohérent
**Temps** : 1h setup + 30 min génération = 1h30 total

---

## RÉSUMÉ WORKFLOW OPTIMAL

```
Jour 1 (2h45)
├─ Créer 6 templates Canva (1h30)
├─ Générer variations couleurs (45 min)
└─ Export 24 PDF + 24 DOCX (30 min)

Jour 2 (1h)
├─ Vérifier qualité (30 min)
├─ Zipper et organiser (15 min)
└─ Upload Gumroad (15 min)

Total : 3h45 pour produit complet
```

---

**Prêt à générer les 24 CV ! Utilise ces prompts et workflows pour une production ultra-rapide.**
