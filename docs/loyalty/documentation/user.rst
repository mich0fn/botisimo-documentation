User API
========

- `List Users`_
- `Get User`_
- `Update User`_
- `Upload A Custom Avatar`_

List Users
----------

List user leaderboard ranked by most points to least points (top 100)

- **GET** /user/list

Request

=========== ======== ==========================================
Field       Type     Description
=========== ======== ==========================================
\-          \-       \-
=========== ======== ==========================================

.. code-block:: js

   const response = await axios.get('https://botisimo.com/api/v1/loyalty/:team/user/list', {
      headers: {
         'x-user-auth-token': 'xxxxxxx',
      },
   });

Response

================================== ======== =================================================================================
Field                              Type     Description
================================== ======== =================================================================================
users                              object   Information about the logged in user
users.avatar                       string   URL to to user avatar
users.createdAt                    string   When the user was created
users.gold                         number   Number of loyalty points the user currently has available
users.goldTotal                    number   Number of loyalty points the user has earned all time
users.goldSpent                    number   Number of loyalty points the user has spent
users.id                           number   The ID of the user
users.loyaltyMembership            [object] The membership the user is subscribed to
users.loyaltyMembership.id         number   The ID of the membership
users.loyaltyMembership.name       string   The name of the membership
users.loyaltyMembership.priceMonth number   The cost of the membership per month in cents
users.loyaltyMembership.priceYear  number   The cost of the membership per year in cents
users.loyaltyMembership.resourceId number   The resource ID of the membership badge icon
users.loyaltyTier                  [object] The tier the user is subscribed to
users.loyaltyTier.id               number   The ID of the tier
users.loyaltyTier.name             string   The name of the tier
users.loyaltyTier.gold             number   The points required to achieve tier
users.loyaltyTier.resourceId       number   The resource ID of the tier badge icon
users.name                         string   The name of the user
users.tags                         object[] List of tags the user is interested in
users.tags.id                      number   The ID of the tag
users.tags.name                    string   The name of the tag
================================== ======== =================================================================================

Get User
--------

Get information about the authenticated user

- **GET** /user

Request

=========== ======== ==========================================
Field       Type     Description
=========== ======== ==========================================
\-          \-       \-
=========== ======== ==========================================

.. code-block:: js

   const response = await axios.get('https://botisimo.com/api/v1/loyalty/:team/user', {
      headers: {
         'x-user-auth-token': 'xxxxxxx',
      },
   });

Response

================================= ======== ==========================================================================
Field                             Type     Description
================================= ======== ==========================================================================
unread                            number   Number of unread notifications for this user
user                              object   Information about the logged in user
user.avatar                       string   URL to to user avatar
user.createdAt                    string   When the user was created
user.dateOfBirth                  string   Date of birth formatted as ``MM/DD/YYYY``
user.gold                         number   Number of loyalty points the user currently has available
user.goldTotal                    number   Number of loyalty points the user has earned all time
user.goldSpent                    number   Number of loyalty points the user has spent
user.id                           number   The ID of the user
user.loyaltyMembership            [object] The membership the user is subscribed to
user.loyaltyMembership.id         number   The ID of the membership
user.loyaltyMembership.name       string   The name of the membership
user.loyaltyMembership.priceMonth number   The cost of the membership per month in cents
user.loyaltyMembership.priceYear  number   The cost of the membership per year in cents
user.loyaltyMembership.resourceId number   The resource ID of the membership badge icon
user.loyaltyTier                  [object] The tier the user is subscribed to
user.loyaltyTier.id               number   The ID of the tier
user.loyaltyTier.name             string   The name of the tier
user.loyaltyTier.gold             number   The points required to achieve tier
user.loyaltyTier.resourceId       number   The resource ID of the tier badge icon
user.name                         string   The name of the user
user.notifications                string   The last time the user read the notifications formatted as ISO date string
user.shippingAddressCity          string   Shipping info for the user
user.shippingAddressCountry       string   Shipping info for the user
user.shippingAddressName          string   Shipping info for the user
user.shippingAddressState         string   Shipping info for the user
user.shippingAddressStreet        string   Shipping info for the user
user.shippingAddressSuite         string   Shipping info for the user
user.shippingAddressZip           string   Shipping info for the user
user.tags                         object[] List of tags the user is interested in
user.tags.id                      number   The ID of the tag
user.tags.name                    string   The name of the tag
================================= ======== ==========================================================================

Example

