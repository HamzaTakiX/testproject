# 🌤️ WeatherShopper E2E Automation Project

## 📝 Description
Ce projet contient des **tests automatisés end-to-end (E2E)** de la boutique en ligne [WeatherShopper](https://weathershopper.pythonanywhere.com) en utilisant **Selenium + Pytest**. Il simule l'achat automatique de produits (crèmes solaires ou hydratants) en fonction de la température affichée sur le site.

## 🎯 Objectif

- Automatiser le parcours utilisateur complet :
  1. Lire la température
  2. Choisir les bons produits
  3. Ajouter les deux produits les moins chers au panier
  4. Vérifier le panier
  5. Effectuer un paiement via Stripe
  6. Vérifier la confirmation de paiement

## 🛠️ Technologies Used

- **Python** - Programming language
- **Selenium WebDriver** - Browser automation
- **Pytest** - Test framework
- **Pytest-HTML** - HTML test reports
- **Page Object Model (POM)** - Design pattern for test automation

## 📂 Project Structure

```
projtest-main/
├── assets/
│   └── style.css
├── images/
│   ├── verification.png
│   ├── temperature.png
│   └── products.png
├── pages/
│   ├── home.py
│   ├── moisturizers.py
│   ├── sunscreens.py
│   ├── cart.py
│   └── payment_page.py
├── tests/
│   └── test_happy_path.py
├── utils/
│   └── helpers.py
├── conftest.py
└── requirements.txt
```

## 🚀 Features

- **Sélection de produits basée sur la température** :
  - En dessous de 19°C : Propose des hydratants
  - Au-dessus de 34°C : Propose des crèmes solaires
  - Entre 19°C et 34°C : Le test est ignoré

- **Automated shopping flow**:
  - Adds the two cheapest products from specified categories
  - Verifies cart contents and total amount
  - Completes the checkout process with test payment

- **Robust test framework**:
  - Page Object Model implementation
  - Explicit waits for better stability
  - HTML test reports

## 🏃‍♂️ Getting Started

### Prerequisites
- Python 3.8+
- Chrome or Firefox browser
- ChromeDriver or GeckoDriver (for Selenium)

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd projtest-main
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running Tests

Run the test suite with:
```bash
pytest tests/test_happy_path.py -v --html=report.html
```

## 🧪 Test Scenarios

Le test principal (`test_happy_path.py`) vérifie :
1. La détection de la température sur la page d'accueil
2. La navigation vers la page de produits appropriée
3. La sélection des deux produits les moins chers des catégories spécifiées
4. La vérification du panier
5. Le processus de paiement avec des données de test

## 📝 Notes importantes

- **Données de test Stripe** :
  - Carte : `4242 4242 4242 4242`
  - Date d'expiration : `12/34` (à entrer sous forme `"1234"`)
  - CVC : `123`
  - Code postal : `12345`
- Le test gère automatiquement le chargement des iframes Stripe avec des temps d'attente appropriés
- Des captures d'écran sont automatiquement enregistrées pour faciliter le débogage

## 📸 Captures d'écran

- [Page d'accueil](images/temperature.png)
- [Sélection des produits](images/products.png)
- [Paiement Stripe](images/stripe_after_submit.png)
- [Confirmation de paiement](images/verification.png)

## 📊 Reporting

Test execution generates an HTML report (`report.html`) with detailed test results, including:
- Test status (Pass/Fail)
- Execution time
- Console logs
- Screenshots (on failure)

## 👥 Auteurs

- **Hamza Taki**
- **Hamza El Bouatmani**

Projet développé pour l'apprentissage des tests E2E avec Python.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
