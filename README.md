# mern-stack-with-mongodb-realm

### MongoDB Realm is the serverless implementation of MongoDB

###### Create a monogoDB account and set up backend

1. Go to https://cloud.mongodb.com
2. Create an account (w/ organization name just use <FirstName> Org and any project name)
3. Choose "Javascript" as your preferred language
4. Choose the free tier under "Shared Clusters"
5. Choose a cloud provider and your region. I chose "AWS" and I'm on the westcoast so I choose the Oregon server
6. Click "Create Cluster" (Side Note: This step may take awhile depending on your network speed)
7. After cluster has been created it will take you to the cluster dashboard click "Connect" to configure connection
8. Click "Add Your Current IP Address" then type a username and password of your choice and click "Create Database User"
9. We are connecting our application to our cluster using MongoDB native drivers so copy the connection string and replace <password> (make sure you replace all of it with your password to include < and >) with your password and replace MyFirstDatabase with "sample_restaurants"
10. Now we need to create our clusters so go back to cluster dashboard click the three dots ... then click "Load sample dataset" (FYI this step will take awhile to complete)
11. As you can see there are several datasets but we are going to be working with restaurants. The dataset includes restaurants from NY.

###### Create Node/Express Backend

1. Create a folder for the project
2. Open bash terminal in folder
3. Create a directory called "backend" with "mkdir backend"
4. Change directory into the folder with "cd backend"
5. Check that you have node installed with "node -v" (if you do not have node.js you can download it here: https://nodejs.org/en/download/current/)
6. Then create a package.json with "npm init -y"
7. Now install necessary packages with "npm isntall express cors mongodb dotenv" (note: express is the web server, cors stands for cross-origin resource sharing and it allows us to ajax requests to skip the same-origin policy and access resources from remote hosts, the cors package provides an express middleware that can enable cors with different options, basically it's gonna make it so we can make the right connections on our network that we need to make, without that could have some errors, then mongodb allows us to connect to our mongodb database, and lastly the dotenv dependency loads environment variables from a dotenv file in process.env, so instead of setting environment variables on our development machine they can be stored in a file)
8. Then install nodemon (globally) with "npm install -g nodemon" (note: its going to make development easier by helping node.js applications by automatically restarting the node application when file changes occur and the directory are detected so we don't have to restart the server every time we make an update to our files)
9. Lastly go one directory back up by typing "cd .." in bash terminal then open vscode in that folder with "code ."
10. Go to package.json and after "main": index.js were going to add "type": "module" (note: this allows us to use the import statement from ES6) then save
11. Now create a file in your "backend" directory called "server.js" like the one I have under my "backend" directory
12. Now create a file in your "backend" directory called ".env" and enter the following
    Note: you will not find my .env in my repo because I did not include it for security reasons

###### .env file (you will need the connection string you copied earlier in this step)

RESTREVIEWS_DB_URI=mongodb+srv://(Your username):(Your password)@cluster0.cqbl1.mongodb.net/sample_restaurants?retryWrites=true&w=majority
RESTREVIEWS_NS=sample_restaurants
PORT=5000
