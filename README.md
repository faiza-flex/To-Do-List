# To-Do-List
We are going to make a To Do List

	<style type="text/css">

		body{
			background: #663399;
		}

		.task_container{
			display: flex;
			margin-top: 10px;
			background: #9370db;
		}
		#addTask{
			width: 250px;
			padding: 1rem;
			color: #663399;
			background:lavender;
		}
		.task{
			background: #9370db;
			color: white;
			padding: 0.5rem;
		}
		.dltb{
			background: #ff6347;
			padding: 0.5rem;
		}
		.edtb{
			background:green;
			padding: 0.5rem;
		}
		#add{
			padding: 1rem;
			background: #7b68ee;
			color: white;
		}
	</style>

</head>
<body>

	<input type="text" name="" id="addTask" placeholder="Enter Task">
	<button id="add">Add</button>

	<script type="text/javascript">
		
		let addtask = document.getElementById("addTask");
		let add = document.getElementById("add");
		let body = document.querySelector("body");

		add.addEventListener("click", function(){
			if(addTask.value == ""){
				alert("Please Enter The Task");
				return;
			}
			let container = document.createElement("div");
			container.classList.add('task_container');
			body.appendChild(container);

			let taskInput = document.createElement("input");
			taskInput.type = 'text';
			taskInput.setAttribute("readonly" , "readonly");
			taskInput.classList.add('task');

			container.appendChild(taskInput);

			let buttons = document.createElement("div");

			container.appendChild(buttons);

			let deletebtn = document.createElement("button");
			deletebtn.innerHTML = "Delete";
			deletebtn.classList.add('dltb')
			deletebtn.addEventListener("click" , function(){
				container.remove();
			})

			buttons.appendChild(deletebtn);

			let editbtn = document.createElement("button");
			editbtn.innerHTML = "Edit";
			editbtn.classList.add('edtb');
			buttons.appendChild(editbtn);
			editbtn.addEventListener("click", function(){
				if(editbtn.innerHTML == "Edit"){
					editbtn.innerHTML = "Save";
					taskInput.removeAttribute("readonly"); 
				}else{
					editbtn.innerHTML = "Edit";
					taskInput.setAttribute("readonly","readonly");
				}

			})

			taskInput.value = addTask.value;
			addTask.value = "";
		})
	</script>

</body>
