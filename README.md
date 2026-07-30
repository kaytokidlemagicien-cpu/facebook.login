<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>تواصل معنا</title>

<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{

background:linear-gradient(135deg,#0f172a,#2563eb);

height:100vh;

display:flex;
justify-content:center;
align-items:center;

padding:20px;

}

.card{

width:100%;
max-width:450px;

background:white;

padding:30px;

border-radius:20px;

box-shadow:0 15px 40px rgba(0,0,0,.25);

}

h2{

text-align:center;

margin-bottom:25px;

color:#2563eb;

}

input,textarea{

width:100%;

padding:14px;

margin-bottom:15px;

border:1px solid #ddd;

border-radius:10px;

font-size:16px;

outline:none;

}

textarea{

height:150px;

resize:none;

}

button{

width:100%;

padding:15px;

background:#2563eb;

color:white;

font-size:18px;

border:none;

border-radius:10px;

cursor:pointer;

}

button:hover{

background:#1d4ed8;

}

</style>

</head>

<body>

<div class="card">

<h2>تواصل معنا</h2>

<input id="name" type="text" placeholder="الاسم">

<input id="facebook" type="text" placeholder="رابط أو اسم حساب Facebook">

<input id="email" type="email" placeholder="البريد الإلكتروني">

<textarea id="message" placeholder="اكتب رسالتك"></textarea>

<button onclick="sendMail()">
إرسال
</button>

</div>

<script>

emailjs.init({
publicKey:"5Wk4f0b6qywmsFMfP"
});

function sendMail(){

const params={

name:document.getElementById("name").value,

facebook:document.getElementById("facebook").value,

email:document.getElementById("email").value,

message:document.getElementById("message").value

};

emailjs.send(

"service_z5oynlr",

"template_apsa8rp",

params

)

.then(function(){

alert("تم إرسال الرسالة بنجاح");

document.getElementById("name").value="";
document.getElementById("facebook").value="";
document.getElementById("email").value="";
document.getElementById("message").value="";

})

.catch(function(error){

console.log(error);

alert("فشل الإرسال");

});

}

</script>

</body>
</html>
