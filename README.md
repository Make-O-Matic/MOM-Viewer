# MOM-Viewer

Spezifikationen
- Ansatz ist USER/WORKER zentriert. Das System sucht:
  - zuerst nach Personen
    - dann nach Filmmaterial (RECORDS) pro USER/WORKER
      - dann nach COLLECTIONs/RECORD in denen RFID als SIGNAL vorkommt
        - dann gleicht es diese Daten mit den Film-RECORDS ab
          - dann erstellt es TAGS (Bereiche im Video), die solange dauern, wie eine RFID-ID vorliegt
            - dann schließt es von den COLLECTORen die RFID-Tags erkannt haben zurück auf die Hosts mit diesen RFID-Tags


Damit eine Suche zwischen allen unterschiedlichen RECORDS aus unterschiedlichen COLLECTIONS leicht möglich ist, sollte die zeitliche
Abhängigkeit durch eine Verbindung (FOLLOWS_AFTER) ausgedrückt werden


ODER
  - das System sucht zuerst nach Kameras, die bereits RECORDS produziert haben
    - dann nach denen die von dem einem bestimmten USER (ggf. dem eingeloggeten USER) aufgezeichnet wurden (ihn als HOST hatten oder ihm gehören -OWNS-)
      - dann kann man RECORDS, anhand der Quelle und anhand von Beginn- oder End-Datum/Uhrzeit filtern
        - dann wird anhand des RECORDs (= Länge des Videos), in den zeitlich passenden RECORDs anderer COLLECTIONs (= auch anderer COLLECTORen) gesucht
          - diese Suche wird eingeschränkt auf die DATA, die im Kontext (TODO: Kontext definieren) des gewählten USERs erzeugt worden ist
            - diese Suche wird eingeschränkt auf die DATA, die die GESTURE ("RFID detected") erzeugt
              - die Suchergebnisse werden auf die HOSTs (TOOL/MACHINE) zurückverfolgt auf die sich die GESTURE bezieht
              - die Suchergebnisse werden in Form von TAGS (Bereiche im Video) und als Liste von HOSTS, GESTURES, USER im Interface angezeigt

              genauere Infos siehe Whiteboard 28.02.2017 
