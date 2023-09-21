# Employee__salary
**#index-html**
<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">     
  <title>Document</title>  
</head> 
  <style>  
    table {          
      width: 50rem;  margin:auto ;  height: 30rem; text-align : center;  font-size: large;         
       background:#f9c3d6;  padding: 1px;  color:black; border: 2px solid blue;  
    }     
    h1{  
        text-align: center;     }  
    .eee{  
        display: none;    }     
button{  
       text-align: center;  justify-content: space-between;  width: 10rem; height: 2rem;        
background-color:deepskyblue; cursor: pointer;   }  
      
    .btn1{  
        margin-left: 32rem;   margin-top: 1rem;   }  
</style>  
<body>  
    <h1> Employee Salary Table.</h1>  
    <table border="1 solid black">  
        <tbody>  
            <tr>  
               <th>Name</th> <th> UID </th>  <th>City</th>  <th>Jobrole</th>  <th>Salary</th>             </tr>  
            <tr> <td> Pushpam Kumari </td>  <td> 20132 </td>  <td>Begusarai</td>  <td> Developer </td>   
                <td>   <input type="text" id="emp1" class="emp" />  </td>   
            </tr>              <tr>    
                <td> Navneet kumar </td> <td> 20149</td> <td> Punjab</td> <td> Programmer </td>   
                <td> <input type="text" id="emp2" class="emp" />    </td>   
            </tr>              
<tr>   
                <td> Deepika </td>   <td>20143</td> <td>HP</td> <td>Analyst</td>   
                <td>   <input type="text" id="emp3" class="emp" />   </td>   
            </tr>   
<tr>   
                <td> prabhat </td>   <td>20143</td> <td>UP</td> <td>Analyst</td>   
                <td>   <input type="text" id="emp3" class="emp" />   </td>   
            </tr>             
<tr>   
                <td> Pushkar </td> <td>20159</td> <td> begusarai</td> <td> Coder </td>                  <td> <input type="text" id="emp4" class="emp" /> </td>   
            </tr>               
        </tbody>   
    </table>  
    <button class="btn1" onclick="show()">show</button>  
    <button class="btn1" onclick="tsalary()">Total Sallary</button>  </div>    <script>     let data1 = 
104500;   //dev     let data2 = 
95000;   //pro     let data3 = 
85000;   //ana     let data4 = 80000;   //coder     function 
show() {  
let emp1 = (document.getElementById("emp1").value = data1);       
let emp2 = (document.getElementById("emp2").value = data2);       
  let emp3 = (document.getElementById("emp3").value = data3);       
  let emp4 = (document.getElementById("emp4").value = data4);       
  let emp5 = (document.getElementById("emp5").value = data1);        
    }  
    function tsalary(){  
        let total=data1+data2+data3+data4+data5;  
        alert(total);  
        document.getElementById("totalsalary").value = total;  
    }    
</script>  
</body>  
</html>  
**DISCRIPTION**
This HTML document creates a web page for displaying an employee salary table. Here's a short description of the code:

It defines an HTML5 document structure with metadata and a title.
There's a CSS <style> section that styles a table, headings, and buttons.
The page contains an employee salary table with columns for Name, UID, City, Jobrole, and Salary.
JavaScript functions are included:
show(): Sets predefined salary values for employees when the "show" button is clicked.
tsalary(): Calculates and displays the total salary of all employees when the "Total Salary" button is clicked. However, there's a missing data5 variable and an issue setting the total salary value.
The code has some structural and logical issues, such as the missing data5 variable and an attempt to set a non-existent element's value for total salary.

**Node.js Code (index.js)  **
  
const fs = require('fs').promises; const fs1 = require('fs'); 
const http = require('http');  
  
async function readFile(filePath){     
try{  
        const data = await fs.readFile(filePath);         
        console.log(data.toString());         
        const data1 = data.toString();         
        fs.writeFile('newFile.html', data1)  
    }catch(error){  
        console.log("Error", error, "in file ", filePath );  
    } }  
readFile('index.html');
http.createServer(function (req, res){     
fs1.readFile('newFile.html', 
function(err, data) {        
if (err) {            
res.writeHead(404);  
console.error('Error reading HTML file:', err);           
res.end();  
        }        
else {  
 res.writeHead(200, {'Content-type': 'text/html'})             
 res.write(data);              
 res.write("<h1>Total Salary = 729000</h1>");  
        }  
    });  
}).listen(8080);  

**DISCRIPTION**
This Node.js code, found in the index.js file, performs the following tasks in a concise description:

File Reading and Writing:

It uses the Node.js fs module to read the content of an index.html file asynchronously.
It then writes the content to a new file called newFile.html.
HTTP Server:

It creates an HTTP server using the http module, listening on port 8080.
When a client (e.g., a web browser) makes a request to this server, it reads the content of newFile.html and sends it as an HTML response.
If any errors occur during file reading, it responds with a 404 status code.
It also appends an additional HTML <h1> element to display the total salary as "Total Salary = 729000" in the response.
In summary, this Node.js code reads an HTML file, serves it through an HTTP server, and adds extra HTML content to the response.
