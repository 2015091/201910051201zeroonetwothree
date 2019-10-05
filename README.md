# 201910051201_Krestiki_Noliki
<!-- (w) cadaber, Jul 1999. //-->
<html>

<head>
<title>xo</title>
<script LANGUAGE="JavaScript">
<!--
var cell = new Array(9);
for (i=0; i<9; i++) cell[i] = 0;

x = new Image(64,64);
x.src = "http://spassk.ru/games/xo1/x.gif";
o = new Image(64,64);
o.src = "http://spassk.ru/games/xo1/o.gif";
e = new Image(64,64);
e.src = "http://spassk.ru/games/xo1/z.gif";

function Cross(value) {
  if (value == 0) document.pole0.src = x.src;
  if (value == 1) document.pole1.src = x.src;
  if (value == 2) document.pole2.src = x.src;
  if (value == 3) document.pole3.src = x.src;
  if (value == 4) document.pole4.src = x.src;
  if (value == 5) document.pole5.src = x.src;
  if (value == 6) document.pole6.src = x.src;
  if (value == 7) document.pole7.src = x.src;
  if (value == 8) document.pole8.src = x.src;
}

function Zero(value) {
  if (value == 0) document.pole0.src = o.src;
  if (value == 1) document.pole1.src = o.src;
  if (value == 2) document.pole2.src = o.src;
  if (value == 3) document.pole3.src = o.src;
  if (value == 4) document.pole4.src = o.src;
  if (value == 5) document.pole5.src = o.src;
  if (value == 6) document.pole6.src = o.src;
  if (value == 7) document.pole7.src = o.src;
  if (value == 8) document.pole8.src = o.src;
}

function CheckVictory() {
  if (cell[0] == cell[1] && cell[1] == cell[2] && cell[2] > 0) return true; 
  if (cell[3] == cell[4] && cell[4] == cell[5] && cell[5] > 0) return true;
  if (cell[6] == cell[7] && cell[7] == cell[8] && cell[8] > 0) return true;
  if (cell[6] == cell[3] && cell[3] == cell[0] && cell[0] > 0) return true;
  if (cell[7] == cell[4] && cell[4] == cell[1] && cell[1] > 0) return true;
  if (cell[8] == cell[5] && cell[5] == cell[2] && cell[2] > 0) return true;
  if (cell[6] == cell[4] && cell[4] == cell[2] && cell[2] > 0) return true;
  if (cell[0] == cell[4] && cell[4] == cell[8] && cell[8] > 0) return true;
}

function CompTurn() {
  for (i=0; i<9; i++) if (cell[i] == 0) PutHere = i;
  for (i=0; i<3; i++) {
  if (cell[0] == cell[1] && cell[2] == 0 && cell[0] == i) PutHere = 2;
  if (cell[0] == cell[2] && cell[1] == 0 && cell[0] == i) PutHere = 1;
  if (cell[1] == cell[2] && cell[0] == 0 && cell[2] == i) PutHere = 0;
  if (cell[3] == cell[4] && cell[5] == 0 && cell[3] == i) PutHere = 5;
  if (cell[3] == cell[5] && cell[4] == 0 && cell[3] == i) PutHere = 4;
  if (cell[4] == cell[5] && cell[3] == 0 && cell[5] == i) PutHere = 3;
  if (cell[6] == cell[7] && cell[8] == 0 && cell[6] == i) PutHere = 8;
  if (cell[6] == cell[8] && cell[7] == 0 && cell[6] == i) PutHere = 7;
  if (cell[7] == cell[8] && cell[6] == 0 && cell[8] == i) PutHere = 6;

  if (cell[6] == cell[3] && cell[0] == 0 && cell[6] == i) PutHere = 0;
  if (cell[6] == cell[0] && cell[3] == 0 && cell[6] == i) PutHere = 3;
  if (cell[3] == cell[0] && cell[6] == 0 && cell[3] == i) PutHere = 6;
  if (cell[7] == cell[4] && cell[1] == 0 && cell[7] == i) PutHere = 1;
  if (cell[7] == cell[1] && cell[4] == 0 && cell[7] == i) PutHere = 4;
  if (cell[4] == cell[1] && cell[7] == 0 && cell[4] == i) PutHere = 7;
  if (cell[8] == cell[5] && cell[2] == 0 && cell[8] == i) PutHere = 2;
  if (cell[8] == cell[2] && cell[5] == 0 && cell[8] == i) PutHere = 5;
  if (cell[5] == cell[2] && cell[8] == 0 && cell[5] == i) PutHere = 8;

  if (cell[6] == cell[4] && cell[2] == 0 && cell[6] == i) PutHere = 2;
  if (cell[6] == cell[2] && cell[4] == 0 && cell[6] == i) PutHere = 4;
  if (cell[4] == cell[2] && cell[6] == 0 && cell[4] == i) PutHere = 6;
  if (cell[0] == cell[4] && cell[8] == 0 && cell[0] == i) PutHere = 8;
  if (cell[0] == cell[8] && cell[4] == 0 && cell[0] == i) PutHere = 4;
  if (cell[4] == cell[8] && cell[0] == 0 && cell[4] == i) PutHere = 0;
  }
  Zero(PutHere);
  cell[PutHere] = 2;
  if (CheckVictory() == true) {
    alert("Выиграл JavaScript =).");
    GameOver();
  }
}

