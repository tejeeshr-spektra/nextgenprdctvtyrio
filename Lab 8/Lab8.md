# Streamlining IT Support Operations with Autonomous Copilot Agent using Copilot Studio

**Estimate Time: 30 minutes**

**Objective**

The objective of this lab is to enable participants to streamline IT
support operations at Zava Solutions by creating an autonomous Copilot
agent. Participants will learn to set up Microsoft Copilot Studio,
configure the IT Support Agent, integrate Power Apps and Dataverse,
enhance the bot's capabilities with a knowledge base, and automate
ticket creation using Power Automate. This hands-on lab will equip users
with the skills to improve IT workflows, reduce manual effort, and
enhance support efficiency.

**Solution**

Participants will create a customized Zava IT Support Agent using
Microsoft Copilot Studio, configure it to handle common IT issues, and
integrate it with Dataverse for storing support data. They will set up a
development environment, add knowledge sources, and refine the bot\'s
conversation flows for better user interaction. By leveraging Power
Apps, participants will create a Dataverse table to manage IT support
records. Using Power Automate, they will automate ticket creation and
email notifications for unresolved issues. Finally, participants will
test the agent to validate its troubleshooting accuracy and workflow
automation, ensuring seamless IT support operations.

## Exercise 1: Getting Started with Power Apps

This exercise introduces participants to Power Apps and Dataverse. The
goal is to log in to Power Apps, set up a working environment, and
create a Dataverse table by importing data from an Excel file.
Participants will learn essential skills for working with data-driven
applications.

### Task 1: Logging into Power Apps

1. Navigate to power apps website <https://www.microsoft.com/en-us/power-platform/products/power-apps> and
    click on the **Try for Free** button.

    ![](media/media/image2c.png)

1. On the **Power Apps Developer Plan** sign-up page, enter **Email (1)** field, select the agreement checkbox **(2)**, and then choose **Start free (3)** to activate the developer plan.

    - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

       ![](media/media/dwe1t1s2.png)

3. Select **Get Started**.

    ![](media/media/dwe1t1s3.png)

### Task 2: Update the Developer environment settings

1. From a new tab in the browser, navigate to
    <https://admin.powerplatform.microsoft.com/> and sign in with 
 
    - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

	- **Password:** <inject key="AzureAdUserPassword"></inject>

        ![](media/media/image2f.png)

2.  Select  **Manage (1)** from the left pane and select **+ New (3)** under **Environments (2)**.

    ![](media/media/dwe1t1s4.png)

3. Provide the environment name as **Dev One (2)** and select the Type as  **Developer (1)** and select  **Next (3)**.

    ![](media/media/dwe1t1s5.png)

4.  Select  **Save** in the  **Add Dataverse**  dialog.

    ![](media/media/dwe1t1s6.png)

5.  Once the environment is **Ready**, select the created **Dev
    One** environment.

    ![](media/media/imagec.png)

6.  You will be redirected to the overview page. Select **Edit** from
    top right corner in **Details** tab.

    ![](media/media/imaged.png)

7.  In the Edit pane, toggle  **Administration mode** to  **ON** and
    select  **Save**.

    ![](media/media/imagee.png)

    > **Note:** Wait for the environment update process to complete and ensure that the **Finalize** stage shows **Succeeded** before proceeding to the next task. This process may take a few minutes to complete.

8.  Once the edited changes are saved, select **Settings**.

    ![](media/media/imagef.png)

9.  Select **Product - Features**.

    ![](media/media/image10.png)

10. Under the **Features**, toggle on **Dataverse search**,
    select **save**, then toggle **Single table search** option to On
    and select **Save**.

    ![](media/media/image11.png)

    ![](media/media/image12.png)

### Task 3: Setting Up a Dataverse Table

1.  Navigate back to the  **PowerApps page** and select
    the **DevOne** environment from the list of environments.

    ![](media/media/image13.png)

2.  From the left navigation bar select **Tables.** In the tables
    section top bar click on the **+ New table** and then
    select **Create new tables**.

    ![](media/media/image14.png)

