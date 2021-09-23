# Catalina Digital - Backend Hiring Test

This test is part of our hiring process for Rails developers. [Apply now](https://www.linkedin.com/jobs/view/2593042141/?refId=ovvdoqLmKpMS6xrf8%2BKvXQ%3D%3D&trackingId=uI5TYGRH01SO9mRsjQ5UgA%3D%3D)

## Context
As a talented developer, you are hired in a company which is creating a new backend solution for the government.
This solution permits to list available vaccines for a country and fullfill injections made.

I - Features
--
### Develop backoffice views :
> no design needed - scaffold accepted
1. Create/Read/Delete country :
* *Required fields :*
  - name: string, 
  - reference: string
2. Create/Read/Update/Delete vaccine :
* *Required fields :*
  - name: string, 
  - reference: string, 
  - composition: long text, 
  - vaccine booster delay in days : integer, 
  - mandatory: boolean, 
  - countries in which vaccine is available: array of countries

### Develop a rake task to import datas 
> csv files - separator ";" - no header

> Pay attention to performance : file can countain millions of lines
1. Vaccinated people containing : 
  - user reference, 
  - vaccine reference, 
  - last vaccination date *(format : YYYY-MM-DD)*

### Develop RESTful APIs
1. List vaccines available for a country
- order by : 
  - vaccine not administered but mandatory
  - vaccine not administered not mandatory
  - vaccine administered
- input parameters : 
  - country reference (mandatory)
  - user reference (optional)
- output : An array of vaccines available for the country containing :
  - vaccine reference
  - vaccine name
  - vaccine composition
  - mandatory yes/no
  - percentage of vaccinated people for the country
  - next vaccination booster date for current user if present
  - Array of countries for which vaccine is available

2. Mark a vaccin as injected for a member
  > It can be a booster of an existing vaccine (imported with rake task) or a first injection.
  - input parameters : 
    - user reference
    - vaccine reference
  - output : errors / empty if success

II - Technical specifications
--
1. Must be written in Ruby on Rails or PHP Laravel
2. Pay attention to performance : Application should be able to work for thousands of vaccines / millions of users
3. It must be fully tested (you can use gem of your choice).
4. Spend as much time as you need to build it up, don't pay too much attention on backoffice views


III - What do we judge ?
--
1. Overall quality and readability of the code
2. The way you structure the project
3. Performance optimizations
4. Quality of your tests
5. Design pattern you tried to use
