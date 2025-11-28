# II. Präsentationsstruktur (20 Minuten)

### 1. Einleitung und Kontext (ca. 2 Minuten)

* **Spannende Einführung:** Telstar 1 als historisches Beispiel für TID-Effekte.
  * 1962: Der erste Kommunikationssatellit startet am 10. Juli von Cape Canaveral aus und ist ein voller Erfolg. Telstar 1 überträgt die ersten Live-Fernsehbilder zwischen den USA und Europa – die Grenzen der Welt schrumpfen. Doch die Euphorie verfliegt schnell. Bereits im Herbst beginnt der 60-Millionen-Dollar-Gigant, Befehle zu ignorieren. Den Ingenieuren im Kontrollzentrum steht der kalte Schweiß auf der Stirn: Was greift die empfindlichen Schaltkreise an? Manchmal muss ein Befehl dreimal wiederholt werden. Trotz verzweifelter, genialer Wiederbelebungsversuche, die den Satelliten kurz reaktivieren, kommt am 21. Februar 1963 das unvermeidliche Ende: Telstar 1 wird für immer stumm. Totalausfall!
  * aber wie kam es dazu? Und damit Wilkommen: (...)
*   **Titel & Übersicht:** Begrüßung und Agenda.

## **Folie 2: Einordnung der Strahlungseffekte**

**Auf der Folie (Stichpunkte/Grafik):**
* Tabelle: **Kumulative Effekte vs. Single Event Effects**

  | Kategorie              | Beispiele            | Zeitverhalten              | Typische Folgen                      |
  |------------------------|----------------------|----------------------------|--------------------------------------|
  | Kumulative Effekte     | **TID**, DDD         | langsam, dosisabhängig     | Parameterverschiebung, Degradation  |
  | Single Event Effects   | SEU, SEL, SEB, SEGR  | Einzelereignisse, spontan | Bitflips, Latchup, Zerstörung       |

* Stichpunkte:
  * **TID/DDD**: Dosis akkumuliert → Bauteil driftet aus Spezifikation
  * **SEE**: Einzelne Partikel → unmittelbare, oft sporadische Fehler
  * Fokus dieser Präsentation: **TID** in MOS- und integrierten Bauteilen

**Sprechertext:**
„Strahlungseffekte in Elektronik lassen sich grob in zwei Klassen einteilen. Erstens die kumulativen Effekte: Total Ionizing Dose und Displacement Damage. Hier zählt die aufsummierte Dosis – Parameter wie die Schwellenspannung verschieben sich langsam, bis das Bauteil nicht mehr innerhalb der Spezifikation arbeitet. Zweitens die Single Event Effects: einzelne Partikel können spontan Bitflips oder sogar destruktive Ereignisse wie Latchup auslösen. Heute konzentrieren wir uns auf die TID, also die kumulative Wirkung der Ionisation, weil genau das der zentrale Ausfallmechanismus bei Telstar 1 war.“

---

## **Folie 3: Strahlungsquellen im Weltraum (Überblick)**

**Auf der Folie (Stichpunkte/Grafik):**
* Diagramm: schematische Erde mit:
  * **innerem/äußerem Van-Allen-Gürtel**
  * **Südatlantischer Anomalie (SAA)**
  * Hinweis auf **solare Ereignisse** und **galaktische kosmische Strahlung (GCR)**
* Stichpunkte:
  * **Quellen:**
    * Sonne: solare Protonenereignisse, solare Teilchenstrahlung
    * **Van-Allen-Gürtel**: gefangene Protonen & Elektronen
    * **GCR**: hochenergetische schwere Ionen (geringer Fluss)
  * Relevanz für TID:
    * **Elektronen & Protonen** → dominanter Beitrag zur TID
    * Photonen/sekundäre Elektronen → ergänzender Beitrag

