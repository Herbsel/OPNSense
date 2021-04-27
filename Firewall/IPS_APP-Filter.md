#IDS, IPS, Application Filtering

Killerfeatures wie es Enterprise UTM Firewalls bieten. Ist UTM eigentlich noch so ein Buzzword in der IT? Wie dem auch sei, hier geht es exakt darum. Ob für eine Schule, im eigenen Heimnetz, oder Firmennetz, die OPNSense kommt mit allem zurecht. Vorausgesetzt, die Hardwareressourcen sind vorhanden. Gerade Application Filterin (und Virenscanner) sind sehr Arbeitsspeicherhungrig.

##IDS (Intrusion Detection System) / IPS (Intrusion Preventation System)

Kurz zusammengefasst, da viele Fragen haben wie sie was auf welches Interface legen. IPS gehört auf das WAN Interface, da ein Intrusion Preventation (oder Detection) System den eingehenden Verkehr auf bösartige Streams (patterns, matches oder wie auch immer man es nennen mag). Dieser Verkehr kommt typischerweise auf dem WAN Interface an.

##Sunnyvallays Sensei (Deep Packet Inespection)

Das ist noch alles sehr Standard. Ein echtes Killerfeature ist das Plugin Sensei von Sunnyvalley. Meiner Meinung nach ist Sensei ein mehr als passender Name. Erst einmal geht es darum das Plugin zu installieren. Ist es installiert, geht es an die Arbeit.

Je nach Netz wird dieses auf die LAN Schnittstelle gesetzt, oder auf das Interace von welchem Clientseitiger Verkehr gefiltert werden soll. Dies kann natürlich auch ein Gastnetzwerk sein, Schülernetz oder whatever.

Die kostenlose homeedition bietet leider nur eingeschränkte Funktionsvielfalt, aber für das gröbste reicht sie aus. In größeren Umgebungen lohnt sich durchaus eine der kostenpflichtigen Lizenzen. Diese sind nicht gerade günstig. Die Preise werden gestaffelt, je nachdem wie viele Clients in dem (Sub)-Netz sind, die überwacht werden sollen. Warum sich das geld IMHO lohnt? Mit diesem Plugin könnt ihr nahezu alle Apps sperren und es kommen regelmäßig neue hinzu. Ähnlich wie das IPS, filtert es strems, also eindeutige Netzverkehrpatterns, die nur diese eine App haben.

So ist es bspw. möglich Whatsapp, Tinder, TikTok, Instagram zu sperren, aber Signal, Threema etc. zuzulassen. Es wird also nicht mit Portsperren gefiltert, sondern tatsächlich auf den Netzverkehr. DeepPacketInspection kostenlos im Heimnetz, wie genial ist das denn?
