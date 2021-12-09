George Pastushok 2021

logoGen is a program that takes user input or database input and creates a logo from a set of templates in Illustrator.

--------------------------------------
WIP-WIP-WIP
--------------------------------------
User input is powershell
database is database.json, or whatever I'll migrate to in the future.
powershell should have an alias for the script for ease of use
the script should have flags for options.
any mismatches (e.g. soccer logo on a softball team) should return errors.
any missing information from a campaign/team in the database should return an error without catastrophically failing.
the script should take just an order ID
	"logoGen 2168266"
the script then should look for global variable $database.$1 and set $2 = $database.$1
$2 should contain:
	.logoscript (usually has a | divider for top and bottom texts)
	.logoID (1-20)
	.priColor
	.secColor
	.fundID
	and the counts for all the logos req'd for this order
	(counts of 4x3,6x3,8x4 and 11x6)

create a CSV file that has the format:
{topText,bottomText, etc...
teamName,sportsBall, etc...}
find the template file to use based on .logoID (and in the future, the length of the text in .logoScript)
open the file in illustrator ( or Illustrator VBA)
apply the CSV file we just created to the Illustrator document.
apply any additional actions for print prep ( could be a flag to skip/add anything at this point. If the need ever arose to create a web-ready logo vs a print-ready, or for DTG/embroidery)
save with the filename in the format fundID_logoSize_logoScript.eps (file extension, name and location could also be changed via flags.) into the current working directory.