**Sprechertext:**
„Die Strahlungsumgebung im Orbit wird im Wesentlichen von drei Quellen bestimmt: von der Sonne mit ihren solaren Protonenereignissen, von den Van-Allen-Gürteln mit gefangenen Protonen und Elektronen sowie von der galaktischen kosmischen Strahlung aus dem interstellaren Raum. Für die Total Ionizing Dose sind vor allem Elektronen und Protonen relevant, da sie langfristig Ladung in den Oxiden unserer Bauteile erzeugen. Photonen und sekundäre Elektronen tragen ebenfalls bei, aber die Van-Allen-Gürtel und besonders die Südatlantische Anomalie sind für einen LEO-Satelliten meist die dominanten TID-Quellen.“

---

## **Folie 4: Van-Allen-Gürtel & SAA als TID-Hotspots**

**Auf der Folie (Stichpunkte/Grafik):**
* Karte: Projektion der **Südatlantischen Anomalie** über Südamerika/Atlantik
* Schematische Dichteverteilung:
  * innerer Gürtel: **Protonen-dominant**
  * äußerer Gürtel: **Elektronen-dominant**
* Stichpunkte:
  * SAA: lokaler **Erdmagnetfeld-Einbruch**
  * Erhöhte Flüsse von **MeV-Protonen und -Elektronen**
  * Satelliten in **LEO**: wiederholte Durchflüge → **Dosis akkumuliert**
  * Typisch: TID über Missionsdauer **10–100 krad(Si)** (missionsabhängig)

**Sprechertext:**
„Die Van-Allen-Gürtel sind keine homogene Schicht um die Erde, sondern haben lokale Besonderheiten. Besonders kritisch ist die Südatlantische Anomalie, wo das Magnetfeld geschwächt ist und der innere Protonengürtel viel näher an die Erde heranreicht. Satelliten in niedrigen Orbits durchqueren diese Region regelmäßig, bekommen dabei erhöhte Flußraten von MeV-Protonen und -Elektronen ab und sammeln so über Monate und Jahre eine beträchtliche Totaldosis. Je nach Orbit und Abschirmung liegen wir hier schnell im Bereich von zig krad in Silizium.“

---

## **Folie 5: MOS-Querschnitt & Grundprinzip der Ionisation**

#### **Abbildung (zentral):**

Eine große schematische Querschnittszeichnung eines NMOS:

