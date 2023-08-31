Das **Internet Group Management Protocol** (**IGMP**) ist ein [Netzwerkprotokoll](https://de.wikipedia.org/wiki/Netzwerkprotokoll "Netzwerkprotokoll") der [Internetprotokollfamilie](https://de.wikipedia.org/wiki/Internetprotokollfamilie "Internetprotokollfamilie") und dient zur Organisation von [Multicast](https://de.wikipedia.org/wiki/Multicast "Multicast")-Gruppen. IGMP benutzt wie [ICMP](https://de.wikipedia.org/wiki/Internet_Control_Message_Protocol "Internet Control Message Protocol") das [Internet Protocol](https://de.wikipedia.org/wiki/Internet_Protocol "Internet Protocol") (IP) und ist Bestandteil von IP au^f allen [Hosts](https://de.wikipedia.org/wiki/Host_(Informationstechnik) "Host (Informationstechnik)"), die den Empfang von IP-[[Multicast]] unterstützen.

## Verwendung

[![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/IGMP_LAN.svg/220px-IGMP_LAN.svg.png)](https://de.wikipedia.org/wiki/Datei:IGMP_LAN.svg)

Struktur von IGMP

Das _Internet Group Management Protocol_ basiert auf dem Internet Protocol (IP) und ermöglicht [IPv4](https://de.wikipedia.org/wiki/IPv4 "IPv4")-Multicasting (Gruppenkommunikation) im Internet. IP-Multicasting ist die Verteilung von [IP-Paketen](https://de.wikipedia.org/wiki/IP-Paket "IP-Paket") unter einer [IP-Adresse](https://de.wikipedia.org/wiki/IP-Adresse "IP-Adresse") an mehrere Stationen gleichzeitig. IGMP bietet die Möglichkeit, dynamisch Gruppen zu verwalten. Die Verwaltung findet nicht in der [Sende](https://de.wikipedia.org/wiki/Absender "Absender")-Station statt, sondern in den [Routern](https://de.wikipedia.org/wiki/Router "Router"), an denen [Empfänger](https://de.wikipedia.org/wiki/Empf%C3%A4nger_(Information) "Empfänger (Information)") einer Multicast-Gruppe direkt angeschlossen sind. IGMP bietet Funktionen, mit denen eine Station einem Router mitteilt, dass sie Multicast-IP-Pakete einer bestimmten Multicast-Gruppe empfangen will. Multicast-Routing-Protokolle ([DVMRP](https://de.wikipedia.org/wiki/Distance_Vector_Multicast_Routing_Protocol "Distance Vector Multicast Routing Protocol"), [MOSPF](https://de.wikipedia.org/wiki/MOSPF "MOSPF"), [PIM](https://de.wikipedia.org/wiki/Protocol_Independent_Multicast "Protocol Independent Multicast")) übernehmen die Koordination der Übertragung zwischen den Routern. Der Sender von Multicast-IP-Paketen weiß dabei nicht, welche und wie viele Stationen seine Pakete empfangen, denn er verschickt nur ein einziges [Datenpaket](https://de.wikipedia.org/wiki/Datenpaket "Datenpaket") an seinen übergeordneten Router. Dieser dupliziert das IP-Paket bei Bedarf, wenn er mehrere ausgehende [Schnittstellen](https://de.wikipedia.org/wiki/Schnittstelle "Schnittstelle") mit Empfängern hat.

Für [IPv6](https://de.wikipedia.org/wiki/IPv6 "IPv6")-Systeme findet das in [ICMPv6](https://de.wikipedia.org/wiki/ICMPv6 "ICMPv6") integrierte _Multicast Listener Discovery (MLD)_ Verwendung, das in ähnlicher Weise wie IGMP arbeitet.

Es gibt drei Versionen von IGMP mit folgenden prinzipiellen Eigenschaften:

- **IGMPv1** Ein Host kann einer Multicast-Gruppe beitreten. Ein Abmelden ist hier nicht implementiert. Nach einem [Timeout](https://de.wikipedia.org/wiki/Timeout_(Netzwerktechnik) "Timeout (Netzwerktechnik)") ist der Host wieder ausgetragen.
- **IGMPv2** Ein Host kann sich jetzt von der Multicast-Gruppe abmelden (Leave-Message implementiert). Damit können auch Multicasts mit großer Bandbreite behandelt werden.
- **IGMPv3** Hier kann nun vorgegeben werden, von welcher Quelle der Multicast-[Stream](https://de.wikipedia.org/wiki/Datenstrom "Datenstrom") gewünscht wird. Dies ist ein wesentlicher [Sicherheitsaspekt](https://de.wikipedia.org/wiki/Informationssicherheit "Informationssicherheit"), wenn auch nicht der optimale.

## Paketformat

IGMP-Pakete (in Version 1 und Version 2) haben eine Größe von 64 Bit. Folgendes Format wird verwendet:

|   |   |   |
|---|---|---|
|0 … 7|8 … 15|16 … 31|
|Typ|maximale [Antwortzeit](https://de.wikipedia.org/wiki/Antwortzeit "Antwortzeit")|Prüfsumme|
|Multicast-Gruppenadresse|   |   |

Das Feld „maximale Antwortzeit“ ist nur für Typ 0x11 definiert, bei allen anderen Typen wird dieses Feld ignoriert.

Dabei können folgende Werte für den Typ angenommen werden:

|Typ|Adresse|Bedeutung|
|---|---|---|
|0x11|ohne|allgemeine Anfrage|
|0x11|mit|gruppenspezifische Anfrage|
|0x12|mit|IGMPv1 Mitgliedschaft anmelden/bestätigen|
|0x16|mit|IGMPv2 Mitgliedschaft anmelden/bestätigen|
|0x17|mit|IGMPv2 Mitgliedschaft beenden|
|0x22|mit|IGMPv3 Mitgliedschaft anmelden/bestätigen/beenden|

IGMP-Pakete werden, wie [ICMP](https://de.wikipedia.org/wiki/Internet_Control_Message_Protocol "Internet Control Message Protocol"), in IP-[Datagramme](https://de.wikipedia.org/wiki/Datagramm "Datagramm") gekapselt und benutzen die [IP-Protokollnummer](https://de.wikipedia.org/wiki/Protokoll_(IP) "Protokoll (IP)") 2. IGMP ist im [OSI-Schichtenmodell](https://de.wikipedia.org/wiki/OSI-Modell "OSI-Modell") also in der Vermittlungsschicht anzusiedeln.