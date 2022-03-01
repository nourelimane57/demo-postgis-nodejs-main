# WM-22
Web Mapping

# How to do  it:
You can use the code from this repo, but ensure you have :
- [ ] **Postgres** and _postgis_ with a populated database
- [ ] **Nodejs** with **pg**, **express** and **body-parser** packages installed 

See below for details.

## 1. Download the code from this repo

## 2. Prepare the frontend i.e a website 

### Build your web page 

## 3. Prepare the backend

For the back end, we will be using `nodejs` for the server language and `postgresql` for our database because it supports `PostGIS` extension.

### a. Prepare your database (`Postgres` and `PostGIS`) on your laptop

* Install `Postgresql` from [here](https://www.postgresql.org/download/)
* Activate PostGIS by running `CREATE EXTENSION postgis;`
* Populate your databse
![Screenshot_20220224_112838](https://user-images.githubusercontent.com/63267601/155507007-378a7f9d-64ef-4fba-a200-bbd98cf3b964.png)

### b. Install `nodejs` 
1. Install nodejs from [here](https://nodejs.org/en/download/).

2. Init your project by running and complete setup:
```
npm init
```

3. Install from `terminal` (_PowerShell_ or _cmd_ for **Windows**, _bash_,...) the needed `npm` packages : 
```
npm install pg
npm install express
npm install body-parser
```
4. Setup connection by changing `connections.js` parameters to your personal ones.
5. Run to launch your app by running:
```
node index.js
```
![Screenshot_20220224_112945](https://user-images.githubusercontent.com/63267601/155507170-c1f9342b-51c1-4671-91a2-a43fffe8c4b4.png)

6. Enjoy your app at : `http://localhost:3000/`.

7. For these spatial queries please fetch the **geometry** as `GeoJSON` and alias **geom** as: `ST_AsGeoJSON(geom) AS geom`

8. Try like this query (maroc table needed to be in your db):
```
SELECT id, ST_AsGeoJSON(geom) AS geom FROM maroc
```
![ezgif-5-cb393bb8b4](https://user-images.githubusercontent.com/63267601/155508530-f9d03cb3-f43b-4185-bc7e-64defc1a7e0e.gif)
