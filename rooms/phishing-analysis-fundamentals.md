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








