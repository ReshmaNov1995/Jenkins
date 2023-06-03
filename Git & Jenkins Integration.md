Plugins,
In Dashboard->Manage Jenkins->Plugins->select Available plugins tab & in search type ->Git


Click on New Item,
Give some name(GitJenkinsIntegration) & select Freestyle project -> Save.

Dashboard->GitJenkinsIntegration->Config/Configuration,
  Popup will be opened. 
  On that Pop up,
   **SourceCode Management** -> **Enable Git** radio button.
   **Pass the url** which is from the github->Code->url(Repository url)
   
   In **Build Triggers->Enable "Poll SCM"**.
   Inside schedule, *  *  *  *  * (Mins,Hours,Days,Month,Year)
   
    Pycharm,
    **pip freeze > kk.txt** (All the package name with version will be copied in the txt file, Any name for the text file).
    
   Jenkins,
   In Build Step-> Add Build step-> choose Execute window batch command-> 
   **pip install -r kk.txt** (-r for recovery).
   py GitJenkins.py (Pgm name which needs to run in Jenkins)
   Apply & Save.
   
Then Run it.
Run->Build Now
