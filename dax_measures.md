# 📐 DAX Measures for Cookie Store Dashboard

---

## 📊 Revenue per Cookie

Revenue per Cookie = 
DIVIDE(SUM(Orders[Revenue]), SUM(Orders[CookiesShipped]))

## 📊 Previous Order Date
Previous Order Date = 
CALCULATE(
    MAX(Orders[Order Date]),
    FILTER(
        Orders,
        Orders[Customer ID] = EARLIER(Orders[Customer ID]) &&
        Orders[Order Date] < EARLIER(Orders[Order Date])
    )
)

## 📊 Days Between Orders
Days Between Orders = 
DATEDIFF([Previous Order Date], Orders[Order Date], DAY)


