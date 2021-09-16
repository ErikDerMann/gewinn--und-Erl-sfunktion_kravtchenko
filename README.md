# gewinn--und-Erl-sfunktion_kravtchenko

<!doctype html>
<html>
	<head>
		<title>Tabelle bauen</title>
			</head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
		<script>
			"use strict";
			function programm() {
			// Quellcode

			var vPmenge;
			var vAusgabe;
			var vX;
			var vKosten;
			var vVkosten;
			var vFkosten;
			var vSzahl;
			var vGewinn; 
			var vErlös;
				
				
				
				
			vX = 0;

			vPmenge = parseFloat(document.getElementById("idPmenge").value);
			vVkosten = parseFloat(document.getElementById("idVkosten").value);
						
				vFkosten = parseFloat(document.getElementById("idFkosten").value);
							vSzahl = parseFloat(document.getElementById("idSzahl").value);
		
				
				
				
				
				
				vAusgabe = "";
			vAusgabe = "Jetzt kommt eine Wertetabelle...<br>";

			vAusgabe = vAusgabe + "<table border=1>";
			vAusgabe = vAusgabe + "<tr><th>Menge</td><th>Kosten K(x) = kf + kv * x</td><th>Erlöse E(x)= p*x</td><th>Gewinn G(x)= E(x) - k(x)<th>Bemerkung</td> </td>          </tr>";

			while (vX <=vPmenge) {
				
				vKosten = vFkosten + vVkosten * vX
				vErlös = vSzahl * vX
				vGewinn = vErlös - vKosten
				
				if (vGewinn< 0) {
				vAusgabe = vAusgabe + "<tr><td>" + vX + "</td><td>" + vKosten + "</td><td>" + vErlös + "</td><td style=color:red>" + vGewinn + "</td><td>" + "verlustzone" + "</td></tr>";

				} else {
					
					
					vAusgabe = vAusgabe + "<tr><td>" + vX + "</td><td>" + vKosten + "</td><td>" + vErlös + "</td><td>" + vGewinn +  "</td><td>" + "gewinnzone" + "</td></tr>";
					
				}
				
				
				
				
				

			vX = vX + 1000;
}
			vAusgabe = vAusgabe + "</table>";

			document.getElementById("divAusgabe").innerHTML = vAusgabe;
		}

		</script>


	<body>
		<h1>Gewinn- und Erlösfunktion</h1>
	
		Kosten-Variable(k): x läuft von 1 bis <input id="idVkosten" type="text" value="4.50">
		
		Kosten-fix: <input id="idFkosten" type="text" value="12800"><br><br>


			
        Produktionsmenge(x): <input id="idPmenge" type="text" value="20000">
	
		stückpreis(p): <input id="idSzahl" type="text" value="6.00">
		<button onClick="programm();">Wertetabelle erzeugen!</button><br /><br />
        <div id="divAusgabe">Button klicken!</div>
	</body>
</html>
