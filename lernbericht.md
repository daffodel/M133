# Lern-Bericht
Delia Reho

## Einleitung

Bei diesem Projekt musste man mit JSF eine Sitzungsverfolgung realisieren.

## Was habe ich gelernt?

1. Ich habe gelernt neue JSP-Tags anzuwenden.
2. Ich habe gelernt Inputs auf einer Seite zu speichern und dann auf einer anderen Seite zu zeigen.

## Beschreibung
Da ich keine Erfahrung habe mit JSP waren mir alle Tags neu, obwohl sie Ähnlichkeiten haben mit HTML-Tags. Im Java Teil des Projektes habe ich den Nachnamen unter helloManagedBean.nachname gespeichert und das Gleiche mit dem Vornamen, einfach mit helloManagedBean.vorname. Um alles zusammen zu haben, habe ich die sessionID auch im helloManagedBean konfiguriert und dann als hellomanagedBean.sessionID gespeichert. Bei jeder jeweiligen Seite habe ich es dann mit #{helloManagedBean.[vorname/nachname/sessionID]} angezeigt.

Link zu einer selbstaufgenommener Bildschirm-Aufname der Webseite:
https://youtu.be/8tDkyfblEGA

Code-Ausschnitt bei dem ich JSF Tags verwendet habe: 

    <h:head>
        <title>Sitzung: Schritt 1</title>
    </h:head>
    <h:body>
        <h1>Sitzungsverfolgung Schritt 1</h1><br></br>
        <h:outputLabel value="Ihre Sitzung wurde verfolgt: #{helloManagedBean.sessionID}"/>
        <h:form>
            <h:outputLabel value="Ihr Nachname: "/>
            <h:inputText value="#{helloManagedBean.nachname}" id="nachname"/>
            <h:commandButton value="Submit Query" action="#{helloController.nachnameWL}"/>
        </h:form>
    </h:body>

Code Ausschnitt bei dem ich die Eingaben des Nutzers gespeichert habe:

    /* nachname */
    public String getNachname() {
        return nachname;
    }

    public void setNachname(String nachname) {
        this.nachname = nachname;
    }
    
    /* vorname */
    public String getVorname(){
        return vorname;
    }
    
    public void setVorname(String vorname){
        this.vorname = vorname;
    }
    
    /* sessionID */
    public String getSessionID(){
        return sessionID;
    }

## Verifikation

In der Bildschirm-Aufnahme erkennt man, dass die Webseite, das macht, was sie sollte.
In den Code-Ausschnitte sieht man, wie ich es zum funktionieren gebracht habe.

# Reflektion zum Arbeitsprozess

Die Speicherung des Vornamens und des Nachnames verlief einwandfrei und mit diesem Teil des Auftrages war ich sehr schnell fertig.
Der Teil mit der SessionID konnte ich nicht selber lösen und musste warten bis es erklärt wurde bis ich es lösen konnte.
Leider funktioniert es immernoch nicht, dass die SessionID bei jeder SessionID die Gleiche ist.

**VBV**: Ich werde mich über @RequestScoped, @SessionScoped und @ApplicationScoped weiter informieren damit ich so eine Auftrag selbst lösen kann.
