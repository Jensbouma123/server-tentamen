# Primnary keys
Bij het aanmaken van een model en je hebt een speciale primary key nodig en je hebt geen methode met Id, dan is het handig om er een primary key als data notation neer te zetten.
Dus stel je hebt geen Id maar bijvoorbeeld een BSN zoals hier onder:
```
using System.ComponentModel.DataAnnotations;

namespace ApiOpdracht.Models
{
    public class Owner
    {
        public int BSN { get; set; }

        // overige code ...
    }
}

```

Deze moet dan een primary key worden. Dit kan door er een data notation **[key]** boven te zetten.
```
using System.ComponentModel.DataAnnotations;

namespace ApiOpdracht.Models
{
    public class Owner
    {
        [Key] // <------ Dit gedeelte
        public int BSN { get; set; }

        // overige code ...
    }
}
```

Dan heb je nu een primary key gemaakt op de model. Maar wil je een tussen tabel maken en heb je meerdere primary keys nodig? Dan kun je naar de volgende stap gaan.

#
### Primary keys in many to many tussen tabel
Stel we hebben een tussen tabel nodig om meerdere tabellen met elkaar te verbinden. Dan is z'n tussen tabel heel handig. Maar wat als je daar 2 primary keys op moet zetten? Dan gaat de **[key** niet meer werken.
Zie de code hier onder als voorbeeld:

```
using Microsoft.EntityFrameworkCore;

namespace Opdracht1.Models;

public class CityRestaurant
{
    public int CityId { get; set; }
    public int RestaurantId { get; set; }
    
    // overige code ...
}
```
In dit voorbeeld zie je dat er meerdere publieke ints zijn met een Id, alleen zullen deze beiden geen primary key zijn.
Dat moet je zelf nog implementeren. Dit doe je door ```[PrimaryKey(nameOf(<method>))]``` boven aan de gehele model te zetten.
Zoals hier onder zie je dan dat je er twee moet gebruiken en deze regel staat boven de model classe. Dus niet in de classe maar er buiten.
```
using Microsoft.EntityFrameworkCore;

namespace Opdracht1.Models;

[PrimaryKey(nameof(CityId), nameof(RestaurantId))] // <-------- Dit gedeelte
public class CityRestaurant
{
    public int CityId { get; set; }
    public int RestaurantId { get; set; }
    
    // overige code ...
}
```

En zo heb je een primary key aangegeven aan twee id's in een model.