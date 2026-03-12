<!DOCTYPE html>
<html>
<head>
<title>SAR-1 AI Chatbot</title>

<style>
body{
font-family: Arial;
background:#0f172a;
display:flex;
justify-content:center;
align-items:center;
height:100vh;
margin:0;
}

.chat-container{
width:400px;
background:#1e293b;
border-radius:10px;
overflow:hidden;
box-shadow:0 0 20px rgba(0,0,0,0.5);
}

.header{
background:#2563eb;
color:white;
padding:15px;
text-align:center;
font-weight:bold;
}

.chat{
height:400px;
overflow-y:auto;
padding:10px;
}

.message{
margin:10px 0;
padding:10px;
border-radius:8px;
max-width:80%;
}

.user{
background:#2563eb;
color:white;
margin-left:auto;
}

.bot{
background:#334155;
color:white;
}

.input-area{
display:flex;
border-top:1px solid #444;
}

input{
flex:1;
padding:10px;
border:none;
outline:none;
}

button{
background:#2563eb;
border:none;
color:white;
padding:10px 20px;
cursor:pointer;
}
</style>

</head>

<body>

<div class="chat-container">

<div class="header">
SAR-1 AI Chatbot
</div>

<div id="chat" class="chat"></div>

<div class="input-area">
<input id="input" placeholder="Ask something..." />
<button onclick="sendMessage()">Send</button>
</div>

</div>

<script>

const chat = document.getElementById("chat");

function addMessage(text, sender){

const msg = document.createElement("div");
msg.classList.add("message");
msg.classList.add(sender);
msg.innerText = text;

chat.appendChild(msg);
chat.scrollTop = chat.scrollHeight;

}

function sendMessage(){

const input = document.getElementById("input");
const text = input.value;

if(!text) return;

addMessage(text,"user");

input.value="";

setTimeout(()=>{

const responses = [
"Interesting question.",
"I think that could work.",
"Tell me more.",
"That's fascinating.",
"I'm still learning but that sounds cool."
];

const reply = responses[Math.floor(Math.random()*responses.length)];

addMessage(reply,"bot");

},1000);

}

addMessage("Hello! I'm SAR-1 AI assistant.","bot");

</script>

</body>
</html>
