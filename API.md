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
  "patronymicName":"[string]"
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

## Preparation for minting
<details>
<summary>
  Used to get json for mint
  
**URL** : `/nft/upload_data/`

**Method** : `POST`
</summary>

**Auth required** : YES
  
**Socket** //it may be wrong
Socket at `/nft/upload_data` on port `4000`
  
After upload media and previews:
  
```
  mintSocket.on("connection", (socket: Socket) => {
                socket.emit(`progress`, 1);
            });
```
  
Aafter generating the agreement and uploading:
  
```
  mintSocket.on("connection", (socket: Socket) => {
                socket.emit(`progress`, 2);
            });
```
  

**Data constraints**

```json
{
  "media":"[base64]",
  "title":"[string]",
  "description":"[string]",
  "previews":"[Array of Data base64]",
  "receiverId": "[string]", 
  "documentType":"[string]"
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
  
  "media": "R0lGODlhMgA.......yAPcAAAAA",
  "title": "First token",
  "description": "Test token",
  "documentType": "none",
  "previews": [ "R0lGODlh////MzP.....Mmf/MZv/M", "R0lGODlhcwBxAPU....Mmf/MZv/M" ],
  "receiverId": "122121312312.testnet", 
  "documentType": "none"
}
```


## Success Response

**Code** : `200 OK`

**Content example**

```json

  
{
    "mintParams": {
                    "token_id": 1,
                    "receiver_id": "122121312312.testnet",
                    "metadata": {
                        "title": "TESTTESTTESTTESTTESTTESTTESTTESTTESTTESTTESTTEST",
                        "description": "test",
                        "media": "bafybeiex62a6qqqxzdlottdaoqhpfelu2ddip45kn3upgvoxlgwi4zq3gi.ipfs.infura-ipfs.io",
                        "reference": "bafybeibsggvf2q3hvp2z7uxk5uepmojchunlkcsfp7ttpsvpi67oia6jpi.ipfs.infura-ipfs.io",
                        "copies": 1
                    }
    },
    "documentUrl": "bafybeigcbx6gbp5jhqshm2gctf73vvfucjk45zsqwkb3sdedcpqipn463q.ipfs.infura-ipfs.io"
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

## Error response

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
