# Assignment 3 - Initial CUJ

## Group and Submission Details
**Team Name**: Team Achievo (formerly CatPnadas)

**Team Members**:
- Hongzip Kim - 1007637826 
- Anushka Sharma - 1008060704 
- Zoey Xie - 1009001465
- Cynthia Zhou - 1009028918
- Kathy Lee (CSC454 only) - 1007276314

**Submission Date**: 2025/09/21

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
Purr is a student and software engineer. Purr’s expertise level in databases is intermediate and has not used Databricks SQL Warehouse/Editor before. However, Purr has previous coding experience in Python, SQL and other database warehousing software.

**Tools Used**: Google, Python IDE, Databricks (SQL Warehouse, SQL Editor, AI Code assistant), ChatGPT for local debugging

</td>
</tr>
</table>

Putting ourselves in the shoes of our persona, Purr, our overall experience in achieving our goal was relatively smooth, especially considering it was our first time using Databricks. Our aim is to incorporate Databricks into our product workflow, we were glad to be able to test how data could be stored and retrieved from a SQL Warehouse. One of the highlights was the seamless integration between Python and the Databricks SQL Warehouse. Although the initial setup took some time, once established, the development process was smooth and efficient. 

What didn’t work as smoothly was managing permissions– including granting access to other group members, as well as managing permission/viewability settings. That said, once those were sorted out, everything else came hand in hand. Please refer to the table below for a summary of our highlights and pain points. 


