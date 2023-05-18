# Przygotowanie środowiska pracy:
  * [Git](https://git-scm.com/) - [v2.40.1](https://github.com/git-for-windows/git/releases/download/v2.40.1.windows.1/Git-2.40.1-64-bit.exe) - _opcjonalnie_ w trakcie instalacji wybrać [Notepad++](https://github.com/notepad-plus-plus/notepad-plus-plus/releases/download/v8.5.3/npp.8.5.3.Installer.x64.exe) jako domyślny edytor
  * [GitHub CLI](https://docs.github.com/en/github-cli/github-cli/quickstart)([github](https://github.com/cli/cli)) [v2.29.0](https://github.com/cli/cli/releases/download/v2.29.0/gh_2.29.0_windows_amd64.msi)

# [Rozpoczęcie pracy](https://docs.github.com/en/get-started/quickstart)
  * [Konto GitHub](https://docs.github.com/en/get-started/onboarding/getting-started-with-your-github-account):
    - [utworzyć konto](https://github.com/signup)
  * Konfiguracja [Git](https://git-scm.com/book/en/v2) - [tożsamość](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup#_your_identity):
    ```bash
    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com
    ```
  * Konfiguracja [GitHub CLI](https://cli.github.com/manual/):
    - wygenerować [Personal access token](https://github.com/settings/tokens/new)
    - ustawić zmienną środowiskową [GITHUB_TOKEN](https://cli.github.com/manual/gh_help_environment):
     - prawym klawiszem "Start"
       - System -> Informacje -> Informacje o systemie
         - Zaawansowane ustawienia systemu -> zakładka _Zaawansowane_ -> przycisk _Zmienne środowiskowe...":
           - _Zmienne użytkownika dla USER_ -> _Nowa..._

       sprawdzenie:
       ```bash
       echo %GITHUB_TOKEN%
       gh auth status
       ```
    - ustawienie autentykacji _git_ przez _GitHub CLI_:
      ```bash
      gh auth setup-git
      ```
  * [Tworzenie repozytorium](https://docs.github.com/en/get-started/quickstart/hello-world#creating-a-repository)
  * [Tworzenie gałęzi](https://docs.github.com/en/get-started/quickstart/hello-world#creating-a-branch)
  * [Wprowadzanie i zatwierdzanie zmian](https://docs.github.com/en/get-started/quickstart/hello-world#making-and-committing-changes)
    ```bash
    # pobranie aktualnej wersji zdalnego repozytorium do lokalnego repozytorium
    git pull

    # właściwe wprowadzenie zmian w plikach
    # ...

    # sprawdzenie zmian
    git diff

    # dodawanie zawartości pliku do indeksu
    git add .

    # Rejestrowanie zmian w lokalym repozytorium
    git commit -s -m "Dodanie poleceń opisujących wprowadzanie i zatwierdzanie zmian"

    # wysłanie aktualnej wersji lokalnego repozytorium do zdalnego repozytorium
    git push
    ```
  * [Otwieranie "pull request"](https://docs.github.com/en/get-started/quickstart/hello-world#opening-a-pull-request)

    ```bash
    # przełączenie na nową gałąź "szkolenie"
    git checkout -b szkolenie

    git add .
    git commit -s -m "Dodanie poleceń opisujących otwieranie pull request"

    # utworzenie "pull request"
    gh pr create --title "Szkolenie GIT" --body "Opis pull request"

    ```
  * [Scalanie "pull request"](https://docs.github.com/en/get-started/quickstart/hello-world#merging-your-pull-request)
