## Auth
<details>
<summary>
Login

Used to collect a Token for a registered User.

**URL** : `/auth/login/`

**Method** : `POST`
</summary>

**Auth required** : NO

**Data constraints**

```json
{
  "walletId": "[valid near address]",
}
```

**Data example**

```json
{
  "walletId": "duck2020.testnet",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
  "user": {
    "walletId": "duck2020.testnet"
  },
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiIxMjExMTExMTExMTExMTExMTExMSIsImlhdCI6MTY1MDI3NzQ0MiwiZXhwIjoxNjUwMzc3NDQyfQ.OwjFrp6GduXAsF76Ft_xf8f58MyoQetq6-n6p9qjGBI",
  "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiIxMjExMTExMTExMTExMTExMTExMSIsImlhdCI6MTY1MDI3NzQ0MiwiZXhwIjoxNjUwMzc3NDQyfQ.F8J_lWrNOhBGa2UCYfpK2zrV-X36MzmAGSMSfR0nCkM"
}
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>

<details>
<summary>
Logout

Used to logout and refreshToken deletion.

**URL** : `/auth/logout/`

**Method** : `POST`
</summary>

**Auth required** : NO

**Data constraints**

```json
{
  "refreshToken": "[contained in cookies]",
}
```

**Data example**

```json
{
  "refreshToken": "eyJhbGciOiJIUzI1NiIsI......EzxnH4DlFv9OZLl4cHApJYnM",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
  
}
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>

<details>
<summary>
Refresh token

Used to refresh accessToken and refreshToken.

**URL** : `/auth/refresh/`

**Method** : `POST`
</summary>

**Auth required** : NO

**Data constraints**
 
```json
{
  "refreshToken": "[contained in cookies]",
}
```

**Data example**

```json
{
  "refreshToken": "eyJhbGciOiJIUzI1NiIsI......EzxnH4DlFv9OZLl4cHApJYnM",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "user": {
        "walletId": "duck2020.testnet"
    },
    "accessToken": "eyJhbGciOiJIUzI1NiIs.....ZcQ5mUqbl1StDnjMeqk",
    "refreshToken": "eyJhbGciOiJIUzI1Nig.....OO6nR97hio1qb22_EqU"
}
```
</details>


## Profile
<details>
<summary>
Get profile data

Used to get profile data about a registered User.

**URL** : `/profile/get_profile/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "is extracted automatically from the accessToken",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
  "id": 1,
  "walletId": 12321,
  "profilePicture": null,
  "country": "USA",
  "documentType": "passport",
  "passportNumber": "191493",
  "name": "Test",
  "surname": "TestSur",
  "patronymicName": "TestPatronymic",
  "createdAt": "2022-04-18T10:48:17.000Z",
  "completed": false
}
```
</details>
<details>
<summary>
Update profile data

Used to update profile data of registered User. All parameters are optional and you can update only one of parameter

**URL** : `/profile/update_profile/`

**Method** : `POST`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "[is extracted automatically from the accessToken]",
  "profilePicture":"[img in base64]",
  "country": "[string]",
  "documentType":"[string]",
  "passportNumber":"[string]",
  "name":"[string]",
  "surname":"[string]",
  "patronymicName":"[string]",
  "affiliate":"[string]",
  "email":"[string]",
  "instagram":"[string]",
  "twitter":"[string]",
  "discord":"[string]",
  "bio":"[string]",
  "website":"[string]",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
