# import-mail-and-pass-to-firebase

>import user mail&password(**plain text**) from CSV to firebase auth   
>and you **need not to care about UID**

## Requirements

- recommended: keyboard macro (so primitive! :-P)

## Setup

after cloning this repo,

### Modify CSV to nested array

needed like this;
```
['test@tes.com','password', ... ],
['test2@tes.com','password2', ... ]
```
(it don't matter where mail/password is)

``` bash
vi foo.csv

# replace (depends on the csv) 
#
#   I assume CSV like this;
#     test@tes.com,password, ... 
#     test2@tes.com,password2, ... 
#
:%s/,/','/g | :%s/\n/'],\r['/g 
```

and add `['` on first and remove excess `['` on last

### Paste CSV array 

open `index.html` and paste it   
you must set **mail/password index number** where there are

### Firebase Setting 
open `index.html` and paste your firebase snippet

## Usage

```
$ npm install -g live-server  # if you haven't already
$ live-server                 # open localhost:8080 in your browser
```

click the button on the page   
you can import one user per click   
   
if clicking too often, '**too-many-request**' error occured   
maybe about 15click / 10min is limit     
## To Do(but may not do :-P)

- direct reading from CSV
- loop processing