.. code-block:: js

    {
        "unread": 0,
        "user": {
            "id": 30758,
            "createdAt": "2021-07-12T21:15:53.000Z",
            "updatedAt": "2022-04-08T17:05:55.000Z",
            "emailUser": {
                "id": 1239,
                "email": "oscar@otothea.com",
                "name": "oscar@otothea.com",
                "displayName": "Oscar",
                "createdAt": "2021-07-12T02:00:00.000Z"
            },
            "twitchUser": {
                "id": 2,
                "twitchId": 87416554,
                "name": "otothea",
                "chatName": "otothea",
                "displayName": "OtotheA",
                "createdAt": "2017-02-25T02:31:31.000Z"
            },
            "youtubeUser": {
                "id": 129076,
                "youtubeChannelId": "UCjX4fLpD7BNtYwuLEl2xwPg",
                "name": "botisimo",
                "displayName": "Botisimo",
                "createdAt": "2018-06-29T04:47:32.000Z"
            },
            "facebookUser": {
                "id": 29,
                "facebookId": "2148122302184574",
                "name": "Luna Doge",
                "displayName": "Luna Doge",
                "createdAt": "2020-06-22T20:38:48.000Z"
            },
            "twitterUser": {
                "id": 1,
                "twitterId": "835748192708923392",
                "name": "Botisimo",
                "displayName": "Botisimo",
                "createdAt": "2021-03-24T01:56:45.000Z"
            },
            "discordUser": {
                "id": 1,
                "discordId": "187951925965225984",
                "name": "OtotheA",
                "displayName": "OtotheA",
                "createdAt": "2017-02-24T23:07:04.000Z"
            },
            "spotifyUser": {
                "id": 1,
                "spotifyId": "1221486274",
                "name": "1221486274",
                "displayName": "Chip Armstrong",
                "createdAt": "2021-04-06T22:35:06.000Z"
            },
            "steamUser": {
                "id": 1,
                "steamId": "76561197978302905",
                "name": "OtotheA",
                "displayName": "Oscar",
                "createdAt": "2022-02-25T20:54:39.000Z"
            },
            "tiktokUser": {
                "id": 1,
                "tiktokId": "76561197978302905",
                "name": "OtotheA",
                "displayName": "Oscar",
                "createdAt": "2022-02-25T20:54:39.000Z"
            },
            "name": "otothea",
            "avatar": "https://static-cdn.jtvnw.net/jtv_user_pictures/974caf6e-4ad3-4d42-a495-7e73280a2c36-profile_image-300x300.png",
            "notifications": "2022-04-08T16:53:36.000Z",
            "loyaltyMembership": {
                "id": 4,
                "enabled": true,
                "archived": false,
                "order": 0,
                "name": "Gold",
                "description": "Stay connected with your favorite teams, players, and creators at OpTic!",
                "priceMonth": 500,
                "priceYear": 3000,
                "goldMultiplier": 1,
                "stripeProductId": "prod_xxxxx",
                "stripeMonthlyPlanId": "plan_xxxxx
                "stripeYearlyPlanId": "plan_xxxxx",
                "resourceId": 6812,
                "badgeResourceId": null,
                "createdAt": "2022-03-07T22:58:17.000Z",
                "updatedAt": "2022-03-19T15:25:25.000Z"
            },
            "loyaltyTier": {
                "id": 4,
                "enabled": true,
                "order": 0,
                "name": "Prestige 1",
                "description": "Stay connected with your favorite teams, players, and creators at OpTic!",
                "gold": 0,
                "resourceId": 6812,
                "badgeResourceId": null,
                "createdAt": "2022-03-07T22:58:17.000Z",
                "updatedAt": "2022-03-19T15:25:25.000Z"
            },
            "dateOfBirth": "06/25/1988",
            "shippingAddressName": null,
            "shippingAddressStreet": null,
            "shippingAddressSuite": null,
            "shippingAddressCity": null,
            "shippingAddressState": null,
            "shippingAddressZip": null,
            "shippingAddressCountry": null,
            "tags": [
                {
                    "id": 3,
                    "name": "OpTic Texas",
                    "createdAt": "2022-03-07T23:15:50.000Z"
                },
                {
                    "id": 9,
                    "name": "Scump",
                    "createdAt": "2022-03-08T21:40:08.000Z"
                }

                ...
            ],
            "gold": 2519385,
            "goldSpent": 10040000,
            "goldTotal": 12559385
        }
    }

Update User
-----------

Update profile information for the authenticated user

- **PUT** /user

Request

====================== ========== ==========================================================================
Field                  Type       Description
====================== ========== ==========================================================================
email                  [string]   Update the email address
dateOfBirth            [string]   Date of birth formatted as ``MM/DD/YYYY``
shippingAddressCity    [string]   Shipping info for the user
shippingAddressCountry [string]   Shipping info for the user
shippingAddressName    [string]   Shipping info for the user
shippingAddressState   [string]   Shipping info for the user
shippingAddressStreet  [string]   Shipping info for the user
shippingAddressSuite   [string]   Shipping info for the user
shippingAddressZip     [string]   Shipping info for the user
avatarResourceId       [number]   Update custom avatar resource (see `Upload A Custom Avatar`_)
username               [string]   Update custom username
tags                   [number[]] List of tag IDs the user is interested in
====================== ========== ==========================================================================

.. code-block:: js

   const response = await axios.put('https://botisimo.com/api/v1/loyalty/:team/user', {
      dateOfBirth: '01/01/1990',
      username: 'myusername'
   }, {
      headers: {
         'x-user-auth-token': 'xxxxxxx',
      },
   });

Response

