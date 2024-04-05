
# Data notations in models
Het gebruik van data notations is veel makkelijker dan een model builder en zal je sneller op weg helpen.
Hier onder zijn een aantal voorbeelden die je kunt gebruiken en wat de betekenis daarvan zijn.

### Required
Bij de data notation **_Required_** kun je een veld verplicht maken van een model in de database. Dit doe je door de data notation
**[Required]** toe te voegen boven een veld van een model. Bijvoorbeeld zoals hieronder:
```
public class Book
{
    public int Id { get; set; }
    
    [Required]      // <-------- Boven de titel
    public string Title { get; set; }
    // Andere eigenschappen van het boek...
}
```
Wanneer je dit hebt toegevoegd en een boek wil maken, dan moet je een titel hebben opgegeven anders werkt het niet.

### Range
Bij de data notation **_Range_** kun je aangeven dat een waarde binnen een bepaalde range moet zitten. Als die er buiten valt dan wordt de aangemaakte klasse niet geaccepteerd. Dit doe je door **[Range(<min>, <max>)]**