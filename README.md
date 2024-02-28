**Problem**: **Sourcing** is a quite complex task in Amazon, lots of parameter to be monitored for lots of manufacturer and then distributors. In particular it could be complex to understand among the various sourcing options which is the **most profitable**.

**Solution**: I created a **data pipeline** which ends in a **Quicksight dashboard** to not only help the users to visualize the information, but also to give them product level **actionable suggestions**.

**Back end**: I created a **dataset** on Quicksight querying the data through **Amazon Redshift** using this [SQL query](https://github.com/pietro-fantini/Distributors-Profitability-Dashboard/blob/main/SQL_query).

**Problem**: The stakeholders I shared this dashboard with asked expand it to a broader audience. Quicksight has a very tight **query time limitation**, therefore I tackled this problem by:
1. Creating my own table.
2. Subscribe that to relevant clusters.
3. Create an **ETL transform job** with my SQL query to feed the data lake.
4. Create an **ETL load job** to fill the table with data.
5. Simply quering this table on Quicksight to avoid time limitation.

**Procedure**:
1. Select the period and the dynamic controls as needed.

![first distributor](https://github.com/pietro-fantini/Distributors-Profitability-Dashboard/assets/136325329/43690c49-8676-4be2-84b1-fc9ba33bd1d3)

2. Click on any particular cell (which will be the combination of a manufacturer, distributor and marketplace) and a drill down action will occur, opening a new sheet. Use case: deep dive on a particularly non profitable distributor in a marketplace.

3. The new sheet will have the same date filter as the starting sheet and will be filtered by manufacturer, distributor and marketplace based on where the user clicked.

![image](https://github.com/pietro-fantini/Distributors-Profitability-Dashboard/assets/136325329/e4acd0bf-b491-4712-aa56-e4ebf51e6bcd)

4. From this product level deep dive (visual on the left) it is possible to target non profitable products. Clicking on one of them the visual on the right will be filtered, showing all the distributors from which it is possible to source that product, highlighting more profitable solutions.

*data censored for privacy*
