
Market Basket Analysis using Instacart Online Grocery Dataset
=============================================================

Which products will an Instacart consumer purchase again?
---------------------------------------------------------

To showcase the concept of market basket analysis with the [Databricks Unified Analytics Platform](https://databricks.com/product/unified-analytics-platform), we will use the Instacart's [3 Million Instacart Orders, Open Sourced](https://www.instacart.com/datasets/grocery-shopping-2017) dataset.

The Instacart Online Grocery Shopping Dataset 2017 Accessed from_ [_https://www.instacart.com/datasets/grocery-shopping-2017_](https://www.instacart.com/datasets/grocery-shopping-2017) _on 01/17/2018. This anonymized dataset contains a sample of over 3 million grocery orders from more than 200,000 Instacart users. For each user, we provide between 4 and 100 of their orders, with the sequence of products purchased in each order. We also provide the week and hour of day the order was placed, and a relative measure of time between orders.

Whether you shop from meticulously planned grocery lists or let whimsy guide your grazing, our unique food rituals define who we are. Instacart's grocery ordering and delivery app aims to make it easy to fill your refrigerator and pantry with your personal favorites and staples when you need them. After selecting products through the Instacart app, personal shoppers review your order and do the in-store shopping and delivery for you.

This notebook will show how you can predict which items a shopper will purchase whether they buy it again or recommend to try for the first time.

![](readme_files/image002.jpg)
==============================

Data Engineering Pipeline
-------------------------

Data engineering pipelines are commonly comprised of these components:

**Ingest Data**: Bringing in the data from your source systems; often involving ETL processes (though we will skip this step in this demo for brevity)

**Explore Data**: Now that you have cleansed data, explore it so you can get some business insight

**Train ML Model**: Execute FP-growth for frequent pattern mining

**Review Association Rules**: Review the generated association rules

![](readme_files/image004.jpg)


# Notebook Reference Link

https://databricks.com/notebooks/gallery/MarketBasket.html
