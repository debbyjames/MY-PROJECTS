<html>
<HEAD>
    <title> TO-DO LIST </title>
    <style type="text/css">
    #textbox{
    	width: 60%;
    border-radius:2px solid red;
    padding: 5px;
    margin-bottom: 10px;
    }
    #button{
    border: 2px solid #1d1b1b;
    background-color:#1d1b1b;
    color:white;
    padding: 5px;
    margin-bottom: 10px;
    width: 15%;

    }
    .background{
     background-color: #1552bb;
     padding: 10px 0px 0px 0px;
     max-width: 30%;
     color: white;
     text-align: center;
    }

    #list{
    background-color: #f1f0f0;
     width: 405px;
    
    }
    .countTotal{
     text-align: center;
     padding: 10px 0px 10px 0px;
    }

    #txt{

    	padding: 6px;
    	font-size: 20px;
    	font-family: tw cen mt;
    }
    .txt{
    	text-decoration: line-through;
    }
    
    </style>
    <script language="javascript">


        

        function addList(myList) {

            if (document.getElementById('textbox').value==" ")
                {
                    alert ("Field Empty");
                    return false;
                }
 
            var count = document.getElementById(myList).rows.length;
            var row = document.getElementById(myList).insertRow(count);
           
 
            var createCell = row.insertCell(0);
            var rowList = document.createElement("input");
            rowList.id="txt";
            rowList.style.width="100%";
            rowList.style.border="#f1f0f0";
            rowList.style.background="#f1f0f0";
            rowList.value=document.getElementById('textbox').value;
	        createCell.appendChild(rowList);


            var createCell1 = row.insertCell(1);
            var rowList1 = document.createElement("input");
            rowList1.type = "checkbox";
            rowList1.name="chkbox[]";
            createCell1.appendChild(rowList1); 
            


document.getElementById('textbox').value=" ";
document.getElementById('countTotal').innerHTML= count + 1;
  
  
       }


       
function deleteList(myList) {
            
            var count = document.getElementById(myList).rows.length;

 
            for(var i=0; i<count; i++) {
                var row = document.getElementById(myList).rows[i];
                var chkbox = row.cells[1].childNodes[0];
                if(null != chkbox && true == chkbox.checked) 
                {
                    document.getElementById(myList).deleteRow(i);
                    count--;
                    i--;
              
            document.getElementById('countTotal').innerHTML= count;
 
            }
            }
        }

 
    </script>
</head>
<body style="font-family: tw cen mt">
<div class="background">
<h2>To-Do List</h2>
 <input type="textbox" id="textbox" placeholder="title..."   ;"/>
 <input type="button" id="button" value="Add" onclick="addList('list')"  />
 
 <input type="button" id="button" value="Delete" onclick="deleteList('list')" />
 
 
    <table id="list"></table>
    
 <div class="countTotal" >Total Work Left <a id="countTotal" ></a> </div>
 </div> 
</body>
</html>

