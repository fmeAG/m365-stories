# **README - fme's Microsoft 365 Stories**

## **Flow - Automatic out-of-office notifications**
## **Flow - Automatische Abwesenheitsbenachrichtigungen**

*Yannick Osterloh*

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
    - Office 365 User

### Import <a name="engImport"></a>

1. Open [Microsoft Power Automate](https://emea.flow.microsoft.com/)
2. Select "Import" under "My Flows
3. Update the necessary connections
4. Import
5. Edit the flow to make the necessary adjustments
    1. Adjust the selected calendar
    2. Adjust the selected [time zone](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/default-time-zones?view=windows-11)

### How it works <a name="engHowItWorks"></a>

This Microsoft Power Automate Flow searches the specified calendar for all upcoming appointments marked with out-of-office. From these appointments, it then selects the next one in time and sets an out-of-office notification for it. It runs once an hour every day between 7 am and 5 pm and sets out-of-office notification if not already enabled.

### Limitations <a name="engLimitations"></a>

- Can only be used with Outlook accounts with only one inbox
- Does only consider one calendar
- Does not consider appointment series
- Newly set appointments, but already started in the past, are not considered, even if they are still running
- The user must be assigned to a supervisor

---

## Deutsche Version <a name="gerVersion"></a>

### Einleitung <a name="gerIntroduction"></a>

Die Microsoft Power Platform stellt eine Produktfamilie dar, die Lösungen zur Analyse, Automatisierung, und Entwicklung bietet. Eine dieser Lösungen ist Microsoft Power Automate. Mit Microsoft Power Automate können Prozesse durch die Erstellung von Flows auf Basis von Low-Code automatisiert werden. Flows nutzen Verbindungen zu anderen Diensten. Diese Verbindungen liefern Konnektoren, die die Kommunikation mit den anderen Diensten ermöglichen. Konnektoren können in Trigger und Aktionen unterschieden werden. Trigger lösen die Ausführung eines Flows aus. Aktionen beinhalten konkretes, vordefiniertes Verhalten. Ein Beispiel für die vorangegangenen Erläuterungen. Es soll der Dienst SharePoint Online in einem Flow verwendet werden. Dazu wird die Verbindung zu SharePoint Online eingerichtet. Daraufhin können die Trigger und Aktionen des SharePoint Online Konnektors genutzt werden. Ein solcher Trigger kann zum Beispiel die Änderungen oder Erstellung eines Listenelements in einer SharePoint Online Liste sein, die die Durchführung eines Flows auslöst. Eine solche Aktion kann zum Beispiel das Löschen eines Listenelements in einer SharePoint Online Liste sein.

### Voraussetzungen <a name="gerRequirements"></a>

Der Flow benötigt Zugriff auf folgende Verbindungen.
- Verbindungen
    - Office 365 Outlook
    - Office 365 User


### Import <a name="gerImport"></a>

1. Öffnen von [Microsoft Power Automate](https://emea.flow.microsoft.com/)
2. Auswahl von „Importieren“ unter „Meine Flows“
3. Aktualisierung der notwendigen Verbindungen
4. Importieren
5. Bearbeiten, um notwendige Anpassungen vorzunehmen
    1. Anpassen des ausgewählten Kalenders
    2. Evtl. anpassen der ausgewählten [Zeitzone](https://docs.microsoft.com/de-de/windows-hardware/manufacture/desktop/default-time-zones?view=windows-11)

### Funktionsweise <a name="gerHowItWorks"></a>

Dieser Microsoft Power Automate Flow sucht im angegebenen Kalender alle anstehenden Termine, die mit out-of-office gekennzeichnet sind, heraus. Aus diesen Terminen wählt er dann den zeitlich gesehen nächsten aus und stellt für diesen eine Abwesenheitsbenachrichtigung ein. Er läuft jeden Tag zwischen 7 und 17 Uhr einmal stündlich und stellt, insofern nicht bereits aktiviert, Abwesenheitsbenachrichtigung ein.

### Limitierungen <a name="gerLimitations"></a>

- Nur mit Outlook-Konten mit nur einem Postfach verwendbar
- Berücksichtigt nur einen Kalender
- Berücksichtigt keine Terminserien
- Neu eingestellte Termine, die in der Vergangenheit jedoch bereits gestartet sind, werden, auch wenn sie noch laufen, nicht berücksichtigt
- Der Benutzer muss einem Vorgesetzten zugeordnet sein