================================= ======== ==========================================================================
Field                             Type     Description
================================= ======== ==========================================================================
unread                            number   Number of unread notifications for this user
user                              object   Information about the logged in user
user.avatar                       string   URL to to user avatar
user.createdAt                    string   When the user was created
user.dateOfBirth                  string   Date of birth formatted as ``MM/DD/YYYY``
user.gold                         number   Number of loyalty points the user currently has available
user.goldTotal                    number   Number of loyalty points the user has earned all time
user.goldSpent                    number   Number of loyalty points the user has spent
user.id                           number   The ID of the user
user.loyaltyMembership            [object] The membership the user is subscribed to
user.loyaltyMembership.id         number   The ID of the membership
user.loyaltyMembership.name       string   The name of the membership
user.loyaltyMembership.priceMonth number   The cost of the membership per month in cents
user.loyaltyMembership.priceYear  number   The cost of the membership per year in cents
user.loyaltyMembership.resourceId number   The resource ID of the membership badge icon
user.loyaltyTier                  [object] The tier the user is subscribed to
user.loyaltyTier.id               number   The ID of the tier
user.loyaltyTier.name             string   The name of the tier
user.loyaltyTier.gold             number   The points required to achieve tier
user.loyaltyTier.resourceId       number   The resource ID of the tier badge icon
user.name                         string   The name of the user
user.notifications                string   The last time the user read the notifications formatted as ISO date string
user.shippingAddressCity          string   Shipping info for the user
user.shippingAddressCountry       string   Shipping info for the user
user.shippingAddressName          string   Shipping info for the user
user.shippingAddressState         string   Shipping info for the user
user.shippingAddressStreet        string   Shipping info for the user
user.shippingAddressSuite         string   Shipping info for the user
user.shippingAddressZip           string   Shipping info for the user
user.tags                         object[] List of tags the user is interested in
user.tags.id                      number   The ID of the tag
user.tags.name                    string   The name of the tag
================================= ======== ==========================================================================

Upload A Custom Avatar
----------------------

Use this endpoint to get a URL for uploading a custom avatar

- **GET** /resource

Request

=========== ======== ==========================================
Field       Type     Description
=========== ======== ==========================================
name        string   The name of the file
type        string   The mime type of the file
base64      [string] Set to "true" to enable base64 upload
=========== ======== ==========================================

.. code-block:: js

   const response = await axios.get('https://botisimo.com/api/v1/loyalty/:team/resource', {
      headers: {
         'x-user-auth-token': 'xxxxxxx',
      },
      params: {
         name: 'my-avatar.png',
         type: 'image/png',
      },
   });

Response

=========== ======== ==========================================
Field       Type     Description
=========== ======== ==========================================
url         string   The URL to upload the image to
resourceId  number   The ID of the resource
=========== ======== ==========================================

.. code-block:: js

   {
      "url": "https://s3.amazon-aws.com/xxxxx",
      "resourceId": 65
   }

Full Example

1. Get a URL to use to upload the file
2. Upload the file to the URL
3. Update the avatarResourceId for the user

.. code-block:: js

   async function onUploadFile(file) {
      if (file) {
         // Get a URL to use to upload the file
         const response = await axios.get('https://botisimo.com/api/v1/loyalty/:team/resource', {
            headers: {
               'x-user-auth-token': 'xxxxxxx',
            },
            params: {
               name: file.name, // ex: my-avatar.png
               type: file.type, // ex: image/png
            },
         });

         // Upload the file to the URL
         const uploadResponse = await axios.put(response.data.url, file, {
            headers: {
               'Content-Type': file.type,
            },
            withCredentials: false,
         });

         // Update the avatarResourceId for the user
         if (uploadResponse.status === 200) {
            const updateResponse = await axios.put(
               'https://botisimo.com/api/v1/loyalty/:team/user',
               { avatarResourceId: response.data.resourceId },
               {
                  headers: {
                     'x-user-auth-token': 'xxxxxxx',
                  },
               }
            );
         }
      }
   }

   ...

   <input type="file" onchange="onUploadFile(this.files[0]);">

Also supports Base64 uploads

.. code-block:: js

   async function onUploadBase64(name, type, base64String) {
      // Get a URL to use to upload the file
      const response = await axios.get('https://botisimo.com/api/v1/loyalty/:team/resource', {
         headers: {
            'x-user-auth-token': 'xxxxxxx',
         },
         params: {
            name: name,     // ex: my-avatar.png
            type: type,     // ex: image/png
            base64: 'true', // set to 'true' to enable base64 upload
         },
      });

      // Upload the file to the URL
      const uploadResponse = await axios.put(
         response.data.url,
         Buffer.from(base64String, 'base64'),
         {
            headers: {
               'Content-Type': type,
               'Content-Encoding': 'base64', // Must set Content-Encoding to 'base64'
            },
            withCredentials: false,
         }
      );

      // Update the avatarResourceId for the user
      if (uploadResponse.status === 200) {
         const updateResponse = await axios.put(
            'https://botisimo.com/api/v1/loyalty/:team/user',
            { avatarResourceId: response.data.resourceId },
            {
               headers: {
                  'x-user-auth-token': 'xxxxxxx',
               },
            }
         );
      }
   }

