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
Once your feature branch has been created, you will need to run the following command::
```
git push origin feature_branch
```
This will generate 

