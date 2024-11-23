### Documentation du Module `localemembers`

Bienvenue dans la documentation du module `localemembers`. Ce module Python est conçu pour détecter et formater les informations de localisation du système, en utilisant le module `locale`. Il fournit également une interface graphique élégante et épurée pour afficher ces informations à l'utilisateur.

#### Table des Matières

- [Documentation du Module `localemembers`](#documentation-du-module-localemembers)
  - [Table des Matières](#table-des-matières)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Fonctionnalités](#fonctionnalités)
- [Interface Graphique](#interface-graphique)
  - [Exemple d'interface graphique](#exemple-dinterface-graphique)
- [Contribuer](#contribuer)
- [Licence](#licence)

### Installation

Vous pouvez installer le module `localemembers` en utilisant pip :

```bash
pip install localemembers
```

Pour une installation locale, vous pouvez cloner le dépôt GitHub et installer le module en mode développement :

```bash
git clone https://github.com/votrecompte/localemembers.git
cd localemembers
pip install -e .
```

### Utilisation

Voici un exemple de la façon d'utiliser le module `localemembers` pour obtenir et afficher les informations de localisation du système :

```python
import localemembers

# Pour exécuter la fonction principale
localemembers.main()

# Pour exécuter l'interface graphique
localemembers.gui_main()
```

### Fonctionnalités

Le module `localemembers` fournit les fonctionnalités suivantes :

- **Détection et formatage des informations de localisation** :
  - `system_locale`: Locale du système.
  - `locale_encoding`: Encodage de la locale.
  - `friendly_language`: Langue de la locale.
  - `locale_country`: Pays de la locale.
  - `language_code`: Code de la langue.
  - `country_code`: Code du pays.
  - `formatted_language_code`: Code de la langue formaté.
  - `currency_symbol`: Symbole monétaire.
  - `decimal_point`: Point décimal.
  - `thousands_separator`: Séparateur de milliers.
  - `date_format`: Format de la date.
  - `time_format`: Format de l'heure.
  - `radix_char`: Caractère radix.
  - `thousands_sep`: Séparateur de milliers.
  - `yes_expr`: Expression régulière pour "oui".
  - `no_expr`: Expression régulière pour "non".
  - `currency_str`: Chaîne de devise.
  - `era`: Ère.
  - `era_d_t_fmt`: Format de date/heure basé sur l'ère.
  - `era_d_fmt`: Format de date basé sur l'ère.
  - `era_t_fmt`: Format de l'heure basé sur l'ère.
  - `alt_digits`: Chiffres alternatifs.

### Interface Graphique

Le module `localemembers` inclut une interface graphique élégante et épurée, créée avec PyQt5, pour afficher les informations de localisation à l'utilisateur. L'interface graphique est maximisée au démarrage et les composants sont dynamiques.

#### Exemple d'interface graphique

```python
import localemembers

# Pour exécuter l'interface graphique
localemembers.gui_main()
```

### Contribuer

Les contributions sont les bienvenues ! Veuillez ouvrir une issue ou soumettre une pull request sur le dépôt GitHub.

### Licence

Ce projet est sous licence MIT - voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

Avec cette documentation complète, vous êtes prêt à utiliser et à contribuer au module `localemembers`. Si vous avez besoin de plus d'aide ou de modifications supplémentaires, n'hésitez pas à me le faire savoir ! 😊