Request Body
{
  "profilePicture": null,
  "country": "USA",
  "documentType": "passport",
  "passportNumber": "191493",
  "name": "Test",
  "surname": "TestSur",
  "patronymicName": "TestPatronymic",
  "affiliate":"Test",
  "email":"Test",
  "instagram":"Test",
  "twitter":"Test",
  "discord":"Test",
  "bio":"Test",
  "website":"Test",
}
```


## Success Response

**Code** : `200 OK`

**Content example**

```json
{
  "id": 1,
  "walletId": 12321,
  "profilePicture": null,
  "country": "USA",
  "documentType": "passport",
  "passportNumber": "191493",
  "name": "Test",
  "surname": "TestSur",
  "patronymicName": "TestPatronymic",
  "createdAt": "2022-04-18T10:48:17.000Z"
  "completed": false
}
```
</details>

<details>
<summary>
Get completed profiles

Used to get a list of completed profiles

**URL** : `/profile/get_completed_profiles/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "is extracted automatically from the accessToken",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
```

## Success Response

**Code** : `200 OK`
  
 Array of completed profiles:

**Content constraints**

```json
[
     {
        "walletId": "[string]",
        "name": "[string]",
        "surname": "[string]",
        "profilePicture": "[image in base64]"
     }
]
```

**Content example**

  
```json
[
    {
        "walletId": "1111111222.testnet",
        "name": "Test123",
        "surname": "TestSur",
        "profilePicture": "eyJhbGci....OiJIU"
    },
    {
        "walletId": "11111.testnet",
        "name": "Test",
        "surname": "TestSur",
        "profilePicture": "eyJhbG....ciOiJIU"
    }
]
```
  
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
  
</details>


<details>
<summary>
Get a profile picture.

Used to get a profile picture by walletId.

**URL** : `/profile/get_image/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "is extracted automatically from the accessToken",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
```

## Success Response

**Code** : `200 OK`
  
 Array of completed profiles:

**Content constraints**

```json
     {
        "profilePicture": "[image in base64]"
     }
```

**Content example**

  
```json
  
    {

        "profilePicture": "eyJhbG....ciOiJIU"
    }

```
  
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
  
</details>

## IPFS data
<details>
<summary>
Upload image

Used to upload a file to ipfs.

**URL** : `/ipfs/upload/`

**Method** : `POST`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "[is extracted automatically from the accessToken]",
  "data":"[img in base64]",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
Request Body
{
  "data": "JVBERi0xLjcNCiW1tbW1DQo.....IDAgb2JqDQo8PC9UeXBlL0NhdGFs",
}
```


## Success Response

**Code** : `200 OK`

**Content example**

```json
{
  "hash": "QmVTh5EFPXTuoKPUZAKyNE25241v3xGeek8jHKsKSRKqCE"
}
```
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>
<details>
<summary>
Download a file from ipfs
  
Used to download a previously downloaded file from ipfs.

**URL** : `/ipfs/download/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "[is extracted automatically from the accessToken]",
  "hash": "[string]",
}
```

**Data example**

```json
{
  "walletId": "duck2020.testnet",
  "hash": "QmVTh5EFPXTuoKPUZAKyNE25241v3xGeek8jHKsKSRKqCE",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "filename": "QmVTh5EFPXTuoKPUZAKyNE25241v3xGeek8jHKsKSRKqCE.pdf",
    "data": "JVBERi0xLjcNCiW1tbW1DQoxIDAgb2......JqDQo8PC9UeXBlL0NhdGFsb2cvUGFnZ",
}
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
  
</details>

## Agreements
<details>
<summary>
Add agreement

Used to add agreement.

**URL** : `/agreement/add/`

**Method** : `POST`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "[is extracted automatically from the accessToken]",
  "type":"[string]",
  "text": "[string]",
  "description":"[string]",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
Request Body
{
  "type":"full",
  "text": "My agreement 24/04/2022",
  "description":"My first test agreement.",
}
```


## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "id": 2,
    "type": "full",
    "text": "My agreement 24/04/2022",
    "description": "My first test agreement."
}
```
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
  
</details>
</details>

<details>
<summary>
Get text by type

Used to get text of agreement by type.

**URL** : `/agreement/get_text/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "is extracted automatically from the accessToken",
  "type":"[string]",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
  
