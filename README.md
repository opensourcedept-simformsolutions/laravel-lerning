# Basic Practice

## Modules
1. Country
2. City
3. Address

### Country
Create CRUD for country.

Database fields are:
  - id
  - name
  - createdAt (datetime)
  - updatedAt (datetime)

##### Listing page 

ID | Name | Action
-----|-------|-------
1 | India | Edit Delete
2 | UK | Edit Delete

* Search by Name using like query
* In Edit, we can change name of country.

### City
Create CRUD layout for City. Require to implement Listing, Add, Edit and Delete action.

Database fields are:
  - id  (primary)
  - name   (string, not null)
  - country_id (foreign key of country, not null)
  - active (boolean, by default true)
  - createdAt (datetime)
  - updatedAt (datetime)
  - DeletedAt (datetime)

###### Listing page should like this:

ID | Name    | Country          | Status     | Action
--- |--------|------------------|------------| ----------
1 | Ahmedabad | India            | Active     | Edit Delete 
2 | Surat     | India | Not Active | Edit Delete 

* Search by Name should have like query. And user can search by status dropdown too.
* Search by Country dropdown
* In form, Name field must be required with server side validation
* use softdelete for deleteing record.
* Display flash message in listing page when any event happen. i.e. City name changed successfully

###### Add Form

Country | Dropdown of country name | ---
-------|--------------------------| ----
Name | textbox                  | Add More
Active | checkbox                 | default selected

* When click on Add More button, it's open more name fields, so we can insert multiple city for selected country.
* If more textbox open, there is Delete option too, so we can remove city if not want to create it.
* At-least one city value must require

###### Edit Form
Country | Dropdown
------- | --------
Name | textbox
Active | checkbox

### Address
Create CRUD for address module. User can add, edit, delete address.

##### Listing page
Id | Street Name | Postcode | City | Country | Action
---| ---------- | ---------- | ------ | ------ | ------
1 | Gold Plaza | 525632 | Ahmedabad | India | Edit Delete

##### Add/Edit Form

Country | dropdown
--------|--------
City | dropdown
Street Name | textarea
Postcode | textbox 

* Only load city which are related to selected country.
* Country/City dropdown will work with javascript, Also handle it's form value by Form Events
* Allow only number value in postcode field.
* Street value require.

## Authentication

* create authentication and provide role to user. i.e admin, supervisor.
* country record can deleted by admin only, other delete can be performed by supervisor. (authorization)

## Doc

Detail information: https://laravel.com/docs
