# IN-HOUSE API

Tutorial use API In-House

## APP

# Get all apps advertisement

```bash
GET : /apps/{page}/{per_page}
```

```bash
    PARAM     | DESCRIPTION

    page      | page number to retrieve(default =1)
    per page  | number of items per page (default =10)
```

```bash
Response : code 200
value : 
{
 "apps":[
  {
  "id" : Int ,
  "iconUrl" : String ,
  "title" : String,
   "des" : String ,
  "imageUrls" : <String>[] ,
  "videoUrl" : String,
   "rateCount" : Int ,
  "totalInstallCount" :  Int,
  "platform": String
  },
  {
  "id" : Int ,
  "iconUrl" : String ,
  "title" : String,
   "des" : String ,
  "imageUrls" : <String>[] ,
  "videoUrl" : String,
   "rateCount" : Int ,
  "totalInstallCount" :  Int.
  "platform": String
  }
 ],
 "isLoadMore": bool
}
```

function 2. Delete app from server

```bash
DELETE /apps/{id}/delete
```
```bash
Response : code 200
```
function 3. Add new app

```bash
POST /apps/create_app
```
```bash
Body: 
{
  "iconUrl" : String ,
  "title" : String,
   "des" : String ,
  "imageUrls" : <String>[] ,
  "videoUrl" : String,
   "rateCount" : Int ,
  "totalInstallCount" :  Int
}
```
```bash
Response : code 200
```

function 4. Get info app
```bash
GET /apps/{id}
```

```bash
Response : code 200
value : 
{
  "id" : Int ,
  "iconUrl" : String ,
  "title" : String,
   "des" : String ,
  "imageUrls" : <String>[] ,
  "videoUrl" : String,
   "rateCount" : Int ,
  "totalInstallCount" :  Int
}
```

function 5. Update info App
```bash
POST /apps/:id
```
```bash
Body: 
{ 
  "id": Int
  "iconUrl" : String 
  "title" : String 
  "des" : String 
  "imageUrls" : <String>[]
   "videoUrl" : String 
  "rateCount" : Int 
  "totalInstallCount" : Int  
}
```
```bash
Response : code 200 - success
```

function 6. Restore App
```bash
GET /apps/{id}/restore
```

```bash
Response : code 200
value : 
{
  "iconUrl" : String ,
  "title" : String,
   "des" : String ,
  "imageUrls" : <String>[] ,
  "videoUrl" : String,
   "rateCount" : Int ,
  "totalInstallCount" :  Int
}
```

## Campaign
function 1. Get all campaign
```bash
GET /campaigns/{page}/{perpage}
```
```bash
    PARAM     | DESCRIPTION

    page      | page number to retrieve(default =1)
    per page  | number of items per page (default =10)
```
```bash
Response : code 200
value : 
{
  "campaigns": [
   { 
  "id" : String 
  "iconUrl" : String 
  "title" : String 
  "des" : String 
  "imageUrls" : <String>[]
   "videoUrl" : String 
  "rateCount" : Int 
  "totalInstallCount" : Int   
   },
   { 
  "id" : String 
  "iconUr l" : String 
  "title" : String 
  "des" : String 
  "imageUrls" : <String>[]
   "videoUrl" : String 
  "rateCount" : Int 
  "totalInstallCount" : Int  
   },
  ...
  ],
 "isLoadMore": bool
}
```

function 2. Delete campaign
```bash
DELETE /campaigns/{id}/delete
```

```bash
Response : code 200
```

function 3. Update Campaign
```bash
POST /campaigns/{id}
```
```bash
    PARAM     | DESCRIPTION

    isActive  | state active of campaign (require)   
```
```bash
Response : code 200
```

function 4. Create Campaign
```bash
POST /campaigns/create_campaign
```
```bash
Body: 
{ 
   "id":Integer 
  "name":String
   "note":String 
   "appAds": <String>[]  
  "appObjs":<String>[]  
  "nationals":<String>[]
  " language":<String>[]
  "hobbies":<String>[] 
  "adsType":String[] 
  "isActive":bool 
  "isTemp":bool  
}

```
```bash
Response : code 200
```

function 5. Update Campaign
```bash
POST /campaigns/update_campaign/{id}
```
```bash
Body: 
{ 
  "name":String
   "note":String 
   "appAds": <String>[]  
  "appObjs":<String>[]  
  "nationals":<String>[]
  " language":<String>[]
  "hobbies":<String>[] 
  "adsType":String[] 
  "isActive":bool 
  "isTemp":bool  
}

```
```bash
Response : code 200
```

function 6. Get info campaign
```bash
GET /campaigns/{id}
```

```bash
    PARAM     | DESCRIPTION

    appId     | id of app need show infomation (require) 
 shortDateType| short type do filter infomation with it (require)   
```
```bash
Response : code 200
value : 
{
   "id":Integer 
  "name":String
   "note":String 
   "appPkg": String
  "views": Integer
  "installCount": Integer
  "click": Integer
}
```
InHouse app tutorial
App Manager Screen
- function get all apps from server : [App function 1](#Get all apps advertisement)
- function delete some app :  [App function 2](#af2)
- add more app to server: [App function 3](#af3)
Edit app Screen 
- get info app from server : [App function 4](#af4)
- update info app from server : [App function 5](#af5)
- restore info app : [App function 6](#af6)
Campaign Screen
- get all campaigns from server: [Campaign function 1](#cf1)
- delete some campaign by id : [Campaign function 2](#cf2)
- pause/resume campaign by id : [Campaign function 3](#cf3)
- create new campaign : [Campaign function 4](#cf4)
- update campaign by id : [Campaign function 5](#cf5)
- get info campign by filter : [Campaign function 6](#cf6)


