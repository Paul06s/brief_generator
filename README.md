# brief_generator
Local app to turn Schema into word brief

# Mon Projet de Générateur de Brief

Ce dépôt contient une application Flask permettant de :

- Coller une capture d'écran pour OCR (via Tesseract),
- Détecter des produits dans des fichiers JSON,
- Sélectionner un template Word (3 choix),
- Générer un fichier Word final.

## Structure

mon_projet/ 
├── app.py 
├── lancer.bat 
├── requirements.txt 
├── README.md 
├── templates/ 
  │ ├── template_catalogue_40p_avril.docx 
  │ ├── template_depliant_5volets_avril.docx 
  │ └── template_depliant_5volets_juillet_aout.docx 
├── data/ 
  ├── output/ 
  └── uploads/


- **app.py** : Le code principal Flask
- **templates/** : Contient les 3 exemples de templates Word
- **data/** : Fichiers JSON (optionnel pour OCR/matching)
- **output/** : Les .docx générés
- **uploads/** : Les images copiées/collées

## Installation

1. Installer Python 3+
2. `pip install -r requirements.txt`
3. Installer Tesseract-OCR :
   - Sur Windows : [Tesseract Windows Installer](https://github.com/UB-Mannheim/tesseract/wiki)
   - Mac : `brew install tesseract`
4. S'assurer que `pytesseract` trouve Tesseract (variable `TESSDATA_PREFIX` si nécessaire).

## Usage

- Double-cliquer `lancer.bat` (Windows) ou faire :

python app.py


- Ouvrir le navigateur à [http://localhost:5000](http://localhost:5000)
- Saisir la période, choisir un template, coller éventuellement une image de chemin de fer (OCR).
- Cliquer sur **Générer le brief Word** → Le .docx est téléchargé et stocké dans `output/`.

## Personnalisation

- Éditer `app.py` pour ajuster la logique (search & replace, insertion de paragraphes, etc.).
- Ajouter des balises dans les templates Word (ex: `{{periode}}`) si besoin de remplacements plus complexes.

---
