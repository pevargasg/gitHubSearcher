# Angular2 Github Search Source


This repository holds the TypeScript source code of the Github search project,
In this project we use Github's API to retrive data from the json objects containig the information of the gitHub users.

#Conection and retriving using REST
import {Injectable} from '@angular/core';
import {Http, Headers} from '@angular/http';
import 'rxjs/add/operator/map';

@Injectable()
export class GithubService{
    private username:string;
    private client_Id = 'use the one github provided you';
    private client_secret = 'use the one github provided you';
    
    constructor(private _http: Http){
        console.log('Github Service Ready...');
        this.username = 'pevargasg';
        //Retriving User
        getUser(){
            return this._http.get('http://api.github.com/users/'+this.username+'?client_id='+this.client_Id+'&client_secret='+this.client_secret)
            .map(res => res.json());
        }
        //Retriving repos
        getRepos(){
            return this._http.get('http://api.github.com/users/'+this.username+'/repos?client_id='+this.client_Id+'&client_secret='+this.client_secret)
                .map(res => res.json());
        }
        //Method that updated the user when start typing in the search bar
        updateUser(username: string){
            this.username = username;
        }
    }
    
   
}

## Prerequisites

Node.js and npm are essential to Angular development. 
    
<a href="https://docs.npmjs.com/getting-started/installing-node" target="_blank" title="Installing Node.js and updating npm">
Get it now</a> if it's not already installed on your machine.
 

# gitHubSearcher
