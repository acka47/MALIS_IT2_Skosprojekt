#Projektbericht

##Usecase

<p>Das Nationalmuseum für Archäologie, Geschichte und Kunst (MNAHA) verwendet in seiner Sammlungsmanagementsoftware Museum Plus eine Vielzahl von Vokabularen. Als 2018 eine neue Datenbank eingeführt wurde, entschied man sich die bis dahin vorhandenen Freitextfelder, die zur Beschreibung der Objekte verwendet wurden, größtenteils durch Felder auf Basis von normierten Vokabularen zu ersetzen. Die Vokabulare des [Service des Musées de France](https://www.culture.gouv.fr/Thematiques/Musees/Pour-les-professionnels/Conserver-et-gerer-les-collections/Informatiser-les-collections-d-un-musee-de-France/Vocabulaires-scientifiques-du-Service-des-musees-de-France/Telecharger-les-vocabulaires-scientifiques-du-Service-des-musees-de-France] wurden als Basis genommen. Seither wurden sie am MNAHA weiterentwickelt und an die lokalen/nationalen Bedürfnisse angepasst. Im Kontext der Open-data Politik des Staates sollen die luxemburgischen Versionen der Vokabulare in Zukunft als Linked open data publiziert werden.</p>

<p>Dieses Projekt war eine ideale Gelegenheit erste Erfahrungen mit der Publikation von Vokabularen in Form von Linked open data zu sammeln und notwendige nächste Schritte zu definieren. Das hier ausgewählte Vokabular, Rollen, eignet sich gut dafür die Möglichkeiten von SKOS kennenzulernen ohne dabei den Rahmen dessen zu sprengen, was manuell möglich ist. Es handelt sich um einen mehrsprachigen Thesaurus - Mehrsprachigkeit ist in Luxemburg üblich - mit vielen Überschneidungen mit anderen Vokabularen, inklusive, natürlich, dem des Service des Musées de France.</p>

##Zusammenarbeit auf Github - Wie hat es funktioniert? Was wurde gelernt? Wo sind noch Probleme?
<p>Die Zusammenarbeit auf Github lief ohne Probleme. Im Projektteam waren unterschiedliche Vorkenntnisse vorhanden, dennoch gelang der Einstieg und die ersten Schritte in Github allen Beteiligten. Für die Kommunikation wurde zoom sowie ein Messenger genutzt. Ein Kanban-Board kam nicht zum Einsatz. Die Grundfunktionen von Github wurden in den notwenigen Schritten des Projekts durchgeführt und erlernt: Benutzerkonto einrichten, Forken des Repos, Einladen und Hinzufügen von Teammitgliedern zum Projekt, Arbeit im Projekt, Speichern des Arbeitsfortschritts, Veröffentlichung der Ergebnisse.</p>

<p>##Probleme beim Einrichten des Repos? (Wie kann die Dokumentation verbessert werden?</p>

<p>##Verständnis von RDF und SKOS vor und nach der Bearbeitung?<p>
<p>Vor Bearbeitung der Aufgabe nur wenig Kenntnisse im Bereich Linked open data, Kenntnisse von RDF und SKOS waren nicht vorhanden. Durch die Umsetzung des SKOS-Vokabulars wurde ein Grundverständnis für linked open data und den Nutzen kontrollierter Vokabulare für die Auffindbarkeit und Verbindung von Daten erlangt. Die praktische Anwendung ermöglichte eine intensive Auseinandersetzung mit dem Aufbau und den Anwendungsgebieten von RDF und SKOS.</p>

<p>##Was wird durch die SKOS-Repräsentation des Vokabulars und seiner Publikation im Web gewonnen?</p>

<p>Das ausgewählte Vokabular soll dazu dienen die Rollen von Personen im Zusammenhang mit einem Objekt zu beschreiben. Die Rollenbezeichnungen sind in drei Sprachen angegeben: Französisch, Deutsch und Englisch. Genutzt wird das Vokabular für eine Museumsdatenbank in welcher alle luxemburgischen Museen zusammengeschlossen sind. Durch die Zuordnung von Wiki Data Nummern ist eine eindeutige Identifikation sowohl in menschlesbarer als auch maschinenlesbarer Form vorhanden. Bei Aktualisierung der Wiki Data Datensätze wird zudem auch das Vokabular aktuell gehalten.</p>

<p>##Welche Anwendungsfälle gibt es?</p>

<p>Im Verlauf des Projektes traten zwei Themen in den Vordergrund: **Lösungen für eine geschlechtergerechte Gestaltung des Vokabulars** sowie die **Einbindung von mit übersetzbaren Begriffen**. <p>
<p>Die geschlechtergerechte Gestaltung von Prozessen ist ein Ziel der EU und soll durchgehend Anwendung finden. Während die geschlechtergerechte Sprache im Englischen kein Thema ist, wird es sowohl für Deutsch als auch für Französisch teilweise sehr kontrovers diskutiert. Während in Frankreich das schriftliche Gendern nicht erlaubt ist, wird es in Deutschland von der Regierung befürwortet und in Behörden etc. gebraucht. Das Gendern von Informationen, vor allem strukturierter Vokabulare wird ebenfalls diskutiert. Aktuell ist die weibliche oder genderneutrale Form in der Regel der männlichen Form untergeordnet bzw. beigeordnet z.B. über „also known as“ bei wikidata. Im Projekt bearbeiteten Vokabular wurde die gegenderte Form mit Sternchen als String eingebunden. Eine mögliche Lösung, welche die Gleichwertigkeit von Bezeichnungen schon innerhalb des Vokabulars ausdrückt, wäre eine einzelne Aufführung aller Formen mit einem zusätzlichen Tagging, welches das Geschlecht benennt.</p> 
<p>Beispiel:</p>

<p><Role/172141>
    a skos:Concept ;
    skos:inScheme <Role> ;
    skos:broader <Role172415> ;
    skos:prefLabel
        "Dessinateur"@fr,@mask
        "Dessinateurice"@fr,@fem
        "Zeichner"@de,@mask
        "Zeichnerin"@de,@fem
        "Draughtsperson"@en ;
    skos:closeMatch wikidata:<Q15296811> .</p>

<p>Eine neutrale Variante wäre hier ebenfalls denkbar. 
Eine solche Lösung würde zwar einen größeren Aufwand bedeuten, dafür aber auch bessere Suchmöglichkeiten bieten, da auch weibliche Formen ohne Umweg gefunden werden. Ein Vorteil, wenn davon ausgegangen wird, dass in Zukunft auch die weiblichen Formen häufiger gesucht werden.
Eine solche Änderungen in der Struktur müssten aber für alle Nutzenden beschlossen werden, da über die Vernetzung der Vokabulare einer einheitlichen Struktur folgen müssen, um Interoperabilität zu gewährleisten. Durch die sehr unterschiedlichen Ansätze in Umgang mit weiblichen, männlichen und geschlechtsneutralen Begriffen in Deutschland, Frankreich und England, ist eine solche Lösung zeitnah nicht zu erwarten. Der Diskurs zur geschlechtergerechten Sprache, ihre Möglichkeiten und Grenzen, ist noch lange nicht abgeschlossen und wird auch Auswirkungen auf die Gestaltung von datenbasierten Prozessen nehmen.</p>


