# PR notification bot with golang

## Require
* heroku
* heroku cli

## Usage

1. Heroku login
    
    ```
    $ heroku login
    Please type your e-mail address and passward
    $ heroku plugins:install heroku-config
    ```

2. Clone this project
    
    ```
    $ go get github.com/bookun/slackbot
    $ cd ${GOPATH}/src/github.com/bookun/slackbot
    ```

3. Prepare .env

    ```
    $ cp .env.sample .env
    $ vim .env
    Please edit slack webhook and channel name.
	Opptional) Please add GithubName=SlackName for mention function in slack.
    ```
    More detail in https://slack.com/services/new/incoming-webhook

3. Create Heroku App

    ```
    $ heroku create
    $ git push heroku master
	$ heroku config:push
    (This command push .env to heroku app)
    ```
	You can get your app's URL.

4. Setting Webhook in GitHub
    1. https://github.com/<repo>/slackbot/settings/hooks
    2. Put "Add webhook" button
	3. Input your app's URL to "Payload URL"
	4. Content type is "application/json"
	5. Choise "Let me select individual events"
	6. Check "Pull requests" only.

