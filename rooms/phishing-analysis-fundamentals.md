in deze room word er naar alle componenten bekeken hoe een email word opgemaakt en welke rpotocols deze volgt van afzender naar ontvanger. in deze room word er gebruik gemaakt van het prgoramma thunderbird voor diepere analysis van eventuele phishing emails. 
wat goed is aan deze room is dat het begint bij de basics dus voor iemand zoals mij is dit perfect want ik heb de theorie hierachter nooit gezien. 

een email is opgesplitist in 2 delen, de domain name en de username. 

de domain name specifieert de mail server die verantwoordelijk is voor het vezenden van de email. de username is de ontvangers mailbox op de mail server. 


als je een email stuurt, werken meerdere protocollen met elkaar om de mail van bij de verzender tot bij de ontvanger te krijgen. uw email server gebruikt een  van de volgende protocollen, afhankelijk van hoe de mailbox geconfigureerd is. 

POP3: emails worden gedownload en bewaaard op 1 device, zijn ook alleen bereikbaar via dit device en de mails wordne verwijderd van de server na het downloaden. meer gebruik voor offline werken en meer privacy 

IMAP: hier worden de emails bewaard op de server en kunnen gedownload worden door meerdere devices, verstuurde mails wordden bewaard op de server en synchroniseert berichten over meerdere devices.  meer gebruikt zakelijk als meerdere collegas toegan moeten hebben tot dezelfde mailbox. ik denk dat dit voor een attacker interessanter is omdat de mails op een server blijven staan dus gevaarlijker is voor attackers of toch meer vulnerable voor attackers. pop3 eens de mail gedownload is is het verwijderd en kan een attacker zo goed als niet aan de mail geraken 


voor de volgende oefeningen maakte ik via de attached vm gebruik van het programma thunderbird voor diepere analysis van de ontvangen emails.

iedereen kent een email header en de informatie die hier in staat, dit is vrij standaard maar er is nog een andere manier om zelfs meer data te kunnen bekijken van een email, data dat niet zomaar in de header staat meestal en dit is door de raw data te gaan bekijken van een email. 

voor deze opdracht moest ik via thunderbird de raw data bekijken van een email attached in de attached vm lab dit ging als volgt: 

in de email samples file stond er een email die ik opende met thunderbird, eens deze open was klikte ik op view en daarna message source om de raw data te bekijken van de email. 

'insert foto raw data email'  


ik heb hiervoor niet met thunderbird gewerkt en wist eerlijk gezegd oook niet dat je een email dieper kon inspecteren dan enkel de mail bekijken. dit is een interessante inkijk op hoe een mail kan gemanipuleerd worden. 


met deze informatie kon ik de vraag beantwoorde die vroeg welke ip de originating was. 


tegenover de email header heb je ook de email body, deze contains de message die verzonden wordt. emails worden enkel verzonden als plain-text of geformatteerd in html. html support foto's videos, gifs etc.. 
hiervan kan je ook de underlying source inspecteren om te controleren op phishing attempts of malicous contents. 

net zoals de email headers, kunnen wij ook de body van een mail verder inspecteren door view message code. thunderbrid blokkeert automatisch foto's uit een email die bekeken word. door de raw qource te bekijken kan je zien hoe de html in een mail is gestructureerd. 

in deze raw data staan eventueel ook attachments die zijn bijgevoegd bij de mail, zo kunnen deze ook geanaliseerd worden en geinspecteerd op eventuele malware of phishing pogingen. 

'insert foto html code' 

er was een opdracht om de base 64 string in pdf te zetten om een flag te verkrijgen en de vraag in te vullen. 
voor deze opdracht heb ik de base64 string gekopieerd naar apivoid om deze string te converten naar een online pdf. 

inserrt foto pdf en string 


ik vind deze  room interessant want hiervoor had ik eigenlijk nooit gekeken of beseft dat een email meer achterhoud dan dat het laat zien, dit maakt het in mijn ogen makkelijk voor threat actors om emails met malicious files of attachments te sturen. heb in deze room geleerd dat een email eigenlijk meer achterhoud dan mensen beseffen, en dat je met behulp van programmas of zelfs zonder programmas kan kijken wat er eigenlijk onder de motorkap zit van een email en hoe je hier kan herkennen of hier iets achter word gehouden of verstoptin de mail zoals malicious attachments. denk dat deze room interessant  is als iemand interesse heeft om in een soc center te werken omdat men hier dagelijks mee in contact zal komen.


nu ik meer weet over hoe een mail in elkaar zit, header, body, hoe deze te inspecteren en over hoe een mail versturen werkt, welke  protocollen  deze gebruikt is het interessant om te weten hoe een threat actor deze kan abusen, emails izjn dan ook de meest gebruikelijke entry points voor threat actors. 

er zijn veel verschillende phishing types, denk maaar aan spam, vishing, smishing, spearphishing ( het targetten van een specifiek iemand en gebruik maken van persoonlijke informatie). er zijn veel verschillende attack tactics maar vele gebruiken wel dezelfde inhoud characteristics, deze zijn: 


Urgent Subject or Message: The email creates a sense of urgency (“Your account will be locked in 24 hours”)
Brand Impersonation: The email is designed to mimic a legitimate organization (logos or colors matching a real company)
Grammar & Spelling Issues: The message may contain errors, though with AI these are now less common (awkward phrasing or unnatural wording)
Generic Content: The message lacks personalization (“Dear Customer” instead of your name)
Hidden or Shortened Links: Hyperlinks may disguise their true destination (bit.ly/secure-login)
Malicious Attachments: Attachments are included and disguised as legitimate files (invoice.pdf.exe)


in een van de laatste vragen werd er gevraagd om een attached email in de room te inspecteren en de vraag te beantwoorden, welke organisatie hier gespoofed werd, dit was niet moeilijk wnt dit staat gewoon in de email header. 

er was oook een vraag om een email te inspecteren en terug te komen met de defanged x-originating-IP 
hier heb ik met view message source gekeken naar de x-originating-IP en dee in cybercheff gekopieerd 
 om het ip adres te defangen. 

 insert foto cyberchef output*


 ik vond deze room interessant om de basis van phishing en de anatomy van een email te begrijpen en meer mee in contact te komen. in volgende room writeups ga ik meer de praktische kant opzoeken en zelf kijken hoe ik eventueel phishing mails kan inspecteren/controleren en dit eventueel ook in een siem environment toe te passen, voor mij zijn dit soort rooms interessant omdat ik vabn blue team nog niet veel ervaring heb en op deze manier mijn kennis kan verbreden. 









