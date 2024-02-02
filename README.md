# Домашнее задание к занятию "`Базы данных`" - `Громов Андрей`

---

### Задание 1

Таблица "Employees":
Столбец "Employee ID" (тип данных: SERIAL, PRIMARY KEY) 
Столбец "Full Name" (тип данных: VARCHAR(100))
Столбец "Salary" (тип данных: DECIMAL)
Столбец "Position" (тип данных: VARCHAR(50))
Столбец "Department Type" (тип данных: VARCHAR(50))
Столбец "Department Structure" (тип данных: VARCHAR(50))
Столбец "Hire Date" (тип данных: DATE)
Столбец "Branch Address" (тип данных: VARCHAR(100))
Столбец "Project" (тип данных: VARCHAR(50))

Таблица "Positions":
Столбец "Position ID" (тип данных: SERIAL, PRIMARY KEY)
Столбец "Position Title" (тип данных: VARCHAR(50))

Таблица "Departments":
Столбец "Department ID" (тип данных: SERIAL, PRIMARY KEY)
Столбец "Department Type" (тип данных: VARCHAR(50))

Таблица "StructuralDepartments":
Столбец "Structural Department ID" (тип данных: SERIAL, PRIMARY KEY)
Столбец "Structural Department Name" (тип данных: VARCHAR(50))

Таблица "Branches":
Столбец "Branch ID" (тип данных: SERIAL, PRIMARY KEY)
Столбец "Branch Address" (тип данных: VARCHAR(100))

Таблица "Projects":
Столбец "Project ID" (тип данных: SERIAL, PRIMARY KEY)
Столбец "Project Name" (тип данных: VARCHAR(50))

Таблица "HireDates":
Столбец "Hire Date ID" (тип данных: SERIAL, PRIMARY KEY)
Столбец "Hire Date" (тип данных: DATE)

Примечание:

В таблице "Employees" столбец "Position" связан с таблицей "Positions" по столбцу "Position ID".
В таблице "Employees" столбец "Department Type" связан с таблицей "Departments" по столбцу "Department ID".
В таблице "Employees" столбец "Department Structure" связан с таблицей "StructuralDepartments" по столбцу "Structural Department ID".
В таблице "Employees" столбец "Branch Address" связан с таблицей "Branches" по столбцу "Branch ID".
В таблице "Employees" столбец "Project" связан с таблицей "Projects" по столбцу "Project ID".
В таблице "Employees" столбец "Hire Date" связан с таблицей "HireDates" по столбцу "Hire Date ID".

---

### Задание 2

В данной денормализованной таблице можно выделить следующие функциональные зависимости:

Employee ID -> Full Name, Salary, Position, Department Type, Department Structure, Hire Date, Branch Address, Project
Правило вывода: Разделить таблицу "Employees" на две таблицы: "Employees" с столбцами "Employee ID" (PRIMARY KEY), "Full Name", "Salary", "Position ID", "Department ID", "Structural Department ID", "Hire Date ID", "Branch ID", "Project ID" и "EmployeePosition" с столбцами "Position ID" (PRIMARY KEY), "Position Title". Добавить внешний ключ "Position ID" в таблицу "Employees".

Position ID -> Position Title
Правило вывода: Оставить таблицу "Positions" без изменений.

Department ID -> Department Type
Правило вывода: Оставить таблицу "Departments" без изменений.

Structural Department ID -> Structural Department Name
Правило вывода: Оставить таблицу "StructuralDepartments" без изменений.

Branch ID -> Branch Address
Правило вывода: Оставить таблицу "Branches" без изменений.

Project ID -> Project Name
Правило вывода: Оставить таблицу "Projects" без изменений.

Hire Date ID -> Hire Date
Правило вывода: Оставить таблицу "HireDates" без изменений.

Чтобы нормализовать данные и соблюсти принципы связности, каждая функциональная зависимость должна быть представлена отдельной таблицей со своими атрибутами и корректными отношениями между таблицами.
