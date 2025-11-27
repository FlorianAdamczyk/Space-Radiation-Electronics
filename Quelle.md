# I. Zusammenfassung der TID-Effekte basierend auf den Quellen

Die Total Ionizing Dose (TID) fällt unter die Kategorie der **kumulativen Effekte**, welche durch die akkumulierte Exposition gegenüber ionisierender Strahlung verursacht werden und zu einer allmählichen Degradation der Elektronik führen.

### 1. Physischer Mechanismus und Definition
Kumulative Effekte führen zu einer Leistungsverschlechterung, wie erhöhten Leckströmen, die letztendlich zum vollständigen Funktionsverlust des Bauteils führen können.

*   **TID vs. DDD:** Die kumulativen Effekte unterteilen sich in die Total Ionizing Dose (TID) und die Displacement Damage Dose (DDD). Die TID-Effekte werden durch die ionisierenden Komponenten der Strahlung bestimmt.
*   **Ionisationsprozess:** Der dominanteste Effekt in der Elektronik ist die Erzeugung von Elektron-Loch-Paaren (e–h) durch die Energiedeposition ionisierender Strahlung (Photonen oder Partikel).
    *   Die durchschnittlichen Energien, die zur Erzeugung eines e–h-Paares erforderlich sind, betragen 3,6 eV in Silizium (Si) und 17 ± 1 eV in Siliziumdioxid ($\text{SiO}_2$).
    *   TID-Effekte treten auf, wenn die Dichte der induzierten e–h-Paare die intrinsische Dichte freier Elektronen des Zielmaterials übersteigt und ein elektrisches Feld vorhanden ist, um die überschüssigen Ladungsträger zu sammeln.
*   **Ladungsfalle:** TID-Effekte werden durch jene strahlungsinduzierten Ladungsträger gesteuert, die der Rekombination entgehen und nicht durch elektrische Felder abgeführt werden. Da die Elektronenmobilität, insbesondere in Dielektrika, höher ist als die von Löchern, sind es typischerweise die Löcher, die eingefangen (trapped) werden. Dieser Effekt ist in Dielektrika stärker ausgeprägt als in Halbleitern. Im Falle von an der Grenzfläche eingefangener Ladung befindet sich diese jedoch auf der Halbleiterseite der Dielektrikum-Halbleiter-Grenzfläche.

### 2. Auswirkungen auf elektronische Bauteile
Die TID-Effekte äußern sich in graduellen Veränderungen der charakteristischen Eigenschaften der Elektronik:

*   **Schadensbilder:** Dazu gehören die Verschiebung der Schwellenspannung (threshold voltage shifts) und die Abnahme der Lebensdauer der Minoritätsladungsträger (decrease in the minority carrier lifetimes).
*   **Betroffene Technologien:** TID-Effekte können sowohl in Metall-Oxid-Halbleiter (MOS)-Bauteilen als auch in bipolaren Bauteilen auftreten.
*   **Kontext:** Da der Weltraum-Strahlungsraum von leichten Partikeln (Protonen und Elektronen) dominiert wird, ist die Gesamtionisationsdosis (TID) eines der ersten zu berücksichtigenden Probleme.

### 3. TID-Tests und Qualifikation (RHA)
Die Überprüfung der Strahlungshärte (Radiation Hardness Assurance, RHA) ist entscheidend für Komponenten, die in rauen Umgebungen eingesetzt werden.

*   **Testquellen:** TID-Tests werden generell mit Elektronen oder Gammastrahlen durchgeführt.
    *   Die ESA ESCC Basic Specification No. 22900 empfiehlt Kobalt-60-Gammastrahlen (Photonenenergien bei 1.17 MeV und 1.33 MeV) oder Elektronenbestrahlung im Dauerbetrieb bei einer Energie von mindestens 1 MeV am empfindlichen Volumen.
    *   Diese Partikel und Energien werden bevorzugt, da sie eine hohe Penetrationstiefe aufweisen und keine signifikanten Verlagerungsschäden (Displacement Damage) verursachen.
*   **Testparameter:**
    *   Die Dosisrate kann angepasst werden. ESCC-Spezifikationen erlauben einen Bereich von 36 rad/h bis 180 krad/h.
    *   Wichtig ist die Berücksichtigung der **Enhanced Low Dose Rate Sensitivity (ELDRS)** des zu testenden Bauteils bei der Wahl der Dosisrate.
    *   Die Bestrahlung muss bei Raumtemperatur und kann in Luft durchgeführt werden.
*   **Testdurchführung:** Im Gegensatz zu dynamischen Tests für Single Event Effects (SEE) ist für TID-Tests keine kontinuierliche Überwachung des Bauteils während der Bestrahlungsphase erforderlich. Funktionstests oder Messungen werden periodisch durchgeführt, wenn das Gerät nicht bestrahlt wird.
*   **Probenvorbereitung:** Um den Verlust von Energie durch entweichende Sekundärelektronen zu verhindern, wird empfohlen, die Prüflinge mit Material zu umgeben, das ein Gleichgewicht geladener Teilchen (Charged-Particle Equilibrium) gewährleistet. Bei Co-60-Bestrahlung wird eine Abschirmung von mindestens 1,5 mm Blei mit 0,7 mm Aluminiumfutter empfohlen, um den Niedrigenergie-Schweif des Co-60-Gammaspektrums zu mindern.
