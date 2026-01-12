# PHP/TYPO3 Development Standards

## Code Style
- Respektiere PSR-12 für alle PHP-Dateien
- Nutze die vorhandene .editorconfig für Einrückung und Formatierung
- Orientiere dich am Stil existierender Dateien im Projekt
- Nutze ausschließlich `'` für Strings in PHP

## Code Quality & Clean Code
- Vermeide Code Smells wie:
    - Long Methods (> 20-30 Zeilen)
    - Large Classes (> 300 Zeilen)
    - Duplicate Code
    - Too Many Parameters (> 3-4)
    - Deep Nesting (> 3 Ebenen)
    - Magic Numbers und Strings
- Bevorzuge sprechende Variable- und Methodennamen
- Single Responsibility Principle beachten
- DRY-Prinzip: Extrahiere wiederholten Code in Methoden/Services
- Komplexität reduzieren: Early Returns statt verschachtelte If-Blöcke

## TYPO3 Spezifisch
- Verwende TYPO3 Coding Guidelines (für PHP siehe https://docs.typo3.org/m/typo3/reference-coreapi/main/en-us/CodingGuidelines/CglPhp/GeneralRequirementsForPhpFiles.html#general-requirements-for-php-files)
- Nutze moderne Extbase/Fluid Patterns
- Doctrine DBAL statt deprecated DB-Queries
- Verfolge das Prinzip eines Slim Controllers
- Verwende `RequestFactory` statt `GeneralUtility::getUrl()` (siehe https://docs.typo3.org/m/typo3/reference-coreapi/main/en-us/ExtensionArchitecture/HowTo/RestRequests/Index.html)
- Vermeide die Verwendung von `$GLOBALS['TSFE']`
- PHP-Logik sollte sich immer zentral und im Verzeichnis `Classes/Domain/` (oder Unterordner) befinden
- Verwende bitte bevorzugt Dependency Injection über `__construct()`

## TYPO3 Anti-Patterns (vermeiden!)
- Geschäftslogik in Templates (Fluid)
- Direkter Zugriff auf `$_GET`, `$_POST`, `$_SESSION`
- Statische Utility-Aufrufe wo DI möglich ist
- SQL-Queries außerhalb von Repositories
- Unterdrückte Errors mit `@`

## Best Practices
- Schreibe aussagekräftige Commit Messages (Conventional Commits) und orientiere dich am Stil vorhandener Commit Messages
- Dokumentiere komplexe Logik inline
- Keine hardkodierten Strings - nutze XLIFF
- Unit Tests für neue Business Logic

## Workflow
- Prüfe existierende Code-Patterns vor neuen Implementierungen
- Frage bei Architektur-Entscheidungen nach, bevor du Code schreibst
- Bevorzuge Refactoring vor Feature-Additions
- Weise auf bestehende Code Smells hin, wenn du sie beim Arbeiten entdeckst