**Highlights and Lowlights Table**:
| Task | Experience | Note |
|:---|:---|:---|
| Local Setup | Moderate | Understanding how to navigate Databricks as first-time users, doing our research, and figuring out how to connect to Python on a local app is easy but requires many steps |
| Local Development | Severe | We ran into some errors while connecting Databricks with our local app, such as [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed error, which was difficult to debug |
| View Result | Great | Being able to see our test data in a database and be able to easily query it using SQL |
| Permission Setup | Severe | Grant permission to others requires a lot of manual steps for the administrator |
| Debug | Moderate | AI Code Assistant is helpful, and there are some documentation online |

The usability of Databricks was good, considering it was our first time using the platform. While the initial learning curve was steep, once we understood the interface and features, it became much easier to collaborate within a shared workspace, and be able to see metrics and insights in real time. One feature of using Databricks which we enjoyed was being able to see all past queries, and the UI makes it easy for us to identify when tasks failed/completed. Using the AI Code Assistant made it easy for us to debug and help us solve our permission setting issues. By integrating Python as our backend, and connecting with SQL Warehouse, we were able to feed in data, which was easily visualised in Databrick’s SQL Editor. This made it easy to test our code, and see if it provided the desired output. This allowed us to ensure that our task was completed and was correct.

As aforementioned, the pain points and moments of confusion lied around setting it up and trying to solve permission issues. However, the Code Assistant within Databricks made it very helpful for us to understand how our group admin workspace permissions can be granted to other developers. We took proactive measures to ensure that everyone had access and could check the code by sharing our screen and walking through each step together. This collaborative measure made it easy for us to resolve any pain points swiftly. 

The key insights and purpose of using this alludes to our product - we fed in data, which would include assignment deadlines, as well as student schedules. By understanding the database section of our technical feature, it makes it easy for us to identify how our table is to be constructed, and the design feature, such that we plan ahead and ensure that we don’t run into future errors of missing certain fields or not being able to manage our data correctly. This also comes into data privacy issues if on a broader scale, hence, understanding how our data is stored is essential at an early stage.  We saw, from this exercise, how we can integrate Databricks and understand how to resolve permission settings. In future scenarios where we run into similar issues, we understand how to resolve it quickly.  Refer to our Full CUJ Table for a step-by-step documentation of our process. 


## Recommendations

**Product Recommendations**: 
Providing a more detailed section on setting up Databricks for a project for first-time users, particularly regarding how to address issues that we may run into, such as Python version compatibility with Databricks connector library, as well as how how fix specific errors such as `[SSL: CERTIFICATE_VERIFY_FAILED]` error, which is something we ran into multiple times. 

When we try to grant developers permission to use the SQL editor, the owner/administrator must perform many small steps using SQL commands. For example:
```
GRANT USE CATALOG ON CATALOG workspace TO <your_username_or_group>;
GRANT USE SCHEMA ON SCHEMA workspace.schedules_db TO <your_username_or_group>;
GRANT SELECT ON TABLE workspace.schedules_db.assignments TO <your_username_or_group>;
```
Instead of requiring manual SQL commands for every case, there could be an interface to simplify management. This interface could also provide a button that allows developers to request permissions directly from the administrator.

**Recommendations for Future Users**:
If running into errors on the Databricks UI, be sure to use the Code Assistant feature as it provides helpful guidance. If in a group setting, working collaboratively will ensure that issues that revolve around permission issues can be swiftly resolved. Be sure to clearly outline which tools each potential collaborator will be using. This will help when setting up user permissions due to its tedious nature.

## CUJ Overview
| Task | Time | Switches |
|:---|:---|:---|
| Create Databricks account | 3 min | 2 |
| Generate Access Token | 2 min | 5 |
| Write code | 20 min | 4 |
| Grant permissions to others | 10 min | 2 |
| Debug Errors | 60 min | 2 |
| Testing | 20 min | 2 |

**Total time**: 115 mins \
**Total switches**: 17 switches

## Detailed CUJ
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
  
  <tr>
  <td>
    2
  </td>
  <td>
  Created a Databricks account by linking with Google account
  </td>
  <td width="550">
    <img width="3022" height="1644" alt="image" src="https://github.com/user-attachments/assets/37e3ddf4-31d2-4920-871f-c3c64b8bb713" />
  </td>
  </tr>
  
  <tr>
  <td>
    3
  </td>
  <td>
  Navigate to Access tokens tab in Developer settings
  </td>
  <td width="550">
    <img width="1954" height="1070" alt="image" src="https://github.com/user-attachments/assets/7c7e2029-df9e-4b28-8aa3-3d6b275a7978" />
  </td>
  </tr>
  
  <tr>
  <td>
    4
  </td>
  <td>
  Click Generate new token & copy your token for future use
  </td>
  <td width="550">
    <img width="1442" height="604" alt="image" src="https://github.com/user-attachments/assets/21405582-b3e1-4569-981d-aba814d8ad44" />
  </td>
  </tr>

  <tr>
  <td>
    5
  </td>
  <td>
  Open SQL Warehouse & click on Create SQL Warehouse 
  </td>
  <td width="550">
    <img width="1468" height="670" alt="image" src="https://github.com/user-attachments/assets/0d056b90-7272-4b8d-b5ad-6da7d0241598" />
  </td>
  </tr>

  <tr>
  <td>
    6
  </td>
  <td>
  Navigate to to Connection details tab
  </td>
  <td width="550">
    <img width="887" height="281" alt="image" src="https://github.com/user-attachments/assets/efcc39ba-d651-42bc-86f1-b33c44bc835e" />
  </td>
  </tr>

  <tr>
  <td>
    7
  </td>
  <td>
  Copy your Server hostname and HTTP path, & store in a file for future use
  </td>
  <td width="550">
    <img width="1292" height="437" alt="image" src="https://github.com/user-attachments/assets/2b878ba5-868f-4d02-b42f-1365eb05d0db" />
  </td>
  </tr>

  <tr>
  <td>
    8
  </td>
  <td>
  Install SQL Connector for Python library, i.e. `databricks-sql-connector` 
  </td>
  <td width="550">
    <img width="803" height="120" alt="image" src="https://github.com/user-attachments/assets/7ccdf110-bd45-4b83-a306-faf86e84f5e7" />
  </td>
  </tr>

  <tr>
  <td>
    9
  </td>
  <td>
  Copy sample Python code and open IDE
  </td>
  <td width="550">
    <img width="818" height="732" alt="image" src="https://github.com/user-attachments/assets/54859d21-b59d-43d3-b4ff-b2b4a01eac85" />
  </td>
  </tr>

  <tr>
  <td>
    10
  </td>
  <td>
  Paste copied code into Python file, and set `server_hostname`, `http_path`, and `access_token` parameters, and set ` _tls_no_verify=True` to avoid certificate-related errors
  </td>
  <td width="550">
    <img width="891" height="34" alt="image" src="https://github.com/user-attachments/assets/26e926ee-0581-460b-bad3-9faf4a751e9b" />
  </td>
  </tr>

  <tr>
  <td>
    11
  </td>
  <td>
  Use a cursor object to create a database and your desired table(s) by running `cursor.execute()` with your SQL query. Close your cursor & connection when done
  </td>
  <td width="550">
    <img width="572" height="272" alt="image" src="https://github.com/user-attachments/assets/16180f48-fa12-48f8-a410-4180f25c126a" />
    <img width="155" height="52" alt="image" src="https://github.com/user-attachments/assets/430cc0e1-59cd-4b7c-8dcb-313650d7b8e6" />
  </td>
  </tr>

  <tr>
  <td>
    12
  </td>
  <td>
    Try testing, debug when running into errors
  </td>
  <td width="550">
    <img width="1225" height="102" alt="image" src="https://github.com/user-attachments/assets/ecee6143-801e-465f-a7f9-4344c2e46390" />

  </td>
  </tr>

  <tr>
  <td>
    13
  </td>
  <td>
  Local testing with SQL command
  </td>
  <td width="550">
    <img width="340" height="87" alt="image" src="https://github.com/user-attachments/assets/5c0fb9f9-123d-4f9d-b9dc-84422842ca24" />
  </td>
  </tr>

  <tr>
  <td>
    14
  </td>
  <td>
  Add developers to the workspace in Settings (click Manage beside Users section in the Identity and access tab)
  </td>
  <td width="550">
    <img width="1157" height="541" alt="image" src="https://github.com/user-attachments/assets/44e708c9-3825-4e23-9fab-860129f03bb1" />
  </td>
  </tr>

  <tr>
  <td>
    15
  </td>
  <td>
  Grant other developers permission to warehouse
  </td>
  <td width="550">
    <img width="1285" height="505" alt="image" src="https://github.com/user-attachments/assets/d4a449c5-a9e1-4615-8a4b-93fb50d94eb1" />
  </td>
  </tr>

  <tr>
  <td>
    16
  </td>
  <td>
    Try testing on SQL Editor in Databricks UI, discover permission issue for other developers, debugging with AI
  </td>
  <td width="550">
    <img width="1020" height="530" alt="image" src="https://github.com/user-attachments/assets/9183a9a0-5d78-43e8-9124-a0467a3b19c5" />
    <img width="1250" height="584" alt="image" src="https://github.com/user-attachments/assets/4097db59-8a21-453f-a1c7-fa3add197cf3" />
  </td>
  </tr>

  <tr>
  <td>
    17
  </td>
  <td>
    Final testing on SQL Editor
  </td>
  <td width="550">
    <img width="1266" height="683" alt="image" src="https://github.com/user-attachments/assets/0e21ad6d-2ff0-4fde-a005-eb16a95d9804" />
  </td>
  </tr>

</table>
