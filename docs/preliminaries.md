## Issues!!

### Homestead

Some troubles with Homestead latest release. This may have been fixed by the time teaching occurs. But a solution can be found [here](https://stackoverflow.com/questions/56456595/laravel-5-8-a-facade-root-has-not-been-set-after-homestead-restart?noredirect=1&lq=1).



Is essence need to rollback to version 7.2.1. Update homestead.yaml file with  
```
version:7.2.1
```

Update composer.json with  
```
"extra_data":{  
    "box":{  
       "name":"laravel/homestead",
       "provider":"virtualbox",
       "version":"dev-release"
    }
}
```

Then destroy box, remove broken box version and add previous stable box version  
```
vagrant destroy
vagrant box remove laravel/homestead --box-version=8.0.0-alpha2
vagrant box add laravel/homestead --box-version=7.2.1
vagrant up
```

N.B. when you use ```artisan migrate``` you might run into some issues as your .env file will not match current config... Should read  
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```

### Validation
To see the validated response when using FormRequests, ensure that you send the request with the header Accept: application/json

## HTTP
### Methods
### Response Codes
## APIs
## RESTful APIs
### JSON
## Tools - Postman

