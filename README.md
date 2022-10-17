# Developer Open Space 2022 - Recap

Vom  14.10.2022 bis 16.10.2022  fand wie jedes Jahr der dretägige Developer Open Space statt. Die Veranstaltung besteht aus zwei Teilen. Für den Freitag konnte man sich für einen von 8 verschiedenen Workshops entscheiden. Samstag und Sonntag gab es dann die Möglichkeit im Barcamp-Format zu jeweils einstündigen Sessions zu gehen. 

## Workshop - Crossplane

Crossplane ist ein Open Source Projekt, welches es ermöglicht, Kubernetes als Management Plattform für Cloud Ressourcen zu nutzen. Crossplane ist ein Projekt der [Cloud Native Computing Foundation](https://www.cncf.io/). 

Der Workshop wurde von [Sven Wilhelm](https://twitter.com/refnode) geleitet. Er ist Software Engineer bei [DB Systel](https://twitter.com/dbsystel) und hat den Workshop sehr gut vorbereitet. Ich war einer von drei Teilnehmern, die sich für den Workshop entschieden haben. Da ich zuvor noch nie mit Crossplane gearbeitet habe, war ich sehr gespannt auf den Workshop.

Im Vergleich zu Terraform ist Crossplane eine sehr junge Technologie. Crossplane ist noch nicht in der Version 1.0 angekommen. Die aktuelle Version ist 0.14.0. Crossplane ist noch nicht so weit verbreitet wie Terraform.

Das USP von Crossplane ist, dass es **kontinuierlich den Zustand der Cloud Ressourcen überwacht und bei Bedarf Änderungen vornimmt**. Das ist ein großer Vorteil gegenüber Terraform!

## Tools

Im Workshop haben wir die folgenden Tools verwendet:

### Tools für die CLI

#### watch

Ein Tool, welches es ermöglicht, einen Befehl in einem bestimmten Intervall auszuführen. Damit lassen sich z.B. die Logs eines Pods in einem bestimmten Intervall anzeigen.

Beispiel:

    watch kubectl get pods

#### bat

Ein Tool, welches die Ausgabe von Befehlen farbig darstellt. Damit lassen sich z.B. die Logs eines Pods farbig darstellen.

Beispiel:

    kubectl logs -f pod-name | bat  

#### Plug

Ein Tool, welches es ermöglicht, die Ausgabe von Befehlen in einem Pager anzuzeigen. Damit lassen sich z.B. die Logs eines Pods in einem Pager anzeigen.

Beispiel:

    kubectl logs -f pod-name | plug

#### neovim

Ein Texteditor, welcher sehr gut für die Arbeit mit der Kommandozeile geeignet ist. Im Unterschied zu vim ist neovim bereits mit vielen Plugins ausgestattet.

#### pwgen

Ein Tool, welches zufällige Passwörter generiert.

Beispiel:

    pwgen -s 16 1

#### fzf

Ein Tool, welches es ermöglicht, in einer Liste von Einträgen zu suchen. Damit lassen sich z.B. die Pods in einem Namespace suchen.

Beispiel:

    kubectl get pods -n namespace | fzf

#### shellcheck

Ein Tool, welches es ermöglicht, Shell Skripte auf Fehler zu prüfen.

Beispiel:

    shellcheck script.sh

#### glow

Ein Tool, welches es ermöglicht, Markdown Dateien farbig darzustellen. Damit lassen sich z.B. die README.md Dateien von GitHub farbig darstellen.

Beispiel:

    glow README.md

#### pass

Ein Tool, welches es ermöglicht, Passwörter zu speichern und zu verwalten. Damit lassen sich z.B. Passwörter für die Cloud Provider speichern.

Beispiel:

    pass show cloud-provider

#### topgrade

Ein Tool, welches es ermöglicht, die Tools auf dem System zu aktualisieren.

Beispiel:

    topgrade

### Tools für Kubernetes

#### krew

Ein Tool, welches es ermöglicht, Plugins für die Kommandozeile zu installieren. Damit lassen sich z.B. Plugins für kubectl installieren.

Beispiel:

    kubectl krew install ns

#### stern

Ein Tool, welches es ermöglicht, die Logs von mehreren Pods gleichzeitig anzuzeigen. Damit lassen sich z.B. die Logs von mehreren Pods gleichzeitig anzeigen.

Beispiel:

    stern -n namespace pod-name

#### skopeo

Ein Tool, welches es ermöglicht, Container Images zu kopieren. Damit lassen sich z.B. Container Images von einem Container Registry in ein anderes Container Registry kopieren.

Beispiel:

    skopeo copy docker://docker.io/library/nginx:latest docker://docker.io/library/nginx:1.21.3

#### fluxed/tab/flux

Ein Tool, welches es ermöglicht, die Konfiguration von Kubernetes Ressourcen zu versionieren. Damit lassen sich z.B. die Konfiguration von Kubernetes Ressourcen in einem Git Repository speichern.

Beispiel:

    flux install | kubectl apply -f -

#### rancher

Ein Tool, welches es ermöglicht, Kubernetes Clustern zu verwalten. Damit lassen sich z.B. Kubernetes Clustern in einem Web Interface verwalten.

Beispiel:

    rancher login https://rancher.example.com

#### kubectx

Ein Tool, welches es ermöglicht, zwischen verschiedenen Kubernetes Clustern zu wechseln. Damit lassen sich z.B. die Kubernetes Konfigurationen von verschiedenen Kubernetes Clustern verwalten.

#### k9s

Ein Tool, welches es ermöglicht, Kubernetes Ressourcen in einem Text-Interface auf der Kommandozeile zu verwalten.

#### kubebuilder

Ein Tool, welches es ermöglicht, Kubernetes Operatoren zu entwickeln.

Beispiel:

    kubebuilder init --domain example.com

#### kubeconform

Ein Tool, welches es ermöglicht, Kubernetes Ressourcen auf Fehler zu prüfen.

#### kube-linter

Ein Tool, welches es ermöglicht, Kubernetes Ressourcen auf Fehler zu prüfen.

Beispiel:

    kube-linter lint pod.yaml

#### helm

Ein Tool, welches es ermöglicht, Kubernetes Ressourcen zu verwalten. Damit lassen sich z.B. Kubernetes Ressourcen in einem Helm Chart verwalten.

Beispiel:

    helm install my-chart

#### kustomize

Ein Tool, welches es ermöglicht, Kubernetes Ressourcen zu verwalten. Damit lassen sich z.B. Kubernetes Ressourcen in einem Kustomize Overlay verwalten.

Beispiel:

    kustomize build .

#### minikube

Ein Tool, welches es ermöglicht, einen lokalen Kubernetes Cluster zu starten. Damit lassen sich z.B. Kubernetes Ressourcen lokal testen.

Beispiel:

    minikube start

### Tools für die Cloud

#### cloud

Ein Tool, welches es ermöglicht, die Cloud Ressourcen zu verwalten. Damit lassen sich z.B. die Cloud Ressourcen von AWS verwalten.

Beispiel:

    cloud aws ec2 describe-instances

#### awscli

Ein Tool, welches es ermöglicht, die Cloud Ressourcen von AWS zu verwalten. Damit lassen sich z.B. die Cloud Ressourcen von AWS verwalten.

Beispiel:

    aws ec2 describe-instances

### Tools für die Entwicklung

#### tig

Ein Tool, welches es ermöglicht, Git Repositories zu verwalten. Damit lassen sich z.B. die Commits eines Git Repositories anzeigen.

#### colordiff

Ein Tool, welches es ermöglicht, die Unterschiede zwischen zwei Dateien farbig darzustellen. Damit lassen sich z.B. die Unterschiede zwischen zwei Dateien farbig darstellen.

Beispiel:

    colordiff file1 file2

#### lazygit

Ein Tool, welches es ermöglicht, Git Repositories zu verwalten. Damit lassen sich z.B. die Commits eines Git Repositories anzeigen.

#### lazydocker

Ein Tool, welches es ermöglicht, Docker Container zu verwalten. Damit lassen sich z.B. die Container anzeigen.

### Tools für den Desktop

#### Obsidian  

Ein Tool, welches es ermöglicht, Markdown Dateien zu verwalten. Damit lassen sich z.B. Markdown Dateien verwalten. Es eignet sich gut für die Verwaltung von Notizen. Durch die Verwendung von Markdown Dateien lassen sich die Notizen auch in einem Git Repository verwalten. In einem Graphen lassen sich die Notizen verknüpfen.
 Es wurde mir als Tools zum Wissensmanagement empfohlen. Es ist Open Source und wird von Obsidian Labs entwickelt.

**Link:** https://obsidian.md/

#### Microsoft Power BI  

Ein Tool, welches es ermöglicht, Daten zu visualisieren. Damit lassen sich z.B. Daten visualisieren. Es eignet sich gut für die Visualisierung von Daten.

**Link:** https://powerbi.microsoft.com/de-de/

#### Google Looker

Ein Tool, welches es ermöglicht, Daten zu visualisieren. Damit lassen sich z.B. Daten visualisieren. Es eignet sich gut für die Visualisierung von Daten. Wie bei MS Power BI lassen sich auch hier die Daten aus verschiedenen Datenquellen verbinden. Dazu werden die Daten in eine Datenbank geladen und dann in Looker visualisiert. Als Quellen können hier Datenbanken, Dateien, APIs, etc. verwendet werden.

Google Looker ist eine gute Alternative zu MS Power BI, vor allem wenn man sich für die Google Cloud interessiert.

**Link:** https://looker.com/

## Fazit

Für mich interessant war, dass hier viele Entwickler aus der C#-Ecke und GitOps-Ecke kamen, die für gewöhnlich für riesige Konzerne arbeiten. Während ich bei den PHP Meetups und Barcamps, die ich sonst so besuche, des Öfteren denke, dass wir technologisch ganz vor mit dabei sind, bekam ich hier mal wieder die Gelegenheit zu erfahren, wie viel ich eigentlich nicht weiß.
