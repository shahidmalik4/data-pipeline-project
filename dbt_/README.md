Welcome to your new dbt project!

### Using the starter project

Try running the following commands:
- dbt run
- dbt test


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices


dbt_project/
├── models/
│   ├── staging/
│   │   ├── stg_orders.sql       # source('raw', 'orders')
│   │   └── stg_customers.sql    # source('raw', 'customers')
│   │
│   └── marts/
│       ├── facts/
│       │   └── fct_orders.sql    # ref('stg_orders'), ref('stg_customers')
│       │
│       ├── dimensions/
│       │   └── dim_customers.sql # ref('stg_customers')
│       │
│       ├── kpis/
│       │   ├── kpi_total_sales.sql       # Output: single value per period
│       │   ├── kpi_monthly_revenue.sql   # Output: 1 row per month
│       │   └── kpi_customer_churn.sql   # Output: 1 row per period
│       │
│       └── analytics/
│           ├── orders_dashboard.sql      # Output: multi-row table
│           ├── top_customers.sql         # Output: table of customers with revenue
│           └── sales_by_region.sql       # Output: aggregated but still multi-row