# How to Configure Local Enviroment

1. Clone the project from given url. ( https://github.com/ahmadsaadkhan/kanban-board-assignment.git )

2. Now cd into project folder and open terminal and run command composer update

3. Now create a .env file get all keys from .env.example and add all to .env file.

4. Now create a OAuth app on github get your client id, client secret. Github link ( https://github.com/settings/developers )
    
    GH_REPOSITORIES= ‘nameOfRepository’
    GH_CLIENT_ID = 'xxxxxxx'
    GH_CLIENT_SECRET = ‘xxxxxxxx’
    GH_ACCOUNT = ‘yourGitHubUsername’

5. Add these four variables to .env file and check your local project by following link
   http://localhost/kanban-board-assignment/public/

# How to Test Deployed Application

1. Visit the link ( https://kanban-board-heroku.herokuapp.com/ )

2. It will ask you for Github authorization, give authorization.

3. You can view the issues that I added to my public repo it contains test php scripts.
     ( https://github.com/ahmadsaadkhan/php_test_scripts_ ) 

4. Its a public repo so after access you would be able to view issues.


# How i run the project

1. The first step is to copy the files to the Xampp folder to run on localhost.

2. Open a terminal in the same folder and run Composer Update.

3. Create a new OAuth app on Github and get credentials for Client Id and Client Secret.

4. Create a .env file for Environment Variables check the example.env file on the root and add the      credentials, which you get after creating the GitHub app and add repo name in GH_REPOSITORIES and GitHub username in GH_ACCOUNT with client id and secret.

5. As the Environment Variable file is added to read the env file we install the following package from the composer
    $ composer require vlucas/phpdotenv

    Package git hub link: https://github.com/vlucas/phpdotenv)\

6. (require '../../vendor/autoload.php'; ) is removed from the constructor of Github.php and added to the top of public/index.php where other files are included. 

NOTE:: It was not executing from the constructor of  Github.php or GithubClient Class

7. In public/index.php on line 12, 13,14 Dotenv\Dotenv Package is loaded.

8. In utilities ( $value = $_ENV[$name]; ) is added instead of line ( $value = getenv($name); ) to read the environmental variables.

NOTE:: getenv was unable to read the environmental variables

NOTE:: (At this point project should execute and show issues according to the given Github repo)

NEXT:: Removed the error and warnings and adjust the UI.

9. Application.php Line 42,43,44 added check completed, queued, and active for array values whether it exists or not else it gives warning same on 73 added check for active issues.

10.  For UI Bootstrap 5 files are added to the public folder now you can view an improved UI. 


Thanks for consideration


