A 2502 error is a result of Microsoft, not giving permissions to the temp folder so 
that it an application can extract itself and run from that folder. It has nothing 
to do with Race Manager Sqorz, or the API. Here is one solution to try.

To resolve the issue, do the following:

- Navigate to File Explorer location: C:\Windows\TEMP
- Right click on the TEMP folder and select "Properties".
- Select the "Security" tab.
- Then select the "Add" button.
- In the "Enter the object names to select (examples):" table, put in (without quote marks) "EVERYONE".
- Then select the button "OK".
- Then in the "Group or user names:" location, select the button "Edit".
- For all Group and user names, allow "Full Control".
- Then select the button "Apply".
- Try the API installation.


!!!FYI
    When you buy a new Windows computer, Microsoft requires you to create a 
    Microsoft account to log into the computer with. The problem with that Microsoft 
    account is that it does not always assign permissions correctly to the file system 
    and the issue you’re encountering is because you do not have rights to the temp folder 
    to Unpackaged the program installer into. 