Request params
{
  "type":"Test",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "text": "My agreement 24/04/2022"
}
```
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
  
</details>
</details>


<details>
<summary>
Get agreements

Used to get all agreements.

**URL** : `/agreement/get_agreements/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "walletId": "is extracted automatically from the accessToken",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
```

## Success Response

**Code** : `200 OK`

**Content example**

List of agreements:
  
```json
[
    {
        "id": 1,
        "type": "11111111testType",
        "text": "My agreement №1 24/04/2022",
        "description": "My first test agreement"
    },
    {
        "id": 2,
        "type": "testType",
        "text": "My agreement №2 24/04/2022",
        "description": "Test description"
    }
]
```
  
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```

  
</details>

## Minting
<details>
<summary>
  Used to get ips links for <code>media</code> and <code>refernce</code>
  
**URL** : `/nft/mint/`

**Method** : `POST`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
  "title":"[string]",
  "description": "[string]",
  "category":"[string]",
  "media": "[img in base64]",
  "typeOfMedia":"[string]",
  "sellType":"[string]",
  "collection": "[string]",
  "tags":"[string]",
}
  
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
Request Body
{
  "title":"Tiger",
  "description": "Tiger",
  "category":"Animals",
  "media": "R0lGODlhMgA.......yAPcAAAAA",
  "typeOfMedia":"",
  "sellType":"",
  "collection": "Test",
  "tags":"",
}
```


## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "address": "0:af513d6a7d8c0bcaeb502bbcf56e204427ef4d4510458b25a42773c25012586e",
}
```
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
  
</details>


## Admin
<details>
<summary>
Admin dashboard.

Used to admin login.

**URL** : `/admin/login`

**Method** : `POST`
</summary>

**Auth required** : NO

**Data constraints**

```json
{
    "login": "[string]",
    "password": "[string]"
}
```

**Data example**

```json
{
    "login": "admin",
    "password": "password",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
true/false
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
    "errorMessage": "Error while admin login"
}
```
  
</details>

<details>
<summary>
Get all collections.

Used to get all collections.

**URL** : `/admin/get_collections`

**Method** : `GET`
</summary>

**Auth required** : NO

**Data constraints**

```json
{
    "login": "[string]",
    "password": "[string]"
}
```

**Data example**

```json
{
    "login": "admin",
    "password": "password",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
*List of collections info*
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
    "errorMessage": "Error while admin login"
}
```
  OR
 ```json
{
}
```
  
</details>


<details>
<summary>
Get all profiles.

Used to get all profiles.

**URL** : `/admin/get_profiles`

**Method** : `GET`
</summary>

**Auth required** : NO

**Data constraints**

```json
{
    "login": "[string]",
    "password": "[string]"
}
```

**Data example**

```json
{
    "login": "admin",
    "password": "password",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
*List of profiles info*
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
    "errorMessage": "Error while admin login"
}
```
  OR
 ```json
{
}
```
  
</details>




## Collections
<details>
<summary>
Create colletion.

Used to create collections.

**URL** : `/collections/create_collection`

**Method** : `POST`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
    "walletId": "[is extracted automatically from the accessToken]",
    "picture": "[img in base64]",
    "name": "[string]",
    "description": "[string]",
}
```

**Data example**

```json
{
    "walletId": "duck2020.testnet",
    "picture": "KJDJKK.....KDFKKK",
    "name": "Name",
    "description": "Test collection",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "id": 3,
    "walletId": "duck2020.testnet",
    "name": "Name",
    "picture": "KJDJKK.....KDFKKK",
    "description": "Test collection.",
    "createdAt": "2022-04-26T21:21:10.000Z"
}
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
    "errorMessage": "The collection name is not unique"
}
```
  
  or

  ```json
{

}
  ```
  
  
</details>



<details>
<summary>
Get all colletions.

Used to get all colletions info.

**URL** : `/collections/get_collections`

**Method** : `GET`
</summary>

**Auth required** : NO

**Data constraints**

```json
{
}
```

**Data example**

```json
{
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "id": 1,
        "walletId": "duck2020.testnet",
        "name": "First",
        "picture": null,
        "description": "Chess collection.",
        "totalSupply": "5",
        "createdAt": "2022-04-26T21:19:24.000Z"
    },
    {
        "id": 2,
        "walletId": "duck2020.testnet",
        "name": "Second",
        "picture": null,
        "description": "Small village near Chicago.",
        "totalSupply": "4",
        "createdAt": "2022-04-26T21:19:26.000Z"
    }
]
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>




