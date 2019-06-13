/* jshint browser: true */
/*jshint esversion: 6 */
/*global dateElement*/
/*global $*/

//DEFINICJA
const clear = document.querySelector(".clear");
const dateElement = document.getElementById("date");
const list = document.getElementById("list");
const input = document.getElementById("input");

//AKTUALNA DATA
const options = {weekday: "long", month: "short", day: "numeric"};
const today = new Date();
document.getElementById("date").innerHTML = today.toLocaleDateString("pl-PL", options); //"en-US" wygląda znacznie lepiej, pl-PL


//FUNKCJA DODAWANIA ITEMÓW
function addToDo(toDo) {
    const item = `<li class="item">
                 <i class="fa fa-circle-thin co" id="complete"></i>
                 <p class="text">${toDo}</p>
                 <span><i class="fa fa-trash-o de" id="delete"></i></span>
             </li>
                `;
    const position = "beforeend";  
    list.insertAdjacentHTML(position, item);
}


//DODAJ ITEM PO WCIŚNIĘCIU ENTER PRZEZ UŻYTKOWNIKA
document.addEventListener("keydown", function(even) {
    if(event.keyCode == 13) {
        const toDo = input.value;
        //jeśli input nie jest pusty
        if(toDo) {
            addToDo(toDo);
        }
        input.value = ""; //czyści input
    }
});

//WYCZYSZCZENIE CAŁEJ LISTY PO WCIŚNIĘCIU FA FA REFRESHA
$(".clear").click(function(){
    $("ul").empty();
});

//USUNIĘCIE ZADANIA PO WCIŚNIĘCIU KOSZA
$("ul").on("click", "span", function() {
           $(this).parent().fadeOut(500, function() {
                $(this).remove();
});
event.stopPropagation();
});


//ITEM'S GETTING LINED THROUGH PO KLIKNIĘCIU KOŁA 
$("ul").on("click", "li", function() {
     $(this).children().eq(1).css("text-decoration", "line-through");
});

    

//ITEM KOŁO DONE CHANGE COLOR
$("ul").on("click", "li" , function() {
    $(this).children().eq(0).removeClass("fa fa-circle-thin co").addClass("fa fa-check-circle");
});




