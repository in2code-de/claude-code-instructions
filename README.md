# Claude Code Instructions für TYPO3 Projekte

Dieses Repository enthält standardisierte Anweisungen und Coding Guidelines für die Arbeit mit Claude Code in TYPO3-Projekten.

## Installation

### Globale Installation (empfohlen)

#### CLAUDE CODE

Die `CLAUDE.md` Datei kann global als `~/.claude/CLAUDE.md` abgelegt werden. Diese globale Konfiguration wird dann für alle Claude Code Sessions verwendet:

```bash
git clone https://github.com/in2code-de/claude-code-instructions.git
mkdir -p ~/.claude
cp claude-code-instructions/CLAUDE.md ~/.claude/CLAUDE.md
```

#### GEMINI CLI

Ähnlich wie bei Claude wird eine `~/.gemini/GEMINI.md` benötigt. Details siehe oben.

### Projekt-spezifische Installation (optional)

#### Manuelle Installation

Checke dieses Repository aus und entpacke den Inhalt in das `.config/claude-code/` Verzeichnis deines Projekts:

```bash
git clone https://github.com/in2code-de/claude-code-instructions.git
mkdir -p dein-projekt/.config/claude-code
cp -r claude-code-instructions/* dein-projekt/.config/claude-code/
```

#### Installation via Makefile

Füge folgenden Target zu deinem Makefile hinzu, um die Claude Code Instructions automatisch herunterzuladen und zu installieren:

```makefile
## Create .config/claude-code directory and download latest claude-code-instructions
.create-claude-config-dir:
    echo "$(EMOJI_dividers) Creating .config/claude-code directory"
    mkdir -p .config/claude-code
    echo "$(EMOJI_receive) Downloading latest claude-code-instructions from GitHub"
    curl -L https://github.com/in2code-de/claude-code-instructions/archive/refs/heads/main.zip -o /tmp/claude-code-instructions.zip
    unzip -o /tmp/claude-code-instructions.zip -d /tmp/
    cp /tmp/claude-code-instructions-main/CLAUDE.md .config/claude-code/CLAUDE.md
    ln -sf CLAUDE.md .config/claude-code/instructions.md
    rm -rf /tmp/claude-code-instructions.zip /tmp/claude-code-instructions-main
    echo "$(EMOJI_thumbsup) Claude Code instructions installed"
```

Anschließend kannst du die Installation mit folgendem Befehl ausführen:

```bash
make .create-claude-config-dir
```

*Hinweis*: Es empfiehlt sich dann, den Befehl `.create-claude-config-dir` in `install-project` mit aufzunehmen
