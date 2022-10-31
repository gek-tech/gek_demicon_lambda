# gek_demicon_lambda

Dieses Projekt dient zur Dokumentation und Bearbeitung der Aufgabe im Bewerbungsprozess bei der Demicon.  

<details><summary>Aufgabenstellung</summary>
<br>
Es soll eine Amazon Lambda Funktion erstellt werden, welche ein beliebiges Terraform State file aus einem S3 Bucket abruft und die hinterlegten Terraform Outputs zurück.<br>  
Die Rückgabewerte sollen von Cloud Fromation genutzt werden können.<br>  
Die genutzte Programmiersprache ist frei wählbar.<br>  
</details>

<details><summary>Bestandsaufnahme</summary>
<br>
Bevor die Aufgabe angegangen wird, erstelle ich eine Bestandsaufnahme der verwendetetn Technologien und meiner Kenntnisse dazu.<br>  
Die Bewertung erfolgt mit folgenden Zeichen: "-" bedeutet wenig bis keine Kenntnisse, "=" bedeutet gute bis wenig Kenntnisse, "+" bedeutet gute bis sehr gute Kenntnisse.<br>

- Terraform -   
> Ich habe an einem PoC zu Terraform in einem Automationsprojekt teilgenommen.  
- Terraform State Files -  
> Sind im JSON Format gespeichert.  
- Amazon Web Services (AWS) -  
> Ich hatte bisher keine Berührungspunkte mit AWS.  
- S3 Bucket -  
> Ist ein Objekt Store Container der AWS.  
- Cloud Formation -  
> Ich hatte bisher keine Berührungspunkte mit Cloud Formation  
- Python =  
> Die Programmiersprache mit der ich bisher die meisten Erfahrungen habe, wenn auch im Skripting Bereich.
</details>

<details><summary>Planung</summary>
<br>
Um die Aufgabe möglichst in der vorgegebenen Zeit abschließen zu können, bedarf es einer kleinen Planung.<br>  
Im ersten Planungsabschnitt kümmere ich mich um den Aufbau der nötigen Skills.<br>
Anschließend widme ich mich der Aufgabenstellung.<br>
Der Zeitrahmen startet am 25.10.2022 mit dem Tag 1.<br>

- Tag 1<br>
    - Aufgabenstellung verstehen und in eigenen Worten wiedergeben.<br>
    - Auflistung der genutzten Technologien und meiner Kenntnisse dazu.<br>
    - Kurze Recherche zu den jeweiligen Themengebieten.<br>
    - Erstellen eines Schulungskonzeptes für fehlende Skills.<br>  
    - Erstellen eines neuen Git Projekts in meinem persönlichen Gitlab zur Dokumentation.<br>  
- Tag 2<br>
    - Aufbau von Terraform Skills mit einem Kurs vom Anbieter Kodekloud auf Udemy.<br>  
    - Erstellen eines Lösungskonzeptes für die Aufgabenstellung.<br>
- Tag 3<br>
    - Aufbau von AWS Skills durch einen Udemy Kurs.<br>
    - Evaluierung der Lösungsansätze.<br>
    - Wählen einer Programmiersprache.<br>
- Tag 4<br>
    - Aufbau der erforderlichen Programmierskills mit einem Udemy Kurs.<br>
    - Aufbau der AWS Infrastruktur mittels Terraform.<br>
    - Recherche zu Cloud Formation.<br>
- Tag 5<br>
    - Puffer für den Aufbau von Skills und Infrastruktur.<br>
- Tag 6<br>
    - Coding der Lambda Funktion.<br>
    - Testing der Funktion.<br>
- Tag 7<br>
    - Optimierung der Funktion und Dokumentation.
</details>

<details><summary>Lösungsansätze</summary>

- Lösungsansatz 1
    - Nutzereingabe des Namen der abzurufenen Datei ohne Dateiendung
    > Dateiendung wird innerhalb der funktion gesetzt. ".tfstate"
    - Abrufen der benannten Datei
    > Fehlermeldung ,wenn die genannte Datei nicht vorhanden ist. (Dateinamen überprüfen)
    - Nutzung von JSONPATH um die gesetzten Outputs in der Datei zu finden.
    - Ausgabe der Outputs

- Lösungansatz 2
    - Erstellen einer EventBridge Rule zum Triggern von Lambda Funktionen bei Änderung von Dateien im S3 Bucket mit der Dateiendung .tfstate
    - Abruf der geänderten Datei
    - Parsing der Outputs per JSONPATH
    - Ausgabe der Outputs 
<br>
Nach Rücksprache mit Demicon reicht eine Ausgabe der Outputs.

</details>

<details><summary>gewählter Lösungsansätze</summary>

- Lösungansatz 2
    - Erstellen einer EventBridge Rule zum Triggern von Lambda Funktionen bei Änderung von Dateien im S3 Bucket mit der Dateiendung .tfstate
    - Abruf der geänderten Datei
    - Parsing der Outputs per JSONPATH
    - Ausgabe der Outputs 

</details>
