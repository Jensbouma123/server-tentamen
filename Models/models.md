# Models in entity framework
Hoe maak je een model, hoe voeg je data notations toe en meer.

### Models aanmaken
```
1. Klik op de map models met rechtermuisknop.
2. Klik op class
3. Voer een naam in en druk op enter.
```

Wanneer je een model hebt aangemaakt en je hebt niet per se eisen er aan verbonden. Kun je het beste direct een ```public int Id {get; set;}```
neer zetten. Dit zorgt er voor dat de **_Id_** alvast een **_primary key_** wordt.
Wanneer je deze niet mag gebruiken en iets anders hebt zoals _**BSN**_ die als primary key wordt gebruikt
kun je het beste een **_data notation_** maken en er boven zetten.

### Data notations in models
Het gebruiken van datanotations kan veel handiger zijn dan bij de model builder. Het is simpeler om te gebruiken en 
werkt veel overzichterlijker als er iets fout gaat. Kijk voor alle opties in de **_datanotations.md_**

**_Kijk voor primary keys en foreign keys in de apart gemaakte bestanden._**
