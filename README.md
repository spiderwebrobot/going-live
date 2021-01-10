# Going Live

Deploying a [Next.js](https://nextjs.org/) project with [GitHub](https://github.com/), [Vercel](https://vercel.com/) and [GoDaddy](https://www.godaddy.com/).

## Create a GitHub repository

1. Navigate to https://github.com/new
2. Enter a "Repository name", e.g. my-project-name
3. Select the "Private" option
4. Check the "Add a README file" checkbox
5. Click on the "Create repository" button

###  Pull down and configure the repository

1. Clone the repository, e.g.
   ```
   git clone git@github.com:username/my-project-name.git
   ```
2. Navigate into the repository-directory
   ```sh
   cd my-project-name
   ```
3. Specify push and pull behaviors
   ```sh
   git config pull.rebase false && git config push.default current
   ```
4. Establish your identity, e.g.
   ```sh
   git config user.name "Your Name" && git config user.email your@address.com
   ```

### Add Next.js to the repository and then push the changes

1. Remove the README file
   ```sh
   rm README.md
   ```
2. Create a Next.js application
   ```sh
   yarn create next-app .
   ```
3. Add and commit the changes
   ```sh
   git add . && git commit
   ```
4. Push the changes
   ```sh
   git push
   ```

## Start and deploy a new Vercel project

1. Navigate to https://vercel.com/new
2. Click on the "Import" button next to your repository-name on the "Import Git Repository" screen
3. Click on the "Select" button next to your "PERSONAL ACCOUNT" on the "Select Vercel Scope" screen
4. Click on the "Deploy" button on the "Import Project" screen

### Add a domain to the project

1. Navigate to the project dashboard, e.g. https://vercel.com/username/my-project-name
2. Click on the "View Domains" button (left side of screen)
3. On the "Domains" page, enter a domain, e.g. mywebsite.com, and click on the "Add" button
4. An IP address will appear on the screen

## Update DNS in GoDaddy

1. Navigate to https://dcc.godaddy.com/domains
2. Click on the domain that was added to the Vercel project, e.g. mywebsite.com
3. On the Domain Settings page, click on the "Manage DNS" link (bottom of the screen)
4. On the DNS Management page, click on the edit-icon for the "A" record
5. Enter the IP address from the Vercel project into the "Points to" input
6. Select "1 hour" from the TTL dropdown-menu
7. Click on the "Save" button
