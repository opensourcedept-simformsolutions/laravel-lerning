# Basic Practice

## Modules
1. Users
2. Departments
3. Shift

### Users
Create CRUD for Users.

Database fields are:
  - id
  - first_name
  - last_name
  - email
  - number
  - department_id (foreign key of department, not null)
  - role
  - password
  - createdAt (datetime)
  - updatedAt (datetime)

##### Listing page 

ID | Name | Email | Role | Reporting To | Action
-----|-------|--------------------|----------------------|-------------|-------
1 | Harshil Amreliya | harshil.a@simformsolutions.com | software engineer | Chintan Dave | Edit Delete
2 | Dhyanam Trivedi | dhyanam.t@simformsolutions.com | Sr.software engineer | Bhavin Nakrani | Edit Delete

* Dropdown for role column to change role. (This column should visible for Team leader and admin only)
* In Edit, user can change name and only admin can change role to users, Team leader can change role to there team members.
* send email and text message notification when user added or role changes.

### Departments
Create CRUD layout for Departments. Require to implement Listing, Add, Edit and Delete action.

Database fields are:
  - id  (primary)
  - name   (string, not null)
  - active (boolean, by default true)
  - createdAt (datetime)
  - updatedAt (datetime)
  - DeletedAt (datetime)

###### Listing page should like this:

ID | Name     | Status     | Action
--- |---------|------------| ----------
1 | Open Source | Active   | Edit Delete 
2 | Mean     | Not Active | Edit Delete 

* Switch button for status change.
* use softdelete for deleteing record.
* Display flash message in listing page when any event happen. i.e. Department status updated

### Shift
Create CRUD for Shift module. Team leader can add, edit, delete shifts.

Database fields are:
  - id  (primary)
  - owner_id  (foreign key of users, not null)
  - team_leader_id  (foreign key of users, not null)
  - start_time (string, not null)
  - end_time (string, not null)
  - createdAt (datetime)
  - updatedAt (datetime)
  - DeletedAt (datetime)

##### Listing page
Id | owner | Repoting | Start Time | End Time | Action
---| ---------- | ---------- | ------ | ------ | ------
1 | Test User | Harshil Amreliya | 09:00 | 06:00 | Edit Delete


* Reproting manager, team lead, and admin can change shift in higherkey.
* send nofitification of shift update and creation.

## Authentication

* create authentication and provide role to user. i.e admin, supervisor.
* country record can deleted by admin only, other delete can be performed by supervisor. (authorization)

## Cron

* creat cron job for users to send notification next day shift timeing through mail and text message.
* One cron to send weekly total payment hours * 1000 * weekdays.

## Doc

Detail information: https://laravel.com/docs

Role management librery: https://spatie.be/docs/laravel-permission/v5/introduction
