# Lawfred Intelligence
Search Legal Intelligence directly from your Alfred App. 
It will display the 10 most relevant results. Clicking a result will open the Legal Intelligence link to the document. If your desired result isn't there, at the bottom there is also a 'view all results', which directs you to your search query on Legal Intelligence. You need not be logged into Legal Intelligence, however you do need a token, which expires every day. I am working on a way to generate this every day.

![](Lawfredinaction.gif)

# Installation 
Download the workflow from [releases](https://github.com/ABeehive/lawfred-intelligence/releases). 

You require a Legal Intelligence account, client-secret, and authorisation token.
It also requires an Alfred Powerpack license.

## Getting a client-secret 
Go to your account [settings](https://www.legalintelligence.com/userprofile) and request a client-secret. Copy this somewhere as you'll need it for your authorisation token, and it is not displayed in your account. 

## Getting an authorisation token 
You can get an authorisation token by using the following curl command. Replace [CLIENT-ID] and [CLIENT-SECRET] with your own credentials. For me, the client-id was my university email address. For more information, or if you run into difficulty, see the [API documentation](https://www.legalintelligence.com/handleidingen/api-technical-information/).

``` 
curl -k  -L -X POST -H 'Content-Type: application/x-www-form-urlencoded' -H 'X-SubSiteCode: LI' -d 'grant_type=client_credentials&client_id=[CLIENT-ID]&client_secret=[CLIENT-SECRET]' 'https://api.legalintelligence.com/token'
```

This should return a large string, which is your Authorisation Token. Copy this. 

## Insert authorisation token in workflow
Open the imported workflow in Alfred. 
Open the Environmental Variables and insert your with your Authorisation Token at the token variable. 

Save and that ought to do it!


# TODO
- [X] ~~Fix bug that less than 10 results won't be displayed. (has to do with the use of count function)
- [x] ~~Include a delay, so that api is not called for each letter that is typed
- [x] ~~Find a way that login is not required in browser for it to work
- [ ] Find a way to automatically generate authorisation token
- [x] ~~Insert a link to all the search results in Legal Intelligence itself 
