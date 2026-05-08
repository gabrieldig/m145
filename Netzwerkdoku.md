1. Netzwerkadresse vom Standort Samedan?
192.168.3.0/24

2. IP-Adresse des AccessPoints in Bellinzona?
Der AccessPoint selbst hat keine explizit eingetragene IP im Diagramm. Er ist am Switch angeschlossen (Port 24, VLAN-3). Die Switch-IP lautet .253 → 192.168.4.253. Eine dedizierte Management-IP des APs ist nicht dokumentiert.

3. In welchem VLAN befinden sich die Arbeitsplatz-PCs?
VLAN-2 (Office) – an allen drei Standorten sind die Ports 1–23 dem VLAN-2 «Office» zugewiesen.

4. IP-Adresse des Manageable-Switch am Standort Chur?
192.168.2.253

5. LAN- und tunnelseitige IP des VPN-Gateways in Bellinzona?

LAN-seitig (Gateway): 192.168.4.1
Tunnelseitig (VPN-B, Point-to-Point): 172.200.4.2/24


6. Standardgateway an Arbeitsplatz-PCs in Samedan?
192.168.3.1 (= Router/Firewall/Web-Proxy, GW)

7. VPN-Konfiguration für einen Aussendienst-Mitarbeiter (RAS)?
Der Aussendienst nutzt VPN-C (Remote Access Service). Die Konfiguration:

VPN-Server-Adresse (Gegenstelle): öffentliche IP des Hauptsitzes Chur → 82.4.12.158 bzw. Domain ingcaprez.ch
Tunnelnetz-seitig wird eine IP aus dem Netz 172.200.5.x/24 zugewiesen (VPN-C: 172.200.5.1/24 ist die Server-Seite in Chur)


8. Wer hat im CAD Wasserbau die VoIP-Telefone installiert?
abisang (alle VoIP-Telefone in E10 und E11 wurden von abisang eingetragen)

9. Wann wurde im Bistro der AccessPoint installiert?
23.07.2014 – Anschluss E8/1, eingetragen von rsauter

10. René Sauter (rsauter) verlässt die Firma – betroffene Arbeiten?
Folgende Anschlüsse wurden von rsauter dokumentiert/installiert:

E1/1 – Empfang EG, Arbeitsplatz-PC
E2/1 – CAD Tiefbau, CAD Workstation
E3/2 – Bauleiterbüro, MF-Kopierer
E8/1 – Bistro, AccessPoint

Als zukünftigen Ansprechpartner würde ich blaeuchli vorschlagen, da diese Person ebenfalls mehrere Installationen vorgenommen hat (E2/4, E6/1, E10/2, E10/4, E11/2, E11/4) und damit gute Kenntnis der Infrastruktur hat.

11. RJ45-Steckdosen im Bauleiterbüro – total und frei?
Anschlüsse E3, E4, E5, E6 → je 2 Ports = 8 Ports total

E3/1 – frei
E3/2 – belegt
E4/1 – belegt
E4/2 – belegt
E5/1 – belegt
E5/2 – belegt
E6/1 – belegt
E6/2 – frei

→ 2 Ports sind noch frei (E3/1 und E6/2)

12. Weiteres VoIP-Telefon in CAD Tiefbau – Patchpanel & Switch-Port?
Der einzige freie Anschluss in CAD Tiefbau ist E2/2.

Patchpanel: E2/2 patchen auf einen freien Switch-Port im VLAN-1 (Telefon)
Am Churer Switch (ZyXEL XGS1910-24 stacked) einen Port dem VLAN-1 (Telefon) zuweisen (Ports 24–47 laut Diagramm sind VLAN-1 zugeordnet)


13. Ethernetverbindung im Bistro für Projektpräsentation?
Verfügbare freie Anschlüsse im Bistro: E8/2, E9/1, E9/2 (Status leer = frei).
→ Eines dieser Kabel auf einen freien Switch-Port im VLAN-2 (Office) patchen (Ports 1–23).

14. Temporärer zusätzlicher Arbeitsplatz in CAD Wasserbau?
Alle Anschlüsse E10 und E11 (4 × 2 = 8 Ports) sind bereits vollständig belegt. Mögliche Lösungen:

Einen vorhandenen freien Port aus einem anderen Bereich ummappen (z. B. aus dem Bistro: E9/1 oder E9/2)
Alternativ: WLAN über den bestehenden AccessPoint (VLAN-2/Office) nutzen
Oder: Einen kleinen unmanaged Switch an einem bestehenden Port anschliessen (temporäre Lösung)


15. Anzahl Switches am Standort Chur?
2 Switches – zwei ZyXEL XGS1910-24 betrieben im Stacked-Modus («2 ZyXEL XGS1910-24 stacked»)

16. Frau Sommer (CAD Workstation) hat keine Internetverbindung – was prüfen?
Schrittweise Fehlersuche:

Anschluss E2/1 am Patchpanel und Kabelverbindung zum Switch prüfen
Switch (192.168.2.253) – Port-Status und VLAN-2-Zuweisung prüfen
Router/Firewall/Web-Proxy (192.168.2.1) – erreichbar? NAT aktiv?
DHCP-Server (192.168.2.3) – hat die Workstation eine gültige IP erhalten?
DNS (192.168.2.3) – Namensauflösung funktionsfähig?
ADSL-Router (Swisscom Vivo XL, 82.4.12.158) – WAN-Verbindung aktiv?
Web-Proxy – korrekt konfiguriert im Browser?