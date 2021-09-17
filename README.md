# Gewinn-und-Erl-s

<html>
	<head>
		<title>Titel</title>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8">

		<script>

			"use strict";

	 function fGE(){
var vAusgabe;
var vKV;
var vKF;
var vProduktionsmenge;
var vStückpreis;
var vMenge= 1000;
var vKosten;
var vErlös;
var vGewinn;
var vBep;
var vSchwelle;

vKV = parseFloat(document.getElementById("idKV").value);
vKF = parseFloat(document.getElementById("idKF").value);
vProduktionsmenge = parseFloat(document.getElementById("idProduktionsmenge").value);
vStückpreis = parseFloat(document.getElementById("idStückpreis").value);




vAusgabe = "";

vAusgabe = vAusgabe + "<table border =1>";
vAusgabe = vAusgabe + "<tr><th> Menge </th><th> Kosten K(x) = kF + kv * x </th><th> Erlöse E (x) = p * x </th><th> Gewinn G(x) = E(x)- K(x) </th><th> Bemerkung </th> </tr>";
             

while(vMenge<=vProduktionsmenge ){
vErlös =  vStückpreis * vMenge;
vKosten = vKF + vKV * vMenge;
vGewinn= vErlös-vKosten;
if(vGewinn<0){



vAusgabe= vAusgabe +
 "<tr><td>" + vMenge +"</td><td> " + vKosten + "</td><td> " + vErlös+ "</td><td> " + vGewinn + "</td><td style=color:red> " + "Verlust" + "</td></tr>";
}
else{


vAusgabe= vAusgabe + 
"<tr><td>" + vMenge +"</td><td> " + vKosten + "</td><td> " + vErlös+ "</td><td> " + vGewinn + "</td><td> " + "Gewinn" + "</td></tr>";


}
vMenge=vMenge+1000;
}
vAusgabe= vAusgabe + "</table>";
vBep = vKF /(vStückpreis-vKV) ;
vSchwelle = vBep * vStückpreis;
vAusgabe = vAusgabe + "Break-even-Point: " +vBep + "<br>" + "Gewinnschwelle: " +vSchwelle;
document.getElementById("idAusgabe").innerHTML = vAusgabe;

}

		 </script>

</head>

	<body>
<h1>Gewinn und Erlösfunktion</h1>
 Kosten-Variabel(k)<input id="idKV" type="text" value="4.50">
  Kosten-Fix:<input id="idKF" type="text" value="12800">
</br> </br>
Produktionsmenge(x):<input id="idProduktionsmenge" type="text" value="20000">
Stückpreis:<input id="idStückpreis" type="text" value="6">

<br> <br> <button onClick="fGE();">Kostentabelle!</button>

<div id="idAusgabe"></div>


	</body>
</html>
