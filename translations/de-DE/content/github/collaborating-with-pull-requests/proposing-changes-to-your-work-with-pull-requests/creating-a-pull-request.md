---
title: Pull Request erstellen
intro: 'Erstelle einen Pull Request, um Änderungen an einem Repository vorzuschlagen und um daran mitzuarbeiten. Um sicherzustellen, dass der Default-Branch eines Repositorys nur vollständig abgeschlossene und geprüfte Commits enthält, werden diese Änderungen in einem separaten *Branch* präsentiert.'
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request
  - /articles/creating-a-pull-request
  - /github/collaborating-with-issues-and-pull-requests/creating-a-pull-request
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
topics:
  - Pull requests
---

Jeder, der Leseberechtigungen für ein Repository besitzt, kann einen Pull Request erstellen. Du benötigst jedoch Schreibberechtigungen, um einen Branch zu erstellen. Wenn Du einen neuen Branch für Deinen Pull Request erstellen möchtest, aber keine Schreibberechtigung hast, kannst Du das Repository zunächst forken. Weitere Informationen findest Du unter „[Einen Pull Request von einem Fork erstellen](/articles/creating-a-pull-request-from-a-fork)“ und „
Informationen zu Forks</a.></p> 

Du kannst festlegen, in welchen Branch Du Deine Änderungen zusammenführen möchtest, wenn Du Deinen Pull Request erstellst. Pull Requests können nur zwischen zwei unterschiedlichen Branches geöffnet werden.

{% data reusables.pull_requests.perms-to-open-pull-request %}

{% data reusables.pull_requests.close-issues-using-keywords %}



## Branch-Bereich und Ziel-Repository ändern