* Gate-Metall
* Gate-Oxid (SiO₂)
* p-Substrat
* Source/Drain
* Eingezeichnete elektrische Feldlinien im Oxid
* Markierte Orte, wo Elektron-Loch-Paare entstehen
* Elektronen → nach oben abdriftend (schnell, entkommen)
* Löcher → langsam → werden **in Oxid-Defekten gefangen**
* Markierte Oxid-Defekte (E' centers, oxygen vacancy traps)
* Ansammlung positiver Ladung im Oxid („positive oxide trapped charge“)
* Pfeil: „Verschiebt Threshold Voltage nach unten (NMOS)”

#### **Stichpunkte auf der Folie:**

* **Ionisation im Oxid:** Strahlung erzeugt *Elektron-Loch-Paare* in SiO₂ (17 eV pro Paar).
* **Drift im elektrischen Feld:**

  * Elektronen: hohe Mobilität → fliehen schnell → Rekombination gering
  * **Löcher: sehr geringe Mobilität → bleiben im Oxid → werden eingefangen**
* **Defektstellen / Traps:**

  * intrinsische Oxiddefekte (Oxygen Vacancies, E’-Center)
  * entstehen durch Herstellung + werden durch Strahlung aktiviert
  * fangen bevorzugt Löcher → **positive Oxidladung**
* **Folge:**

  * Aufbau einer **persistent positiven Raumladung im Oxid**
  * **Verschiebung der Threshold-Spannung** (NMOS: V_th ↓, PMOS: V_th ↑)
  * Startpunkt der TID-Degradation

#### **Sprechernotizen (ausführlich, aber kompakt):**

„Wir schauen uns den TID-Mechanismus direkt im MOS-Transistor an. Entscheidend ist: Der Schaden spielt sich fast komplett *im Isolator*, also dem Gate-Oxid, ab.
Trifft ionisierende Strahlung das Oxid, entstehen Elektron-Loch-Paare. Elektronen sind sehr beweglich und verschwinden schnell – sie rekombinieren entweder oder werden vom Gate-Metall abgesaugt. Löcher dagegen sind in SiO₂ etwa **10.000-mal weniger mobil** {zitat nötig!} und werden in vorhandenen **Oxiddefektstellen** festgehalten.

Diese Defektstellen entstehen bei der Oxidherstellung – besonders oxygen-vacancy defects, sogenannte **E’-Centers**. Unter Strahlung aktivieren sich diese Zentren zusätzlich.

Dort bleiben Löcher langfristig stecken, teilweise über Jahre. Dadurch bildet sich eine **positive Ladungsschicht im Oxid**, die den Transistor elektrisch umprogrammiert:
Im NMOS bedeutet das, dass sich das elektrische Feld, das zur Kanalbildung nötig ist, leichter aufbauen kann → **der Transistor schaltet zu früh → V_th sinkt**.“

---

## **Folie 5: Gesamtwirkung im MOSFET**

**Abbildung:**
Schematische I-V-Kurven eines nMOS vor und nach TID-Belastung:
* x-Achse: V_GS (Gate-Source-Spannung)
* y-Achse: I_D (Drain-Strom)
* Kurve 1: „Vor TID“ – normale Schwellenspannung, steiler Subthreshold-Bereich
* Kurve 2: „Nach TID“ – verschobene Schwellenspannung (nach links), flacherer Subthreshold-Bereich, höherer Leckstrom

**Stichpunkte auf der Folie:**

* Positive Oxidladung → **V_th sinkt (nMOS)**
* Kanal wird früher leitend
* Mehr Leckstrom
* Bei pMOS ist das Vorzeichen der Effekte oft umgekehrt

**Sprechertext:**
„Wenn wir die I–V-Kennlinien eines nMOS vor und nach einer hohen Totaldosis vergleichen, sehen wir drei Merkmale: Die Schwellenspannung ist nach links verschoben – der Transistor schaltet früher durch. Und der Leckstrom im Sperrbereich ist deutlich erhöht. Bei pMOS-Transistoren ist die Situation qualitativ ähnlich, aber mit umgekehrten Vorzeichen bei der Schwellenspannungsverschiebung.“

---

## **Folie 6: Funktionale Konsequenzen in Schaltungen**

**Auf der Folie (Stichpunkte/Grafik):**
* Schema: Inverter oder einfaches CMOS-Gatter:
  * Vor TID: **saubere Logikpegel**
  * Nach TID: **schlechter Noise-Margin**, verschobene Pegel
* Stichpunkte:
  * V\_th-Drift → **Timing-Änderungen**, langsamere Schaltzeiten
  * Erhöhter Leckstrom → **höherer Ruhestrom**, Wärmeentwicklung
  * Mismatch in **Analogschaltungen**:
    * Offsetspannungen
    * Verstärkungsänderungen
  * Langfristig: **Drift aus Spezifikation**, Funktionsausfall

**Sprechertext:**
„Die beschriebenen Parameteränderungen übersetzen sich auf Schaltungsebene direkt in funktionale Probleme. In digitalen Schaltungen können verschobene Schwellenspannungen und erhöhte Leckströme dazu führen, dass Timing-Margen nicht mehr eingehalten werden oder Ruheströme kritisch ansteigen. In analogen Schaltungen verschieben sich Verstärkungen, Offsets und Rauschverhalten. Über die Lebensdauer hinweg driftet das Bauteil so weit aus der Spezifikation, dass es seine Aufgabe im System nicht mehr zuverlässig erfüllen kann – genau das ist das Wesen des TID-Schadens.“

---

## **Folie 7: TID-Härtungstests und Qualifikationsverfahren (RHA)**

**Auf der Folie (Stichpunkte/Grafik):**
* Stichpunkte:
  * **COTS-Bauteile** meist nicht für Raumstrahlung entwickelt
  * **Radiation Hardness Assurance (RHA)**:
    * Nachweis, dass Bauteile unter Missionsdosis funktionieren
  * TID ist eines der **ersten Screening-Kriterien**
  * Zielgrößen:
    * **ΔV\_th**, Verstärkung, Leckströme
    * Funktionsgrenzen (LOGIC „0/1“, analoge Spezifikationen)
* Grafik:
  * Blockdiagramm: **Missionsanalyse → Dosisabschätzung → TID-Testniveau → Qualifikation**

**Sprechertext:**
„Bevor man ein Bauteil in einen Satelliten baut, muss klar sein, ob es die erwartete Strahlungsumgebung übersteht. Die Radiation Hardness Assurance beschreibt den Prozess, mit dem wir das absichern. TID ist dabei ein sehr grundlegendes Kriterium, weil es nahezu alle Technologien betrifft. Wir schätzen zunächst die Missionsdosis im Orbit ab, legen daraus ein Testdosisniveau mit Sicherheitsmarge fest und überprüfen dann, ob die relevanten elektrischen Parameter und die Funktion des Bauteils innerhalb dieser Dosis im zulässigen Rahmen bleiben.“

---

## **Folie 8: TID-Testquellen & Randbedingungen**

**Auf der Folie (Stichpunkte/Grafik):**
* Stichpunkte:
  * **Strahlungsquellen:**
    * **Co‑60-Gammastrahler** (1.17, 1.33 MeV)
    * **Elektronen** (E ≥ 1 MeV)
  * Gründe für diese Quellen:
    * Hohe **Penetration** → homogene Dosis im Bauteil
    * Geringe **Displacement Damage**-Komponente
  * **Testbedingungen** (nach ESCC 22900 u.Ä.):
    * Raumtemperatur, Bestrahlung in Luft möglich
    * Dosisratenbereich z. B. **36 rad/h – 180 krad/h**
    * **Charged-Particle Equilibrium** sicherstellen
    * Co‑60: Abschirmung ~**1,5 mm Pb + 0,7 mm Al** (Low-E-Tail-Reduktion)

**Sprechertext:**
„In der Praxis nutzt man für TID-Tests vor allem Co‑60-Gammastrahler oder Elektronenquellen mit Energien oberhalb von einem MeV. Diese Strahlung dringt tief genug in das Bauteil ein, um eine annähernd homogene Dosis in den empfindlichen Volumina zu erzeugen, ohne nennenswerte Verlagerungsschäden zu verursachen. Normen wie die ESCC 22900 geben Bereiche für die Dosisrate und konkrete Anforderungen an das Strahlungsfeld vor – zum Beispiel die Notwendigkeit, ein Gleichgewicht geladener Teilchen herzustellen und den niederenergetischen Anteil des Co‑60-Spektrums durch Blei- und Aluminiumabschirmung zu unterdrücken.“

---

## **Folie 9: Dosisrate, ELDRS & Testablauf**

**Auf der Folie (Stichpunkte/Grafik):**
* Stichpunkte:
  * **Dosisrate**:
    * Einfluss auf Defektkinetik und Trapping
    * **ELDRS**: Enhanced Low Dose Rate Sensitivity (v. a. Bipolar/BCD)
  * Typischer **Testablauf**:
    * Bauteil charakterisieren (**Pre-Irradiation**)
    * Bestrahlen in **Dosisinkrementen** (z. B. 10 krad-Schritte)
    * Nach jedem Inkrement: **messung im strahlungsfreien Zustand**
    * Endpunkt: spezifizierte **Qualifikationsdosis** + Margin
* Hinweis:
  * Für TID: **keine kontinuierliche dynamische Überwachung** nötig
  * Fokus auf **parametrische Drift** und Funktionsgrenzen

**Sprechertext:**
„Die Dosisrate ist ein kritischer Parameter im TID-Test, weil sie die zeitliche Dynamik der Defektentstehung und -heilung beeinflusst. Besonders in bipolaren Technologien kennt man den ELDRS-Effekt, bei dem das Bauteil bei niedrigen Dosisraten stärker degradiert als bei hohen. In einem typischen TID-Test vermisst man das Bauteil zunächst vor der Bestrahlung, setzt es dann in mehreren Dosisinkrementen der Strahlung aus und führt zwischen den Inkrementen im strahlungsfreien Zustand Messungen durch. So zeichnet man die parametrierte Drift als Funktion der akkumulierten Dosis nach. Eine kontinuierliche, dynamische Überwachung während der Bestrahlung ist für TID in der Regel nicht notwendig.“

---

## **Folie 10: Kernaussagen & Ausblick**

**Auf der Folie (Stichpunkte/Grafik):**
* Stichpunkte:
  * **TID** = kumulative Ionisationsschäden in Oxiden & Grenzflächen
  * Hauptmechanismus:
    * **Oxid-trapped charge** (positive Raumladung)
  * Folgen:
    * **ΔV\_th**, Mobility-Degradation, **Leckstrom↑**
    * Drift aus Spezifikation bis zum **Funktionsverlust**
  * **RHA/TID-Tests** sind unverzichtbar für Raumfahrt-Elektronik
  * Historische Lehre: **Orbit- & Umweltanalyse kritisch** (Telstar 1)

**Sprechertext:**
„Die Total Ionizing Dose ist kein exotischer Randaspekt, sondern ein zentraler, kumulativer Schädigungsmechanismus in der Raumfahrtelektronik. Sie entsteht durch Ionisation im Gate-Oxid und an der Si–SiO₂-Grenze, führt über Oxid-trapped charge und Interface States zu Schwellenspannungsverschiebungen, Mobilitätsverlust und erhöhten Leckströmen und lässt Bauteile langfristig aus der Spezifikation driften. TID-Tests im Rahmen der Radiation Hardness Assurance sind deshalb ein Muss für jede ernstzunehmende Weltraummission.“

---


*   **Rückführung zur Einleitung:**
    *   ...Und damit wissen wir nun, was damals beim Telstar 1 Satellit passiert ist: 
    *   Die Ursache für das Scheitern war der Kumulative Strahlungsschaden (TID). Hochenergetische Teilchen griffen die empfindlichen Transistoren in den Kommando-Decodern des Satelliten an und zerstörten ihre Funktion.
    *   In den MOS-Bauteilen führte die Ansammlung positiver Oxidladung zu verschobenen Schwellenspannungen und erhöhten Leckströmen. Die Kommando-Schaltungen reagierten immer unzuverlässiger, bis der Satellit praktisch nicht mehr steuerbar war.“

*   **Auflösung:** Atombombentest: Starfish Prime.
    *  Das Drama: Obwohl Telstar 1 robust gegen die natürliche Strahlung der Van-Allen-Gürtel geschützt war, überlebte er die wahre Bedrohung nicht. Am Tag vor dem Start hatte der geheime atomare Test Starfish Prime einen künstlichen, (tödlich) verstärkten Strahlungsgürtel geschaffen, der die Lebensdauer des bahnbrechenden Satelliten abrupt beendete. 

---


## **Q&A**

**Auf der Folie (Stichpunkte/Grafik):**
  * **Fragen?**
  * Mögliche Diskussionspunkte:
    * Unterschiede **TID vs. DDD vs. SEE**
    * **Mitigation**: RadHard-by-Design, Shielding, Technologieauswahl
    * Bezug zu **aktuellen Missionen** / **COTS im All**

**Sprechertext:**
„Damit bin ich am Ende der inhaltlichen Präsentation und freue mich auf Ihre Fragen. Wir können gern noch vertiefen, wie sich TID von anderen Strahlungseffekten abgrenzt, welche Design- und Technologie-Strategien es zur Härtung gibt oder wie moderne Missionen mit dem Einsatz von COTS-Bauteilen im All umgehen.“
