# Sql-projetcts
Exos sql


Projets : Petits sites de BDD relationnelles
  
Petits sites de BDD relationnelles
Tu vas concevoir la base de données de plusieurs projets. SPOILER ALERT : ce projet fait également partie du pacours Dev Fullstack (sauf qu'eux devaient les créer pour de vrai). En fait, c'est rarement au Data Analyst de réaliser cette étape mais si tu arrives à le faire, tu auras une meilleure vue d'ensemble et tu pourras facilement dialoguer avec les devs quand tu auras besoin de comprendre et récupérer "leurs" données pour faire tes analyses ✌️

1. Introduction
Pour ce projet, nous allons te demander de modéliser plusieurs applications.

2. Le projet
2.1. FreeDoc - Réserve ton docteur
2.1.1. Le pitch
Allez, on va implémenter pour de vrai un concurrent de Doctolib! À toi d'être chirurgical 👩‍⚕️

2.1.2. Les models
Pour ce premier exercice, nous allons t'aider et te donner les models à créer :

un model Doctor, qui a comme attributs :

un first_name, qui est un string
un last_name, qui est un string
un specialty, qui est un string
un zip_code, qui est un string
un model Patient, qui a comme attributs:

un first_name, qui est un string
un last_name, qui est un string
un model Appointment, qui a comme attributs :

un date, qui est un datetime
Une fois les attributs fixés, on s'attaque aux relations :

Un appointment ne peut avoir qu'un seul doctor, mais un doctor peut avoir plusieurs appointment.
Un appointment ne peut avoir qu'un seul patient, mais un patient peut avoir plusieurs appointment.
Un doctor peut avoir plusieurs patient, au travers des appointments, et vice versa.
2.1.3. Petit coup de boost
Ta startup de docteurs marche à merveille, tellement que tu aimerais ajouter plusieurs tables :

city. Chaque docteur, patient, et rendez-vous est lié à une city. Une city peut avoir plusieurs docteurs, patients, et rendez-vous.
tu voudrais virer la ligne specialty de ta table doctor et la remplacer par un model à part entière : tu vas donc créer un model specialty. Un docteur aurait plusieurs specialty, et une specialty pourrait concerner plusieurs doctor.
Et voilà pour FreeDoc! Doctolib est en PLS.

2.2. Le Airbnb des promenades de chiens
2.2.1. Le pitch
En cours de "Bizness Growth Money Maker", on t'avait demandé de créer une entreprise à fort potentiel. À l'époque tu t'étais dit que ce serait une chouette idée de faire une plateforme où des personnes pourraient promener les chiens des autres, en échange de cash-money.
C'est dingue comme idée: ça va mettre tous les VC aux abois. Allez, on le fait !

2.2.2. Les models
À priori, les models sont simples: il y a un model dogsitter et un model dog (on te laisse choisir au moins un attribut chacun). Un dogsitter peut promener plusieurs dog lors d'une stroll (promenade, en anglais) ; et un dog peut avoir plusieurs dogsitter via les stroll.
Maintenant tu veux préciser la ville des promeneurs et des chiens pour faire un super algorithme de matching. Tu devras donc créer un model City avec comme attribut city_name. Chaque ville contient plusieurs promeneurs et plusieurs chiens mais un chien et un promeneur ne peuvent appartenir qu'a une ville.
Cela ressemble beaucoup à notre schéma de docteurs tout ceci ! C'est fait exprès, rien de tel pour s'entraîner que de refaire les exercices. Tu vas dérouler tes prochains model grâce à ça.

2.3. The Gossip Project
2.3.1 Le pitch
Le parcours utilisateur est le suivant: sur ce super réseau social, un utilisateur va s'inscrire, renseigner son prénom et nom, son mail et son age, puis il précisera sa ville avec une recherche par code postal.

Il aura ensuite toutes les fonctionnalités qui feront de cette appli une future licorne de la Bitchin'Tech:

Les utilisateurs peuvent créer des potins : "askip john est célib hihi"
Les utilisateurs, en créant des potins, peuvent mettre un ou plusieurs tags sur les potins: #romance
Les utilisateurs peuvent commenter des potins : "ahiii j'savé pa lol ptdr 💁‍♂️"
Et puisque ton appli doit respecter les standards de l'industrie, on va faire en sorte qu'il soit possible aussi de commenter des commentaires.
Les utilisateurs peuvent liker des potins.
Les utilisateurs peuvent contacter leur commères favoris en MP pour obtenir des exclus mondiales. L'utilisateur pourra donc rechercher les potins par ville, par utilisateurs, par date (plus récent ou plus ancien), par nombre de likes, par tags, pour trouver les potins les plus croustillants. Ça fait beaucoup?? Oui clairement, y a de la fonctionnalité de déglingos là. Pas de panique. On va te guider! Suis-nous. #### 2.3.2. Dessine-moi une BDD Allez, feuille / tableau / ERD en main et hop! => Imagine les models qu'il faut pour cette app, les relations possibles, puis évidemment les attributs de chaque model. Toute l'architecture de la BDD doit tenir sur un dessin. #### 2.3.3. Les models
LES USERS
Crée une classe User, qui aura comme attributs :

Un first_name, qui est un string
Un last_name, qui est un string
Un description, qui est un text
Un email, qui est un string
Un age, qui est un integer
LES VILLES
Crée une classe City, qui aura comme attributs :

Un name, qui est un string
Un zip_code, qui est un string Un utilisateur appartient à une seule ville mais une ville peut contenir plusieurs utilisateurs.
LES GOSSIPS
Crée une classe Gossip, qui aura comme attributs :

Un title, qui est un string
Un content, qui est un text Un utilisateur peut écrire plusieurs gossips mais un gossip ne peut être écrit que par un seul utilisateur.
LES TAGS
Crée une classe Tag, qui aura comme attributs :

Un title, qui est un string Un gossip peut avoir plusieurs tags et un tag peut être présent sur plusieurs gossip (genre #bromance).
LES MESSAGES PRIVÉS
Crée une classe PrivateMessage, qui aura comme attributs :

Un content, qui est un text Un PM aura un expéditeur et un (ou plusieurs) destinataires.
3. Rendu attendu
3 schémas de base de données relationnelles qui montrent que tu as bien compris le principe et que tu sauras lire à ton tour des schémas 😎
