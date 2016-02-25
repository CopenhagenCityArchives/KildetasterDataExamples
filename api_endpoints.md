Ny liste (fra Github):

Get task JSON schema:

http://kbhkilder.dk/1508/stable/api/taskschema&task_id=1

Add entry:
POST
http://kbhkilder.dk/1508/stable/api/entries

Data format:
```
{
task_id: 1,
page_id: 23, 
post: {

x: 0.5,

y: 0.5,

height: 0.25,

width: 0.25

},

"persons":{  
      "firstnames":"Jensine",
      
      "lastname":"Hansen",
      
      "age":42,
      
      "civilstatus":"Gift",
      
      "dateOfDeath":"01-01-1905",
      
      "yearOfBirth":1905,
      
      "deathcauses":[  
         {  
            "deathcause":"lungebtændelse"
         },
         {  
            "deathcause":"hjertefejl"
         }
      ],
      "burials":{
      "chapel":"Alm. Hosp - Almindelig Hospital",
      "parish":"Helliggejst",
      "cemetary":"Mariebjerg"
      },

addresses: {}

}
```

Update entry:
PATCH
http://kbhkilder.dk/1508/stable/api/entries/76

```
{  
"entity_name":"persons",
"field_name" : "firstnames",
"value":"Niels",
"concrete_entries_id":178,
"task_id":1
}
```


Get tasks:
http://kbhkilder.dk/1508/stable/api/tasks


Get task:
http://kbhkilder.dk/1508/stable/api/tasks/1


Get units:
http://kbhkilder.dk/1508/stable/api/units?collection_id=1&task_id=1


Get pages:
http://kbhkilder.dk/1508/stable/api/pages?unit_id=1&page_number=12

Get page:
http://kbhkilder.dk/1508/stable/api/pages/2
Returns an array of posts and "next_post" which is a best guess of the position and size of the next post (false when there is no more room for posts)

Get entries:
http://kbhkilder.dk/1508/stable/api/entries?task_id=1&post_id=201
Returns the entry for a given task and post (there can be only one entry pr. post and task)

Get post image:
http://kbhkilder.dk/1508/stable/api/posts/188/image
Returns the image for the given post (in this example post with id 188)

Get next available page:
http://kbhkilder.dk/1508/stable/api/pages/nextavailable?task_id=1&unit_id=1&current_page_number=1

Get entry data for post
http://kbhkilder.dk/1508/stable/api/posts/209
Returns a specific post with data for all entries based on the post id

Get specific entry:
http://kbhkilder.dk/1508/stable/api/entries/6

Get error reports:
http://kbhkilder.dk/1508/stable/api/errorreports?task_id=1&post_id=201

Datasources:
http://kbhkilder.dk/api/datasource/1?q=adelgade

Get searchable fields for collections:
http://kbhkilder.dk/1508/stable/api/searchconfig?collection_id=1

Search:
http://kbhkilder.dk/1508/stable/api/search? + SOLR query

Error reporting:
http://kbhkilder.dk/1508/stable/api/errorreports
```
Required post data {
      post_id,
      entity_name,
      field_name,
      concrete_entries_id,
      comment,
      value
}
```

