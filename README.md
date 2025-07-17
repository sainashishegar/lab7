# 📚 ContractLibrarySystem

A Java-based mini library system that uses **design-by-contract principles** to ensure correctness and predictability. This project uses **JML-style comments** to formally specify preconditions, postconditions, and invariants for core methods like adding, removing, and searching books.

---

## 🧠 Features

- Manage a collection of books using a `LinkedList`
- Add, remove, and search for books by title or content
- Check-in/check-out book availability
- Apply **formal method contracts** to validate logic using JML-style annotations
- Override equality to ensure object-level comparison

---

## 🛠️ Tech Stack

- Java  
- Object-Oriented Programming (OOP)  
- JML-style Contract Design  
- Collections Framework (`LinkedList`)

---

## 💡 Key Concepts

| Method           | Design Contract Example                                |
|------------------|--------------------------------------------------------|
| `addBook()`      | Ensures book is not null, list size increases by 1     |
| `removeBook()`   | Ensures book exists before removal, size updates       |
| `hasBook()`      | Does not modify library state                          |
| `findByTitle()`  | Returns matching book object by title                  |

---

## 🧪 Sample Methods

```java
//@ requires newBook != null;
//@ ensures holdings.contains(newBook);
//@ ensures holdings.size() == \old(holdings.size()) + 1;
Library addBook(Book newBook) {
    holdings.add(newBook);
    return this;
}
```

```java
//@ ensures holdings.size() == \old(holdings.size());
Book findByTitle(String atitle) {
    for (Book item : holdings) {
        if (item.title.equals(atitle)) {
            return item;
        }
    }
    return null;
}
```

---

## 👩‍💻 Author

**Saina Shishegar**  
📍 Toronto, Canada  
📫 [saina.shishegar@gmail.com](mailto:saina.shishegar@gmail.com)

---

## 🏁 Status

✅ Complete – designed for educational and academic use in formal software design practices.

