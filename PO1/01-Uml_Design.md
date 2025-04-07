
[01-Uml_Design.md.pdf](https://github.com/user-attachments/files/19637606/01-Uml_Design.md.pdf)

Design Decisions

- Composition is implemented between `CandyManager` and `Candy`, since `CandyManager` is responsible for managing the list of candies.

- Aggregation is applied in `AppController`, which utilizes `CandyManager` and `JSONDBManager` without having complete ownership of them.

- Inheritance was not considered necessary, as the responsibilities are distinctly divided among different roles.

- Error-checking and data validation are consolidated in `JSONDBManager` to ensure that file operations are secure and reliable.
