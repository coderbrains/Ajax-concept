# Ajax-concept
In this particular repo I have put all the concepts of AJAX . 

# Here is the startups.........

# What is An AJAX?

   * Asynchronous Java script and Xml
   * It is not a programming language
   * No Page Reload and refresh
   * Better user Interface..
  * Very Interactive

# How it works?

   * It uses XMLHttpRequest Object also called xhr Object.
   * It uses JSON instead or XML for data Transform


    console.log('This is ajax tutorial....');

    a = document.getElementById('fetch');
    a.addEventListener('click', clicked);

function clicked() {


    // Now we will make xhr object
    xhr = new XMLHttpRequest();


    //open the object named as xhr
    xhr.open('GET', 'https://jsonplaceholder.typicode.com/todos/1', true);

    xhr.onprogress = function () {
        console.log('onprogress is ready........')
    }

    // what to do when response is easy.
    xhr.onload = function () {

        console.log(this.responseText);

    }

    // send the request.

    xhr.send();

    // It will run just after the above line...

    console.log('send......');
}



b = document.getElementById('back');
b.addEventListener('click', clickedd);

function clickedd() {


    // Now we will make xhr object
    xhr = new XMLHttpRequest();


    //open the object named as xhr
    xhr.open('POST', 'http://dummy.restapiexample.com/api/v1/create', true);
    xhr.getResponseHeader('content-type', 'application/x-www-form-urlencoded');

    xhr.onprogress = function () {
        console.log('onprogress is ready........')
    }

    // what to do when response is easy.
    xhr.onload = function () {

        console.log(this.responseText);

    }

    // send the request.

    let params = `{"name":"test","salary":"123","age":"23"}`;

    xhr.send(params);

    // It will run just after the above line...

    console.log('send......');
}





populate = document.getElementById('populate');
populate.addEventListener('click', clicking);

function clicking() {

    console.log('Pophandler is clicked....');

    // Now we will make xhr object
    xhr = new XMLHttpRequest();

    //open the object named as xhr
    xhr.open('GET', 'https://jsonplaceholder.typicode.com/todos/1', true);

    

    // what to do when response is easy.
    xhr.onload = function () {

        obj = JSON.parse(this.responseText);
        console.log(obj);
        let list = document.getElementById('list');
        str = "";
        for(key in obj){
            str += `<li>${obj[key]}</li>`;
        }
        list.innerHTML = str;
    }

    // send the request.

    // let params = `{"name":"test","salary":"123","age":"23"}`;-+

    xhr.send();

    // It will run just after the above line...

    console.log('send......');
}


