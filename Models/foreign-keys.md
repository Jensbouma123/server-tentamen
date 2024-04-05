# Foreign keys
In dit hoofdstuk behandelen we hoe we een foreign key kunnen gebruiken in data notations.
Waarom in data notations? Data notations zijn veel makkelijker en overzichtelijker te gebruiken dan de model 
builder. 

Stel we hebben twee klasses, een **Author** en een **Book** klasse. Een boek kan geschreven worden door een auteur. Dus een **Book** hoort bij
een **Author**.

Als eerste gaan we de klassen maken van de Author
```
public class Author
{
    public int AuthorId { get; set; }
    public string Name { get; set; }
    // Andere eigenschappen van de auteur...
    
    public ICollection<Book> Books { get; set; }
}

```
en de klasse Book
```
public class Book
{
    public int BookId { get; set; }
    public string Title { get; set; }
    // Andere eigenschappen van het boek...

    public int AuthorId { get; set; }
    public Author Author { get; set; }
}
```

Zo heb je twee klassen, alleen zijn ze nog niet direct met elkaar verbonden. De Book klasse heeft wel een AuthorId waar naar verwezen kan worden als foreign key.
Door er een ```[ForeignKey("Author")]``` aan toe te voegen heeft het Book nu een verbinding met de Author klasse.
Zie het voorbeeld:
```
public class Book
{
    public int BookId { get; set; }
    public string Title { get; set; }
    // Andere eigenschappen van het boek...

    [ForeignKey("Author")] // <------ Zet deze bij de AuthorId
    public int AuthorId { get; set; } // Foreign key
    public Author Author { get; set; }
}
```