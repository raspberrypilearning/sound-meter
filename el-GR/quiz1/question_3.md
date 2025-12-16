
--- question ---

---
legend: Ερώτηση 3 από 3
---
Εδώ είναι ο κώδικας για τον προγραμματισμό των μπλοκ `όταν πιεστεί το πλήκτρο button A` και `όταν πιεστεί το πλήκτρο button B`.

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    level += -1
    maximum += -50
    if (level < 1) {
        level = 5
        maximum = 250
    }
    basic.showNumber(level)
    basic.pause(500)
})
input.onButtonPressed(Button.B, function () {
    level += 1
    maximum += 50
    if (level < 5) {
        level = 5
        maximum = 250
    }
    basic.showNumber(level)
    basic.pause(500)
})
```

Τι θα συμβεί όταν πατηθεί το κουμπί `B` στο micro:bit;

--- choices ---

- ( ) Η στάθμη του ήχου θα αλλάξει κατά -1 και η ευαισθησία κατά -50.


  --- feedback ---

  Όχι ακριβώς! Πατώντας το κουμπί `A` θα γίνουν αυτές οι αλλαγές, αλλά όχι το κουμπί `B`.

  --- /feedback ---

- ( ) Η στάθμη του ήχου θα αλλάξει κατά 5 και η ευαισθησία κατά -50.

  --- feedback ---

  Όχι ακριβώς! Ούτε το κουμπί A ούτε το κουμπί B έχουν προγραμματιστεί να αλλάζουν τη στάθμη ή την ευαισθησία του ήχου κατά αυτές τις τιμές.

  --- /feedback ---

- ( x) Η στάθμη του ήχου θα αλλάξει κατά 1 και η ευαισθησία κατά 50.

  --- feedback ---

  Εκπληκτική δουλειά! Το κουμπί B έχει προγραμματιστεί να αυξάνει το επίπεδο ήχου κατά 1 και την ευαισθησία κατά 50.

  --- /feedback ---

--- /choices ---

--- /question ---
