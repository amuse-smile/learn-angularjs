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



# 3. Working with component 

After downloading project, we get folder structure and we will work inside projectname/src/app. Here there woud be the default file but now we will create  our component to work. 

So lets start working with component. 

> Step 1. 
Now to create new component, type following command

```
   ng g c <componentname>

```

> Step 2.  
Import newly created component into app component [app.component.ts]()

```
   import { newComponent} from "./new/new.component";

```

> Step 3. 
Use selector of new component [section.component.ts]() into app components' html (default page of app)

```
@Component({
  selector: 'new-app',
  .................
})

```

There we have selector: [new-app]() in  [section.component.ts](). Now use this selector into [app.component.html]()

```
<new-app> </new-app>

```

Now enjoy working with the new component # (html, css , ts file) and view your result in your browser using [ng serve]() command.
