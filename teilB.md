##### Workshop: project setup, pipelines, docker

## Teil B

* Gibt es kleine Backend-Funktionalitäten, die realisiert werden sollen?
* Sollen Dateien von A nach B geschoben werden?
* Sollen Daten in einer Datenbank abgespeichert werden?
* Sollen Funktionalitäten eventuell modular erweitert werden (eMail/push versenden, etc.)?

Wenn ja, dann nutzen wir das [serverless framework](https://serverless.com/) in Kombination mit AWS.
Das [serverless framework](teilSLS.md) muss idealerweise mit dem awscli (siehe [Teil AWS](teilAWS.md)) aufgesetzt werden.

### serverless-agent

Für jeden Kunden gibt es einen *serverless-agent*. Gibt es diesen noch nicht, muss dieser in IAM angelegt werden.
Die Konvention hierfür ist:

```
kundenname-serverless-agent
```

Der serverless-agent bekommt nur programmatic access, aber dafür alle Rechte! Wird das nicht konfiguriert, kann man mittels
serverless auch keine Komponenten in AWS erstellen!
Der serverless-agent muss dann im Ordner *.aws* im Home-Verzeichnis sowohl in *config* als auch in *credentials* eingetragen werden.
Unsere default region ist *eu-central-1*. Der serverless-agent wird IMMER in der *serverless.yml* definiert. Andernfalls kann es passieren,
dass aufgrund der Vielzahl der lokal konfigurierten Accounts ein Service im falschen Account erstellt wird! Dasselbe gilt für die region.

### Struktur

Es wird wie in Teil A ein Repo aufgesetzt, jedoch mit der großen Unterscheidung, dass wir KEINE automatischen Deployments definieren.
Backend-Kleinfunktioalitäten werden also vom Entwickler lokal in die Cloud gepusht (mittels serverless).
Die Quelle der Wahrheit ist die *serverless.yml*.
Hier werden z.b. functions definiert und ordentlich benannt, um diese dann auch in der Cloud wiederzufinden ([AWS Lambda](https://aws.amazon.com/lambda/) bei functions).

Serverless erstellt ein [CloudFormation](https://aws.amazon.com/cloudformation/) Template und nutzt dieses als Bauplan für das Aufsetzen und Verdrahten der Services in der Cloud.
Mit enthalten ist [CloudWatch](https://aws.amazon.com/cloudwatch/), um sehen zu können, was beispielsweise Funktionen zur Laufzeit loggen.
Alle weiteren AWS Komponenten sowie Rechteverwaltung, werden ALLE in der *serverless.yml* entwickelt.

### Offline DEV vs. remote

Wir entwickeln lokal. Das bedeutet alle AWS eigenen Services werden lokal reproduziert. Es soll die Möglichkeit einer Abnahmeumgebung geben, jedoch nicht wenn durch das Duplizieren der Services Mehrkosten entstehen.

Workshop Werner: [https://github.com/localstack/localstack](https://github.com/localstack/localstack)

Gute Beispiele:

