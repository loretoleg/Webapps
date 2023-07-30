My program is a serverless AWS Lambda function that generates a customized report for a given cistern (storage container) based on data provided in an Excel file. The function is triggered by an HTTP request containing JSON data with relevant parameters, such as the recipient email, cistern number, and the type of report to be generated. This is the continuation of https://github.com/loretoleg/Code

Here's a brief description of the program's functionality:

HTTP Trigger: The program is triggered by an HTTP request, which includes a JSON payload containing necessary parameters for generating the report, such as the recipient's email address, cistern number, and the type of report to be generated.

Data Retrieval: The function retrieves the data required to generate the report from an external Excel file. It downloads the Excel file using an authorization token provided as an environment variable.

Data Processing: The downloaded data is processed using the Pandas library to filter and aggregate the relevant information related to the specified cistern number. The data is then transformed and organized into a DataFrame suitable for generating the report.

Report Generation: The program generates a detailed report for the specified cistern number. The report includes information about the amount of liquid received and dispatched on each date, as well as the total balance for the cistern. The data is organized into pages to accommodate large datasets.

Excel Templating: The report is generated based on an Excel template (provided as "Plantilla_Cisternas.xlsx"). The program uses the "openpyxl" library to load the template, insert the data into specific cells, and save the modified Excel file.

Email Notification: After generating the report, the program sends an email notification to the recipient's email address. The email contains the customized Excel report as an attachment. For sending emails, the program uses the "smtplib" library and MIME (Multipurpose Internet Mail Extensions) components to create the email message with the attachment.

Observation: An observation about the cistern's status is appended to each page of the report. The observation includes details such as the total quantity received, total quantity dispatched, and the remaining balance for the cistern.

Error Handling: The program includes error handling to catch and handle exceptions that may occur during data retrieval, processing, report generation, or email sending. If any error occurs, an appropriate error message is returned to the caller.

Overall, this program streamlines the process of generating customized reports for specific cisterns, automating the data extraction and formatting tasks while allowing easy distribution of the reports via email.
