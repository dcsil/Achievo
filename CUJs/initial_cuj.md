# Assignment 3 - Initial CUJ

## Group and Submission Details
**Team Name**: Team Achievo (formerly CatPnadas)

**Team Members**:
- Hongzip Kim - 1007637826 
- Anushka Sharma - 1008060704 
- Zoey Xie - 1009001465
- Cynthia Zhou - 1009028918
- Kathy Lee (CSC454 only) - 1007276314

**Submission Date**: 2025/09/2#

## Summary of Findings
We tested storing text-based data into a SQL warehouse using Python and Databricks to validate database integration later for our Chrome extension. This process is essential for building the backend pipeline that turns a user’s syllabi into structured, queryable tasks.

**User Goal**:
As a software developer/database engineer, I want to test how text data can be stored in our database, so that I can ensure any given dataset is correctly saved and retrievable.

## Detailed Summary of Findings
<table>
<tr>
<td width="150">
  <img width="121" height="159" alt="image" src="https://github.com/user-attachments/assets/bc0070d1-3f7c-4823-a79d-e829292bd155" />
</td>
<td>

**User Persona**: Purr (Our cat mascot & spiritual animal)  
Purr is a software engineer. Purr’s expertise level in databases is intermediate and has not used Databricks SQL Warehouse/Editor before. However, Purr has  previous coding experience in Python, SQL and other database warehousing software.

**Tools Used**: Python, Databricks (SQL Warehouse and SQL Editor)

</td>
</tr>
</table>

Putting ourselves in the shoes of our persona, Purr, our overall experience in achieving our goal was relatively smooth. We wanted to try to incorporate Databricks into our product design, and given it was our group’s first time using it, we were glad that we were able to figure out how to connect to the SQL Warehouse and Editor to achieve our proposed goal. What worked really well was the seamless integration of using Python to connect directly to the warehouse, once we figured out how to set it up, as it took some time. What didn’t work as smoothly was figuring out the permissions - including giving access to other developers within our group, as well as managing permission/viewability settings. Once those were sorted out, everything else came hand in hand. Please see the table below for  a summary of our highlights, and lowlights. 


**Highlights and Lowlights Table**:
| Task | Experience | Notes |
|:------|:------------|:------|
| Local setup + development | Severe | Understanding how to navigate Databricks as first-time users, doing our research and figuring out how to connect to Python on a local app. We ran into some errors while connecting Databricks with our local app, such as [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed error, which was difficult to debug |
| View Result | Great | Being able to see our test data in a database and be able to easily query it using SQL. |
| Permission Set up | Severe | Grant permission to others requires a lot of manual steps for the administrator |
| Debug | Great | AI assistant is helpful + a lot of documentation online |

The usability of Databricks was good. As it was our first time using it, we weren’t that familiar with it. But once we learned it, we realized how we could collaborate on the same workspace, and be able to see metrics and insights in real time. One feature of using Databricks which we enjoyed was being able to see all past queries, and the UI makes it easy for us to identify when tasks failed/completed and the Code Assistant made it easy for us to debug and help us solve our permission setting issues. By integrating Python as our backend, and connecting with SQL Warehouse, we were able to feed in data, which was easily visualised in Databrick’s SQL Editor. This made it easy to test our code, and see if it provided the desired output. This allowed us to ensure that our task was completed and was correct.

As aforementioned, the pain points and moments of confusion lied around setting it up & trying to solve permission issues. However, the Code Assistant within databricks made it very helpful for us to understand how our group admin workspace permissions can be granted to other developers. We took proactive measures to ensure that everyone had access and can check the code by sharing our screen and walking through each step together. This collaborative measure made it easy for us to resolve any pain points swiftly. 

The key insights and purpose of using this alludes to our product - we fed in data, which would include assignment deadlines, as well as student schedules. By understanding the database section of our technical feature, it makes it easy for us to identify how our table is to be constructed, and the design feature, such that we plan ahead and ensure that we don’t run into future errors of missing certain fields or not being able to manage our data correctly. This also comes into data privacy issues if on a broader scale, hence, understanding how our data is stored is essential at an early stage.  We saw, from this exercise, how we can integrate Databricks and understand how to resolve permission settings. In future scenarios where we run into similar issues, we understand how to resolve it quickly.  Refer to our Full CUJ Table for a step-by-step documentation of our process. 

## Recommendations

**Product Recommendations**: 
Perhaps providing a more detailed section on setting up Databricks for a project for first-time users, particularly regarding how to address issues that we may run into, such as python version compatibility with databricks connector library, as well as how how fix specific errors such as `[SSL: CERTIFICATE_VERIFY_FAILED]` error, which is something we ran into multiple times. 

**Recommendations for Future Users**:
If running into errors on the Databricks UI, be sure  to use the Code Assistant feature as it provides helpful guidance. If in a group setting, working collaboratively will ensure that issues that revolve around permission issues can be swiftly resolved. 

## CUJ Overview
| Task | Time | Switches |
|:---|:---|:---|
| Create Databricks account | 3 min | 2 |
| Generate Access Token | 2 min | 5 |
| Write code | 20 min | 3 |
| Grant permissions to others | 10 min | 1 |
| Debug Errors | 30 min | 2 |
| Testing | 20 min | 2 |


## Detailed CUJ
full CUJ table

<table>
  <tr>
    <th>Step</th>
    <th>Notes (What + Why)</th>
    <th>Screenshot</th>
  </tr>
  
  <tr>
  <td>
    1
  </td>
  <td>
  Googled “Databricks free version” to create an account
  </td>
  <td width="550">
    <img width="3022" height="1644" alt="image" src="https://github.com/user-attachments/assets/16f5206a-ce19-459f-905f-d635ef7cd64e" />
  </td>
  </tr>

</table>