Standardmäßig basieren Pull Requests auf dem Default Branch des übergeordneten Repositorys. Weitere Informationen findest Du unter „[Informationen zu Branches](/github/collaborating-with-issues-and-pull-requests/about-branches#about-the-default-branch)“.

Wenn das standardmäßige übergeordnete Repository nicht korrekt ist, kannst Du über die Dropdownlisten sowohl das übergeordnete Repository als auch den Branch ändern. Du kannst über die Dropdownlisten auch Head- und Basis-Branches untereinander austauschen, um Diffs zwischen Referenzpunkten zu erstellen. Referenzen müssen hier Branch-Namen in Deinem GitHub-Repository sein.

![Branches für Pull-Request-Bearbeitung](/assets/images/help/pull_requests/pull-request-review-edit-branch.png)

Denke im Hinblick auf Branches daran, dass der *Basis-Branch* der Ort ist, **wo** Änderungen angewendet werden sollen, und der *Head-Branch* das enthält, **was** Du ändern möchtest.

Wenn Du das Basis-Repository änderst, änderst Du auch die Benachrichtigungen für den Pull Request. Jeder, der zum Basis-Repository pushen kann, erhält eine E-Mail-Benachrichtigung und bekommt den neuen Pull Request im Dashboard angezeigt, wenn er sich das nächste Mal anmeldet.

Wenn Du Informationen im Branch-Bereich änderst, werden die Vorschauen für „Commit“ (Commit) und „Files changed“ (Dateien geändert) aktualisiert, um Deinen neuen Bereich anzuzeigen.

{% tip %}

**Tipps**:

- Über die Vergleichsansicht kannst Du Vergleiche über einen bestimmten Zeitraum einrichten. Weitere Informationen findest Du unter „[Commits vergleichen](/github/committing-changes-to-your-project/comparing-commits)."
- Projektbetreuer können eine Pull-Request-Vorlage für ein Repository hinzufügen. Vorlagen umfassen Aufforderungen für Informationen im Text eines Pull Requests. Weitere Informationen findest Du unter „[Informationen zu Vorlagen für Issues und Pull Requests](/articles/about-issue-and-pull-request-templates)“

{% endtip %}



## Den Pull Request erstellen

{% include tool-switcher %}

{% webui %}

{% data reusables.repositories.navigate-to-repo %}

2. Wähle im Menü „Branch“ den Branch aus, der Deine Commits enthält. ![Branch-Dropdownmenü](/assets/images/help/pull_requests/branch-dropdown.png) 
   
   {% data reusables.repositories.new-pull-request %}

4. Wähle im _base_ (Basis) Branch-Dropdownmenü den Branch aus, in den Du Deine Änderungen zusammenführen möchtest. Wähle dann im _compare_ (vergleichen) Branch-Dropdownmenü den Themen-Branch aus, in dem Du die Änderungen vorgenommen hast. ![Dropdown-Menüs zur Auswahl von Basis- und Vergleichs-Branches](/assets/images/help/pull_requests/choose-base-and-compare-branches.png) 
   
   {% data reusables.repositories.pr-title-description %}
   
   
   
   {% data reusables.repositories.create-pull-request %}

{% data reusables.repositories.asking-for-review %}

Nachdem Dein Pull Request geprüft wurde, kannst Du ihn [in das Repository mergen](/articles/merging-a-pull-request).

{% endwebui %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

Um einen Pull Request zu erstellen, nutze den `gh pr create` Befehl.  



```shell
gh pr create
```


Nutze die `--assignee` oder `-a` Parameter, um einem Pull Request eine Person zuzuweisen. Du kannst `@me` nutzen, um den Pull Request Dir selbst zuzuweisen. 



```shell
gh pr create --assignee "@octocat"
```


Der Branch, in den der Pull Request gemergt werden soll, kann über die `--base` oder `-B` Parameter spezifiziert werden. Der Branch, der die Commits für den Pull Request enthält, kann über die `--head` oder `-H` Parameter festgelegt werden.



```shell
gh pr create --base my-base-branch --head my-changed-branch
```


Dem neuen Pull Request kann über die `--title` und `--body` Parameter ein Titel und eine Beschreibung vorgegeben werden.



```shell
gh pr create --title "Der Fehler ist behoben" --body "Alles funktioniert wieder"
```


Über den `--draft` Parameter kann ein Pull Request als Entwurf markiert werden.



```shell
gh pr create --draft
```


Die `--label` und `--milestone` Parameter ermöglichen es, dem Pull Request Labels und Milestones hinzuzufügen.



```shell
gh pr create --label "bug,help wanted" --milestone octocat-milestone
```


Mit dem `--project` Parameter kann der neue Pull Request einem bestimmten Projekt hinzugefügt werden.



```shell
gh pr create --project octocat-project
```


Über den `--reviewer` Parameter kann ein Review von einer bestimmten Person oder einem Team angefordert werden.



```shell
gh pr create --reviewer monalisa,hubot  --reviewer myorg/team-name
```


Der Pull Request kann über Angabe des `--web` Parameters im Standard-Webbrowser geöffnet werden. 



```shell
gh pr create --web
```


{% endcli %}

{% desktop %}

{% mac %}

1. Wechsle in den Branch, für den Du einen Pull Request erstellen willst. Weitere Informationen findest Du unter "[Zwischen Branches wechseln](/desktop/contributing-and-collaborating-using-github-desktop/managing-branches#switching-between-branches)."
2. Klicke auf **Create Pull Request** (Pull-Request erstellen). {% data variables.product.prodname_desktop %} wird {% data variables.product.prodname_dotcom %} in Deinem Standard-Webbrowser öffnen. ![Die Create Pull Request Schaltfläche](/assets/images/help/desktop/mac-create-pull-request.png)

3. Sorge dafür, dass in {% data variables.product.prodname_dotcom %} das **base:** Drop-Down Menü auf den Branch eingestellt ist, in den die Änderungen gemergt werden sollen. Stell sicher, dass im **compare:** Drop-Down Menü der Branch ausgewählt ist, in dem sich Deine Änderungen befinden. ![Dropdown-Menüs zur Auswahl von Basis- und Vergleichs-Branches](/assets/images/help/desktop/base-and-compare-branches.png) 
   
   {% data reusables.repositories.pr-title-description %}
   
   
   
   {% data reusables.repositories.create-pull-request %}

{% endmac %}

{% windows %}

1. Wechsle in den Branch, für den Du einen Pull Request erstellen willst. Weitere Informationen findest Du unter "[Zwischen Branches wechseln](/desktop/contributing-and-collaborating-using-github-desktop/managing-branches#switching-between-branches)."
2. Klicke auf **Create Pull Request** (Pull-Request erstellen). {% data variables.product.prodname_desktop %} wird {% data variables.product.prodname_dotcom %} in Deinem Standard-Webbrowser öffnen. ![Die Create Pull Request Schaltfläche](/assets/images/help/desktop/mac-create-pull-request.png)

3. Sorge dafür, dass in {% data variables.product.prodname_dotcom %} das **base:** Drop-Down Menü auf den Branch eingestellt ist, in den die Änderungen gemergt werden sollen. Stell sicher, dass im **compare:** Drop-Down Menü der Branch ausgewählt ist, in dem sich Deine Änderungen befinden. ![Dropdown-Menüs zur Auswahl von Basis- und Vergleichs-Branches](/assets/images/help/desktop/base-and-compare-branches.png)

   {% data reusables.repositories.pr-title-description %}
   
   
   
   {% data reusables.repositories.create-pull-request %}

{% endwindows %}

{% enddesktop %}

{% ifversion fpt %}

{% codespaces %}

1. Klicke auf das **Create Pull Request** Icon, sobald Du alle Änderungen in Deiner lokalen Kopie des Repositorys committet hast. ![Source Control Randfenster mit hervorgehobener Create Pull Request Schaltfläche](/assets/images/help/codespaces/codespaces-commit-pr-button.png)  

2. Prüfe die Korrektheit Deines lokalen Branches und Repositorys von dem aus Du mergt, als auch des Remote-Branches und Repositorys in welches Du mergst. Anschließend kannst Du dem Pull Request einen Titel und eine Beschreibung zuweisen. ![GitHub Pull Request Randfenster](/assets/images/help/codespaces/codespaces-commit-pr.png)

4. Klicke auf **Create** (Erstellen).

Weitere Hinweise vom Erstellen von Pull Requests in {% data variables.product.prodname_codespaces %} findest Du unter "[Codespaces für Pull Requests verwenden](/codespaces/developing-in-codespaces/using-codespaces-for-pull-requests)."

{% endcodespaces %}

{% endif %}


## Weiterführende Informationen

- „[Einen Pull Request von einem Fork erstellen](/articles/creating-a-pull-request-from-a-fork)“
- „[Den Basis-Branch eines Pull Requests ändern](/articles/changing-the-base-branch-of-a-pull-request)“
- „[Issues und Pull Requests über die Seitenleiste zu einem Projektboard hinzufügen](/articles/adding-issues-and-pull-requests-to-a-project-board/#adding-issues-and-pull-requests-to-a-project-board-from-the-sidebar)“
- „[Informationen zur Automatisierung für Issues und Pull Requests mit Abfrageparametern](/issues/tracking-your-work-with-issues/creating-issues/about-automation-for-issues-and-pull-requests-with-query-parameters)“
- "[Issues und Pull Requests anderen GitHub-Benutzern zuweisen](/issues/tracking-your-work-with-issues/managing-issues/assigning-issues-and-pull-requests-to-other-github-users)"
- "[Auf GitHub schreiben](/github/writing-on-github)"
