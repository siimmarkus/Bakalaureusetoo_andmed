# Eesti domeenide statistika
Hobiprojektina alanud ja bakalaureusetööks välja kujunenud ettevõtmine kaardistada .ee domeenide maastiku, nüüd kus Eesti tsoonifail kõigi domeeninimedega on avalik. Ämbliku kood ise jääb kinniseks ja tulemustest on kriitilisem versiooniinfo tarkvara juurest ära peidetud.

- Marvet_Informaatika_2021.pdf - Bakalaureusetöö "Eesti domeenide statistika ja turbeinfo kogumine"
- host.csv - kõik skaneeritud hostid ning nende id teiste failide jaoks
- crawl_results.jsonl - JSON Lines formaadis tulemused viimasest .ee domeenid skaneerimisest. Igal real on tulemused ühe domeeni kohta:
	- "host" - domeeninimi, 
	- "uri" - url, millele GET päring tehti, 
	- "ip" - domeeni ip, 
	- "hosting" - majutusorganisatsioon, 
	- "statusCode" - HTTP GET päringu statusCode, 
	- "curlError" - veaga lõppenud HTTP GET info, 
	- "redirect" - ümbersuunamise aadress, 
	- "cms" - sisuhaldussüsteem, 
	- "ns" - nimeserverid, 
	- "mx" - meiliserverid, 
	- "txt" - tekstikirjed, 
	- "wappalyzer" - wappalyzer tarkvara tuvastamise tulemused (versiooninumbrid peidetud), 
	- "scripts" - lehel tuvastatud JavaScript urlid, 
	- "checked" - kontrollimise kuupäev

- software_version.json - Tuvastatud tarkvara, nende versioonid ja iga versiooni tuvastuste arv domeenidelt. (Versiooninumbrid timestampidena paistavad olevat sellest, kui veebilehed kasutavad cachemist vms ala ../example.js?ver=1619097972)
- hosting_countries.csv - domeenide majutus riigiti
- clusters/clusters_match_70.csv - domeenid jaotatud sarnaste veebilehtede järgi klastritesse (ssdeep heuristiline hinnang sarnasusele >= 70)  
- clusters/host_clusters - domeeni_id, klastri_id
- host_ip_separate.json - eraldi ip aadresside skänn, mida kasutati hostingu statistika tegemiseks (kuna crawl_results failis oli nendega probleem, vt bakatöö pt 2.3.5)

Ämbliku (web crawler) struktuur:

<img src="https://user-images.githubusercontent.com/44495597/119189327-9731ba00-ba84-11eb-9cdc-b03b54aeeb25.png" width="700">
