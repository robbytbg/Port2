1. **Select a Database:** 
  - I've made sure to choose the database from which I wish to import the information. Using the "Navigator" panel, I completed this.

2. Utilizing the Quick Database Diagram, **Open SQL Script from** 
  - I utilized the `CREATE TABLE} commands and foreign key relationships included in the SQL script that Quick Database Diagram created.

3. **Execute SQL Script:** 
  - To build the required tables and relationships in my chosen database, I ran the SQL script in MySQL Workbench.

```
-- Exported from QuickDBD: https://www.quickdatabasediagrams.com/
-- Link to schema: https://app.quickdatabasediagrams.com/#/d/NqTsR5
-- NOTE! If you have used non-SQL datatypes in your design, you will have to change these here.


CREATE TABLE `Campaign` (
    `cf_id` INTEGER  NOT NULL ,
    `contact_id` INTEGER  NOT NULL ,
    `company_name` VARCHAR(50)  NOT NULL ,
    `blurb` VARCHAR(255)  NOT NULL ,
    `goal` INTEGER  NOT NULL ,
    `pledged` INTEGER  NOT NULL ,
    `outcome` VARCHAR(50)  NOT NULL ,
    `backers_count` INTEGER  NOT NULL ,
    `country` VARCHAR(50)  NOT NULL ,
    `currency` VARCHAR(50)  NOT NULL ,
    `launched_at` DATE  NOT NULL ,
    `deadline` DATE  NOT NULL ,
    `category_id` INTEGER  NOT NULL ,
    `sub_category_id` INTEGER  NOT NULL ,
    PRIMARY KEY (
        `cf_id`
    )
);

CREATE TABLE `Sub_category` (
    `sub_category` VARCHAR(50)  NOT NULL ,
    `sub_category_id` INTEGER  NOT NULL ,
    PRIMARY KEY (
        `sub_category_id`
    )
);

CREATE TABLE `Category` (
    `category` VARCHAR(50)  NOT NULL ,
    `category_id` INTEGER  NOT NULL ,
    PRIMARY KEY (
        `category_id`
    )
);

CREATE TABLE `Contact` (
    `contact_id` INTEGER  NOT NULL ,
    `email` VARCHAR(100)  NOT NULL ,
    `first_name` VARCHAR(100)  NOT NULL ,
    `last_name` VARCHAR(100)  NOT NULL ,
    PRIMARY KEY (
        `contact_id`
    )
);

ALTER TABLE `Campaign` ADD CONSTRAINT `fk_Campaign_contact_id` FOREIGN KEY(`contact_id`)
REFERENCES `Contact` (`contact_id`);

ALTER TABLE `Campaign` ADD CONSTRAINT `fk_Campaign_category_id` FOREIGN KEY(`category_id`)
REFERENCES `Category` (`category_id`);

ALTER TABLE `Campaign` ADD CONSTRAINT `fk_Campaign_sub_category_id` FOREIGN KEY(`sub_category_id`)
REFERENCES `Sub_category` (`sub_category_id`);


```

4. Click to launch the Table Data Import Wizard: 
  - I navigated to the particular database where I wanted to import the data using the "Navigator" panel.
  - I made a new table or performed a right-click on the table where I wanted to import the data.
  - I went with the "Table Data Import Wizard."

5. **Select CSV File:** 
  - I selected the "Import from File" option in the "Table Data Import Wizard."
  - I choose the data-containing CSV file.

6. **Columns on the Map:**
  - The wizard tried to automatically translate my CSV file's columns to my MySQL table's columns. I checked to make sure the mapping was accurate.

