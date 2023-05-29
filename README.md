# project
calculator
This is a simple calculator application built using the tkinter library in html, css and javaScript. It provides basic arithmetic operations and some mathematical functions like cos, sin functions, subraction, and Addition.

Features
Addition, subtraction, multiplication, and division operations
Trigonometric functions: sin, cos, tan
Logarithm with a specified base
Square root calculation
Clearing the input field
Deleting the last character
Constants: Euler's number (e) and pi (π)

Usage
Clone the repository or download the calculator.html file.
Run the calculator.html file using javaScript.
The calculator window will appear with a text input field and buttons for different operations.
Enter the numbers and perform calculations using the buttons.
Press the "=" button to get the result.
Use the other buttons to perform additional operations as needed.

Screenshots
![Calculator](https://github.com/Codzahm/project/assets/123078736/b7ac6e10-d39a-4584-979d-19089fe273f4)

<!DOCTYPE html>
<html>
<head>
<style>
	form{
	width:440px;
	padding:25px;
	margin:auto;
	border:5px solid #aaa;
	border-radius:15px 15px;
	}
	
	input{
	background:#888;
	color:#fff;
	font-size:15px;
	padding-top:15px;
	padding-bottom:15px;
	padding-left:19px;
	padding-right:19px;
	margin:6px;
	}

	h2{
	text-align:center;
	}

	.sc{
	background:#fff;
	color:#000;
	}
</style>
<script>
function addChar(input, character) {
	if(input.value == null || input.value == "0")
		input.value = character
	else
		input.value += character
}

function cos(form) {
	form.display.value = Math.cos(form.display.value);
}

function sin(form) {
	form.display.value = Math.sin(form.display.value);
}

function tan(form) {
	form.display.value = Math.tan(form.display.value);
}

function sqrt(form) {
	form.display.value = Math.sqrt(form.display.value);
}

function ln(form) {
	form.display.value = Math.log(form.display.value);
}

function exp(form) {
	form.display.value = Math.exp(form.display.value);
}

function deleteChar(input) {
	input.value = input.value.substring(0, input.value.length - 1)
}

function changeSign(input) {
	if(input.value.substring(0, 1) == "-")
		input.value = input.value.substring(1, input.value.length)
	else
		input.value = "-" + input.value
}

function compute(form) {
	form.display.value = eval(form.display.value)
}

function square(form) {
	form.display.value = eval(form.display.value) * eval(form.display.value)
}

function checkNum(str) {
	for (var i = 0; i < str.length; i++) {
		var ch = str.substring(i, i+1)
		if (ch < "0" || ch > "9") {
			if (ch != "/" && ch != "*" && ch != "+" && ch != "-" && ch != "."
				&& ch != "(" && ch!= ")") {
				alert("invalid entry!")
				return false
				}
			}
		}
		return true
}
</script>
</head>
<body>
<br>
<form name="sci-calc">
<h2>SCIENTIFIC CALCULATOR</h2>
<table cellspacing="0" cellpadding="1">
<TR>
<TD COLSPAN="5" ALIGN="center"><input NAME="display" class="sc" VALUE="0" SIZE="44" MAXLENGTH="25"></TD>
</TR>
<TR>                                  
<td align="center"><input type="button" value="Clear" ONCLICK="this.form.display.value = 0 "></TD>
<td align="center" colspan="2"><input type="button" value="      Backspace     " ONCLICK="deleteChar(this.form.display)"></TD>
<td align="center" colspan="2"><input type="button" value="           Enter          " NAME="Enter" ONCLICK="if (checkNum(this.form.display.value)) { compute(this.form) }"></TD>
</TR> 
<TR>
<td align="center"><input type="button" value=" exp " ONCLICK="if (checkNum(this.form.display.value)) { exp(this.form) }"></TD>
<td align="center"><input type="button" value="  7  " ONCLICK="addChar(this.form.display, '7')"></TD>
<td align="center"><input type="button" value="  8  " ONCLICK="addChar(this.form.display, '8')"></TD>
<td align="center"><input type="button" value="  9  " ONCLICK="addChar(this.form.display, '9')"></TD>
<td align="center"><input type="button" value="   /   " ONCLICK="addChar(this.form.display, '/')"></TD>
</TR>                                  
<TR>                                   
<td align="center"><input type="button" value="  ln   " ONCLICK="if (checkNum(this.form.display.value)) { ln(this.form) }"></TD>
<td align="center"><input type="button" value="  4  " ONCLICK="addChar(this.form.display, '4')"></TD>
<td align="center"><input type="button" value="  5  " ONCLICK="addChar(this.form.display, '5')"></TD>
<td align="center"><input type="button" value="  6  " ONCLICK="addChar(this.form.display, '6')"></TD>
<td align="center"><input type="button" value="   *   " ONCLICK="addChar(this.form.display, '*')"></TD>
</TR>                                   
<TR>                                    
<td align="center"><input type="button" value=" sqrt " ONCLICK="if (checkNum(this.form.display.value)) { sqrt(this.form) }"></TD>
<td align="center"><input type="button" value="  1  " ONCLICK="addChar(this.form.display, '1')"></TD>
<td align="center"><input type="button" value="  2  " ONCLICK="addChar(this.form.display, '2')"></TD>
<td align="center"><input type="button" value="  3  " ONCLICK="addChar(this.form.display, '3')"></TD>
<td align="center"><input type="button" value="   -   " ONCLICK="addChar(this.form.display, '-')"></TD>
</TR>                                  
<TR>                                   
<td align="center"><input type="button" value="  sq  " ONCLICK="if (checkNum(this.form.display.value)) { square(this.form) }"></TD>
<td align="center"><input type="button" value="  0  " ONCLICK="addChar(this.form.display, '0')"></TD>
<td align="center"><input type="button" value="   .  " ONCLICK="addChar(this.form.display, '.')"></TD>
<td align="center"><input type="button" value=" +/- " ONCLICK="changeSign(this.form.display)"></TD>
<td align="center"><input type="button" value="   +  " ONCLICK="addChar(this.form.display, '+')"></TD>
</TR>                                  
<TR>                                   
<td align="center"><input type="button" value="   (    " ONCLICK="addChar(this.form.display, '(')"></TD>
<td align="center"><input type="button" value="cos" ONCLICK="if (checkNum(this.form.display.value)) { cos(this.form) }"></TD>
<td align="center"><input type="button" value=" sin " ONCLICK="if (checkNum(this.form.display.value)) { sin(this.form) }"></TD>
<td align="center"><input type="button" value=" tan" ONCLICK="if (checkNum(this.form.display.value)) { tan(this.form) }"></TD>
<td align="center"><input type="button" value="   )   " ONCLICK="addChar(this.form.display, ')')"></TD>
</TR>                                 

</table>
</form>
</body>
</html>
