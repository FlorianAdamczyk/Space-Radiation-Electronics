# II. Präsentationsstruktur (20 Minuten)

### 1. Einleitung und Kontext (ca. 2 Minuten)

* **Spannende Einführung:** Telstar 1 als historisches Beispiel für TID-Effekte.
  * 1962: Der erste Kommunikationssatellit startet am 10. Juli von Cape Canaveral aus und ist ein voller Erfolg. Telstar 1 überträgt die ersten Live-Fernsehbilder zwischen den USA und Europa – die Grenzen der Welt schrumpfen. Doch die Euphorie verfliegt schnell. Bereits im Herbst beginnt der 60-Millionen-Dollar-Gigant, Befehle zu ignorieren. Den Ingenieuren im Kontrollzentrum steht der kalte Schweiß auf der Stirn: Was greift die empfindlichen Schaltkreise an? Manchmal muss ein Befehl dreimal wiederholt werden. Trotz verzweifelter, genialer Wiederbelebungsversuche, die den Satelliten kurz reaktivieren, kommt am 21. Februar 1963 das unvermeidliche Ende: Telstar 1 wird für immer stumm. Totalausfall!
  * aber wie kam es dazu? Und damit Wilkommen: (...)
*   **Titel & Übersicht:** Begrüßung und Agenda.

*   **Klassifikation der Strahlungseffekte:** Unterscheidung zwischen **kumulativen Effekten** (TID/DDD, langfristig, leistungsmindernd) und **Single Event Effects (SEE)** (spontan, nicht-zerstörerisch/zerstörerisch).
*   **Fokus:** Klarstellung, dass die Präsentation die kumulativen TID-Effekte detailliert behandeln wird.

### 2. Die Weltraum-Strahlenumgebung als TID-Quelle (ca. 3 Minuten)

*   **Quellen ionisierender Strahlung:** Kurze Nennung der Hauptquellen (Sonne, GCR, Trapped Particles).
*   **Relevanz für TID:** Konzentrieren Sie sich darauf, warum die Umgebung TID-relevant ist.
    *   Protonen und Elektronen (dominante leichte Partikel) stammen hauptsächlich aus dem Sonnenwind und den Van-Allen-Gürteln (innere/äußere Gürtel).
    *   **Betonung:** Die Umgebung (insbesondere die Van-Allen-Gürtel und die Südatlantische Anomalie SAA) ist durch leichte Teilchen (Protonen, Elektronen) gekennzeichnet, welche primär das Problem der Gesamtionisationsdosis (TID) aufwerfen.


### **3. Der TID-Mechanismus im MOS-Transistor – vom Strahlungstreffer zur Ladungsakkumulation**

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

### **3.5 Interface States – die zweite zentrale TID-Komponente** 
**(optional)**

#### **Abbildung:**

Detailzoom der Si–SiO₂-Grenzfläche:

* Grenzfläche mit kleinen „Knoten“ oder „dangling bonds“
* Beschriftung: „Pb-Zentren (Pb0, Pb1)“
* Ladung kann je nach Gate-Bias positiv / negativ / neutral sein
* Pfeile:

  * „erhöhte Rekombination“
  * „Mobility Degradation“
  * „Subthreshold Slope schlechter“


#### **Stichpunkte auf der Folie:**

* **Erzeugung von Interface States (Pb-Zentren) an der Si–SiO₂-Grenze**

  * durch strahlungsinduzierte chemische Umstrukturierung
  * wirken als energienahe Traps → können Elektronen ODER Löcher fangen
* **Bias-Anhängigkeit:**

  * positive, negative oder neutrale Ladungszustände je nach Gate-Spannung
* **Elektrische Auswirkungen:**

  * verschlechtern die Beweglichkeit im Kanal (mobility degradation)
  * erhöhen den Subthreshold Slope
  * verstärken Leckströme
  * führen zu zusätzlicher V_th-Verschiebung (oft in Gegenrichtung zu Oxidladung)
* **Gesamtergebnis:**

  * langfristige, kumulative Degradation
  * Funktionsgrenzen verschieben sich → **Bauteil driftet aus Spezifikation**


#### **Sprechernotizen:**

„Neben der Oxidladung gibt es einen zweiten wichtigen Effekt: *Interface States*. Diese entstehen genau an der Grenze zwischen Silizium und Siliziumdioxid. Strahlung bricht dort Si–H-Bindungen auf und erzeugt sogenannte **Pb-Zentren** – das sind ungesättigte Siliziumbindungen.

