# Admissions Viewbook
Vue 3.0

### Install dependencies
First, install Yarn dependencies:
```
yarn
```

### Start the local server
The following command creates and runs a temporary server to view the site locally.
```
yarn dev
```
The command will output the server URL to visit in your browser, ex. http://localhost:3000.

### Test the build locally
The following command creates the build.
```
yarn build
```

The following command creates and runs a temporary python server to view the site in `dist` locally.
```
cd dist
```
```
python3 -m  http.server 8000 
```
The command will output the server URL to visit in your browser, ex. http://localhost:8000.


### Creating a PR
1. Once your feature branch has been created, you will need to run the following command: `git push origin feature_branch`.
2. This will generate a url to use, ex. https://github.com/uiowa/admissions-viewbook/pull/new/feature_branch. 
3. Set the upstream branch with `git push --set-upstream origin feature_branch`.
4. Once you open the url, make sure that you switch the base to `develop` instead of `main` and create the pull request. 
5. When the pull request is approved, merge into `develop`.
6. Once the pull request is merged into `develop`, you can preview the site at https://viewbook.admissions.uiowa.edu/latest/. 
7. If https://viewbook.admissions.uiowa.edu/latest/ is working with the changes from the pull request, merge `develop` into `main`.

### Common errors
If the commands listed above for local development are not working, delete your `node_modules` folder and run `yarn install`. 