# Lab 2 - Exercise 4 - Manage Roles and Permission Policies

In this exercise you will continue in your role as Holly Dickson, Adatum’s
Messaging Administrator. Holly has been tasked with managing Microsoft 365 admin
roles and permission policies for Adatum’s Microsoft 365 messaging environment.
The CTO has asked Holly to create a new Microsoft 365 management role group that
allows an administrator to remotely access a mailbox without having the
password.

In this exercise Holly will access the Exchange admin center for Exchange Online
from her client computer (LON-CL1).

## Task 1 - Create an Admin Role

A management role group is a universal security group used in the Role Based
Access Control (RBAC) permissions model for Exchange Online. A management role
group simplifies the assignment of management roles to a group of users. All
members of a role group are assigned the same set of roles. After the role group
is added, the members of the role group are granted the permissions provided by
the roles assigned to the role group.

In this task, you are going to create a custom role group and then assign
multiple roles to it. In this task, you will create an admin role that allows an
administrator to remotely access a mailbox without having the password. You will
then assign two specific administrators to this role.

1.  Switch to the LON-CL1 VM and if necessary, log in as the **Administrator**
    with a password of **Pa55w.rd**.

2.  The Microsoft Edge browser may still be open from Lab 4 where you were
    logged into Microsoft 365 as a user other than the MOD Administrator
    and you had Compliance center open. Log out of Microsoft 365 and log 
    back in as the MOD Administrator account. 

3.  Close all tabs in the Edge browser except for the **Sign out** tab.

4.  ‎On the **Sign out** tab, enter the following URL in the address bar:
    **https://portal.office.com**

5.  On the **Pick an account** window, select
    **admin@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant
    prefix provided by your lab hosting provider). On the **Enter password**
    window, enter the tenant admin password provided by your lab hosting
    provider and then select **Sign in**.

6.  On the **Office 365 home** page, select the **Admin** icon in the column of
    Microsoft 365 app icons on the left-side of the screen.

7.  On the **Microsoft 365 admin center**, select
    **Show all** in the left-hand navigation pane, and then under **Admin
    centers**, select **Exchange.**
    
8.  In the **Exchange admin center** tab, in the left-hand navigation pane,
    select **Roles.**

9.  At the top of the **Roles** page, the **admin roles** tab should be
    displayed by default; if not, then select it now.

10. The **admin roles** window displays the existing role groups. Each of these
    groups has one or more roles assigned to it.  
      
    For example, the **Compliance Management** role group is highlighted by
    default as it’s the first group in the list. In the details pane on the
    right-hand side of the screen, it displays the properties for this role
    group, which includes the roles and members that have been assigned to it.
    In this task, you are going to create a custom role group and then assign
    multiple roles to it, as well as several existing members.  
    ‎  
    ‎Select the **Add role group** icon on the menu bar to create a new role
    group.

11. In the **add role group** window, enter **Application Impersonation** in the
    **Name** field.

12. Enter (copy and paste) the following text into the **Description** field:
    **This role group allows an administrator to remotely access a mailbox
    without having the mailbox owner’s password.** Then select **Next**.

13. Under **Add permissions**section, either scroll or search for the following roles and select them:

    -   **ApplicationImpersonation**

    -   **Mail Recipients**

    -   **UserApplication**

15. Select the **Next** button, 

16. In the **Assign admins** window, in the **Members** section
    Enter the following then select the names:

    -   **Admin**

    -   **TenantAdmins_-##########** (where ########## represents
        the tenant number at the end of the TenantAdmins group)

18. Select the **Next** button.

19. In the **Review role group and finish** section, confirm that all the information is present and select the  **Add role group** button.

20. The page will return a notification screen stating, **Application Impersonation role group has been added**. select the **Done** button.

    **Important:** Even though the **Application Impersonation** group appears
    in the list of role groups, it typically takes 24 to 48 hours to fully
    propagate changes to the permission configuration.

21. Leave the Exchange Admin Center open and proceed to the next task.

## Task 2 - Manage an Admin Role

In the prior task, you created a custom role group and added roles to the role
group. In this task, you are going to add a user to a role group.

1.  You should still be logged into LON-CL1 as the **Administrator** account
    with a password of **Pa55w.rd**; however, if the log-in screen appears, then
    log in now.

2.  The **Exchange admin center** for Exchange Online should still be open in
    your Edge browser. You should still be on the **permissions** page, which
    should be displaying the **admin roles** tab from the prior task.  
      
    In the list of admin role groups, select the **Discovery Management** role
    group.

3.  The **Discovery Management** pane will open. Select the **Assigned** tab.

4.  In the **Assigned** window, select the  **(+) Add** button.

5.  In the **Add admins** window, Enter **admin** inside the search field.(this is the MOD
    Administrator user account).

6.  Select the **Mod Administrator** account and then select **Add**.

7.  In the **Assigned** tab displays a banner  stating that **1 member added to this role group.** select the **X** to close the **Discovery Management** pane.

8.  Leave the Exchange Admin Center open in your Edge browser and proceed to the next task.

