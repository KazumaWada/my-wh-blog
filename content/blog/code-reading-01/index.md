---
title: I read someones code first time 
date: "2021-09-18T22:40:32.169Z"
---

# how i read it
 i commentted almost every lines and write about 'what does this code mean'.

 ```javascript: app.js
 loadEvents();
// load every event in the page
function loadEvents(){
  document.querySelector('form').addEventListener('submit',submit);
  document.getElementById('clear').addEventListener('click',clearList);
  document.querySelector('ul').addEventListener('click',deleteOrTick);

}
// subit data function
function submit(e){
  e.preventDefault();
  // let taskList;
  let input = document.querySelector('input');//declare input = <input> 
  if(input.value != '')//if not empty in <input>,
    addTask(input.value);//add that value using with addTask function
  input.value = '';//back to empty.
}

// add tasks
function addTask(task){
  let ul = document.querySelector('ul');// ul = <ul></ul>
  let li = document.createElement('li');// li = add new <li></li>
  li.innerHTML = `<span class="delete">×</span><input type="checkbox"><label>${task}</label>`; // after add new <li></li>, inside of <li> should wriiten like that.
  ul.appendChild(li);//you can put <li> exact location with this  
  document.querySelector('.tasksBoard').style.display = 'block';// changing css none ->block bc if no todo valuable here, you should do display:none first.
}

// clear the LIST
function clearList(e){
  let ul = document.querySelector('ul').innerHTML = '';
}

// deleteTick
function deleteOrTick(e){
  if(e.target.className == 'delete')// -> class = "delete" (one with red check box)
    deleteTask(e);
  else {
    tickTask(e);
  }
}

// delete task
function deleteTask(e){
  let remove = e.target.parentNode;
  let parentNode = remove.parentNode;
  parentNode.removeChild(remove);
}

// tick a task
function tickTask(e){
  const task = e.target.nextSibling;
  if(e.target.checked){
    task.style.textDecoration = "line-through";
    task.style.color = "#ff0000";
  }else {
    task.style.textDecoration = "none";
    task.style.color = "#2f4f4f";
  }
}

 ```

 it so simple todo app and it fits my current code review levels. I wll keep reading someones code to improve my code knowledge.


his repo
https://github.com/CaloloCosta/todoListAPP

