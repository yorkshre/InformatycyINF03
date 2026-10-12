1. Zadanie lotto. Zrób program które losuje 6 liczb z zakresu od 1 do 49. Liczby mają być losowanie za pomocą funkcji wbudowanej w Math - liczby nie mogą się powtarzać. Dodaj do tego style i html, zrób z tego aplikacje internetową
 ```js
   <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body{
            font-family: Arial, Helvetica, sans-serif;
            margin:30px;
        }
        
        ul{
            margin-top:15px;
            padding-left: 20px;
        }
        button{
            background-color: blueviolet;
            color:white;
            border:none;
            padding:10px 15px;
            border-radius: 4px;
            font-weight: bold;
        }
    </style>
</head>
<body>
                <h1>Nagłowek jest to</h1>
    <p id="demo">cos tam</p>   
<h1> zadanie lotto</h1> 
 <p>losuj liczby 6</p>
    <button onclick="losujLotto()">losuj liczby</button>
    <!--komunikat o bledzie-->
    <ul id="wynikiLotto"></ul>

    
<script> 
function losujLotto(){
    var wylosowane = new Set();
    while (wylosowane.size<6){
        var liczba = Math.floor(Math.random()*49)+1;
        wylosowane.add(liczba);
    }
    var lista =document.getElementById("wynikiLotto");
    lista.innerHTML="";
    wylosowane.forEach(liczba=>{
        let li = document.createElement("li");
        li.textContent=liczba;
        lista.appendChild(li);
    });
}

</script>
</body>
</html>
```
2. **Tabliczka mnożenia**: Napisz skrypt, który generuje tabliczkę mnożenia dla wybranej liczby (od 1 do 10) i wyświetla ją wewnątrz listy `<ul>` w HTML.
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body{
            font-family: Arial, Helvetica, sans-serif;
            margin:30px;
        }
        .error{
            color:red;
            font-weight:bold;
        }
        ul{
            margin-top:15px;
            padding-left: 20px;
        }
    </style>
</head>
<body>
                <h1>Nagłowek jest to</h1>
    <p id="demo">cos tam</p>   
    <h2>Tabliczka mnozenia</h2>
    <p>woriwadz liczbe od 1 do 10</p>
    <input type="number" id="liczbaInput" placeholder="np. 5">
    <button onclick="generujTabliczke()">Generuj</button>
    <!--komunikat o bledzie-->
    <div id = "komunikat"> class ="error"</div>
    <ul id="wynikiLista"></ul>

    
<script> 
function generujTabliczke(){
    var inputVal=document.getElementById("liczbaInput").value;
    var komunikat=document.getElementById("komunikat");
    var lista=document.getElementById("wynikiLista");
    //czysczenie poprzednich wynikow
    lista.innerHTML="";
//krok1 walidacja pustych pól lub złego wpisywania np. litera wpisana zamiast liczba
    if (inputVal.trim() == "" || isNaN(inputVal)) {
    komunikat.textContent = "Błąd: wprowadź poprawną liczbę";
    return;
}
    var liczba=Number(inputVal);

    //krok 2 walidacja od 1 do 10

    if(liczba<1||liczba>10){
        komunikat.textContent="Błąd, liczba nie miesci sie w zakresie";
        return;
    }
    //krok 3 generowanie elementu listy (<li>) za pomocą for
        for(let i=1;i<=10;i++){
            var li = document.createElement("li");
            li.textContent=liczba+"*"+i+"="+(liczba *i);
            lista.appendChild(li);
        }
    }

</script>
</body>
</html>
```
3. **Kalkulator** wykonaj kalkulator naukowy zawierający funkcje (+,-,/,*,%,potęgowanie, pierwiastkowanie, walidacja danych), dodaj style css do przyciskow kalkulatora.
