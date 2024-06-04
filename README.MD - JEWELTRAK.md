
# How to Start JewelTrak locally


When we are working on Jeweltrak for the first time, you need to do following the below in order to get started with the application with latest changes.

## Installation

When we are working on Jeweltrak for the first time, you need to do following the below in order to get started with the application with latest changes.

* Start the docker container
* Install all the dependencies

```bash
pnpm install
```

* Run the local development server

```bash
pnpm dev
```

* By the time you have cloned and ran the local dev environtment for the first time, someone might have just pushed the code, as we are working async. So in order to be in sync with those changes, make sure you pull those changes. Or fetch and merge, whatever works for you.

```bash
git pull
```

* Create a new branch and start with a name with clear indication on what you are working.
* In order to run the applications with latest db changes with all the migrations, you need to run the following command:

```bash
supabase db reset
```

It will run as below:

```Resetting local database...
Recreating database...
Setting up initial schema...
Applying migration 20230116105323_init.sql...
Applying migration 20230116105324_enum.sql...
Applying migration 20230116105327_tables.sql...
```

* Once done, you can magic link by giving your username and Navigate to [http://localhost:54324](http://localhost:54324) and click on monitor.

* Click on the latest message and follow the instructions. You will be taken to the welcome page of the application, where you need to accept the terms and create a “Profile Name” for yourself. 

* Now, go to http://localhost:54323/project/default and click on Authentication tab to the left navigation. (Supabase Dashboard)

* Create a new user (One admin and one User, if you’d like) by clicking on “Add User” and authorize it on page and save the password for reference.

* Now, go to table editor on the left nav, select “Organization” table. Click “Insert” and then “Insert Row” and fill in information for the Org like Name and click save.

* Now go to “Organization members” and click “Insert” and then “insert row”.
    - Remember, you have created two users in the Authentication tab. Pick one user from the “member_id” field from the select record popup. 
    - Select the appropriate record from the table
    - Select the role as “Admin” 
    - Save
    - Repeat the same for other record but this time, the role is “User”.


* One last step in configuration, Select “user_roles” from the search and make sure you select the user who we have created earlier as an admin, from the “Select record” and then map it to the role “admin”.

* You are done with configuration and can now, see your dashboard is visible for you with your organization.