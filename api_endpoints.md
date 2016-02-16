Ny liste (fra Github):

Get task JSON schema:

http://kbhkilder.dk/1508/stable/api/taskschema&task_id=1

Add entry:
http://kbhkilder.dk/1508/stable/api/entries/1 

Where 1 = task id

Data format:
```
{

page_id: 23, 

task_id: 1,


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

Get tasks:
http://kbhkilder.dk/1508/stable/api/tasks


Get task:
http://kbhkilder.dk/1508/stable/api/tasks/1


Get units:
http://kbhkilder.dk/1508/stable/api/units?collection_id=1&task_id=1


Get pages:
http://kbhkilder.dk/1508/stable/api/pages?unit_id=1&page_number=12


Get next available page:
http://kbhkilder.dk/1508/stable/api/pages/nextavailable?task_id=1&unit_id=1&current_page_number=1

Datasources:
http://kbhkilder.dk/api/datasource/1?q=adelgade

Get searchable fields for collections:
http://kbhkilder.dk/1508/stable/api/searchconfig?collection_id=1

Search:
http://kbhkilder.dk/1508/stable/api/search? + SOLR query
