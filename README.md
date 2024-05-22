# Portfolio : Mise en Place et Configuration d'un SIEM (Azure Sentinel) dans Azure

## Objectif du Projet
L'objectif de ce projet est de déployer et de configurer Azure Sentinel, une solution de gestion des informations et des événements de sécurité (SIEM) dans Azure. Azure Sentinel permet de collecter, détecter, enquêter et répondre aux menaces sur l'ensemble de l'entreprise. Le projet vise à améliorer la sécurité globale et la capacité de réponse aux incidents en utilisant une solution SIEM prête à l'emploi.

## Problématique
Les entreprises font face à une augmentation des menaces de cybersécurité, avec des attaques de plus en plus sophistiquées et fréquentes. La détection rapide et la réponse aux incidents sont cruciales pour protéger les actifs critiques. Cependant, les défis incluent :
- La gestion d'un grand volume de données de sécurité.
- La corrélation des événements de sécurité provenant de diverses sources.
- La nécessité d'une solution évolutive et intégrée.
- La capacité à réagir rapidement et efficacement aux incidents de sécurité.

## Solution
La solution proposée est la mise en place d'Azure Sentinel, un SIEM natif du cloud, pour améliorer la détection et la réponse aux incidents de sécurité. Azure Sentinel offre les fonctionnalités suivantes :
- Collecte de données à grande échelle de différentes sources.
- Analyse et corrélation des données pour identifier les menaces.
- Visualisation des données de sécurité avec des tableaux de bord interactifs.
- Automatisation des réponses aux incidents de sécurité.

### Étapes de Mise en Place et de Configuration d'Azure Sentinel

#### Étape 1 : Créer un Espace de Travail Log Analytics
1. **Se connecter au portail Azure** : Allez sur le [portail Azure](https://portal.azure.com) et connectez-vous.
2. **Accéder à la création d'un espace de travail** : Dans le menu de gauche, cliquez sur `Créer une ressource`, recherchez `Log Analytics workspace` et sélectionnez `Créer`.
3. **Configurer les paramètres de l'espace de travail** :
   - Nom : `EspaceDeTravailSentinel`
   - Groupe de ressources : `MonGroupeDeRessources`
   - Région : Choisissez votre région
   - Cliquez sur `Revoir + créer`, puis `Créer`.

![Capture d'écran](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/media/log-analytics-tutorial/log-analytics-create.png)

#### Étape 2 : Activer Azure Sentinel
1. **Accéder à Azure Sentinel** : Dans le menu de gauche, cliquez sur `Microsoft Sentinel`.
2. **Créer une instance Sentinel** : Cliquez sur `+ Ajouter` pour ajouter Azure Sentinel à un espace de travail Log Analytics existant.
   - Sélectionnez `EspaceDeTravailSentinel` créé précédemment.
   - Cliquez sur `Ajouter`.

![Capture d'écran](https://docs.microsoft.com/en-us/azure/sentinel/media/sentinel-create/add-sentinel.png)

#### Étape 3 : Connecter les Sources de Données
1. **Accéder aux connecteurs de données** : Dans Azure Sentinel, allez dans `Connecteurs de données`.
2. **Configurer les connecteurs de données** : Sélectionnez les sources de données à connecter (par exemple, Azure AD, Azure Security Center, Office 365).
   - Suivez les instructions spécifiques pour chaque connecteur pour configurer les permissions et les paramètres nécessaires.

![Capture d'écran](https://docs.microsoft.com/en-us/azure/sentinel/media/sentinel-connect-data/connect-data.png)

#### Étape 4 : Créer des Règles d'Analyse
1. **Accéder aux règles d'analyse** : Dans Azure Sentinel, cliquez sur `Règles d'analyse`, puis sur `+ Créer`.
2. **Configurer une règle d'analyse** :
   - Nom : `DétectionAnomalies`
   - Description : `Détecter les activités anormales`
   - Source de données : Sélectionnez la source de données configurée.
   - Conditions : Configurez les conditions pour déclencher l'alerte.
   - Actions : Définissez les actions à entreprendre lorsque l'alerte se déclenche (par exemple, envoyer une notification, créer un incident).
   - Cliquez sur `Enregistrer`.

![Capture d'écran](https://docs.microsoft.com/en-us/azure/sentinel/media/sentinel-create-rules/create-rule.png)

#### Étape 5 : Configurer les Réponses Automatisées
1. **Accéder aux playbooks** : Dans Azure Sentinel, cliquez sur `Automatisation`, puis sur `Playbooks`.
2. **Créer un playbook** : Cliquez sur `+ Ajouter un playbook`.
   - Utilisez Azure Logic Apps pour créer un nouveau playbook.
   - Configurez les déclencheurs et les actions du playbook en fonction des scénarios de réponse aux incidents.
   - Enregistrez et activez le playbook.

![Capture d'écran](https://docs.microsoft.com/en-us/azure/sentinel/media/sentinel-playbooks/create-playbook.png)

## Conclusion
En suivant ces étapes, Azure Sentinel est déployé et configuré pour surveiller l'activité des services, détecter les menaces et automatiser les réponses aux incidents. Cette solution améliore la posture de sécurité de l'entreprise et réduit le temps de réponse aux incidents de sécurité.

## Réflexion
L'implémentation d'Azure Sentinel a montré son efficacité pour renforcer la sécurité de l'infrastructure en offrant une vue centralisée et des capacités d'analyse avancées. À l'avenir, il serait bénéfique d'explorer davantage l'intégration avec d'autres outils de sécurité et de continuer à affiner les règles d'analyse pour s'adapter aux nouvelles menaces et aux changements de l'environnement. L'automatisation des réponses aux incidents peut également être étendue pour couvrir davantage de scénarios et améliorer encore la réactivité aux incidents de sécurité.
