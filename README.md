# documentationAPI
lecture on API documentation


FORMAT: 1A
HOST: https://polls.apiblueprint.org/
https://app.apiary.io/documentationlecture/editor

# documentationLecture

The REST API will need to enable users to:

Store people, houses and addresses
Look up a house, it’s address and owner
Look up people in our neighbourhood within certain age brackets and with specific household sizes

## Questions Collection [/all]

### List All People [GET]

+ Response 200 (application/json)

        [
            {
                "people": {
                        "name": "Swift",
                        "age": 2048,
                        "household size": 4
                    }
                "house": {
                        "address": {
                            "street": "21 Mulberry Strt",
                            "postcode": "UB40 341"
                        },
                        "owner": "Jeff"
                    }
            }
        ]

### Create a New Person [POST]

Store people, houses and addresses - need all info as stored in SQL

+ Request (application/json)

        [
            {
                "people": {
                        "name": STR,
                        "age": INT,
                        "household size": INT
                    }
                "house": {
                        "address": {
                            "street": STR,
                            "postcode": STR
                        },
                        "owner": STR
                    }
            }
        ]

+ Response 201 (application/json)

    + Headers

            Location:/people/:postcode
            
            This is a get request to Look up a house, it’s address and owner, using the postcode

    + Body

        [
            {
                "house": {
                        "address": {
                            "street": "STR",
                            "postcode": "STR"
                        },
                        "owner": "STR"
                    }
            }
        ]
        
        
    + Headers   
    
        Location:/people?ages=''-''&household-size=''
        
        Look up people in our neighbourhood within certain age brackets and with specific household sizes
        returns a list of names only
        
    + Body
    
    
    
        [
            {
                "people": {
                        "name": "Swift", "Jeff", "Karen", "Bulbasaur", "Nowshad", "Beth
                        }
            }
        ]
                        
    
    
    
    
                        
    
    
    
    
    
    
