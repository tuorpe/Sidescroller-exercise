# LUE TÄMÄ ENSIN!!

## Lisääminen unityyn
Tee uusi 3D projekti. Lisää repositorion "sidescroller_Peter_Tuoriniemi.unitypackage" valitsemalla Assets -> Import Package -> Custom package… ja valitse lataamasi unitypackage.

## Ennen ensimmäistä käynnistystä!
Projekti käyttää pluginia nimeltään Cinemachine, joka ei tule unitypackagen:n mukana, vaan se tulee asentaa erikseen. Asenna Cinemachine valitsemalla unityssä Window -> Package Manager -> Packages-kohdassa tulee olla Unity Registry -> kirjoita Cinemachine oikeassa yläkulmassa hakukenttään ja paina enter. Asenna Cinemachine valitsemalla se Packages-listasta ja painamalla Install nappia.

Lisäksi projektin scenet tulee lisätä projektin käännösasetuksiin. Tee se valitsemalla File - Build Settings. Ikkuna aukeaa. Etsi projektista ./Assets/Scenes/ polun takaa kaikki skenet, raahaa kaikki Scene-tiedostot auenneeseen ikkunaan (poislukien Sample Scene:ä). Sulje ikkuna ja pelin pitäisi olla nyt valmis kokeiltavaksi.

## Pelaaminen
Peli käynnistyy aukeavalla päävalikolla. Pelisession saa käynnistettyä painamalla NEW GAME-painiketta. Pelistä pääsee poistumaan painamalla QUIT-painiketta. 
Pelin loputtua on mahdollista aloittaa uudelleen painamalla TRY AGAIN-painiketta tai palata päävalikkoon MAIN MENU-painiketta painamalla.

## Pelin tarkoitus
Tarkoituksena on juosta karkuun kaukana siintäviä jahtaajia, mutta eteen osuu paljon esteitä. Painamalla välilyöntiä (SPACE) hahmo hyppää ilmaan ja pääsee näin ylittämään esteet. Ajoittain hahmon eteen osuu dollarisymboleita, joita keräämällä hahmo voi kerätä lisäpisteitä. Pelin edetessä esteet tulevat useammin ja useammin vastaan. Peli loppuu kun hahmo osuu esteeseen. 

## Tekniset tiedot
Peli on tehty Unityn omien Create With Code tutoriaalien pohjalta Unit 3:n ohjeita seuraamalla. Itse tein valikot, valikoiden animaatiot ja osan ääniefekteistä. Musiikit ovat sekä Unityn tutoriaalipaketeista sekä pixabay:stä löydettynä. Hahmon omat äänet ovat itse tehtyjä.

Skriptien kuvaus:

EndGameController.cs - Näyttää viimeisen valikon, kun pelaaja on kuollut. Näyttää edellisen pelin tulokset ja mahdollistaa paluun uuteen peliin tai päävalikkoon

MenuController.cs - Hallitsee päävalikon toiminnot. Hoidaa alun videoklippien ja äänien toistamisen. Suorittaa valikon elementtien näyttämisen oikeaan aikaan ja valikon nappien taustatoiminnot

SpawnManager.cs - Luo uusia esteitä ja palkintoja vaikeustason mukaisesti. Lisää vaikeustasoa tarvittaessa pienentämällä esteiden ja palkintojen ilmestymisväliä pienentämällä

RepeatBackground.cs - Hallitsee taustan ja lattian siirtämisen juoksusuuntaan. Kun tausta ja lattia on tarpeeksi liikkunut, siirretään niitä alkusijaintiin, jotta tulee tunne pitkästä juoksuradasta.

ScoreController.cs - Hallitsee pisteidenlaskun, high scoren tarkastamisen, pisteiden tallennuksen pysyväismuistiin ja vaikeustason lisäämisen aloituksen. Hoitaa pelin aikana ruudulla näkyvät piste ja tasotiedot.

PlayerController.cs - Hallitsee pelaajan hyppimisen, animaatioiden käynnistyksen. Hoitaa iskeytymisen esteisiin. Lisäksi hoitaa pelin alussa kameran kääntämisen oikeaan kuvakulmaan.

MoveLeft.cs - Hoitaa peliobjektien siirtämisen vasemmalle, mukaan lukien esteet ja palkinnot. Hallitsee pelaajan osumisen palkintoon, jolloin pyytää antamaan lisäpisteitä. Tuhoaa peliobjektiivin kun se kulkee tarpeeksi kauan tai pelaaja osuu palkintoon.