# **README - fme's Microsoft 365 Stories**

## **Flow - Automatic bookings of hours**
## **Flow - Automatisierte Stundenbuchung**

*Mara Teresa Carlota Klicker*

---

## Table of Contents - Inhaltsverzeichnis

- [English Version](#engVersion) 
    - [Introduction](#engIntroduction)
    - [Requirements](#engRequirements)
    - [Import](#engImport) 
    - [How it works](#engHowItWorks)
    - [Limitations](#engLimitations)
- [Deutsche Version](#gerVersion)
    - [Einleitung](#gerIntroduction)
    - [Voraussetzungen](#gerRequirements)
    - [Import](#gerImport)
    - [Funktionsweise](#gerHowItWorks)
    - [Limitierungen](#gerLimitations)

---

## English Version <a name="engVersion"></a>

### Introduction <a name="engIntroduction"></a>

The Microsoft Power Platform is a family of products that provides solutions for analysis, automation, and development. One of these solutions is Microsoft Power Automate. With Microsoft Power Automate, processes can be automated by creating flows based on low-code. Flows use connections to other services. These connections provide connectors that enable communication with the other services. Connectors can be divided into triggers and actions. Triggers initiate the execution of a flow. Actions involve concrete, predefined behavior. An example for the previous explanations. The SharePoint Online service is to be used in a flow. For this purpose, the connection to SharePoint Online is set up. Then the triggers and actions of the SharePoint Online connector can be used. Such a trigger can be, for example, the change or creation of a list item in a SharePoint Online list, which triggers the execution of a flow. Such an action can be, for example, the deletion of a list item in a SharePoint Online list.

### Requirements <a name="engRequirements"></a>

The flow needs access to the following connections to use their connectors.

- Connections
    - Office 365 Outlook

### Import <a name="engImport"></a>

1. Open [Microsoft Power Automate](https://emea.flow.microsoft.com/)
2. Select "Import" under "My Flows
3. Update the necessary connections
4. Import
5. Edit the flow to make the necessary adjustments
    1. Adjust the selected calendar
    2. Adjust the selected [time zone](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/default-time-zones?view=windows-11)

### How it works <a name="engHowItWorks"></a>

The flow reads all appointments of the current day from the specified calendar and stores the related information, i.e. title, start time, end time and category. The category must be set manually in advance by creating it for e.g. a specific work package in Outlook. The category consists of a clear name and an ID or designation, these are separated by a hyphen. This is important so that the ID or designation can be successfully filtered out in the flow. Then the information is sent to the booking system via an HTTP request. Since we cannot provide the part of the flow with the booking system, there is the appointment information by mail in the provided flow.

### Limitations <a name="engLimitations"></a>

- Exactly one category must be assigned to an appointment that corresponds to the defaults
    - Defaults
        - A category is structured as follows "Designation -ID/ Designation"
        - If no designation is required " -ID/designation".
        - If a space is inserted between hyphen and ID/designation, this is also present in the converted category in the first place
        - There must not be another hyphen in the designation or the designation, so that it is separated correctly
- When using the flow, all appointments of the current day are read out, no appointments can be excluded in advance
- Parallel appointments can be a problem in the booking system and thus prevent the flow from running successfully
- For all-day appointments, the conversion of time zones fails

---

## Deutsche Version <a name="gerVersion"></a>

### Einleitung <a name="gerIntroduction"></a>

Die Microsoft Power Plattform stellt eine Produktfamilie dar, die Lösungen zur Analyse, Automatisierung, und Entwicklung bietet. Eine dieser Lösungen ist Microsoft Power Automate. Mit Microsoft Power Automate können Prozesse durch die Erstellung von Flows auf Basis von Low-Code automatisiert werden. Flows nutzen Verbindungen zu anderen Diensten. Diese Verbindungen liefern Konnektoren, die die Kommunikation mit den anderen Diensten ermöglichen. Konnektoren können in Trigger und Aktionen unterschieden werden. Trigger lösen die Ausführung eines Flows aus. Aktionen beinhalten konkretes, vordefiniertes Verhalten. Ein Beispiel für die vorangegangenen Erläuterungen. Es soll der Dienst SharePoint Online in einem Flow verwendet werden. Dazu wird die Verbindung zu SharePoint Online eingerichtet. Daraufhin können die Trigger und Aktionen des SharePoint Online Konnektors genutzt werden. Ein solcher Trigger kann zum Beispiel die Änderungen oder Erstellung eines Listenelements in einer SharePoint Online Liste sein, die die Durchführung eines Flows auslöst. Eine solche Aktion kann zum Beispiel das Löschen eines Listenelements in einer SharePoint Online Liste sein.

### Voraussetzungen <a name="gerRequirements"></a>

Der Flow benötigt Zugriff auf folgende Verbindungen.
- Verbindungen
    - Office 365 Outlook

### Import <a name="gerImport"></a>

1. Öffnen von [Microsoft Power Automate](https://emea.flow.microsoft.com/)
2. Auswahl von „Importieren“ unter „Meine Flows“
3. Aktualisierung der notwendigen Verbindungen
4. Importieren
5. Bearbeiten, um notwendige Anpassungen vorzunehmen
    1. Anpassen des ausgewählten Kalenders
    2. Evtl. anpassen der ausgewählten [Zeitzone](https://docs.microsoft.com/de-de/windows-hardware/manufacture/desktop/default-time-zones?view=windows-11)

### Funktionsweise <a name="gerHowItWorks"></a>

Der Flow liest aus dem angegebenen Kalender alle Termine des aktuellen Tages aus und speichert die dazugehörigen Informationen, also Titel, Startzeit, Endzeit und Kategorie. Die Kategorie muss im Voraus manuell gesetzt werden, indem man diese für z.B. ein bestimmtes Arbeitspaket in Outlook erstellt. Die Kategorie besteht aus einer klaren Benennung und einer ID oder Bezeichnung, diese werden durch einen Bindestrich getrennt. Das ist wichtig, damit die ID oder Bezeichnung im Flow erfolgreich herausgefiltert werden können. Dann werden die Informationen über ein HTTP-Request an das Buchungssystem übermittelt. Da wir den Teil des Flows mit dem Buchungssystem nicht bereitstellen können, gibt es in dem bereitgestellten Flow die Termininformationen per Mail.

### Limitierungen <a name="gerLimitations"></a>

- Einem Termin muss **genau eine** Kategorie zugeordnet sein, die den Vorgaben entspricht
    - Vorgaben
        - Eine Kategorie ist wie folgt aufgebaut „Benennung –ID/ Bezeichnung“
        - Wenn keine Benennung benötigt wird „ -ID/Bezeichnung“
        - Wird zwischen Bindestrich und ID/Bezeichnung ein Leerzeichen eingefügt, ist dieses ebenfalls in der konvertierten Kategorie an erster Stelle vorhanden
        - In der Bezeichnung oder der Benennung darf kein weiterer Bindestrich vorkommen, damit es korrekt getrennt wird
- Wenn man den Flow nutzt, werden alle Termine des aktuellen Tages ausgelesen, es können keine Termine im Voraus ausgeschlossen werden
- Paralleltermine können im Buchungssystem ein Problem darstellen und somit den erfolgreichen Flow-Durchlauf verhindern
- Bei ganztägigen Terminen schlägt die Konvertierung der Zeitzonen fehl
