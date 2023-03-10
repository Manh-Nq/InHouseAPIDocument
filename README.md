# IN-HOUSE API

Tutorial use API In-House

# App Manager Screen
- [function get all apps from server](#Get-all-apps-advertisement)
- [function delete some app](#Delete-app-from-server)
- [add more app to server](#Add-more-app-to-server)

# Edit app Screen 
- [get info app from server](#Get-info-app)
- [update info app from server](#Update-info-App)
- [restore info app](#Restore-App)

# Campaign Screen
- [get all campaigns from server](#Get-all-campaign)
- [delete some campaign by id](#Delete-campaign)
- [pause/resume campaign by id](#Update-Campaign)
- [create new campaign](#Create-Campaign)
- [get info campaign by filter](#Get-info-campaign)

# Mobile Client
- [Get all app ads](#Get-all-app-ads)


## APP

### Get all apps advertisement

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

### Delete app from server

```bash
DELETE /apps/{id}/delete
```
```bash
Response : code 200
```
### Add more app to server

```bash
POST /apps/create_app
```
```bash
Body: 
{
  "appUrl":String
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

### Get info app
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

### Update info App
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

### Restore App
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
### Get all campaign
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

### Delete campaign
```bash
DELETE /campaigns/{id}/delete
```

```bash
Response : code 200
```

### Create Campaign
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

### Update Campaign
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

### Get info campaign
```bash
GET /campaigns/{id}
```

```bash
    PARAM     | DESCRIPTION

    appId     | id of app need show infomation (require) 
 shortDateType| sort type do filter infomation with it (require)   
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

# Mobile Client

### Get all app ads
```bash
GET /apps/ads/{id}
```

```bash
    PARAM     | DESCRIPTION

    languagge | String (require) 
    national  | String (require) 
    hobby     | String (require)
appInstalled  | String[](default empty)
```

### Response
```bash
[
 {
  "id" : Int,
  "appUrl":String,
  "iconUrl" : String,
  "title" : String,
  "des" : String,
  "rateCount" : Int,
  "totalInstallCount" :  Int,
  "adsType":String
  },
 ...
]
```
```bash
Response : code 200
```