3. Select **Import an Excel file or CSV** option to create a new
    table.

    ![](media/media/image15.png)

4.  Click on the **Select form device** option and select **Support Ticket** excel file from  **C:\Users\LabFiles\labfiles\lab 8 files**  folder.

    ![](media/media/dxt3s4.png)

5.  Select **Import**.

    ![](media/media/image17.png)

6.  Select the table and click on **View data** to see the data.

    ![](media/media/image18.png)

    >**Note:** This case, the table is named  *Support Ticket*. The name may vary with each execution. Please save the table name for future reference.The column name may also vary in the execution.

7.  Go to table data, select the drop down next to the **Issue
    Description** field, select  **Edit column.**

    ![](media/media/image19.png)

8.  Set the data type as **Text** /**Multiple lines of text/** **Plain Text** and
    click on the **Update**. The column name may be different in each
    case.

    ![](media/media/image1a.png)

    ![](media/media/image1b.png)

    >**Note:** The **column name might be slightly different**, but it will be
something similar to the issue description since it is Copilot
generated.

9.  Select drop down next to the **Ticket Status** field, select **Edit
    column**, Set the Choices as ```Unresolved```, ```Resolved```,
    ```Processing```. Set Default choice as **Unresolved** and click on
    the **Update**.

    ![](media/media/image1c.png)

10. From top right side click on **Save and exit** to save the table.

    ![](media/media/image1d.png)

### Task 4: Add a file to the OneDrive

1. From the top left of the Power Apps page, select the menu and
    select **OneDrive**.

    ![](media/media/image1e.png)

2. Select  **My files** - **+ Create or upload**.

    ![](media/media/image1f.png)

3. Select  **Files upload**. Choose  **Support Ticket.xlsx**  from 
    **C:\LabFiles\Labfiles**.

    ![](media/media/image20.png)

4.  This file will be used in a later exercise.

## Exercise 2: Creating the Zava IT Support Agent

This exercise focuses on logging into Microsoft Copilot Studio and
creating a customized Copilot agent tailored for IT support operations
at Zava. Participants will gain hands-on experience navigating Copilot
Studio, configuring environments, and building an AI-powered agent to
streamline IT workflows.

1. Navigate to the Copilot Studio tab
    <https://copilotstudio.microsoft.com> and
    choose **DevOne** environment.

    ![](media/media/dwe1t3s3.png)

2. Open <https://admin.powerplatform.microsoft.com/>.
    Select **Manage** -\> **Environments** -\> **Dev env** and select
    the value of the **Environment ID**.

    ![](media/media/image21.png)

3. Navigate back to the Copilot Studio tab and open
    <https://copilotstudio.microsoft.com/environments/>\<
    EnvironmentID \>(Replacing **\< Environment \>** with the value
    fetched above)
    
    ![](media/media/image22.png)

4. Select  **Agents**.

    ![](media/media/image23.png)

5. Select  **+ Create blank agent**.

    ![](media/media/image24.png)

6.  Enter **Name** and select  **Create.**

    **Name:** **Zava IT Support Agent**

    ![](media/media/image25.png)

7.  **Description & Instruction** : Select the **Copy** option and 
    **Paste** it in the  **Description**  & **Instruction** field and click **Save**.

- **Description:**

    ```
    Create a Zava IT Support Agent which transforms IT support at Contoso Solutions by providing instant troubleshooting for common issues,
    automating ticket creation for unresolved problems, and storing all
    interactions in Dataverse. This solution enhances response times,reduces manual workloads, and boosts employee productivity.
    ```

- **Instruction**(Select the **Copy** option and **Paste** it in
  the **Instruction** field):

    ```
    Create the Copilot Agent and configure it to handle IT support operations. Add a knowledge source containing solutions for common IT issues like hardware troubleshooting, connectivity, and software glitches. Set up a trigger to detect updates to a OneDrive file describing unresolved issues. Create an action to save these technical issues into a Dataverse table, ensuring all details are stored for tracking and reporting. Test the agent to validate its troubleshooting accuracy and ticket automation workflow before deployment.

    ```

    ![](media/media/image26.png)

8. From top right corner of the agent, click on
    the **Settings** button.

    ![](media/media/image27.png)

9. Scroll down and disable the **Allow ungrounded responses** option
    and **Use information from the web** under the **Knowledge** section
    and then click on **Save**.

    ![](media/media/image33.png)

10. Once **saved**, **close** the Settings pane.

## Exercise 3: Enhancing Bot Capabilities

This exercise focuses on enhancing the capabilities of the Zava IT
Support Agent by adding a knowledge base and customizing bot topics for
improved interaction. Participants will refine the bot's responses and
ensure it effectively assists users in troubleshooting and escalation.

### Task 1: Add Knowledge Base

1.  On the Zava agent overview page, scroll down and click on **+ Add
    Knowledge** button.

    ![](media/media/image34.png)

2.  Select **Upload file** to add the lab file  **Support Ticket_1.xlsx** from **C:\Users\LabFiles\labfiles\lab 8 files** folder and then click on **Add to agent** to save the file.

    ![](media/media/image35.png)

3. Again, go to agent overview page, scroll down and click on **+ Add
    knowledge.**

    ![](media/media/image36.png)

1. Select **Dataverse** option as data source.

    ![](media/media/image37.png)

5.  Search for Support Ticket, select **Support Ticket** table.
    Then select **Add to agent** button to add the knowledge source.

    ![](media/media/image38.png)
    
6. Select **Publish** agent.

    ![](media/media/dxe3s6.png)

    ![](media/media/image2b.png)

    >**Note:** The **table name might be different** in your case since it is a Copilot generated one. Try searching for **Support Ticke**t if needed.

    >**Important:** From the Knowledge page, ensure that the added knowledge source has been successfully uploaded. This will generally
take 10 to 15 30 minutes to complete.

## Exercise 4: Test the agent

This exercise guides participants through testing the Contoso IT Support
Agent to validate its functionality. Participants will check how the bot
handles prompts using the knowledge base and fallback topics to ensure
seamless interaction and escalation.

1. From top right corner click on the **Test** button.

    ![](media/media/image3a.png)

2. Enter the prompt ```My printer is not working how to fix it.``` It
    gives the solution as per knowledge source.

    ![](media/media/dxe4s1.png)

3.  Review the output:

    ![](media/media/image3c.png)

## Lab Summary

In this lab, you built an autonomous IT support solution for Zava
Solutions using Microsoft Copilot Studio integrated with Power Platform.
You began by provisioning a dedicated Dev One developer environment in
the Power Platform admin center, enabling Dataverse search settings, and
creating a Dataverse table by importing structured ticket data directly
from an Excel file --- configuring the Issue Description column as
multi-line plain text and the Ticket Status column as a choice field
defaulting to Unresolved.

You then created the Zava IT Support Agent in Copilot Studio, defining
its description and instructions to handle common troubleshooting
scenarios --- hardware issues, connectivity problems, and software
glitches --- while disabling ungrounded responses and web grounding to
keep the agent scoped strictly to trusted organizational knowledge. From
there, you strengthened the agent\'s knowledge base by uploading the
Zava Common IT Issue reference document and connecting the
Dataverse-backed Support Ticket table as a live knowledge source, giving
the agent visibility into real ticket history alongside static
troubleshooting guidance.

Finally, you published and tested the agent, validating that it could
correctly retrieve and apply knowledge-base guidance in response to a
real-world prompt --- resolving a printer issue using the uploaded
reference material rather than a generic or web-sourced answer.

This lab demonstrates how Copilot Studio, paired with Power Apps and
Dataverse, enables organizations to stand up a grounded, self-service IT
support agent that reduces manual ticket triage, keeps responses
anchored to verified internal knowledge, and lays the foundation for
further automation --- such as Power Automate--driven ticket creation
and escalation for issues the agent cannot resolve on its own.
