1) Git Jenkins Integration:
    Push the Pycharm script in git then run in Jenkins.
    Config/Configuration, Popup will be opened. On that Pop up, **SourceCode Management -> Enable Git** radio button. 
    Pass the url which is from the github->Code->url(Repository url)
    **In Build Triggers->Enable "Poll SCM". Inside cron schedule, * * * * * (Mins,Hours,Days,Month,Year)**
    **In Build Step-> Add Build step-> choose Execute window batch command**-> pip install -r kk.txt (-r for recovery). 
    py GitJenkins.py (Pgm name which needs to run in Jenkins) 
    Apply & Save.
2) Allure Integration:
    Jenkins->**Tools(Global tool configuration)->Allure commandline installations**->disable "install automatically"->Give path in Installation directory then Allure Name. 
    Apply & Save.
    Click on **Add build step-> choose "Execute windows batch command"** -> Then type, "call ./venv/Scripts/activate.bat"(Venv folder->activate.bat's path) 
    pip install pytest pytest -v -s --alluredir="allure report's path" program name Ex: pytest -v -s --alluredir="test_Jenkins/AllureReports/Report1" test_Jenkins/Test_Basicpytest.py
    Click on **Add Post build action -> Allure Report** -> Then give the path of the Allure Report. Ex: test_Jenkins/AllureReports/Report1/ Apply & Save.
3) Automated Mail:
In Dashboard->**Manage Jenkins->System->Extended Email Notification.** (Advanced Mail) SMTP Server(smtp.gmail.com) SMTP Port "465"
Click on **Add Post build action -> Editable Email Notification** Project Name Default details Attach Build Log->Attach Build Log Attachment from local "Path of the file with name & extension" - It's global FTP requires. 
Add -> Developer **Add Trigger->Always**
Apply & Save.
**Add build step-> choose "Execute windows batch command"**

100 to 200 Testcase will run using jenkins.
Allure will integrated in jenkins, It will send report, Logs in mail.
Refer crontab.guru for cron schedule
