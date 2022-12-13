# Pràctica Kaggle APC UAB 2022-23
### Nom: David Feliu de la peña Vilarroig
### DATASET: League of Legends SOLO-Q Ranked Games
### URL: [kaggle](https://www.kaggle.com/datasets/bobbyscience/league-of-legends-soloq-ranked-games)
## Resum
Aquesta base de dades ha sigut extreta de la Riot API , i a més a més ha fet servir scrapping per a treure més mostres,hi ha més de 240 000 de les quals 25 000 són d'un nivell de platino. A la nostra base de dades hi ha 59 atributs que dona informació sobre com està la partida en certs instants de temps en concret.
### Objectius del dataset
Volem aprender a classificar una partida a traves dels diferents atributs que ens proporciona la base de dades amb la maxima presicio possible. 
## Experiments
Durant aquesta pràctica hem realitzat diferents experiments, hem probat els diferents models i els hem comparat a la hora de procesar  hem provat si era millor normalitzant dades o sense normalitzar quins atributs agafar depenent de la seva correlacio hem provat les diferents correlacions els diferents hyperparametres per veure a on la curva d'apranentatge era practicament la mateixa.

### Preprocessat
Quines proves hem realitzat que tinguin a veure amb el pre-processat? com han afectat als resultats?
### Model
| Model | Hiperparametres | Mètrica | Temps |
| -- | -- | -- | -- |
| Random Forest | 100 Trees, criterion='gini', max_depth=None, min_samples_split=2, min_samples_leaf=1, max_features='auto', max_leaf_nodes=None, bootstrap=True, oob_score=False, n_jobs=1, random_state=None, verbose=0, min_density=None, compute_importances=None  | 77.22% | 18,65 s |
| SVM | C=1.0, kernel='rbf', degree=3, gamma='scale', coef0=0.0, shrinking=True, probability=False, tol=0.001, cache_size=200, class_weight=None, verbose=False, max_iter=-1, decision_function_shape='ovr', break_ties=False, random_state=None| 78% | 814 s |
| Knn | n_neighbors=5, *, weights='uniform', algorithm='auto', leaf_size=30, p=2, metric='minkowski', metric_params=None, n_jobs=None | 77.64% | 22 s|
| SVC Linear | penalty='l2', loss='squared_hinge', *, dual=True, tol=0.0001, C=1.0, multi_class='ovr', fit_intercept=True, intercept_scaling=1, class_weight=None, verbose=0, random_state=None, max_iter=1000 | 78% | 0.88s|
| Neuronal Network |  layers=None, name=None| 78% | 76 s |
## Conclusions
El millor model que s'ha aconseguit ha estat bastant be ja que accertem el resultat de la partida en un 80% dels casos aixo creec que es un bon resultat ja que en aquestes partides sempre poden pasar coses que no tenim controlades com per exemple si un jugador es desconecta aixo afectara molt a la partida i no en tenim cap seguiment. Per coses com aquestes trobo que esta be tenir el 80%
## Idees per treballar en un futur
Crec que seria interesant indagar més en els atributs com per exemeple el id de la partida i el minut que s'agafen les dades, jo al principi d'aquest treball no els hi vaig donar importancia aquest atributs pero just al acabar em vaig donar compte que es podria fer un model per a cada diferent instant de la partida i despres a la hora de fer el predict de la partida s'evalua en els diferents models a traves de les diferents dades que tenim i si hi ha mes 1 donem com a resultat 1 si no es aixi el resultat es igual a 0 , aixi imagino que millorariem molt les metriques d'evaluacio.
