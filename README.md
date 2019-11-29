## Workshop: project setup, pipelines, docker

### Synopsis

Dieses Repository fasst zusammen, auf welche Art und Weise Projekte aufgesetzt werden.
Hier steht nicht die Software im Vordergrund, sondern das gesamte Drumherum. Bitte alles lesen!
Hierbei wird zurzeit auf hybride-App-Entwicklung und JAMStack-Anwendungen verzichtet, da diese speziell und viel
zu umfänglich sind.
Es geht hier vorangig um folgende Fragen:

* Was für eine Art Projekt soll erstellt werden?
* Wo lege ich ein Repository an?
* Auf Basis der Projektart: Was für Komponenten werden benötigt?
* Wo gehört welche Komponente hin?
* Wie deploye ich welche Komponente?
* Wie erstelle ich eine gitlab Pipeline?
* Was ist Docker und wofür brauche ich das?
* Was ist serverless?
* Wie kann ich das, was lokal bei mir läuft, in die Cloud bringen?

Zuallererst muss man sich fragen:

* Ist das Projekt eine Frontend Anwendung? -> [Teil A](teilA.md)
* Beinhaltet das Projekt Backend Funktionalitäten? -> [Teil B](teilB.md)
* Ist das System eine Laufzeitumgebung mit oder ohne Datenbank? -> [Teil C](teilC.md)

* AWS Generell -> [Teil AWS](teilAWS.md)
* AWS Kommandos -> Teil AWS CLI
* Serverless Handhabe -> [Teil SLS](teilSLS.md)
* Docker Kommandos -> Teil Docker
* Git, Gitlab und Pipelines -> Teil Git
