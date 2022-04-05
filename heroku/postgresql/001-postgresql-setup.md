# Install pgAdmin
Downoad the latest version of pgAdmin: <br>
```
https://www.pgadmin.org/download/
```
Follow the installation steps for your chosen OS:
```
#recommended
https://www.pgadmin.org/download/pgadmin-4-windows/
```

# Setup PostgreSQL on Heroku
## ```Resources``` tab of Application dashboard
### Step 1. Add ```Heroku Postgres``` Add-on
![image](https://user-images.githubusercontent.com/5201843/161617611-4373bdf5-5c82-4229-aff5-e0ca433a1b5c.png)
### Step 2. Select ```Hobby Dev - Free``` in the Plan Name Dropdown
![image](https://user-images.githubusercontent.com/5201843/161618119-b21c6537-925d-42f0-bb38-29687496e54d.png)
### Step 3. Get the database credentials and connection URL
1. Navigate to the ```Resources``` tab again
2. Select ```Heroku Postgres```
![image](https://user-images.githubusercontent.com/5201843/161618354-33c31ae6-8f7b-4fe2-bc12-d905bf6eaca1.png)
3. Should look something like this
![image](https://user-images.githubusercontent.com/5201843/161618430-35a14c43-e263-4220-81a4-56eb1f41360a.png)
4. Select ```Settings``` Tab
![image](https://user-images.githubusercontent.com/5201843/161618528-efbbbe5a-bb22-4c54-9704-b37afc7d408a.png)
5. Click on ```View Credentials```
![image](https://user-images.githubusercontent.com/5201843/161618593-e0b8bedd-9c3e-4088-920f-5565b396462e.png)
6. Note down the credentials in notepad or keep the tab open for the next steps.
```
Host:
Database:
User:
Port:
Password:
```
# Connect to the setup database from PG Admin
1. Open pgAdmin
![image](https://user-images.githubusercontent.com/5201843/161619682-f42bf13f-937f-4f43-af10-f860ff390248.png)
2. Right-Click on ```Servers > Register > Server``` and enter a name of your choice
![image](https://user-images.githubusercontent.com/5201843/161620151-66c1ad8e-0024-4dc5-be1e-0e66c7be4f1b.png)
3. Navigate to the Connection Tab and enter the connection infor collected in the previous step
![image](https://user-images.githubusercontent.com/5201843/161620821-56942c74-afbb-4110-a7ef-ab2a731586fc.png)
4. Navigate to the SSL Tab and set SSL Mode as required
![image](https://user-images.githubusercontent.com/5201843/161620922-56f8a718-563c-400b-b464-e7c95ba0e8db.png)
5. Navigate to the Advanced tab and set ```DB Restriction``` to the name of the database you previously copied
![image](https://user-images.githubusercontent.com/5201843/161622391-cf955e75-3bf9-4398-8372-015314ad701b.png)
7. Click on Save to see a similar dashboard
![image](https://user-images.githubusercontent.com/5201843/161621214-ef2925ea-4e27-4517-8620-eaa2ff5179ad.png)
