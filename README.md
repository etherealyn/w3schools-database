# W3Schools Parquet Database

This repository is a fork of [AndrejPHP](https://github.com/AndrejPHP)'s [w3schools-database](https://github.com/AndrejPHP/w3schools-database)

I used the [Apache Spark](https://github.com/apache/spark) engine to read and translate the original SQL file to [Parquet](https://github.com/apache/parquet-mr).

Motivation: sometimes to test a feature in Spark, one needs to quickly access a database with a meaningful schema especially if you're coming from relational background. Feel free to use it.

In Spark, you can read the tables as DataFrames like this:

```scala

val repoRoot = "/home/etherealyn/source/repos/w3schools-database/parquet" // change to your own path

val customers = spark.read.parquet(s"file://$repoRoot/customers")
val categories = spark.read.parquet(s"file://$repoRoot/categories")
val employees = spark.read.parquet(s"file://$repoRoot/employees")
val orders = spark.read.parquet(s"file://$repoRoot/orders")
val orderDetails = spark.read.parquet(s"file://$repoRoot/order_details")
val products = spark.read.parquet(s"file://$repoRoot/products")
val shippers = spark.read.parquet(s"file://$repoRoot/shippers")
val suppliers = spark.read.parquet(s"file://$repoRoot/suppliers")

```

> I'm not associated with W3Schools but I have to give them a big shout-out. This is their website:
> https://www.w3schools.com
> 
> They provide excellent tutorials on the topic of web development. More than 15 years ago in the early 2000s when I was barely a teenager, I discovered their site and that's when I became interested in web development and started learning things little by little.
> 
> Anyway this repository contains the database they use for their SQL tutorial here:
> https://www.w3schools.com/sql/default.asp
> 
> You can see the database tables and the data on the right hand side if you run this example:
> https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all

> However, there is nowhere a link to download the database so I decided to create a SQL code for it which I hope you'll find useful because it is nice to have this database locally where you can perform all sorts of SQL queries, tests, for practicing and learning purposes etc. Enjoy!

> When the SQL file is executed it creates database named __w3schools__ with the following tables

    categories
    customers
    employees
    orders
    order_details
    products
    shippers
    suppliers
    
> and inserts the respective data. 

> You can change the database name if you want by modifying these 2 lines of code

    CREATE DATABASE IF NOT EXISTS `w3schools`
    USE `w3schools`;
