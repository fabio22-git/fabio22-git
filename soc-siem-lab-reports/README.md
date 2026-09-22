# 🛰️ SOC & SIEM Lab Reports

Raccolta di tre indagini svolte in un laboratorio SOC controllato, costruite per documentare non soltanto l'uso di **Splunk**, ma soprattutto il metodo seguito per trasformare un alert in una decisione motivata.

Le analisi mostrano il percorso completo: lettura dell'alert, definizione dello scope, ricerca e correlazione dei log, verifica sull'endpoint, validazione tramite Threat Intelligence, classificazione dell'evento e proposta di remediation o tuning.

> **Contesto:** esercitazioni pratiche svolte su TryHackMe. I report non rappresentano esperienza in un SOC di produzione e non contengono dati reali di clienti o aziende.

---

## 🔎 Metodo di analisi

1. Comprensione dell'alert e formulazione delle prime ipotesi.
2. Definizione delle domande di scoping e degli elementi da verificare.
3. Ricerca e correlazione degli eventi in Splunk.
4. Analisi del contesto: utente, host, processo, parent-child relationship e timeline.
5. Pivot sull'endpoint e raccolta di ulteriori evidenze, quando necessaria.
6. Verifica di hash e indicatori tramite fonti di Threat Intelligence.
7. Classificazione come True Positive o False Positive.
8. Documentazione delle evidenze e proposta di remediation o tuning della detection.

---

## 📄 Report

| Scenario | Analisi svolta | Esito | Report |
|---|---|---|---|
| Phishing - Eredità sospetta | Verifica della consegna, ricerca di interazioni in uscita, scoping dell'impatto ed estrazione degli IOC | **True Positive** | [Apri il report](reports/01-phishing-alert-analysis.pdf) |
| Processo sospetto - TrustedInstaller | Analisi della catena `services.exe → TrustedInstaller.exe`, verifica del percorso, calcolo SHA-256 e controllo su VirusTotal | **False Positive** | [Apri il report](reports/02-trustedinstaller-process-analysis.pdf) |
| Processo sospetto - taskhostw | Analisi della catena `svchost.exe → taskhostw.exe KEYROAMING`, correlazione temporale, verifica SHA-256 e controllo su VirusTotal | **False Positive** | [Apri il report](reports/03-taskhostw-process-analysis.pdf) |

---

## 🧰 Strumenti e competenze applicate

- **Splunk:** ricerca, filtraggio, lettura dei campi e correlazione degli eventi.
- **Sysmon:** analisi di eventi Process Create e relazioni parent-child.
- **PowerShell:** verifica del file sull'endpoint e calcolo dell'hash SHA-256.
- **VirusTotal:** validazione degli indicatori e controllo della firma digitale.
- **SOC workflow:** triage, scoping, analisi degli IOC, classificazione e reporting.
- **Detection tuning:** distinzione tra comportamento malevolo e attività legittima per ridurre i falsi positivi.

---

## 🎯 Obiettivo del progetto

Questo progetto rende osservabile il mio approccio all'analisi: non fermarmi al nome di un processo o al verdetto di uno strumento, ma verificare contesto, coerenza delle evidenze e impatto prima di arrivare a una conclusione.

**Autore:** [Fabio Capano](https://github.com/fabio22-git)  
**Profilo:** Junior Cybersecurity Specialist | Blue Team & SOC Analyst
