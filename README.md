# ExpenseReportApp
The Expense Report App is a Power Platform application that utilizes Power Apps, Power Automate, and Power BI to streamline expense management and reporting. This README provides an overview of the app's features and functionality.

## Features

The Expense Report App consists of several screens and workflows that work together to provide a comprehensive expense management solution:

### Power Apps

#### Screen 1: View Expenses

- View expenses: Users can easily navigate and view a list of expenses.
- Filter and search expenses: Users can apply filters and search criteria to quickly find specific expenses.
- Mail directly: Users can mail directly to the Approver with the inquiry when the status of an expense is "Submitted" or "Declined".
- Reset filters: Users can reset all filtering fields with a single button click.

#### Screen 2: Add Expenses

- Create new expenses: Users can create new expense entries with ease.
- Automatic date assignment: The app automatically fills the expense date field with the current date.
- Automatic approver assignment: The app automatically selects the assigned approver based on the user's manager status in Office 365.
- Submit to SharePoint List: Expenses are submitted to a SharePoint list using the Patch function. Notifications inform the user if the expense has been successfully submitted or when the to fields are missing.
- Reset fields: Users can reset all input fields with a single button click.

#### Screen 3: Expense Analysis

- Power BI report integration: Users can access a Power BI report that allows for multiple selections and data visualization. This provides a comprehensive overview of expenses.

#### Screen 4: Created By

- Contact and app author information: This screen provides information about the author of the Expense Report App.

**Additionaly**

- Colors of the app are set by global variable invoke OnStart, which leds to easily changes.
- Two designed components allow for easy changes of the app header or left column which works as navigation panel.

### Power Automate

#### Expense Approval

- Approval Email notifications: When a new expense item is created in the SharePoint list, Power Automate sends an email to the approver with detailed information and possibility to direct approve or reject the expense.
- Status update: Based on the approver's choice, the status of the expense in the SharePoint list is updated accordingly.

#### Refresh a Power BI dataset

- Data synchronization: Whenever a new expense item is created or modified in the SharePoint list, Power Automate triggers a refresh of the corresponding Power BI dataset. This ensures that the expense report in Power Apps reflects the most current data.

### Power BI Service

- Expense analysis report: A Power BI report has been created based on the SharePoint list data.
- Filtering and data visualization: The report allows for filtering by date, submitter, status, and category, and provides visualizations to help analyze the expense data.

## Import to the environment

To get started, ensure that you have access to the Power Platform and the necessary permissions to create and manage Power Apps, Power Automate workflows, and Power BI reports. You will also need a SharePoint list to store the data.

- Dowload all elements of the Expense Report App repository.
- Import [dbExpenses.iqy](https://github.com/KlaudiaMagdalena/ExpenseReportApp/blob/main/dbExpenses.iqy) file to SharePoint list.
- Import [Expense_reports_analysis.pbix](https://github.com/KlaudiaMagdalena/ExpenseReportApp/blob/main/Expense_reports_analysis.pbix) file to Power BI.
- Import the [PowerAutomate_Expense_Approval.zip](https://github.com/KlaudiaMagdalena/ExpenseReportApp/blob/main/PowerAutomate_Expense_Approval.zip) and [PowerAutomate_Refresh_a_Power_BI_dataset.zip](https://github.com/KlaudiaMagdalena/ExpenseReportApp/blob/main/PowerAutomate_Refresh_a_Power_BI_dataset.zip) workflows to Power Automate. Then connect the “Expense Approval” to “dbExpenses” Sharepoint list. Finally connect the “Refresh a Power BI dataset” workflow to “dbExpenses” Sharepoint list and “Expense_reports_analysis" report in Power BI.
- Then import solution [ExpenseReportApp_1_0_0_2.zip](https://github.com/KlaudiaMagdalena/ExpenseReportApp/blob/main/ExpenseReportApp_1_0_0_2.zip) to you Power Apps environment. Select required Connections during import (ver 1.0.0.2 only uses Outlook 365 and SharePoint) as well required environment variables (ver 1.0.0.2 only uses SharePoint Site).

## Contributors

The Expense Report App was created by Klaudia Wieczorek. If you have any questions or need assistance, please feel free to reach out to [klaudiamagdalenawieczorek@gmail.com](mailto:klaudiamagdalenawieczorek@gmail.com).
