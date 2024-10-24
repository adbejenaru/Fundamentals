Iată un task mai practic, inspirat din viața de zi cu zi, care folosește **date** și **timp** în Java:

### Task: Planificator de Evenimente
Scrie un program care să ajute un utilizator să planifice evenimente și să calculeze timpul rămas până la fiecare eveniment. Programul ar trebui să facă următoarele:

1. Afișează data și ora curente.
2. Permite utilizatorului să introducă data și ora unui eveniment viitor (ex.: 24 decembrie 2024, ora 18:00).
3. Calculează și afișează câte zile și ore rămân până la evenimentul respectiv.
4. Dacă evenimentul este în trecut, afișează un mesaj de eroare.
5. Afișează numele zilei săptămânii în care se va desfășura evenimentul (ex.: Luni, Marți, etc.).

### Exemplu de rezultat:
```
Data și ora curente: 2024-10-24T10:30
Introdu data evenimentului (format: YYYY-MM-DDTHH:MM): 2024-12-24T18:00
Timp rămas până la eveniment: 61 zile, 7 ore
Evenimentul va avea loc într-o zi de Marți.
```

### Puncte cheie:
- Folosește clasele `LocalDateTime`, `Duration`, și `Period` pentru a calcula diferențele de timp.
- Poți folosi un `Scanner` pentru a prelua input-ul de la utilizator.

#### Exemplu de cod Java:
```java
import java.time.LocalDateTime;
import java.time.Duration;
import java.time.format.DateTimeFormatter;
import java.time.DayOfWeek;
import java.util.Scanner;

public class EventPlanner {
    public static void main(String[] args) {
        // Afișează data și ora curente
        LocalDateTime now = LocalDateTime.now();
        System.out.println("Data și ora curente: " + now);

        // Preia data și ora evenimentului de la utilizator
        Scanner scanner = new Scanner(System.in);
        System.out.println("Introdu data și ora evenimentului (format: YYYY-MM-DDTHH:MM):");
        String input = scanner.nextLine();
        
        // Parsează input-ul utilizatorului
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd'T'HH:mm");
        LocalDateTime eventDateTime = LocalDateTime.parse(input, formatter);

        // Verifică dacă evenimentul este în viitor
        if (eventDateTime.isBefore(now)) {
            System.out.println("Eroare: Evenimentul este în trecut!");
        } else {
            // Calculează durata rămasă până la eveniment
            Duration duration = Duration.between(now, eventDateTime);
            long days = duration.toDays();
            long hours = duration.toHours() % 24;
            System.out.println("Timp rămas până la eveniment: " + days + " zile, " + hours + " ore");

            // Afișează ziua săptămânii evenimentului
            DayOfWeek dayOfWeek = eventDateTime.getDayOfWeek();
            System.out.println("Evenimentul va avea loc într-o zi de " + dayOfWeek);
        }

        scanner.close();
    }
}
```

### Pași:
1. Rulează programul.
2. Introdu o dată viitoare când îți cere programul (exemplu: `2024-12-24T18:00`).
3. Vezi cât timp a mai rămas până la eveniment și în ce zi a săptămânii va avea loc.

Acest task te ajută să exersezi lucrul cu date și ore, iar scenariul este aplicabil pentru diverse tipuri de planificări!
