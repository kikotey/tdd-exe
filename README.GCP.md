
## Google function deployment (implicite)

#
##
### exercice 1 (point bonus en cas de documentation)
##
#
GCP: 
https://cloud.google.com/iam/docs/service-accounts-create?hl=fr#iam-service-accounts-create-gcloud
- (step 1) Créer un compte GCP
- (step 2) Activité les google function
- (step 3) Installez le cli gcp sur votre poste en local
- (step 4) Créer un compte de service
- (step 5) Donner les rules nécessaire à ce compte pour lui autoriser le droit de faire des déploiements.


#
##
### exercice 2 
##
#
CD (indication):
https://cloud.google.com/functions/docs/tutorials/http?cloudshell=true#functions-clone-sample-repository-nodejs
- chaque membre d'équipe doivent choisir un trigrame
- chaque déploiement doivent permettre d'identifier celui qui a lancé le déploiement. norme de nommage des déploiement: <nom du deploiement>-<trigrame>
- l'acces au compte de service doit etre permis au différent utilisateur
- les déploiements doivent ce faire dans un premier temps en < insecure >, ensuite une proposition pour sécuriser l'accès aux ressources doit être fait.

#
##
### exercice 3 (point bonus en cas de documentation)
##
#
Github action (avec clef json d'identification de service account)
https://cloud.google.com/iam/docs/keys-create-delete#iam-service-account-keys-create-gcloud
- créer un pipeline qui accède à votre environnement gcp en vue d'un déploiement via votre compte de service
- le secret pour la clef est: svcaccount et doit contenir la clef json de compte de service
