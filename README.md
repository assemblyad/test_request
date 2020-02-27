# test_request
Explanation for used abbreviations can be found in the end of this file.

1.	Next assumptions made: 
	a.	The Application under test:
		i.	QA exception criteria passed
			1.	Passed sanity test and intergradation test successfully or any other QA testing practice implemented in the company 
		ii.	QA exit criteria will be passed
			1.	All planned Regression test will be run after or in parallel of new feature testing
			2.	All defects targeted for closure after or before code freeze in this release have been closed
			3.	Or any other QA testing practice implemented in the company
		iii.The meeting involving QA representative to bring up recommendations will take a place to review test results and take decisions for moving release/sprint into UAT or production.
		iv.	Enough time allocated for testing 

2.	Coverage – The coverage expected to cover 100% of BR to find out and report all possible defects
	a.	The top priority are TCs with business logic that represents actual day by day business
	b.	The second priority are less common and negative scenarios
	c.	Each TC has Reference Requirement and short Test Description of scenario to promise 100% of coverage.

	Please note: I didn’t specify any priorities for these TCs because of taken assumption that enough time allocated for testing this specific BR.

3.	Instructions for Test Case - New Enhanced excel file:
	The TCs written for OS Windows 10 and can be executed on Ubuntu 16.04 and Mac OS X - Sierra, High Sierra or nay other OSs.
	I tested BR only on Windows 10 and recommend to execute TCs on other OS as well.
	There are 3 excel worksheets
	1.	Functional - Test Cases:  Listed all functional test case written for this BR
	2.	Non-Functional - Test Case: Listed all non-functional test case written for this BR
	3.	FunctionalTest Execution Report: Test execution report for functional testing, including summary of pass, failed and blocked TCs for execution.

	a. You can find attached screen shots of failed TCs with TC reference number in the file name.
	b. The functional and non-functional worksheets include different columns to make the test case clear for everyone who reads this document.
	   These columns as following:  Test Case #, Reference Requirement, Test Type, Functional Area, OS Under Test , Test Description, Web service method , Endpoint , Resource, Body, Response, Test Steps, Expected Result, Test case status, Tester, Test Writer, Comments, Execution date, Data, Population, Database
		
		Example: In column Test Steps you will find cells divided into parts or two sections: 

			The first one is  “Precondition”  this is what QA engineer required to implement / check  prior to the test execution in order to promise that only required functionality will be under test. 
			The other section called “Test steps”, this section includes test steps required to execute to validate functionality.
			The next column in excel file is “Expected Result” where you can find expected results as per executed Test Step. If no test step mentioned the it applies to all section “Test steps” from Test Steps column.

	c. As for now I wrote reported defect description in Comment column. Normally there should be separate column named defect # where QA should populate defect number.
	   The comment column can be useful for additional information of research made by QA engineer.
	  

4.	Reported defects: 
	1.	TC#2:  
	Short Description: Launching application without internet connection
	Problem:  The application operates even when no internet connection is established
	Recommended solution: The BR asking to http connection but can run without it. Using my knowledge and scope of BR, I could not find real reason why this HTTP connection really required. So, I recommend to go UAT or Production and supply fix later.
	2.	TC#7: 
	Short description:  Validate if job identifier is returned immediately within POST request for password hash
	Problem: The response for POST request with Job Identifier # takes always more than 5 takes
	Recommended solution:  I would strongly recommend to fix that one before delivery because it is a lot of time in the IT world with fast internet. But I would not say this is highest priority since any way the computed password hash will be generated only after 5 seconds of wait time.
	3.	TC#11:
	Short description: Send GET request for stats validation doesn’t work correctly
	Two problem reported
	Problem #1: Inconsistent behavior happens for POST Stats Web Service . It returns sometime ZERO for request average time when POST requests send out . I saw that this happens during first time of period but after that time it returns value.
	I could not identify how long last this period but too long.
	Problem #2: The number that Stats Web Service returns for average time of POST requests is wrong and too big. 
	It seems as value got multiple by 1000 instead of to be divided by 1000 before sending out in response.
		   Recommended solution: I would recommend to fix both found issues. 
			 The problem #2 This one doesn’t seems to be risky to fix. Instead of multiplication by 1000 use division by 1000.
			 The problem #1 Though sometimes it returns zero it does work after certain time. So in principal the functionality does work but still small fix required. This can be debugged and fixed.
5.	The TCs written in the detailed format to promise that that anyone with different knowledge level is capable to execute them and it also make it easy for automation later.

Abbreviation for Glossary: 
BR – Business requirements 
UAT– User Acceptance Test
# - Number
OS – Operating system 
TC – Test Case is singular and TCs is plural
AUT – Application Under Test

