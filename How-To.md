# How to Set Up Power Platform ALM with GitHub Actions

Follow these steps to set up the Power Platform ALM template in your project.

## Prerequisites

- A GitHub repository for your project
- Power Apps solution and Power BI reports you want to deploy
- Node.js installed on your local machine

## Step 1: Clone the Repository

Clone this repository to your local machine:

## Step 2: Install Dependencies

Install the required dependencies: npm install


## Step 3: Configure Environment Settings

Edit the `config.json` file to include the connection strings for each environment, Power BI workspace IDs, and paths to your Power Apps solution, Power BI reports, and data migration scripts.

Replace the placeholders with the appropriate values for your environment.


## Step 4: Set up the GitHub Actions Workflow 

Create a new file named alm.yml in your repository's .github/workflows folder. 

## Step 5: Deploy and Migrate Data

Push your changes to the repository, and the GitHub Actions workflow will automatically deploy your Power Apps solution and Power BI reports to the specified environments.

If you want to enable data migration between environments, set the "enableDataMigration" flag in the `config.json` file to `true`. You will need to implement the data migration logic in the `migrateData` function within the `deploy.js` file. This may involve using the Power Platform CLI, custom scripts, or other tools to migrate data between your environments.

Once the data migration feature is enabled and implemented, the GitHub Actions workflow will also handle data migration when triggered.

## Conclusion

With the provided setup, you can now automate ALM for Power Apps solutions and Power BI reports across multiple environments using GitHub Actions and the Power Platform CLI. Data migration between environments can also be optionally enabled as needed.
