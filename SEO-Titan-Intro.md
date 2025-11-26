# 🚀 SEO Titan — Analysez n’importe quel site en quelques secondes et obtenez un rapport SEO clair et exploitable

**SEO Titan** est un analyseur SEO conçu pour aller droit à l’essentiel :
vous entrez une URL → vous obtenez un rapport complet, propre et actionnable.

Il s’adresse aux **professionnels**, aux consultants SEO, aux développeurs, et à toutes les entreprises qui souhaitent comprendre en un instant la qualité SEO d’une page web.

---

# 🧠 Pourquoi SEO Titan ?

Que vous soyez développeur, consultant ou propriétaire d’un site, vous le savez :
**un audit SEO rapide et fiable peut faire la différence entre un site invisible et un site qui performe**.

SEO Titan répond à ce besoin en vous offrant :

* Une analyse simple et immédiate
* Un rapport clair, structuré et prêt à l’usage
* Aucune interface compliquée
* Une totale transparence sur ce qui doit être optimisé

Vous gagnez du temps, vous gagnez en précision — vous gagnez en performance.

---

# 🛠 Fonctionnement de SEO Titan

SEO Titan repose sur deux modules principaux :

### **1. `SEOAnalyzer`**

Analyse technique et structurelle de la page web.

### **2. `SEOReport`**

Génère un rapport texte propre et organisé.

Le tout est orchestré par ce script principal :

```python
"""
Script principal de l'analyseur SEO
"""

from colorama import init, Fore, Style
from seotitan.analyzer import SEOAnalyzer
from seotitan.report import SEOReport

def main():
    init()  # Initialize colorama
    print(f"{Fore.YELLOW}=== Analyseur SEO ===\n{Style.RESET_ALL}")
    
    while True:
        url = input("Entrez l'URL du site à analyser (ou 'q' pour quitter) : ").strip()
        if url.lower() == 'q':
            break
            
        if not url.startswith(('http://', 'https://')):
            url = 'https://' + url
            
        output_file = input("Nom du fichier de sortie (ex: rapport_seo.txt) : ").strip()
        if not output_file.endswith('.txt'):
            output_file += '.txt'
            
        try:
            analyzer = SEOAnalyzer(url)
            report = SEOReport(analyzer)
            report.generate(output_file)
        except Exception as e:
            print(f"{Fore.RED}Erreur: {str(e)}{Style.RESET_ALL}")
        
        print("\nVoulez-vous analyser un autre site ?")

if __name__ == "__main__":
    main()
```

 Ce script reste **fidèle, simple et robuste**.

---

# 📦 Installation

```bash
git clone https://github.com/gofastpanam/seo-titan.git
cd seo-titan
```

Créer un environnement virtuel (recommandé) :

```bash
python -m venv venv
source venv/bin/activate      # Linux/Mac
venv\Scripts\activate         # Windows
```

Installer les dépendances :

```bash
pip install -r requirements.txt
```

---

# ▶️ Utilisation

Lancer l’analyseur :

```bash
python main.py
```

SEO Titan vous demandera alors :

* l’URL du site à analyser
* le nom du fichier de sortie

Vous obtiendrez un rapport **.txt** comportant :

* l’analyse technique
* l’analyse du contenu
* les problèmes détectés
* les axes d’amélioration

Simple, direct, efficace.

---

# 📋 Format du rapport

Un rapport généré ressemble à ceci :

```
RAPPORT D'ANALYSE SEO
=====================
URL analysée: https://example.com
Date: 2025-01-01 09:13:04

...

SUGGESTIONS D'AMÉLIORATION
=====================
CRITIQUE - Meta description manquante
Problème : Aucune meta description n'est définie.
Solution : Ajoutez une meta description de 150-160 caractères.
```

Le style est volontairement minimaliste pour rester lisible, clair et exploitable dans n’importe quel contexte professionnel.

---

# 🤝 Contribuer

Les contributions sont les bienvenues !

1. Forkez le projet
2. Créez une branche de fonctionnalité
3. Commitez vos modifications
4. Ouvrez une Pull Request

---

# 👤 Auteur

**Benjamin Jaccob** – Développeur & fondateur de **VisiCraft**
Création de sites web • SEO • UX • Optimisation technique

📧 **[contact@visicraft.fr](mailto:contact@visicraft.fr)**
🌐 **[https://visicraft.fr](https://visicraft.fr)**
