# Git & GitHub 101 Mini øvelse

**Tid (20-30 min):** Øv på fork -> branch -> fetch -> PR -> merge -> resolve merge conflict.

- **Gloser (Markdown, en fil)**

> Fullstendig nettleser-basert via **GitHub Codespaces** (ingen lokal installasjon nødvendig)

---
## Fremgang (deltaker)

### Viktig for denne økten
Vi bruker **Kursgrenen**: `github101-kurs` (IKKE `main`)

1. **Åpne** Dette repositoriet (Øverst til høyre -> *<> Code*) -> **Clone** lokalt, eller åpne i **Codespaces**
2. Når **codespace** er opprettet: velg **branch = `github101-kurs`**
3. I **codespace** terminalen:
    ```bash
    git checkout -b doc/<ditt navn>     #din arbeidsgren for kurset
    git remote add upstream https://github.com/Funkweb/GitHub101-Practical.git
    git fetch upstream
    ```
    Hvis *codespace* starter på `main`:
    ```bash
    git fetch
    git switch github101-kurs
    git checkout -b feature/<ditt-navn>
    ```
4. Finn oppgave filen **glossary.md**:
    - Erstatt **TBD** med kort beskrivelse på norsk. 
5. Commit & push:
    ```bash
    git add -A
    git commit -m "docs: oppdaterte glossary for <ditt navn>"
    git push --set-upstream origin HEAD
    ```
6. Opprett Pull Request
<br>Fra din fork -> **compare & pull request**
    - Base branch ```github101-kurs```
    - compare: ```doc/<ditt navn>```

7. Hvis det oppstår konflikter
    ```bash
    git remote add upstream https://github.com/Funkweb/GitHub101-Practical.git

    git fetch upstream
    git pull --rebase upstream github101-kurs # (eller git merge upstream/github101-kurs)
    git add -A
    git rebase --continue || git commit -m "chore: løste konflikt"
    git push
    ```
