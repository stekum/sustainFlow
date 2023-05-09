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

Create a new file named alm.yml in your repository's .github/workflows folder. Copy the following content to the alm.yml file:

name: ALM Workflow

on:
  push:
    branches:
      - main
  schedule:
    - cron: '0 3 * * *' # Scheduled at 3 AM daily

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2
      
    - name: Setup Node.js
      uses: actions/setup-node@v2
      with:
        node-version: 14

    - name: Install dependencies
      run: npm ci

    - name: Deploy Solution and Power BI Reports
      run: npm run deploy

    - name: Migrate Data
      run: npm run migrate-data
