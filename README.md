## Learn-angularjs

# 1. Install and run 

> Step 1. download nodejs ( visit [nodejs.org](https://nodejs.org/en/) )

> Step 2. Open command line and type following command ( visit [cli.angular.io](http://cli.angular.io/)  ) . After successful installation of angular cli go for another steps.

```
   npm install -g @angular/cli
```

> Step 3. Start creating project 

```
   ng new projectname
   cd projectname
```

> Step 4: Now run project, this will give you portnumber

```
   ng server
```


> Step 5: Goto browser and type localhost:portnumber



# 2. Installing bootstrap and jquery 

> Step 1. Installing bootstrap 

```
   npm install boostrap --save
```

> Step 2. Installing jquery 

```
   npm install jquery --save
```

> Step 3. Link this bootstrap  files

```
      "styles": [
        "styles.css",
        "../node_modules/bootstrap/dist/css/bootstrap.min.css"
      ]
```


> Step 4. Link this  jquery files 

```
      "scripts": [
        "../node_modules/jquery/dist/jquery.min.js",
        "../node_modules/bootstrap/dist/js/bootstrap.min.js"
      ]
```



# 3. Working with component 

After downloading project, we get folder structure and we will work inside projectname/src/app. Here there woud be the default file but now we will create  our component to work. 

So lets start working with component. 

> Step 1. Now to create new component, type following command

```
   ng g c <componentname>

```

> Step 2.  Import newly created component into app component app.component.ts

```
   import { newComponent} from "./new/new.component";

```

> Step 3. Use selector of new component section.component.ts into app components' html (default page of app)

```
@Component({
  selector: 'new-app',
  .................
})

```

There we have selector: new-app in  section.component.ts. Now use this selector into app.component.html

```
<new-app> </new-app>

```

Now enjoy working with the new component html, css , ts file and view your result in your browser using ng serve command.


# 4. Working with data binding 

So lets start working with data binding  now. 

> working with content

```
/* html file */
  <h1>  {{welcometitle}} </h1>
  <p>  {{welcomemsg}} </p>

```

```
/* ts file */
  public welcometitle = "Welcome to angular tutorials";
  public welcomemsg = "This is angular4 tutorials for beginners.";
  
```
> working with images

```
/* html file */
  <img  src={{ngImg}}>

```

```
/* ts file */
 public ngImg = "../assets/img/angular.png";
  
```


# 5. Working with expression 

So lets start working with expression now. 

> working with ngFor

We have list in html file and array in ts file inside class.

```
/* html file */
   <ol>
    <li *ngFor="let l of language"> {{l}} </li>
  </ol>

```

```
/* ts file */
  public language = ['c' , 'c++' , 'java'];
  
```

Now We have list in html file and json variable in ts file inside class.

```
/* html file */
 <ol>
    <li *ngFor="let x of developer">{{x.name}}, {{x.language}}</li>
 </ol>

```

```
/* ts file */
 public developer = [
    {
    'name' : 'John',
    'language' : 'PHP'
    },
    {
      'name' : 'Tia',
      'language' : 'Java'
      }
];
  
```


> working with ngIf

We have paragraph tag in html file and boolean variable in ts file inside class.

```
/* html file */
  <p *ngIf = "checkvalue"> I am displayed </p>
  <p *ngIf = "!checkvalue"> I am not displayed </p>

```

```
/* ts file */
 public checkvalue:Boolean = true;

```

# 6. Working with pipes 

So lets start working with pipes(filters) now. 

> working with all pipes 

We have list in html file and experssion in ts file inside class.

```
/* html file */
      <table class="table" >
        <tr>
          <th> Filters </th>
          <th> Result </th>
        </tr>
        <tr>
          <th> Currency </th>
          <td>{{ priceValue | currency:'CAD'}} </td>
        </tr>
        <tr>
          <th> Date </th>
          <td>{{ dateValue | date:'y-M-d, h:m:s' }}</td>
        </tr>
        <tr>
          <th>Decimal </th>
          <td> {{demicalValue| number:'2.2-3' }} </td>
        </tr>
        <tr>
          <th>LowerCase </th>
           <td> {{lowercaseValue | lowercase }} </td>
        </tr>
        <tr>
          <th>UpperCase </th>
           <td> {{upperValue| uppercase }} </td>
        </tr>
        <tr>
          <th>Percent </th>
          <td> {{percentValue | percent :'2.2-2' }}  </td>
        </tr>
        <tr>
          <th>Slice </th>
          <td> {{sliceValue | slice:6:8}}  </td>
        </tr>
        <tr>
          <th> Json</th>
          <td> {{jsonValue | json}}  </td>
        </tr>
      </table>

```

```
/* ts file */
   public priceValue = 4320.33434;
   public dateValue = new Date();
   public demicalValue = 5.6;
   public lowercaseValue = "WELcome";
   public upperValue = "welcoME";
   public percentValue = 343.45344;
   public sliceValue = "hello world";
   public jsonValue = [{ 'name' : 'John', 'hobby' : 'dance' }];
  
```

# 7. Working with routes 

So lets start for routing. 

There are three main components that we use to configure routing in Angular:
-	Routes describes our application’s routes
-	RouterOutlet is a “placeholder” component that gets expanded to each route’s content
-	RouterLink is used to link to routes


> # Routes 

> Step 1.  Create routes.ts file

> Step 2. Imports 

in module.ts 

```
import { Routes, RouterModule }   from '@angular/router'; 

```

and in routes.ts

```
import { Routes }   from '@angular/router'; 

```

 When we put RouterModule in our imports it means that we’re able to use the RouterOutlet and RouterLink components in this module.


> Step 3.  routes.ts 

```
 export const approuter:Routes =
[
]

```

> Step 4. Import all necessary components

```
import { HomeComponent } from './home/home.component';

```

> Step 5. Start routing the components 

```
export const approuter:Routes =
[
  {
        path: 'home',
        component: HomeComponent
    },
    {
        path: '',
        redirectTo: 'home',
        pathMatch:'full'
    },
    {
        path: '**',
        redirectTo: 'home',
    },
    { 
        path:'admin',
        component:AdminComponent,
        children:[
            {path: Home, component: HomeComponent },
            { path:'',redirectTo: '/admin/home, pathMatch:'full'},
            { path: '**', component: HomeComponent
   }

]

```


> Step 6.  Now import again in module 

```
import { approuter}   from './routes'; 

```

and 

```
RouterModule.forRoot(approuter) inside NgModule’s import 

```

To install our router into our app we use the RouterModule.forRoot() function in the imports key of our NgModule and  we give our routes as the argument to RouterModule.forRoot().


> # RouterOutlet

> in html file where needed
 
```
<router-outlet></router-outlet>   
 
```

> # RouterLink

> use these routes as navigation in html file where needed
 
```
<a routerLink="/home">Home</a>

```

> For active link
 
```
<li routerLinkActive="active current" ><a routerLink="/home">Home</a></li>  

```







