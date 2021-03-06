# Copenhagen Data Tank Parking API
## Brug
### Nyeste
Endpoint: data.kk.dk/parking/latest/{antal}

Respons: Givent {antal} nyeste parkeringstilladelser

[Eksempel: data.kk.dk/parking/latest/100](http://data.kk.dk/dataset/parkeringstilladelser-parking-rights/resource/476fe848-7d66-4997-ba4b-03123f103a00)

### Timebaseret 
Endpoint: data.kk.dk/parking/{år}/{måned}/{dag}/{time:minut}

Respons: Parkeringstilladelser for timen op til det angivne tidspunkt

[Eksempel: data.kk.dk/parking/2017/01/09/08:00](http://data.kk.dk/dataset/parkeringstilladelser-parking-rights/resource/0fa86bfe-28d1-47f2-9333-f434bf37025c)

### Interval
Endpoint: data.kk.dk/parking/{år}/{måned}/{dag}/{time:minut}-{time:minut}

Respons: Parkeringstilladelser indenfor det angivne tidsrum

[Eksempel: data.kk.dk/parking/2017/01/09/12:00-12:30](http://data.kk.dk/dataset/parkeringstilladelser-parking-rights/resource/6da318e9-3b1f-4162-bb77-4968694051d6)

(Note: Brede intervaller kan resultere i meget store datasæt, som tager længe at hente. Begræns evt. hentning til flere kald af mindre pakker)
## Vedligeholdelse
### Løsning af '502 Bad Gateway'
En fejl 502 kan skyldes to forskellige problemer, der kan løses på følgende måder:

Genstart af nginx routeren:
 - Forbind med SSH til cph.opendata.dk
 - Kør kommandoen 'sudo service nginx restart'
 - Indtast kodeord hvis konsollen beder om det
 
Genstart af node:
 - Forbind med SSH til cph.opendata.dk
 - Gå til nodens lokation med 'cd /etc/node-servers/parking'
 - Start noden med 'forever start parking.js'
