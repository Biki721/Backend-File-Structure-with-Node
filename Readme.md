# Backend file Structure setup

This is a basic setup for a backend file structure for MERN. This structure is based on the Model-View-Controller (MVC) pattern, which is a widely used design pattern in software development. The structure is as follows:

Sure! Here's the entire process written in Markdown:

````markdown
## Initialize npm

```bash
npm init
```
````

Follow the prompts to enter the necessary details for your project (name, version, description, entry point, test command, git repository, keywords, author, license).

## Add a README file

```bash
echo "# This is a backend file structure setup done professionally" > README.md
```

## Initialize a Git repository

```bash
git init
git add .
git commit -m "add initial files for backend"
```

## Create a new repository on GitHub

1. Go to GitHub and create a new repository.
2. Follow the instructions to add the remote repository to your local project.

## Change the branch name from master to main

```bash
git branch -M main
```

## Add the remote repository

```bash
git remote add origin <your-repository-url>
```

## Push the initial commit to the main branch

```bash
git push -u origin main
```

## Manage image uploads

1. Create a public folder in the project-level directory.
2. Inside the public folder, create another folder named temp.

### Notes on image uploads

One of the key aspects of our system is managing image uploads. While we rely on third-party cloud storage solutions like AWS S3, Azure Blob Storage, or Cloudinary for storing images, the process can involve intermediate steps for reliability and efficiency.

When a user uploads an image, it is often temporarily stored on our server. This ensures that, in the event of a connection interruption during the upload, the files are retained and not lost. Once the upload is complete, a background process handles the transfer of these files to the cloud storage service. This approach provides a fallback mechanism and allows for any necessary preprocessing of images (e.g., resizing or compression) before they are stored in the cloud.

Alternatively, many modern systems adopt a direct upload strategy, where images are uploaded directly to the cloud from the client-side using pre-signed URLs or SDKs provided by services like AWS or Cloudinary. This method reduces server load and enhances scalability but may require additional client-side implementation to handle potential upload failures.
The choice between these approaches depends on the specific business requirements, system architecture, and operational standards.

## Track the temp folder with .gitkeep

```bash
touch public/temp/.gitkeep
```

## Create a .gitignore file

```bash
touch .gitignore
```

Add sensitive or unnecessary files like `.env` and `node_modules` to `.gitignore`.

### Use a gitignore generator

Visit this site to generate a `.gitignore` template for Node.js projects.

## Create .env and .env.sample files

```bash
touch .env .env.sample
```

## Create a src folder and necessary files

```bash
mkdir src
touch src/app.js src/index.js src/constants.js
```

## Set module type in package.json

Add `"type": "module"` if you want to use ES modules. Otherwise, it defaults to CommonJS.

## Install nodemon as a dev dependency

```bash
npm install --save-dev nodemon
```

## Add a dev script in package.json

```json
"scripts": {
  "dev": "nodemon src/index.js"
}
```

## Perform git add, commit, and push

```bash
git add .
git commit -m "file setup is done"
git push
```

## Create folders inside the src directory

```bash
mkdir db models controllers middlewares routes utils
```

## Track these folders with .gitkeep

```bash
for dir in controllers db middlewares models routes utils; do touch "src/$dir/.gitkeep"; done
```

## Add, commit, and push the file structure

```bash
git add .
git commit -m "added file structure"
git push
```

## Add Prettier as a dev dependency

```bash
npm install --save-dev prettier
```

### Why do we need Prettier?

- Prettier is a code formatter that helps maintain a consistent code style across your project. It automatically formats your code according to specified rules, reducing the chances of stylistic errors and making the codebase easier to read and maintain. This is especially useful in collaborative environments where multiple developers work on the same codebase.

## Create a .prettierrc file

```json
{
  "singleQuote": false,
  "bracketSpacing": true,
  "tabWidth": 2,
  "trailingComma": "es5",
  "semi": true
}
```

## Create a .prettierignore file

```
/.vscode
/node_modules
./dist
_.env
.env
.env._
```

This should cover all the steps you need for setting up your backend file structure.
