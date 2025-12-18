# 📊 Excel Conditional Functions: **SUMIF, AVERAGEIF & COUNTIF**

The **SUMIF**, **AVERAGEIF**, and **COUNTIF** functions in Microsoft Excel (and other spreadsheet applications) perform statistical operations based on **logical criteria**. They allow you to analyze a dataset by applying a specific condition (logical test) to determine which values should be included in the final calculation.

---

## 🔍 Overview of Functions

These functions are highly useful for **data analysis and filtering**:

- **COUNTIF**  
  Counts the number of cells within a specified range that meet a single condition or criterion.

- **SUMIF**  
  Adds up the values in a specified range of cells, but only if those values meet a single given condition.

- **AVERAGEIF**  
  Calculates the average (arithmetic mean) of cells within a range that meet a single specified condition.

> 🔁 For situations requiring **multiple conditions**, related functions such as **COUNTIFS**, **SUMIFS**, and **AVERAGEIFS** are used.

---

## 🧩 Function Syntax and Operations

The basic structure for these functions involves:
- a **range** to check the condition, and  
- a **criteria** (logical condition).

For **SUMIF** and **AVERAGEIF**, an optional third argument specifies the actual values to be summed or averaged.

| Function | Syntax Example | Explanation |
|--------|----------------|-------------|
| COUNTIF | `=COUNTIF(range, criteria)` | Counts cells in *range* that satisfy the criteria (e.g., counting all `"USA"` entries). |
| SUMIF | `=SUMIF(range, criteria, [sum_range])` | Sums values in *sum_range* (or *range* if omitted) when criteria is met (e.g., total sales for `"USA"`). |
| AVERAGEIF | `=AVERAGEIF(range, criteria, [average_range])` | Averages values in *average_range* (or *range* if omitted) when criteria is met (e.g., average price > `$100`). |

---

## 🧠 Using Logical Operators in Criteria

The **criteria** argument can use logical operators to filter data:

- `=`  (equal to)  
- `>`  (greater than)  
- `<`  (less than)  
- `<>` (not equal to)  
- `>=` (greater than or equal to)  
- `<=` (less than or equal to)

### 📌 Important Notes
- Operators with numeric values must be enclosed in **double quotes**  
  - Example: `">100"`
- To use a **cell reference** with an operator, use an **ampersand (`&`)**  
  - Example: `">"&B4`

---

## 🗂 Sample Dataset: **Sales Report**

| Row | Region | Salesperson | Category | Sales Amount | Units Sold |
|----|--------|-------------|----------|--------------|------------|
| 1 | North | Alice | Electronics | $500 | 5 |
| 2 | South | Bob | Clothing | $200 | 10 |
| 3 | North | Charlie | Electronics | $800 | 4 |
| 4 | East | Alice | Clothing | $150 | 15 |
| 5 | West | David | Home | $450 | 3 |
| 6 | North | Alice | Electronics | $300 | 6 |
| 7 | South | Bob | Home | $600 | 2 |

---

## 🔢 **SUMIF Function**

### 🧪 Syntax
```excel
=SUMIF(range, criteria, [sum_range])
🧩 Parameters
range: Cells to evaluate against the criteria

criteria: Condition (e.g., "North", ">300")

[sum_range] (optional): Cells to add

📘 Examples
🎯 Goal	📐 Formula	📝 Explanation	✅ Result
Sum sales for "North" region	=SUMIF(A2:A7,"North",D2:D7)	Adds sales where Region = North	$1600
Sum sales > $400	=SUMIF(D2:D7,">400")	Adds values > 400 (sum_range omitted)	$2350
Sum units sold by Alice	=SUMIF(B2:B7,"Alice",E2:E7)	Adds units where Salesperson = Alice	26

2️⃣ AVERAGEIF Function
🎯 Purpose
Calculates the average of numbers that meet a single criterion.

🧪 Syntax
excel
Copy code
=AVERAGEIF(range, criteria, [average_range])
📘 Examples
🎯 Goal	📐 Formula	📝 Explanation	✅ Result
Avg sales for Electronics	=AVERAGEIF(C2:C7,"Electronics",D2:D7)	Averages electronics sales	$533.33
Avg units for sales > $400	=AVERAGEIF(D2:D7,">400",E2:E7)	Averages units where sales > 400	3.5
Avg sales excluding South	=AVERAGEIF(A2:A7,"<>South",D2:D7)	Excludes South region	$440

3️⃣ COUNTIF Function
🎯 Purpose
Counts the number of cells that meet a specified criterion.

🧪 Syntax
excel
Copy code
=COUNTIF(range, criteria)
📘 Examples
🎯 Goal	📐 Formula	📝 Explanation	✅ Result
Count sales in North	=COUNTIF(A2:A7,"North")	Counts "North" entries	3
Count sales > $400	=COUNTIF(D2:D7,">400")	Counts values > 400	4
Count non-Electronics	=COUNTIF(C2:C7,"<>Electronics")	Excludes Electronics	3

🧾 Summary: Criteria Syntax Rules
🔢 Numbers
Copy code
100
📝 Text
arduino
Copy code
"North"
🔀 Logical Operators
Greater than → ">100"

Less than → "<100"

Not equal → "<>100"

🔗 Cell References
Use ampersand (&) to combine operator with cell value:

excel
Copy code
">"&G1