<details>
<summary>
Get colletions by walletId.

Used to get colletions by walletId.

**URL** : `/collections/get_collections_by_wallet`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
    "walletId": "[is extracted automatically from the accessToken]",
}
```

**Data example**

```json
{
    "walletId": "duck2020.testnet",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "id": 1,
        "walletId": "duck2020.testnet",
        "name": "First",
        "picture": null,
        "description": "Chess collection.",
        "totalSupply": "5",
        "createdAt": "2022-04-26T21:19:24.000Z"
    },
    {
        "id": 2,
        "walletId": "duck2020.testnet",
        "name": "Second",
        "picture": null,
        "description": "Small village near Chicago.",
        "totalSupply": "5",
        "createdAt": "2022-04-26T21:19:26.000Z"
    }
]
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>




<details>
<summary>
Get colletions by id.

Used to get colletion info by id.

**URL** : `/collections/get_collection_by_id`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
    "id": "[number]",
}
```

**Data example**

```json
{
    "id": "1",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "collection": {
        "id": 1,
        "walletId": "duck2020.testnet1212332",
        "name": "",
        "description": null,
        "picture": null,
        "totalSupply": "5",
        "createdAt": "2022-04-30T13:41:45.000Z"
    },
    "collectionTokens": 0
}

```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>



<details>
<summary>
Get colletion tokens by collection id.

Used to get colletion tokens by collection id.

**URL** : `/collections/get_collection_tokens_by_id`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
    "id": "[number]",
}
```

**Data example**

```json
{
    "id": "1",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "title": "CONTROL TEST",
        "description": "test",
        "price": "10",
        "media": "bafybeig66lnkx2fx4hdrxvcrfl76f2hwcfwyr4voqdbbh3duvs6lda47ma.ipfs.infura-ipfs.io",
        "collection": "Test",
        "address": "0:3213540b6c5baa579dc21d6d436be84468201146a5992edcfccb1df50a3452f4",
        "owner": "0:decc4291fcb1f4818413f6de58ffa5e44a222bf32a2fa56f04dc34e959f47948",
        "creator": "0:0eb093156b485497001f06cf5332861b34f306963c2476af5f433fe7050da0a0",
        "createdAt": "1651671222"
    }
]

```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>


<details>
<summary>
Get colletion image by collection name.


**URL** : `/collections/get_collection_image`

**Method** : `GET`
</summary>

**Auth required** : NO

**Data constraints**

```json
{
    "name": "[string]",
}
```

**Data example**

```json
{
    "name": "Test collection",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json

{
        "picture": "kkgkfgkkfgkg.....fgklfkgfkfgkfg",
}

```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>





## Items
<details>
<summary>
Create item.

Used to create items for collections.

**URL** : `/items/create_item`

**Method** : `POST`
</summary>

**Auth required** : YES
 
**Data constraints**

```json
{
  "walletId": "[is extracted automatically from the accessToken]",
  "name": "[string]",
  "description": "[string]",
  "address": "[string]",
  "image": "[img in base64]",
  "collection": "[number]",
  "tags": "[string]",
  "price": "[number]"
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
Request Body
{
  "name": "Test4",
  "description": "My Test Collection",
  "address": "23456782345678923456789345678945678",
  "image": "lfldfkfdkgkddgkdkdkgldgkdkflgkdflflkkfdldffk",
  "collection": "1",
  "tags": "Epic",
  "price": "10000"
}
```
  
