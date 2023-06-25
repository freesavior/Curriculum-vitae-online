# Curriculum-vitae-online

L'objectif est de créer un site CV en utilisant HTML5 et CSS, puis de l'héberger sur un serveur de stockage comme Amazon S3 (Simple Storage Service), ensuite  mettre en place une chaîne CI/CD (Continuous Integration/Continuous Deployment) pour déclencher automatiquement le déploiement du site à chaque modification effectuée en ligne.

La chaîne CI/CD permettra d'automatiser le processus de déploiement en intégrant des actions spécifiques à votre dépôt GitHub. Chaque fois que vous effectuez une modification dans votre dépôt, la chaîne CI/CD sera déclenchée et exécutera les étapes nécessaires pour déployer votre site CV sur AWS S3.

Pour mettre cela en place, voici les étapes générales que vous pouvez suivre :

# Créez votre site CV en utilisant HTML5 et CSS. Assurez-vous que votre structure de fichiers est correcte et que tous les fichiers nécessaires (HTML, CSS, images, etc.) sont inclus.

# Créez un compte AWS si vous n'en avez pas déjà un, puis configurez un bucket S3 pour héberger votre site CV. Assurez-vous d'obtenir les clés d'accès (Access Key) et les informations de secret (Secret Key) nécessaires pour accéder à votre compte AWS via l'interface de gestion AWS.

# Configurez les secrets AWS_ACCESS_KEY_ID et AWS_SECRET_ACCESS_KEY dans votre dépôt GitHub à l'aide de la commande gh secret set. Ces secrets seront utilisés par la chaîne CI/CD pour accéder à votre compte AWS lors du déploiement, ces étapes sont détaillées plus bas.

# Créez un fichier YAML de workflow dans le répertoire .github/workflows de votre dépôt. Ce fichier YAML définira les étapes nécessaires pour déployer votre site CV sur AWS S3. Vous devrez utiliser les actions GitHub appropriées pour effectuer des actions telles que la vérification du code, l'installation des dépendances, la synchronisation avec S3, etc.

# Dans votre fichier YAML de workflow, référencez les secrets AWS_ACCESS_KEY_ID et AWS_SECRET_ACCESS_KEY que vous avez configurés précédemment en utilisant la syntaxe ${{ secrets.NOM_DU_SECRET }}.

Une fois que vous avez configuré votre fichier YAML de workflow, effectuez un commit et un push dans votre dépôt GitHub. Cela déclenchera automatiquement la chaîne CI/CD et votre site CV sera déployé sur AWS S3.
Chaque fois que vous apportez des modifications à votre site CV et les poussez dans votre dépôt GitHub, la chaîne CI/CD sera à nouveau déclenchée et votre site sera mis à jour sur AWS S3.

# Configurez les secrets AWS_ACCESS_KEY_ID et AWS_SECRET_ACCESS_KEY dans votre dépôt GitHub

Installer github cli sur votre machine 

Installez la CLI GitHub selon les instructions spécifiques à votre système d'exploitation. Vous pouvez trouver les instructions d'installation sur le site officiel de la CLI GitHub : https://cli.github.com/

# Ouvrez une fenêtre de terminal ou une invite de commandes.
Connectez-vous à votre compte GitHub en exécutant la commande suivante :
# gh auth login

# Ajoutez vos secrets AWS en utilisant la commande suivante :
gh secret set AWS_ACCESS_KEY_ID --repo "nom d'utilisateur/nom du repo" 
gh secret set AWS_SECRET_ACCESS_KEY --repo "nom d'utilisateur/nom du repo"  

# Pour vérifier que les secrets ont été bien configuréés :
gh secret list --repo "nom d'utilisateur/nom du repo"                  

