# Projektbericht

## Usecase

<p>Das Nationalmuseum für Archäologie, Geschichte und Kunst (MNAHA) verwendet in seiner Sammlungsmanagementsoftware Museum Plus eine Vielzahl von Vokabularen. Als 2018 eine neue Datenbank eingeführt wurde, entschied man sich die bis dahin vorhandenen Freitextfelder, die zur Beschreibung der Objekte verwendet wurden, größtenteils durch Felder auf Basis von normierten Vokabularen zu ersetzen. Die Vokabulare des [Service des Musées de France](https://www.culture.gouv.fr/Thematiques/Musees/Pour-les-professionnels/Conserver-et-gerer-les-collections/Informatiser-les-collections-d-un-musee-de-France/Vocabulaires-scientifiques-du-Service-des-musees-de-France/Telecharger-les-vocabulaires-scientifiques-du-Service-des-musees-de-France) wurden als Basis genommen. Seither wurden sie am MNAHA weiterentwickelt und an die lokalen/nationalen Bedürfnisse angepasst. Dies bedeutet, dass die Begriffe auf Deutsch und Englisch übersetzt wurden, weitere Begriffe hinzgefügt wurden und die Thesaurusstruktur z.T. verfeinert wurde. Im Kontext der Open-data Politik des Staates sollen die luxemburgischen Versionen der Vokabulare in Zukunft als Linked open data publiziert werden.</p>

<p>Dieses Projekt war eine ideale Gelegenheit erste Erfahrungen mit der Publikation von Vokabularen in Form von Linked open data zu sammeln und notwendige nächste Schritte zu definieren. Das hier ausgewählte Vokabular, Rollen, eignet sich gut dafür die Möglichkeiten von SKOS kennenzulernen ohne dabei den Rahmen dessen zu sprengen, was manuell möglich ist. Es handelt sich um einen mehrsprachigen Thesaurus - Mehrsprachigkeit ist in Luxemburg üblich - mit vielen Überschneidungen mit anderen Vokabularen, inklusive, natürlich, dem des Service des Musées de France.</p>

## Zusammenarbeit auf Github - Wie hat es funktioniert? Was wurde gelernt? Wo sind noch Probleme?
<p>Die Zusammenarbeit auf Github lief ohne Probleme. Im Projektteam waren unterschiedliche Vorkenntnisse vorhanden, dennoch gelang der Einstieg und die ersten Schritte in Github allen Beteiligten. Für die Kommunikation wurde Zoom sowie ein Messenger genutzt. Ein Kanban-Board kam nicht zum Einsatz. Die Grundfunktionen von Github wurden in den notwenigen Schritten des Projekts durchgeführt und erlernt: Benutzerkonto einrichten, Forken des Repos, Einladen und Hinzufügen von Teammitgliedern zum Projekt, Arbeit im Projekt, Speichern des Arbeitsfortschritts, Veröffentlichung der Ergebnisse.</p>

## Probleme beim Einrichten des Repos? (Wie kann die Dokumentation verbessert werden?)
<p>Das Einrichten eines Projektrepos gelang ohne Probleme. Unsicherheiten konnten durch das Schauen verschiedener Youtubevideos, oder durch einfaches Probieren geklärt werden. Das Forken des scohub-docker-vocabs Repos war ebenfalls mit Hilfe der bereitgestellten Folien und des Walktrhoughvideos leicht zu bewältigen. Allerdings war bei diesem Schritt unklar, wie man beide Repositorien zusammenführen sollte, oder ob sogar vorgesehen war, dass das Projektrepositorium innerhalb des geforkten Repositoriums eingerichtet werden sollte.</p>
<p>Da dies für die Projektteammitglieder das erste selbst erstellte Repositorium auf Github ist, gab es keine konkrete Vorstellung davon, was hierbei "best practice" ist. Auch eine ausführlichere Erklärung dessen, was die unterschiedlichen Elemente des geforkten scohub Repos sind und wie sie funktionieren - z.B. Workflows, wäre hilf- und lehrreich gewesen.</p>
<p>Nachdem die Vokabulardatei in das geforkte Repo kopiert wurde war insbesondere der Schritt der Validierung eine Überraschung, wenn auch sinnvoll. Nur einem Gruppenmitglied war RDF Validierung bisher bekannt, allerdings nur mit [Shex](https://shex.io/). So war es leider sehr mühsam und zeitaufwendig alle Fehler im Dokument zu finden und zu beheben. Hier eine etwas detailliertere Darstellung dieses Prozesses, die zur eventuellen Verbesserung der Dokumentation beitragen soll.</p>
<p>1. **Der Dateiname.** Bei den ersten Validierungsversuchen wurde das Dokument nicht erkannt. Wie eine Interpretation der Fehlermeldung schliesslich ergab lag dies an den Leerzeichen in dem Dateinamen, welche es dem Skript unmöglich machten die Datei zu erkennen. Ein Hinweis darauf, dass keine Leerzeichen im Dateinamen genutzt werden sollten wäre hier hilfreich gewesen. Die Lektion, warum es allgemein keine gute Praxis ist Leerzeichen in Dateinamen zu verwenden wurde jedenfalls gelernt.</p>
<p>2. **Prefixe wurden nicht erkannt.** Wie in Turtle vorgesehen wurden am Beginn des Dokuments eine Reihe von Präfixen definiert, darunter joconde und wikidata:</p>
<p>
> @prefix joconde: http://data.culture.fr/thesaurus/resource/ark:/ .
</p>
<p>
> @prefix wikidata: https://www.wikidata.org/wiki/ .
</p>
<p>Bei der Validierung wurde jedoch die Angabe: </p>
<p>
> skos:exactMatch joconde:<67717/?idc=T513-35707&idt=th80> ;
</p>
<p> nicht als valide erkannt. Die Fehlermeldung beklagte das Fehlen eines Punktes als Ende des Tripels. Die Syntax war aber korrekt. Schlussendlich konnte diese Meldung nur umgangen werden, indem jeweils die komplette URL angegeben wurde. Leider konnten wir nicht herausfinden, warum dies so ist.</p>
<p> 3. **Schreibrechte für github-actions.** Nachdem das Dokument an sich valide war scheiterte die Publikation schliesslich noch daran, dass bei den Einstellungen des Workflows nicht alle notwendigen Schreibrechte gegeben waren. Diese waren notwendig um dem im Skript verwendeten Bot zu erlauben die github Seite zu verändern. Ein Hinweis dazu, was zu tun ist, wenn diese Fehlermeldung angezeigt wird wäre hier hilfreich. Möglicherweise könnte man dies auch in einer ausführlicheren Erklärung der Workflows und wie sie funktionieren integrieren. </p>

## Verständnis von RDF und SKOS vor und nach der Bearbeitung?
<p>Vor Bearbeitung der Aufgabe gab es in der Gruppe nur wenig Kenntnisse im Bereich Linked open data, Kenntnisse von RDF und SKOS waren nur in Theorie vorhanden. Durch die Umsetzung des SKOS-Vokabulars wurde ein Grundverständnis für Linked open data und den Nutzen kontrollierter Vokabulare für die Auffindbarkeit und Verbindung von Daten erlangt. Die praktische Anwendung ermöglichte eine intensive Auseinandersetzung mit dem Aufbau und den Anwendungsgebieten von RDF und SKOS.</p>

## Was wird durch die SKOS-Repräsentation des Vokabulars und seiner Publikation im Web gewonnen?

<p>Das ausgewählte Vokabular soll dazu dienen die Rollen von Personen im Zusammenhang mit einem Objekt zu beschreiben. Die Rollenbezeichnungen sind in drei Sprachen angegeben: Französisch, Deutsch und Englisch. Ein erster Mehrwert ist die konsequente Dreisprachigkeit, was für bestehende Vokabulare wie Joconde möglicherweise nachnutzbar ist. Die Bemühung für alle Terme "closeMatch" und "exactMatch" Angaben zu machen und damit Verlinkungen zu/Verknüpfungen mit anderen Vokabularen zu ermöglichen ist ein weiterer Gewinn. Schliesslich ist nicht zu vergessen, dass die Vokabulare nicht allein stehen, sondern für die Beschreibung von musealen Objekten nützlich sind. Ihre Veröffentlichung macht sie einerseits anderen Museen zugänglich, andererseits trägt sie auch dazu bei, dass die komplette Objektbeschreibung in Linked open data ermöglicht wird und diese so in weitere "Knowledgegraphen" eingefügt werden können.</p>

## Welche Anwendungsfälle gibt es?

<p>Im Verlauf des Projektes traten zwei Themen in den Vordergrund: **Lösungen für eine geschlechtergerechte Gestaltung des Vokabulars** sowie die **Einbindung von nicht übersetzbaren Begriffen**. <p>
<p>Die geschlechtergerechte Gestaltung von Prozessen ist ein Ziel der EU und soll durchgehend Anwendung finden. Während die geschlechtergerechte Sprache im Englischen kein Thema ist, wird es sowohl für Deutsch als auch für Französisch teilweise sehr kontrovers diskutiert. Während in Frankreich das schriftliche Gendern nicht erlaubt ist, wird es in Deutschland von der Regierung befürwortet und in Behörden etc. gebraucht. Das Gendern von Informationen, vor allem strukturierter Vokabulare wird ebenfalls diskutiert. Aktuell ist die weibliche oder genderneutrale Form in der Regel der männlichen Form untergeordnet bzw. beigeordnet z.B. über „also known as“ bei Wikidata. Im Projekt bearbeiteten Vokabular wurde die gegenderte Form mit Sternchen als String eingebunden. Eine mögliche Lösung, welche die Gleichwertigkeit von Bezeichnungen schon innerhalb des Vokabulars ausdrückt, wäre eine einzelne Aufführung aller Formen mit einem zusätzlichen Tagging, welches das Geschlecht benennt.</p> 
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
Eine solche Lösung würde zwar einen größeren Aufwand bedeuten, dafür aber auch bessere Suchmöglichkeiten bieten, da auch weibliche Formen ohne Umweg gefunden werden könnten. Ein Vorteil, wenn davon ausgegangen wird, dass in Zukunft auch die weiblichen Formen häufiger gesucht werden.
Solche Änderungen in der Struktur müssten aber für alle Nutzenden beschlossen werden, da über die Vernetzung der Vokabulare eine einheitliche Struktur gegeben sein muss, um Interoperabilität zu gewährleisten. Durch die sehr unterschiedlichen Ansätze in Umgang mit weiblichen, männlichen und geschlechtsneutralen Begriffen in Deutschland, Frankreich und England, ist eine solche Lösung zeitnah nicht zu erwarten. Der Diskurs zur geschlechtergerechten Sprache, ihre Möglichkeiten und Grenzen, ist noch lange nicht abgeschlossen und wird auch Auswirkungen auf die Gestaltung von datenbasierten Prozessen nehmen.</p>