## Success Response

**Code** : `200 OK`

**Content example**

```
{
    "id": 3,
    "address": "23456782345678923456789345678945678",
    "name": "Test4",
    "description": "My Test Collection",
    "image": "kfdkljdfkfdfjl...dfdkfdjkfkdfkd",
    "collection": 1,
    "tags": "Epic",
    "price": 10000,
    "creator": "duck2020.testnet",
    "owner": "duck2020.testnet",
    "createdAt": "2022-04-26T21:53:12.000Z"
}

```
## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>


<details>
<summary>
Get item by wallet.

Used to get item by wallet.

**URL** : `/get_items_by_wallet/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
    "walletId": "[is extracted automatically from the accessToken]",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
  ```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "id": 1,
    "address": "23456782345678923456789345678945678",
    "name": "Test4",
    "description": "My Test Collection",
    "image": "fkfkfkfkf....ffkdkfdkdf",
    "collection": 1,
    "tags": "Epic",
    "price": 10000,
    "creator": "duck2020.testnet",
    "owner": "duck2020.testnet",
    "createdAt": "2022-04-26T21:39:47.000Z"
}
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>


<details>
<summary>
Get item by id.

Used to get item by id.

**URL** : `/items/get_item_by_id/`

**Method** : `GET`
</summary>

**Auth required** : YES

**Data constraints**

```json
{
    "walletId": "[is extracted automatically from the accessToken]",
}
```

**Data example**

```json
Request Headers
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3YWxsZXRfaWQiOiJjMTliMDAzMzk0IiwiaWF0IjoxNjUwMzkzMzI2LCJleHAiOjE2NTAzOTUxMjZ9.7pFlmZH_4yMVM9RAkUOMBZgJFFyGRVEZ5ZM0fKyjoGM"
}
  ```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "id": 1,
    "address": "23456782345678923456789345678945678",
    "name": "Test4",
    "description": "My Test Collection",
    "image": "fkfkfkfkf....ffkdkfdkdf",
    "collection": 1,
    "tags": "Epic",
    "price": 10000,
    "creator": "duck2020.testnet",
    "owner": "duck2020.testnet",
    "createdAt": "2022-04-26T21:39:47.000Z"
}
```

## Error Response

**Condition** : -

**Code** : `400 BAD REQUEST`

**Content** :

```json
{

}
```
</details>


## Error responses

Errors are divided into:
<details>
<summary>
Expected
</summary>
Expected errors in the response contain <code>errorMessage</code>.
</details>
<details>
<summary>
Unexpected
</summary>
Unexpected errors contain similar field <code>errorMessage</code>, but two additional fields appear: <code>error</code> with an error description automatically taken from the exception name, and <code>description</code> with an array of data about this error. Below are examples of anticipated errors error 404 and error 401, as well as an unexpected error on the example of error 400.
The status 401 is returned in case of unsuccessful authorization, 404 in case of not found, 400 in case of other expected and unexpected errors when processing the request.
</details>


### Errors

<details>
<summary>404</summary>

```json
{
  "errorMessage": "Not found"
}
```
</details>

<details>
<summary>401</summary>

```json
{
  "errorMessage": "User is not authorized!"
}
```
</details>
<details>
<summary>400</summary>

```json
{
    "errorMessage": "Bad Request: Error while update profile",
    "error": "error: столбец \"RRRRR\" в таблице \"users\" не существует",
    "description": {
        "length": 220,
        "name": "error",
        "severity": "ОШИБКА",
        "code": "42703",
        "position": "29",
        "file": "d:\\pginstaller_13.auto\\postgres.windows-x64\\src\\backend\\parser\\analyze.c",
        "line": "2341",
        "routine": "transformUpdateTargetList"
    }
}
```
</details>
