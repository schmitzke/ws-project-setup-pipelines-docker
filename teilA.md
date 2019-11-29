##### Workshop: project setup, pipelines, docker

## Teil A

Die Anwendung wird keinerlei Backend beinhalten?
Die Anwendung wird hauptsächlich statisch sein?

Wenn ja, dann ist [create-react-app](https://github.com/facebook/create-react-app) das Tool der Wahl.
Frontends gebaut mit desem package können mittels static website hosting gehostet werden.
Der Cloud Provider erster Wahl ist AWS.
Der Service, der in AWS für static website hosting prädestiniert ist, heißt [S3](https://aws.amazon.com/s3/?sc_channel=PS&sc_campaign=acquisition_DE&sc_publisher=google&sc_medium=ACQ-P%7CPS-GO%7CBrand%7CDesktop%7CSU%7CStorage%7CS3%7CDE%7CEN%7CText&sc_content=s3_e&sc_detail=aws%20s3&sc_category=Storage&sc_segment=293614670064&sc_matchtype=e&sc_country=DE&s_kwcid=AL!4422!3!293614670064!e!!g!!aws%20s3&ef_id=Cj0KCQiAoIPvBRDgARIsAHsCw0_WmWTLDUcFlXRtp0cGOxDYbVpiuSEjt0ITVMfUSqIMbcUHM7D8Wt8aAmGzEALw_wcB:G:s).

Lokales Setup (relevant für Pipelines später):

Packages werden global mit
```
npm i -g packagename
```

oder
```
yarn global add packagename
```

installiert.

Im Frontend-Projekt installieren wir mit
```
yarn
```

Package normal hinzufügen
```
yarn add packagename
```

Package in devDependencies hinzufügen
```
yarn add -D packagename
```

Die yarn-lock wird mitcommittet!

Der Workflow sieht vor:

1. Einloggen in das entsprechende Git-Interface und unter der richtigen Kunden/Projekt-Gruppe ein neues Repo anlegen
2. Das leere Repo lokal klonnen.
3. Das Frontend darin aufsetzen/entwickeln (siehe [digital class: Frontend Workshop](https://github.com/schmitzke/digital-class/blob/master/INFO.md))
5. Auf den master-Branch pushen
6. Die Gitlab Environment Variablen anlegen (siehe [Teil Git](teilGit.md))
7. Die gitlab-ci.yml anlegen (siehe [Teil Git](teilGit.md))
8. Pushen auf den entsprechenden branch und ermitteln, ob das automatische Deployment angestoßen und das Frontend deployt wird.

Gute Beispiele: