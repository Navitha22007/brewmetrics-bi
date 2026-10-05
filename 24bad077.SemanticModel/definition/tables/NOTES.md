# Copilot Notes

## Measure 1: MoM Sales Growth

### Copilot's First Suggestion

GitHub Copilot generated a `MoM Sales Growth` measure using `SUM(Fact_Sales[sales_amount])` for current and previous month sales. It used `DATEADD(Dim_Date[date], -1, MONTH)` to retrieve the previous month's sales and `DIVIDE` to calculate the growth rate.

### Correction Made

The first Copilot suggestion returned BLANK when previous-month sales were unavailable. I changed the `DIVIDE` alternate result to `0` so the measure returns zero instead of blank in that situation.

I also changed the calculation to reuse the existing `[Total Sales]` measure instead of repeating `SUM(Fact_Sales[sales_amount])`.

### Final Measure

```DAX
MoM Sales Growth =
VAR CurrentSales =
    [Total Sales]
VAR PreviousMonthSales =
    CALCULATE(
        [Total Sales],
        DATEADD(Dim_Date[date], -1, MONTH)
    )
RETURN
    DIVIDE(
        CurrentSales - PreviousMonthSales,
        PreviousMonthSales,
        0
    )

## Measure 2: Running Total Sales

### Copilot's First Suggestion
```dax
Running Total Sales = 
CALCULATE(
    [Total Sales],
    FILTER(
        ALL(Dim_Date[date]),
        Dim_Date[date] <= MAX(Dim_Date[date])
    )
)