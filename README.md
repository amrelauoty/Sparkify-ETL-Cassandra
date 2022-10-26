# Sparkify ETL

## Table of contents
- [Sparkify ETL](#sparkify-etl)
  - [Table of contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Tools](#tools)
  - [Usage](#usage)
  - [Keyspace Design](#keyspace-design)
  - [Project Files](#project-files)

## Introduction

A startup called **Sparkify** wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. 
The analysis team is particularly interested in understanding what songs users are listening to.

We want to answer those 3 queries

* Give me the **_artist_**, **_song title_** and **_song's length_** in the music app history that was heard during  **_sessionId_** = 338, and **_itemInSession_**  = 4
* Give me only the following: **_name of artist_**, **_song (sorted by itemInSession)_** and _**user (first and last name)_** for **_userid_** = 10, **_sessionid_** = 182
* Give me every **_user name (first and last)_** in my music app history who listened to the song 'All Hands Against His Own'

The ETL extracts the data from event files and but it in a new file called `event_datafile_new` then get the required data for creating Cassandra tables depending on the query.

The database used in the project is **Apache Cassandra**

## Tools

<p style="float:left">
<img src='./images/python.svg' alt="python" title="python"/><img src='./images/cassandra.svg' alt="cassandra" title="cassandra" width="100" height="48"/>
</p>
<div style="clear:both">

## Usage
To run the ETL open `ETL.ipynb` and execute the code sections one by one to create the keyspace and the table and executing the queries

## Keyspace Design

The keyspace contains 3 tables (one table according to each query)

## Project Files

`ETL.ipynb` : 
* the file contains the process of to collect the data from all files to one new `CSV` file
* Connect to cassandra with a cluster then creating a session
* Creating the keyspace for the tables and setting the replication configurations 
* Creating the tables for every query and test the select statement to ensure that result is right
* Dropping the tables and closing the connection