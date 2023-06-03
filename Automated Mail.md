Plugins,
In Dashboard->Manage Jenkins->Plugins->select available tab & in search type -> Email extension template - then Install it.
In Dashboard->Manage Jenkins->Plugins->select available tab & in search type -> Email extension plugin - then Install it.

In Dashboard->Manage Jenkins->**System->Email Notification**. (Basic Mail)
SMTP Server(smtp.gmail.com)

Advanced,
  Use SMTP Authentication->UN:Enter mail id , PSSWD:Enter password. Also "Less secure app" has to be enabled for the sender which resides inside the Manage Account.
  
  Use SSL
  Use TLS
  SMTP Port "465"
  Reply to (Receipent)
  Apply & Save
  
  In Dashboard->Manage Jenkins->**System->Extended Email Notification**. (Advanced Mail)
 SMTP Server(smtp.gmail.com)
 SMTP Port "465"
 
Advanced,
  **Credentials-Add->Jenkins**
  Use SMTP Authentication->UN: , PSSWD: . Also "Less secure app" has to be enabled for the sender which resides inside the Manage Account.
  Enable - "Treat username as secret"(Sender name will be encrypted).
  Use SSL
  Use TLS
  Default Receipent 
  Default Subject 
  Default Content
  **Default Trigger - Always**
  
  Apply & Save
  
  
Click on New Item,
Give name(Email) & select Freestyle project -> Save.

  Dashboard->Email->Configuration,
  Popup will be opened. On that Pop up,
  Click on Advanced -> **Enable Custom workspace** give Project's path(E:\Automation\Practice_Selenium) in Directory.
  
  Click on Add build step-> choose "Execute windows batch command" -> Then type, **"call ./venv/Scripts/activate.bat"**(Venv folder->activate.bat's path)
  pip install pytest
  pytest -v -s --alluredir="pgm path"  program
  Ex: pytest -v -s --alluredir="test_Jenkins/AllureReports/Report1"  test_Jenkins/Test_Basicpytest.py
  
  **Click on Add Post build action -> Allure Report -> Then give the path of the Allure Report.**
  Ex: test_Jenkins/AllureReports/Report1/
  
  **Click on Add Post build action -> Editable Email Notification**
  Project Name
  Default details
  Attach Build Log->Attach Build Log
  Attachment from local "Path of the file with name & extension" ?
  Add -> Developer
  Add Trigger->Always
  
  Apply & Save.
  
