# sample_postgresql_database

## 1- Introduction

Welcome! This **PostgreSQL** repository will help you to understand PostgreSQL quickly with examples and sample database (**imdb**). 
In this repository's database (imdb), you will be introduced to a PostgreSQL sample database that you can use for learning and practice PostgreSQL.

We will use the imdb database for demonstrating the features of PostgreSQL. This database is built up personally for learning purpose. The main purpose of this task was to get familiar with PostgreSQL and python adaptor of PostgreSQL (psycopg2). 

## 2- Layout

![](https://github.com/raosaif/sample_postgresql_database/blob/master/images/detailed_relationship_layout.jpg)

### 2.1- Relationship Layout

![](https://github.com/raosaif/sample_postgresql_database/blob/master/images/relationship_layout.jpg)

#### This relationship is generaed by [omnidb](https://omnidb.org/en/)

### 2.2- Tabular Layout

![](https://github.com/raosaif/sample_postgresql_database/blob/master/images/tabular_layout.jpg)

#### This tabular relationship is generated by [SchemaSpy](http://schemaspy.sourceforge.net/)

For detail overview of the tables, please navigate to [Schema](https://github.com/raosaif/sample_postgresql_database/tree/master/schema) folder and click the index.html file. 

## 3- Overview

### 3.1- There are 11 tables in the imdb database:

1- **actors** – stores actors data including name and actor_id.

2- **contents** – stores films/tv_shows data such as title, release_year,content_rating,user_voting, etc.

3- **content_actors** – stores the relationships between contents and actors.

4- **content_types** – stores content types.

5- **content_ratings** - stores content ratings. https://en.wikipedia.org/wiki/TV_parental_guidelines_(US)

6- **content_directors** - stores the relationships between contens and directors.

7- **content_genres** - stores the relationships between contents and genres.

8- **directors** - stores the information about directors including name and director_id.

9- **genres** - stores the information about imdb genres. http://www.imdb.com/feature/genre/?ref_=tt_ov_inf

10- **episode_list** - stores the inforamtion about episodes for each season of the tv shows.

11- **languages** - stores the information about the languages. (independent table)

## 4- Restoring IMDB Database

### 4.1- Creating a new IMDB database

You need to [create a new database](http://www.postgresqltutorial.com/postgresql-create-database/) in the PostgreSQL database server before loading database schema and data into the database.

First, launch the psql tool.

Second, enter account’s information to login to the PostgreSQL database server.

Third, enter the following statement to create a new dvdrental database.

```
CREATE DATABASE imdb;
```
PostgreSQL will create a new database named dvdrental.

There are multiple ways of loading imdb database

### 4.2.1- from_imdb folder
Navigate to from_imdb directory and run the below command. You will need [beautiful soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/), [urrlib](https://urllib3.readthedocs.io/en/latest/), and [psycopg2](http://initd.org/psycopg/docs/) for this operation. 

#### 4.2.1.1- Pre-Requisites
You need to input username, password, host, and database name in the imdb_upload_data.py file.

![](https://github.com/raosaif/sample_postgresql_database/blob/master/images/from_imdb_detail.jpg)
```
python3 imdb_upload_data.py
```
### 4.2.2- from_csv

Navigate to from_csv directory and run the below command. from_csv parse the csv files available under the csv_files and upload the data to the db. You will need [psycopg2](http://initd.org/psycopg/docs/) for this operation.

#### 4.2.2.1- Pre-Requisites
You need to input username, password, host, and database name in the imdb_upload_data.py file.

![](https://github.com/raosaif/sample_postgresql_database/blob/master/images/from_imdb_detail.jpg)

```
python3 uploading_from_csv.py
```

### 4.2.3- via pg_restore command. 

Navigate to from_pg_restore directory and run the command 

```
pg_restore -u user -n public -d databasename '/path/to/imdb.tar' 
```

### 5- Supported Platforms:

- Linux
- Windows
- OS X
