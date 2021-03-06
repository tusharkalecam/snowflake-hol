# Sharing Data

## Introduction to Data Sharing

Secure Data Sharing enables account-to-account sharing of data through Snowflake database tables, secure views, and secure UDFs.

The principle participants in any data sharing relationship are the provider and one or more consumers. Snowflake enables the sharing of databases through shares, which are created by data providers and “imported” by data consumers.

For example, Snowflake uses secure data sharing to share account usage data and sample data sets with all Snowflake accounts. In this capacity, Snowflake acts as the provider of the data and all other accounts act as the consumers.

## How does Data Sharing Work?

With Secure Data Sharing, no actual data is copied or transferred between accounts. All sharing is accomplished through Snowflake’s unique services layer and metadata store. This is an important concept because it means that shared data does not take up any storage in a consumer account and, therefore, does not contribute to the consumer’s monthly data storage charges. The only charges to consumers are for the compute resources (i.e. virtual warehouses) used to query the shared data.

In addition, because no data is copied or exchanged, Secure Data Sharing setup is quick and easy for providers and access to the shared data is instantaneous for consumers:

- The provider creates a share of a database in their account and grants access to specific objects (i.e. tables, secure views, and secure UDFs) in the database. The provider can can also share data from multiple databases, as long as these databases belong to the same account. One or more accounts are then added to the share, which can include your own accounts (if you have multiple Snowflake accounts).


- On the consumer side, a read-only database is created from the share. Access to this database is configurable using the same, standard role-based access control that Snowflake provides for all objects in the system.

## Reader Account

Data sharing is only supported between Snowflake accounts. As a data provider, you might wish to share data with a consumer who does not already have a Snowflake account and/or is not ready to become a licensed Snowflake customer.

To facilitate sharing data with these consumers, Snowflake supports providers creating reader accounts. Reader accounts (formerly known as “read-only accounts”) provide a quick, easy, and cost-effective way to share data without requiring the consumer to become a Snowflake customer.

Each reader account belongs to the provider account that created it. Similar to standard consumer accounts, the provider account uses shares to share databases with reader accounts; however, a reader account can only consume data from the provider account that created it.

Users in a reader account can query data that has been shared with it, but cannot perform any of the DML tasks that are allowed in a full account (data loading, insert, update, etc.).



## Data Consumer

## Data Producer

[Return to Data Processing](../Data-Processing.md)
