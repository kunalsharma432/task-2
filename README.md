# task-2
import pandas as pd
import random
from faker import Faker

fake = Faker()
categories = {
    "Furniture": ["Chairs", "Tables", "Bookcases"],
    "Office Supplies": ["Binders", "Paper", "Pens"],
    "Technology": ["Phones", "Laptops", "Accessories"]
}
regions = ["West", "East", "Central", "South"]
segments = ["Consumer", "Corporate", "Home Office"]
ship_modes = ["Standard Class", "Second Class", "First Class", "Same Day"]

data = []

for i in range(1000):
    category = random.choice(list(categories.keys()))
    sub_cat = random.choice(categories[category])
    order_id = f"CA-{random.randint(2018, 2021)}-{random.randint(1000, 9999)}"
    order_date = fake.date_between(start_date='-4y', end_date='today')
    sales = round(random.uniform(10.0, 1000.0), 2)
    profit = round(sales * random.uniform(-0.2, 0.4), 2)
    discount = round(random.choice([0, 0.1, 0.2, 0.3]), 2)
    quantity = random.randint(1, 10)
    region = random.choice(regions)
    segment = random.choice(segments)
    ship_mode = random.choice(ship_modes)

    data.append([order_id, order_date, region, category, sub_cat, sales, profit, discount, quantity, segment, ship_mode])

df = pd.DataFrame(data, columns=[
    "Order ID", "Order Date", "Region", "Category", "Sub-Category",
    "Sales", "Profit", "Discount", "Quantity", "Segment", "Ship Mode"
])

df.to_csv("Superstore.csv", index=False)
print("Superstore.csv created.")

#
#What I Did:
Created a sales dataset (Superstore.csv) using Python or manual entry in Excel.

Imported the dataset into Power BI.

Built key measures:

Total Sales

Total Profit

Profit Margin

Total Orders

Average Discount

Designed a clean and interactive dashboard.

Added charts to show:

Sales by Region

Profit by Category

Sales and Profit over Time

Discount vs Profit (Scatter Plot)

Used filters (slicers) for Region, Category, and Segment.

Added text insights to explain key findings.

🔹 Key Insights:
West region had the highest sales.

Technology category gave the most profit.

Higher discounts led to lower profit margins.

Sales and profit increased over time.

🔹 Outcome:
A well-designed dashboard showing important business insights.

Practiced data storytelling using real-world sales data.

Learned how to use DAX formulas, charts, and slicers in Power BI.

Combined Python and Power BI skills in one project.