## Task 3 -Create an Outlook Web App Policy

A mobile device mailbox policy allows you to apply a common set of security and
mobile device settings to a group of users. You can create multiple mobile
device mailbox policies. Each recipient in your organization must have a mobile
device mailbox policy assigned to them. When you install Microsoft Exchange
Server 2013 or later, a default mobile device mailbox policy is created, and new
users are automatically assigned this policy.

In this task, you will create a new Outlook Web App policy that will later be
assigned to several test users in Holly’s pilot project.

1.  You should still be logged into LON-CL1 as the **Administrator** account
    with a password of **Pa55w.rd**; however, if the log-in screen appears, then
    log in now.
2.  In the **Exchange admin center** select the **Classic Exchange Admin center**.
  
3.  In the **Classic Exchange Admin Center**, select the **permissions** section. Then select the **Outlook Web
    App policies** tab.

3.  In the list of Outlook Web App policies, the **OwaMailboxPolicy-Default**
    policy is the only current policy. By default, this policy is assigned to
    all user mailboxes.

4.  To create a new Outlook Web App policy, select the **plus (+) sign** icon on
    the menu bar.

5.  In the **new Outlook Web App mailbox policy** window, enter **Test OWA
    Mailbox policy** in the **Policy name** field.

6.  In the **Communication Management** group, all features are selected by
    default. Select the **Text Messaging** check box to unselect it.

7.  In the **Information management** group, un-check **Journaling**.

8.  In the **User experience** group, select **Places** and **Local events**.

9.  Select **Save** and then select **OK** once the information is successfully
    saved. Your new custom policy should appear in the list of Outlook Web App
    policies.

10. Leave the Edge browser and all tabs open and proceed to the next exercise.

## Task 4: Assign an Outlook Web App Policy to a user mailbox

Assigning an Outlook on the web mailbox policy to an Exchange Online mailbox
controls the Outlook on the web (formerly known as Outlook Web App, or OWA)
experience for the user. You can apply Outlook on the web mailbox policies to
one or more mailboxes or remove the policy assignments in the Exchange admin
center (EAC) or Exchange Online PowerShell.

In this task, you are going to assign the Outlook Web App policy that you
created in the prior task to the mailboxes of three Adatum users who are part of
Holly’s pilot project.

1.  You should still be logged into LON-CL1 as the **Administrator** account
    with a password of **Pa55w.rd**; however, if the log-in screen appears, then
    log in now.

2.  The **Exchange admin center** for Exchange Online should still be open in
    your Edge browser. In the left-hand navigation pane, select **Classic Exchange admin center**.

3.  On the **Welcome** page, select **recipients**. The **mailboxes** tab should be selected by
    default; if not, then select it now.

4.  The prior task indicated that by default, all user mailboxes are assigned
    the **OwaMailboxPolicy-Default** policy. Let’s verify this before assigning
    the new policy to one of the user mailboxes. In the list of Microsoft 365
    user account mailboxes that were created by your lab hosting provider,
    select **Joni Sherman**.

5.  In the **Joni Sherman** detail pane on the right, scroll to the bottom of
    the pane and in the **Email Connectivity** section, select **View details**.

6.  An **Outlook Web App mailbox policy** window should appear that displays the
    Outlook Web App policy that was assigned to this mailbox. Verify the
    **OwaMailboxPolicy-Default** policy appears, and then select **Cancel**.

    -   You will now assign the Outlook Web App mailbox policy that you created
        in the prior task to the mailboxes of three users who are participating
        in Adatum’s pilot project.  
          
        In the list of mailboxes, select **Diego Siciliani** and then hold down
        the CTRL key and select **Joni Sherman** and then **Patti Fernandez.**

7.  By selecting multiple users, a **Bulk Edit** pane appears on the right side
    of the screen. Scroll down in this pane to the **Outlook on the web**
    section and then select **Assign a policy**.

8.  In the **bulk assign Outlook Web App policy** window that opens, select
    **Browse.**

9.  A window appears that displays the list of Outlook on the Web App Policies.
    Select the **Test OWA Mailbox policy** that you created in the prior task
    and then select **OK**.

10. In the **bulk assign Outlook Web App policy** window, select **Save** to
    apply this policy to all three user mailboxes.

11. Select **OK** once the information is successfully saved.

12. You should now verify the **Test OWA Mailbox policy** was applied to the
    users’ mailboxes. You will use Joni’s mailbox for this test. In the list of
    mailboxes, select **Joni Sherman**.

13. In the **Joni Sherman** detail pane on the right, scroll down to the bottom
    of the pane and in the **Email Connectivity** section, select **View
    details**.

14. An **Outlook Web App mailbox policy** window should appear that displays the
    Outlook Web App policy that was assigned to this mailbox. Recall in the
    earlier step that Joni was originally assigned the
    **OwaMailboxPolicy-Default** policy. You should now verify that Joni is
    assigned the **Test OWA Mailbox policy**. Select **Cancel**.

15. Leave the Edge browser and all tabs open and proceed to the next lab.

# End of Lab 6
