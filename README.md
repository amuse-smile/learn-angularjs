## Learn-angularjs

# 1. Install and run 

> Step 1. 

download nodejs ( visit [nodejs.org](https://nodejs.org/en/) )

> Step 2.

Open command line and type following command ( visit [cli.angular.io](http://cli.angular.io/)  ) . After successful installation of angular cli go for another steps.

```
   npm install -g @angular/cli
```

> Step 3. 

Start creating project 

```
   ng new projectname
   cd projectname
```

> Step 4: 

Now run project, this will give you portnumber

```
   ng server
```


> Step 5: 

Goto browser and type [localhost:portnumber]()



# 2. Installing bootstrap and jquery 

> Step 1. 

Installing bootstrap 

```
   npm install boostrap --save
```

> Step 2. 

Installing jquery 

```
   npm install jquery --save
```

> Step 3. 

Link this bootstrap  files

```
      "styles": [
        "styles.css",
        "../node_modules/bootstrap/dist/css/bootstrap.min.css"
      ]
```


> Step 4. 

Link this  jquery files 

```
      "scripts": [
        "../node_modules/jquery/dist/jquery.min.js",
        "../node_modules/bootstrap/dist/js/bootstrap.min.js"
      ]
```
