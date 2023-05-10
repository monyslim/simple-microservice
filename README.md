# Simple Microservice Example

A very simple microservice example with NodeJS, Python and Docker

## Run the API gateway

- Clone the repository and navigate to it

- Install `docker` and `docker-compose`, `python`, `pip`, `flask`,in the root folder of the source code according to your operating system. Use python to install **pip & flask**


- Run `docker compose up` in the root folder to start the services

- Try `GET http://YOUR_HOST:3000/api/status` to check whether application is running

- Try `GET http://YOUR_HOST:3000/api/randomquote`to check if the quoteservice is running

## Build the frontend

The application uses a frontend written with plain html with jQuery and to style with Bulma.
This is built with webpack. This default application is built assuming you are using the `localhost`.

To build this to fit your own **IP Address** please follow the steps before you running the `docker compose up` after you must have installed the necessary things listed below:

- Install NodeJs using `NVM` and `docker` on your system in the root folder

- Go to FrontendApplication directory

- Run `npm install` or if you have yarn `yarn` to install packages

- Now you need to set the API Gateway for this frontend application. It can be any host you have. 
    - Let's say you are hosting this application on `http://example.com` then your `API_GATEWAY` would be this one. 
    - If you are hosting in some machine with IP `123.324.345.1` then your `API_GATEWAY` would be your IP.

- To pass this setting to webpack build you need to set an Environment Variable
    
    - Windows : go to the **FrontendApplication** folder, click on **src** folder the inside the folder click on **script.js** in the `url: api + "/api/randomquote"`, replace the `api` with the **IP Address** you want to use like this: **url: "http://123.324.345.1:3000/api/randomquote",**
    
    - Linux/Max : go to the **FrontendApplication** folder, click on **src** folder the inside the folder click on **script.js** in the `url: api + "/api/randomquote"`, replace the `api` with the **IP Address** you want to use like this: **url: "http://123.324.345.1:3000/api/randomquote",**
    * Remember no / at the end of the URL to get your web app work

- Now you can do `npm run build` or `yarn build`

- Check `dist/` folder for newly created index.html and the main.js

- Now run the `docker compose up` on the root folder of project and check `http://YOUR_HOST:8080` to see web app 

![image](https://user-images.githubusercontent.com/13379595/42726706-82eb0ae6-87b6-11e8-8456-d933b9dfa73b.png)
