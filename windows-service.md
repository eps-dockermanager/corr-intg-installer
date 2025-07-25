# Installing Corr Suite Integration as Windows Service
Corr Suite integration is available as windows service also. To Install the Integration software as Windows Service, follow the steps given below.

## Download the desired build
- Login to Github and click on Actions (https://github.com/eps-packaging/CorrSuiteIntegration/actions/workflows/publish-win.yml)
  
  <img width="1511" alt="image" src="https://github.com/user-attachments/assets/3264909d-0960-4eac-804c-cd5c615f3c78" />

- Look for the Build number you want to download
  
  <img width="1511" alt="image" src="https://github.com/user-attachments/assets/275fc203-ade6-4a92-b4cb-0754fdc40cb8" />

- Download the build

## Keep a MSsql Server with a blank database ready
- Create a database in a MsSql Database called `corrintgdb`
- Keep the connection string to this DB handy
  - e.g: `Server=<host or ip>\\MSSQLSERVER01,1433;Database=corrintgdb;User Id=<userid>;Password=<password>;TrustServerCertificate=True;`
  - Please note double \\ after host or ip if you are using named instance
## Extract the zip on the machine
- Create a directory in the c drive say `c:\corrintg`
- Extract the zip file into `c:\corrintg` folder. You should see 4 folders after extraction
- Open command prompt as administrator and change the directory to `c:\corrintg\config`
- Run `install.bat` and follow the instructions.
- When prompted, enter the connection string to the database
- Enter the port on which you want the config utility to listen
- Enter the automator URL to which integration should be connected with
  -- e.g: http://<eflow_automator_host>:8081
- Enter the user name for the automator and password for the automator.
- Utility will run to configure the database, configure the automator and create windows service.
- Open windows services windows and look for following 2 servcies
  - Corr Data App Config Service
  - Corr Data Scanner Service
- Start the configuration service `Corr Data App Config Service`
- After service starts, you can access the config utility by visiting `http://localhost:<port>`
  -- Port is what you have entered in the previous step.
- Proceed with configuring the instance
- After instance is configured, you can start the service `Corr Data Scanner Service`
