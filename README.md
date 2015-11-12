# question3

Assume a database with the following structure:

Members
ID
NAME 
ADDRESS
PHONE NUMBER
AGE

Organization
ID
MEMBER_ID
LOCATION
DUES
 
-------------------------------------------------------------------------------------------------------
 
Write a query that lists each member name, address, dues and location.

SELECT name, address, dues, location FROM members LEFT JOIN organization ON members.id = organization.member_id
  (assumptions: Displays null for location/dues if member is not part of an org.  Assumes no duplicate records in Organization table.  Assumes that Members.id is primary key and that there is no way to identify duplicates in Members table.)
  
-------------------------------------------------------------------------------------------------------
Write a SQL Query to pull all members that are over 45

SELECT name FROM members WHERE age > 45   

--------------------------------------------------------------------------------------------------------

Write a SQL Query to pull all members that have a dues value of 0.

SELECT DISTINCT members.id, name FROM members LEFT JOIN organization ON members.id = organization.member_id WHERE dues = 0
  (assumptions: If a member has zero dues for one organization but nonzero dues for another organization, the record is still returned.  If a member has zero dues for more than one organization, the record is only returned once.)
