# **Client management**

Using only javascript and HTML, create an application that can add, remove and modify customers to a localStorage Database.

## loadClient(client)

For each client stored in the data base, we need to show it on the `<ul id="client-list">` as a new `<li>`.
Destructure the client to get all the needed information `{name, email, phone, addressInfo: {name, addressNumber}}`, create the new `<li>` using the following template:
```
      li.innerHTML = `
            <strong>USE NAME</strong><br>
            <span>Email: USE EMAIL</span><br>
            <span>Phone: USE PHONE</span><br>
            <span>Address: USE ADDRESS NAME, USE ADDRESS NUMBER</span><br>
            <span>Verified: USE ISVERIFIED</span><br>
            <button class="delete-btn">Delete</button>
            <button class="modify-btn">Modify</button>
            <button class="verify-btn">Verify customer</button>
        `;
```
and append it to `clientList`. 

Finally, add the listeners to all the created buttons.

## addNewClient()

Should add a new client to the localStorage. Create a new client object inside the metod with the attributes `{name, email, phone, addressInfo: {name, addressNumber}}` (that should be retrieved from the form) and save it to the localStorage.
After adding it, the form data should be cleared and the screen have to automatically show the new client, so you will need to call `loadClients()`.

## deleteClient(email)

Using email as the key, retrieve the client from the localStorage and remove it. This method should also reflect the changes done to the localStorage automatically.

## populateFormFields(client)

A simple method that should populate the form fields when you click on "Modify" for any client. 

## updateClient(email)

Get the values of the form fields, validate a name and email are submitted and then create a new object `client` with the needed data. Remove the previous client with this email in the localStorage and then add the new one. ***:warning: Tip : localStorage only accepts JSONs, so you will need to use `JSON.stringify(client)`***.

After that, clear the form, use `resetForm()` to show again the "Add new Client" button and reload the page.

## verifyCustomer(email)

Using this method, the `isVerified` attribute of the client should be set to true. 

To do that, get the client from the localStorage ***Tip :warning: : localStorage returns JSONs, so you will need to use `JSON.parse(client)`*** and then create a new object called `verifiedClient` using the spread operator to copy the client from the localStorage and set the isVerified to true.