function GameOver() {
  for (i=0; i<9; i++) cell[i] = 0;
  document.pole0.src = e.src;
  document.pole1.src = e.src;
  document.pole2.src = e.src;
  document.pole3.src = e.src;
  document.pole4.src = e.src;
  document.pole5.src = e.src;
  document.pole6.src = e.src;
  document.pole7.src = e.src;
  document.pole8.src = e.src;
}

function CheckNobody() {
  no = false;
  for (i=0; i<9; i++) if (cell[i] == 0) no = true;
  if (no == false) {
    alert("Ничья.");
    GameOver();
  }
}

function Place(value) {
  if (cell[value] == 0) {
    Cross(value);
    cell[value] = 1;
    if (CheckVictory() == true) {
      alert("Ты выиграл. Поздравляю.");
      GameOver();
    }
    else {
      CheckNobody();
      CompTurn();
      CheckNobody();
    }
  }
}
//-->
</script>
</head>

<body BACKGROUND="http://spassk.ru/games/xo1/grid.gif" BGCOLOR="#000000" BGPROPERTIES="fixed" TEXT="#00bb00" LINK="#00cc00" ALINK="#00ff00" VLINK="#00aa00">
<tt>

<p ALIGN="center"><font COLOR="#00ff00">крестики-нолики</font><br>
<br>
</p>
<div align="center"><center>

<table BORDER="0" CELLSPACING="0">
  <tr>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole0" onClick="Place(0)" WIDTH="64" HEIGHT="64"></td>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole1" onClick="Place(1)" WIDTH="64" HEIGHT="64"></td>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole2" onClick="Place(2)" WIDTH="64" HEIGHT="64"></td>
  </tr>
  <tr>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole3" onClick="Place(3)" WIDTH="64" HEIGHT="64"></td>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole4" onClick="Place(4)" WIDTH="64" HEIGHT="64"></td>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole5" onClick="Place(5)" WIDTH="64" HEIGHT="64"></td>
  </tr>
  <tr>
    <td align="center"><p align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole6" onClick="Place(6)" WIDTH="64" HEIGHT="64"></td>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole7" onClick="Place(7)" WIDTH="64" HEIGHT="64"></td>
    <td align="center"><img SRC="http://spassk.ru/games/xo1/z.gif" NAME="pole8" onClick="Place(8)" WIDTH="64" HEIGHT="64"></td>
  </tr>
</table>
</center></div>

<p align="center"><br>
(w) cadaber, Jun 1999. </tt></p>
</body>
</html>
