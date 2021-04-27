Da jeder andere Einstellungen für eine Firewall priorisiert, kann dies auch als HowTo betrachtet werden. Jeder sollte im vornherein Gedanken machen, was das Ziel ist und was evtl. im Netz hinter der Firewall alles vorhanden ist.

Weiß was du tust. Gerade wenn du PIHole im Einsatz hast, kann es sein, dass etwas nicht läuft wie du es dir vorstellst. Aufgrund des (zum Glück) gesteigerten aufkommens von https, gibt es keine Eindeutigen Fehlerseiten mehr.

Auf der anderen Seite, hat eine solche Blacklist auf der OPNSense andere Backgrounds als auf dem PiHole. Ich möchte an dieser Stelle keine Netzwerkgrundlagen geben, dazu müsstest du dich selbst informieren. Quellen gibt es dazu im Netz und Youtube genug.

1. Firehol Level 1
Die Firhol Level 1 Blacklist ist eine kommulierte Liste aus verschiedenen Quellen und beinhaltet eine Liste mit ~620.000.000 uniquen IPs. Sie beinhaltet malicous IPs, IPs zu Ransomware und allgemein gefährlichen IPs mit möglichst wenig falsch positiven.

Erstelle einen Alias in der OPNSense bspw. FirholL1 und hinterlege folgende TXT als IP List die alle 24 Std. geupdatet wird.

[Firehol Level 1 List](https://raw.githubusercontent.com/ktsaou/blocklist-ipsets/master/firehol_level1.netset)

Anschließend Firewall --> Regeln --> WAN
Regel WAN eingehend, alle Prokolle und wähle den Alias aus.

Die gleiche Regel für LAN ausgehend. So wird jeglicher Verkehr ein- und ausgehend basierend auf dieser Liste geblockt. Die Regel LAN ausgehend verhindert das aufrufen von Websites mit Cross-Side-Scripting und ähnlichem. Sprich, auch wenn du auf eine bösartige Seite geleitet wirst, werden diese IPS geblockt. Bitte beachte, dass auch dies keinen 100%igen Schutz bietet, sondern nur ein Bausteinen von vielen ist.

2. GeoIP

Zwar kann man auch dies über solche Listen machen, doch gerade das GeoIP-Addon für die OPNSense finde ich super. Ihr müsst euch dazu auf der Seite registrieren und einen API-Key hinterlegen. Eine Anleitung folgt.

Anschließend wird wieder ein Alias angelegt. In diesem ist es möglich Länder auszuwählen. Zum Beispiel Alias "autocratic" und alle autokratischen Seiten auswählen. Dann ebenfalls eine ein- und ausgehende Regel erstellen und es wird jeglicher Traffik von und zu euch zu autokratischen Staten geblockt. Restriktiv bedeutet dies natürlich, dass Alibaba nicht verfügbar wäre, da müsste eine Whitelist erstellt werden und bei den Regeln oberhalb der autocratic verschoben werden.
