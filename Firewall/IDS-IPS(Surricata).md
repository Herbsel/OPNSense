#IDS, IPS, Application Filtering

Killerfeatures wie es Enterprise UTM Firewalls bieten. Ist UTM eigentlich noch so ein Buzzword in der IT? Wie dem auch sei, hier geht es exakt darum. Ob für eine Schule, im eigenen Heimnetz, oder Firmennetz, die OPNSense kommt mit allem zurecht. Vorausgesetzt, die Hardwareressourcen sind vorhanden. Gerade Application Filterin (und Virenscanner) sind sehr Arbeitsspeicherhungrig.

##IDS (Intrusion Detection System) / IPS (Intrusion Preventation System)

Kurz zusammengefasst, da viele Fragen haben wie sie was auf welches Interface legen. IPS gehört auf das WAN Interface, da ein Intrusion Preventation (oder Detection) System den eingehenden Verkehr auf bösartige Streams (patterns, matches oder wie auch immer man es nennen mag). Dieser Verkehr kommt typischerweise auf dem WAN Interface an.

##Listen

Surricata hat in der OPNSense schon sehr gute Listen integriert. Du musst sie nur aktivieren, herunterladen und anwenden. Die abuse.ch Listen muss Niemand mehr manuell integrieren. Alles geht per Knopfdruck.
