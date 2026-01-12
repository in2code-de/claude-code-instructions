# PHP/TYPO3 Development Standards

## Code Style
- Respektiere PSR-12 für alle PHP-Dateien
- Nutze die vorhandene .editorconfig für Einrückung und Formatierung
- Orientiere dich am Stil existierender Dateien im Projekt

## TYPO3 Spezifisch
- Verwende TYPO3 Coding Guidelines
- Nutze moderne Extbase/Fluid Patterns
- Doctrine DBAL statt deprecated DB-Queries

## Best Practices
- Schreibe aussagekräftige Commit Messages (Conventional Commits) und orientiere dich am Stil vorhandener Commit Messages
- Dokumentiere komplexe Logik inline
- Keine hardkodierten Strings - nutze XLIFF
- Unit Tests für neue Business Logic

## Workflow
- Prüfe existierende Code-Patterns vor neuen Implementierungen
- Frage bei Architektur-Entscheidungen nach, bevor du Code schreibst
- Bevorzuge Refactoring vor Feature-Additions
