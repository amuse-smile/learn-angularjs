## Learn-angularjs

## Table of Contents

- [Install and run](#install-and-run)
- [Installing bootstrap and jquery](#installing-bootstrap-and-jquery)
- [Working with component](#working-with-component)
- [Working with data binding](#working-with-data-binding)
- [Working with expression](#working-with-expression)
- [Working with pipes](#working-with-pipes)
- [Working with routes](#working-with-routes)
- [Working with template driven form](#working-with-template-driven-form)
- [Working with service](#working-with-service)
- [Working with http](#working-with-http)


## Install and run 


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



## Installing bootstrap and jquery 

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



## Working with component 

After downloading project, we get folder structure and we will work inside projectname/src/app. Here there woud be the default file but now we will create  our component to work. 

So lets start working with component. 

> Step 1. Now to create new component, type following command in command line

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


## Working with data binding 

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


## Working with expression 

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

## Working with pipes 

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

## Working with routes 

So lets start for routing. 

There are three main components that we use to configure routing in Angular:
-	Routes describes our application’s routes
-	RouterOutlet is a “placeholder” component that gets expanded to each route’s content
-	RouterLink is used to link to routes


> ## Routes 

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


> ##  RouterOutlet

> in html file where needed
 
```
<router-outlet></router-outlet>   
 
```

> ##  RouterLink

> use these routes as navigation in html file where needed
 
```
<a routerLink="/home">Home</a>

```

> For active link
 
```
<li routerLinkActive="active current" ><a routerLink="/home">Home</a></li>  

```


## Working with Template driven form 

> Step 1.  In app.module.ts file

```
import { FormsModule } from '@angular/forms';

@NgModule({
  imports: [
    ...,
    FormsModule
  ]

```

> Step 2. In html file add forms with needed input  

```
        <form novalidate role="form">
            <div class="form-group">
                <label class="control-label">Name</label>
                <input type="text" class="form-control" >
                <span  class="help-block">
                    <span > Name field is required <br> </span> 
                    <span > It contain only alphabet </span>
                </span>
            </div>

            <div class="form-group">
                <label class="control-label">Email</label>
                <input type="email" class="form-control" >
                <span  class="help-block">
                    <span > Email field is required <br> </span> 
                    <span > Email field is invalid </span>
                </span>
            </div>
            
            <button type="submit" class="btn btn-primary btn-block">Submit</button>
        </form> 

```

> Step 3. Add #AnyName= "ngForm" to form tag


```
    <form novalidate role="form" #registration="ngForm">
 
        ......
 
    </form

```

> Step 4. Add all needed attribute in input field


```
    <form novalidate role="form" #registration="ngForm">
       ....
       
       <input type="text" class="form-control" 
            name="Name" 
            minlength="4"  
            required 
            #nameN="ngModel" 
            ngModel>
       
       ...
 
    </form

```

> Step 5. To diasble submit button until form field is success. (As we have #registration="ngForm". So there is registerForm [disabled]="")


```
    <button type="submit"  [disabled]="registerForm.invalid" class="btn btn-primary btn-block">Submit</button>

```

> Step 6. Now finally for displaying error. 

> ## For form group div

Which means class="has-error" when nameN field contain any error and class="has-success" for error free input field.

```
    <div class="form-group" 
            [class.has-success]="nameN.valid && nameN.touched" 
            [class.has-error] = "nameN.invalid && nameN.touched">
                     .......  
    </div>

```

> ## For error span message

This display error message according to the error in input field.

```
    <div class="form-group" 
            [class.has-success]="nameN.valid && nameN.touched" 
            [class.has-error] = "nameN.invalid && nameN.touched">
                  ......
                  
            <span  *ngIf="nameN.invalid && nameN.touched" class="help-block">
                   <span  *ngIf="nameN.errors.required"> Name field is required <br> </span> 
                   <span *ngIf="nameN.errors.minlength"> Name must be at least 4 characters long. </span>
            </span>
    </div>

```

> Step 7. For sending input field data to ts file. 

> ## html : in input field 

Replace ngModel with ngModel into [(ngModel)] (ngModel in banana inside the box )

```
    <input type="text" class="form-control" 
            ..... 
            [(ngModel)]="createdata.Name">
       >

```

> ## ts file : in export class

initialization creatdata in ts file

```
   public createdata:any = {fullname:'', gender:''};


```

on button click submit() function is called

```
   public createdata:any = {fullname:'', gender:''};

  submit(createdata){
    var data = this.createdata;
    console.log(data);
  }

```


## Working with service 

> Step 1.  Now to create new service, type following command in command line 

```
   ng g s <servicename>

```

> Step 2.  Now we have to add it to the providers property of the NgModule decorator in app.module.ts,  

Import service (can be found in spec.ts file for previously created service )

```
   import { <DataServicename>} from './<servicename>.service';

```

Provider ( <DataServicename> can be found in export class of service.ts file)

```
   @NgModule({

  providers: [<DataServicename>],
  
})


```

> Step 3.  Now Working with the Service File

```
  import { Injectable } from '@angular/core';
   @Injectable()
   export class DataService {
     constructor() { }
     colors = [ 'red','yellow','green' ];

     myData() {
       return 'This is my data function';
     }
   }

```

> Step 4.  Now Working with the Components File

The first step requires importing the service at the top of the component.

```
  import { <DataserviceService> } from './dataservice.service';
  
```

 Next, within the constructor, we have to import it through dependency injection (inside export class)

```
  export class AppComponent {
  constructor(private dataService:DataService) {  }
  
}
  
```

Now we can use dataService to access its's associated properties and methods.

Underneath the constructor() { }, let's add the ngOnInit() lifecycle hook, which runs when the component loads


```
  export class AppComponent {
  constructor(private dataService:DataService) { }
  
     colorStr:string = '';
     someProperty:string = '';
     ngOnInit() {
      this.colorStr = this.dataService.colors
      this.someProperty = this.dataService.myData();
     }

}
  
```

> Step 4.  Now use these variable in html file


```
  <p> {{someProperty}} </p> 
  
  <ul>
      <li *ngFor="let x of colorStr" >  {{x}} </li>
  </ul>
  
```

## Working with http

For http we need to create service and import it in app.module.ts file 


> Step 1.  

Now to create new service, type following command in command line 

```
   ng g s <servicename>

```


Import service in app.module.ts and provider 

```
   import { <DataServicename>} from './<servicename>.service';

```

Provider ( <DataServicename> can be found in export class of service.ts file)

```
   @NgModule({

  providers: [<DataServicename>],
  
})


```

> Step 2.  To use the Http service we need to (you guessed it) import & and inject it 

in service.ts file

```
   import { Http, Response } from '@angular/http'; 

```

 in app.module.ts file

```
   import { HttpModule } from '@angular/http'; 

```
and HttpModule ngModule

```
 imports: [
    BrowserModule,
    HttpModule,
  ],
  
 ```


 > Step 3.  Next, within the constructor, we have to import it through dependency injection (inside export class) 

in service.ts file

```
   export class UserService {
      constructor ( private http: Http ) {}
   }

```

in app.component.ts file

```
   export class UserService {
     constructor(private dataService:<DataServicename>) {  }
   }

```

 > Step 4.  Now working with get data  

in service.ts file

```
  public getData(){
    let getposts_url : string = "<urlLink>";
    return this._http.get(getposts_url);
  }
```

in app.component.ts file

```
  public postsdata:any = '';
  public viewJsondata(){
    this.dataService.getData()
    .subscribe(
      response => {
        this.postsdata = response.json();
        console.log(response.json());
      },
      error => {
        console.log(error);
      }
    );
  }
   
   ngOnInit() {
     this.getPostsdata();
  }


```

in app.component.html file 

```
<ul>
  <li *ngFor="let post of postsdata"> {{post.title}}, {{post.body}} </li>
</ul>

```

> Step 5.  Now working with post data  

in service.ts file

```
public createData(data){
    let create_url : string = "<urlLink>";
    return this
    ._http.post(create_url , data).
    .map((res:Response) => res.json());
  }

```

in app.component.ts file

```
  public createdata:any = {title:'' , body:''};
 
  public insertDatapost():void{
    this.dataService.createData(this.createdata)
    .subscribe(
      response => {
        this.createdata = response;
        console.log(response);
      },
      error => {
        console.log(error);
      }
    );
  }

```

in app.component.html file

```
<form #loginForm ="ngForm" >
  <div>
    <label for="title" >Title:</label>
    <input type="text" required #titleT="ngModel" name="title" [(ngModel)]="createdata.title">
  </div>
  
  <div>
    <label for="title" >Body:</label>
    <input type="text" required #bodyB="ngModel" name="body" [(ngModel)]="createdata.body">
  </div>


  <div class="">
    <button type="submit" (click)="insertDatapost()" >Submit</button>
  </div>
</form>

```