Diese Zentren können Elektronen oder Löcher einfangen, abhängig von der Gate-Spannung. Dadurch beeinflussen sie die Kanalqualität direkt: Sie verschlechtern die Beweglichkeit der Ladungsträger, erhöhen die Subthreshold Steilheit und fügen der Threshold-Spannung eine weitere, biasabhängige Verschiebung hinzu.

Das Besondere: Interface Traps wirken oft **entgegengesetzt zur Oxidladung**. Bei NMOS etwa kann Oxidladung V_th stark nach unten verschieben, während Interface-Traps etwas davon wieder nach oben drücken.

Beide Effekte kumulieren über die Lebensdauer, und am Ende driftet das Gerät aus der Spezifikation – das ist im Kern die Total Ionizing Dose (TID).“

---


### **4. Gesamtwirkung im MOSFET**

**Abbildung:**
Schematische I-V-Kurven eines nMOS vor und nach TID-Belastung:
* x-Achse: V_GS (Gate-Source-Spannung)
* y-Achse: I_D (Drain-Strom)
* Kurve 1: „Vor TID“ – normale Schwellenspannung, steiler Subthreshold-Bereich
* Kurve 2: „Nach TID“ – verschobene Schwellenspannung (nach links), flacherer Subthreshold-Bereich, höherer Leckstrom

**Stichpunkte auf der Folie:**

* Positive Oxidladung → **V_th sinkt (nMOS)**
* (Interface-States → Subthreshold-Slope verschlechtert)
* Kanal wird früher leitend
* Mehr Leckstrom
* Bei pMOS ist das Vorzeichen der Effekte oft umgekehrt

**Sprechernotizen:**
„In einem n-MOSFET führen positive Ladungen im Oxid dazu, dass das Gate weniger Spannung braucht, um den Kanal in Leitfähigkeit zu versetzen. Die Schwellenspannung sinkt. Der Transistor leitet also zu früh – oder schaltet nicht mehr richtig aus.
(Zusätzlich stören Interface-States den Subthreshold-Bereich und erhöhen Leckströme.)
Bei pMOS-Bauteilen ist das Vorzeichen oft umgekehrt.
Das Endergebnis: der Transistor verhält sich immer weniger so, wie er ursprünglich designed wurde – bis das Bauteil nicht mehr zuverlässig ist.“


### 5. TID-Härtungstests und Qualifikationsverfahren (RHA) (ca. 4 Minuten)

*   **RHA-Notwendigkeit:** Erklären Sie, dass COTS (Commercial-Off-the-Shelf)-Geräte getestet werden müssen, wenn sie nicht von vornherein strahlengehärtet (RadHard) sind.
*   **Testmethodik:**
    *   **Quellenwahl:** Tests mit Gammastrahlen (Co-60) oder Elektronen (mind. 1 MeV) aufgrund ihrer hohen Penetration und geringen Verlagerungsschäden.
    *   **Dosisrate und ELDRS:** Erläutern Sie die Notwendigkeit, Dosisraten zu kontrollieren (36 rad/h bis 180 krad/h) und die Enhanced Low Dose Rate Sensitivity (ELDRS) zu berücksichtigen.
    *   **Testumgebung:** Notwendigkeit des Charged-Particle Equilibrium und spezielle Abschirmung bei Co-60-Quellen zur Minderung des Niedrigenergie-Spektrums.
    *   **Durchführung:** TID-Tests erfordern keine kontinuierliche Überwachung während der Bestrahlung.

### 6. Fazit und Q&A (ca. 2 Minuten)

*   **Rückführung zur Einleitung:** Aufgreifen des Beispiels von Telstar 1:
    *   ...Und damit, wissen wir nun, was damals beim Telstar 1 Satellit passiert ist: 
*   **Erklärung, warum ist Telstar 1 ausgefallen:** Zusammenfassung der wichtigsten Erkenntnisse über TID-Effekte, ihre Mechanismen, Auswirkungen und Testverfahren.
    *   Die Ursache für das Scheitern war der sogenannte Kumulative Strahlungsschaden (TID). Hochenergetische Partikel griffen die empfindlichen Transistoren in den Kommando-Decodern des Satelliten an und zerstörten ihre Funktion.

*   **Auflösung:** Atombombentest: Starfish Prime.
    *  Das Drama: Obwohl Telstar 1 robust gegen die natürliche Strahlung der Van-Allen-Gürtel geschützt war, überlebte er die wahre Bedrohung nicht. Am Tag vor dem Start hatte der atomare Test Starfish Prime einen künstlichen, tödlich verstärkten Strahlungsgürtel geschaffen, der die Lebensdauer des bahnbrechenden Satelliten abrupt beendete.   
