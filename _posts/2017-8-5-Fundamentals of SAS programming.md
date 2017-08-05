---
layout: post
title: Fundamentals of SAS programming
published: false
---

### Rules for SAS statements

1. All SAS statements (except those containing data) must end with a semicolon (;). 
  Example : "DATA example1;" is an example of a SAS statement.
2. Any number of SAS statements can appear on a single line provided they are separated by a semicolon.
  Example : "DATA example1; Input Name $ ID;" is an example of a SAS statement.
3. SAS statements typically begin with a SAS keyword. (DATA, PROC)
4. SAS statements are not case sensitive, that is, they can be entered in lowercase, uppercase, or a mixture of the two.
  Example : SAS keywords (DATA, PROC) are not case sensitive
5. A delimited comment begins with a forward slash-asterisk (/*) and ends with an asterisk-forward slash (*/). All text within the            delimiters is ignored by SAS.  
6. SAS names are not case sensitive, that is, they can be entered in lowercase, uppercase, or a mixture of the two. (SAS is only case sensitive within quotation marks.)
7.If the variable in the INPUT statement is followed by a dollar sign ($), SAS assumes this is a character variable. Otherwise, the variable is considered as a numeric variable

### DATA Steps

Any portion of a SAS program that begins with a DATA statement and ends with a RUN statement is called a DATA Step. 
DATA steps are used to manage data.  In detail, DATA steps are used to read raw or external data into a SAS data set, to modify data values, and to subset or merge data sets.

### PROC Steps (Procedures)

Any portion of a SAS program that begins with a PROC statement and ends with a RUN statement is called a PROC Step or Procedures. 
PROC steps are in-built programs that allow us to analyze the data contained in a SAS data set. PROC steps are used to calculate descriptive statistics, to generate summary reports, and to create summary graphs and charts.



