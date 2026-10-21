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
3. **Kalkulator** wykonaj kalkulator naukowy zawierający funkcje (+,-,/,*,%,potęgowanie, pierwiastkowanie, walidacja danych), dodaj style css do przyciskow kalkulatora. Zakończ kod:
   Tak by dodać modulo, mnożenie pierwiastkowanie, potęgowanie.

```js
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalkulator naukowy</title>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif;
            margin: 30px;
        }
        ul {
            margin-top: 15px;
            padding-left: 20px;
        }
        button {
            background-color: blueviolet;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 4px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 10px;
        }
        #wynikKalkulator {
            margin-top: 15px;
            font-weight: bold;
        }
        .error {
            color: red;
        }
    </style>
</head>
<body>

<h2>Kalkulator naukowy</h2>

<input type="number" id="calcNum1" placeholder="liczba1">
<input type="number" id="calcNum2" placeholder="liczba2">
<br><br>

<select id="calcOp">
    <option value="+">Dodawanie</option>
    <option value="-">Odejmowanie</option>
    <option value="*">Mnożenie</option>
    <option value="/">Dzielenie</option>
    <option value="pierwiastek">Pierwiastek</option>
</select>
<br>

<button onclick="obliczKalkulator()">Oblicz</button>

<!-- Poprawione ID z wynikalkulator na wynikKalkulator -->
<div id="wynikKalkulator"></div>

<script> 
function obliczKalkulator() {
    var val1 = document.getElementById("calcNum1").value;
    var val2 = document.getElementById("calcNum2").value;
    var op = document.getElementById("calcOp").value;
    var wynikDiv = document.getElementById("wynikKalkulator");
    
    wynikDiv.className = "";
    wynikDiv.textContent = "";

    // Walidacja pierwszej liczby (poprawiono isNaN)
    if (val1.trim() === "" || isNaN(val1)) {
        wynikDiv.className = "error";
        wynikDiv.textContent = "Błąd: pierwsza wartość musi być liczbą";
        return;
    }
    
    var num1 = Number(val1);
    var num2 = 0;

    // Sprawdzenie drugiej liczby (jeśli operacja tego wymaga)
    if (op !== 'pierwiastek') {
        if (val2.trim() === "" || isNaN(val2)) {
            wynikDiv.className = "error";
            wynikDiv.textContent = "Błąd: druga wartość musi być liczbą";
            return;
        }
        num2 = Number(val2);
    }
        
    var wynik;
    
    switch(op) {
        case '+':
            wynik = num1 + num2;
            break;
        case '-':
            wynik = num1 - num2;
            break;
        case '*':
            wynik = num1 * num2;
            break; // Dodano brakujący break
        case '/':
            if (num2 === 0) {
                wynikDiv.className = "error";
                wynikDiv.textContent = "Błąd: nie dziel przez zero!"; // Poprawiono z wynik na wynikDiv
                return;
            }
            wynik = num1 / num2;
            break; // Dodano brakujący break
        case 'pierwiastek':
            if (num1 < 0) {
                wynikDiv.className = "error"; // Poprawiono eror na error
                wynikDiv.textContent = "Błąd: nie pierwiastkujemy liczby ujemnej";
                return;
            }
            wynik = Math.sqrt(num1); // Dodano obliczanie pierwiastka
            break;
        default:
            wynikDiv.className = "error";
            wynikDiv.textContent = "Błąd: nieznana operacja";
            return;
    }
    
    // Wyświetlenie wyniku w divie
    wynikDiv.textContent = "Wynik: " + wynik;
}
</script>

</body>
</html>
  ```
   
