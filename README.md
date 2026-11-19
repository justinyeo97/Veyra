# Veyra

Welcome to Veyra, a sneaker resale management platform built with React, Express, and PostgreSQL. Manage your sneaker inventory, track orders, monitor profits, manage customers, and organize listings and tasks.

Some parts of the app are not working correctly and incomplete.

Use the checklists to keep track of where you are. You have 50 minutes to complete all sections. If you get stuck, you can move on. You may solve in any order.

**Go over the 3 sections to help finish it up!**

☐ Create a new Project in your Supabase. Open the SQL Editor and paste veyra.sql\
☐ Create a file backend/.env and inside write

```
DATABASE_URL=postgresql://postgres.[YOUR-PROJECT-REF]:[YOUR-PASSWORD]@aws-1-ap-southeast-2.pooler.supabase.com:5432/postgres
PORT=4000
```

☐ Run the backend in /backend\
☐ Run the frontend in /frontend

## Bug Reports

**Bug 1**

**Description**

The backend cannot run and shows an error in the terminal

**Steps to reproduce**

1. Run the backend application

**Expected result**

The application runs and shows that its running in some localhost.

**Actual result**

An error message saying it failed to run.

**Bug 2**

**Description**

The terminal shows an incorrect link

**Steps to reproduce**

1. Run the application in the terminal

**Expected result**

The terminal shows a link to open the application
`Veyra API running on http://localhost:4000`

**Actual result**

The terminal shows a link that is incorrect to open the application
`Veyra API running on http://localhost:${port}`

**Bug 3**

**Description**

User cannot login to the frontend

**Steps to reproduce**

1. Go to login page at localhost
2. Write email demo@veyra.app and password veyra123
3. Click "Log in" button

**Expected result**

The user is logged it and redirected to the dashboard

**Actual result**

The user gets a red error message above the Log in button. They remain in the login page.

**Bug 4**

**Description**

There is a typo in the Inventory page

**Steps to reproduce**

1. Login to website
2. Navigate to Inventory page using the navigation bar (hamburger menu or left side panel)
3. View the subheading under the Heading Inventory

**Expected result**

`16 products in stock across 21 records.`

**Actual result**

`16 products on stock across 21 records.`
Note the gramatically incorrect typo "on"

**Bug 5**

**Description**

Clicking on insight link takes user to 404 page

**Steps to reproduce**

1. Login
2. Navigate to Analytics insights page
3. See the dialog `Best sale last 90 days: ORD-1011, $179.47 profit on Nike SB Dunk Low "Jarritos".`
4. Click on the link ORD-1011

**Expected result**

The user is redirected to the order's page. They can see the order

**Actual result**

The user is redirected to the 404 page

**Bug 6**

**Description**

Notification shows errored message

**Steps to reproduce**

1. Login to website
2. Navigate to Tasks page
3. In the filtering section find the sorting option. Next to it there are 2 view options: List and Board
4. Select Board view
5. Choose any card such as "Pack and ship order ORD-1008". Click on the top right corner 3 dots. Choose "Move to In Progress"
6. A notification shows in the bottom right corner.

**Expected result**

The notification says
`"Pack and ship order ORD-1008" moved to In Progress.`

**Actual result**

The notification says
`"undefined" moved to In Progress.`

**Bug 7**

**Description**

When one user presses "Log out", EVERYONE logs out!

**Steps to reproduce**

1. Login to one account on a browser
2. Create and login to another account in another browser
3. Press logout in one account
4. Refresh both pages

**Expected result**

Only the person who clicked logout is logged out. The other people are still logged in.

**Actual result**

Everyone is logged out. Including the person who didn't click the button.

## Feature Addition

☐ Update the database, backend and frontend so a sneaker can be marked as Recycle only. A recycle-only pair is too damaged to sell and will be sent for recycling, so it must never be listed or sold.

Requirements

- Add a `recycle_only` column to the `sneakers` table. It is true or false and defaults to false, so every existing sneaker stays false.
- The API must save and return the new field as `recycleOnly` on every sneaker.
- Add a "Recycle only" switch to the add and edit sneaker form.
- Show a "Recycle only" badge next to the sneaker's status on the Inventory page and on the sneaker details page.
- Recycle-only sneakers must not appear in the sneaker picker when creating a listing or an order.

| Case                                               | Expected behavior                                       |
| -------------------------------------------------- | ------------------------------------------------------- |
| Mark a sneaker as recycle only and reload the page | It is still marked, because it is saved in the database |
| Create a new listing                               | Recycle-only sneakers are not offered                   |
| Create a new order                                 | Recycle-only sneakers are not offered                   |
| Turn recycle only off again                        | The sneaker can be listed and sold again                |

## Deployment

☐ Upload your application on a private GitHub repo\
☐ Deploy the application on Vercel and Railway
