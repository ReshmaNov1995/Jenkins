Gonna run pytest program from pycharm using jenkins & create Allure report using jenkins in pycharm.
Note: This Ex, Create a folder for Allure report inside the pytest pgm folder.

Plugins,
In Dashboard->Manage Jenkins->Plugins->select available tab & in search type -> **Allure Jenkins** - then Install it.
In Dashboard->Manage Jenkins->Plugins->select available tab & in search type -> **ShiningPanda** - then Install it.

Enviornment variable->Take allure path.
E:\Automation\allure-2.17.3\allure-2.17.3
In Dashboard->Manage Jenkins->**Tools(Global tool configuration)->Allure commandline installations->disable "install automatically"->Give path in Installation directory then Allure Name.**
Apply & Save.

Click on New Item,
Give name & select Freestyle project -> Save.

Configuration,
Popup will be opened. On that Pop up,
  Click on Advanced -> **Enable Custom workspace** give Project's path(E:\Automation\Practice_Selenium) in Directory.
  
  Click on Add build step-> choose "Execute windows batch command" -> Then type, **"call ./venv/Scripts/activate.bat"**(Venv folder->activate.bat's path)
  pip install pytest
  pytest -v -s --alluredir="allure report's path"  program name
  Ex: pytest -v -s --alluredir="test_Jenkins/AllureReports/Report1"  test_Jenkins/Test_Basicpytest.py
  
  **Click on Add Post build action -> Allure Report -> Then give the path of the Allure Report.**
  Ex: test_Jenkins/AllureReports/Report1/
  Apply & Save.
  
  Interview Question,
  
  How to use all the requirement library package can be acheived in python?
  Pycharm,
    pip freeze > kk.txt (All the package name with version will be copied in the txt file).
   Jenkins,
   pip install -r kk.txt (-r for recovery).

To Run Allure Report in Jenkins,
  Click on Build Now or play button.
  Click on the running version then click on Console Output.
  Finally Click on Allure Report.
