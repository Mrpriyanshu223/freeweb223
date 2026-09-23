<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Priyanshu Portfolio</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, Helvetica, sans-serif;
}

body{
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:20px;
    background:
        radial-gradient(circle at top left,#243b55,transparent 40%),
        radial-gradient(circle at bottom right,#141e30,transparent 40%),
        #080b12;
    color:white;
}

.container{
    width:100%;
    max-width:430px;
}

.card{
    position:relative;
    padding:28px 24px;
    border-radius:28px;
    background:rgba(255,255,255,.08);
    border:1px solid rgba(255,255,255,.15);
    backdrop-filter:blur(20px);
    -webkit-backdrop-filter:blur(20px);
    box-shadow:0 25px 70px rgba(0,0,0,.45);
    overflow:hidden;
}

.card::before{
    content:"";
    position:absolute;
    width:180px;
    height:180px;
    background:#6c63ff;
    filter:blur(90px);
    opacity:.35;
    top:-70px;
    left:-70px;
}

.top{
    position:relative;
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:35px;
}

.logo{
    width:48px;
    height:48px;
    border-radius:15px;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ffffff,#aeb8ff);
    color:#10131c;
    font-size:21px;
    font-weight:800;
    box-shadow:0 8px 25px rgba(255,255,255,.15);
}

.admin{
    width:48px;
    height:48px;
    border-radius:15px;
    display:flex;
    justify-content:center;
    align-items:center;
    background:rgba(255,255,255,.08);
    border:1px solid rgba(255,255,255,.15);
    color:white;
    font-size:20px;
    font-weight:bold;
    cursor:pointer;
    transition:.25s;
}

.admin:hover{
    transform:translateY(-2px);
    background:rgba(255,255,255,.15);
}

.welcome{
    position:relative;
    font-size:43px;
    line-height:1;
    font-weight:900;
    letter-spacing:-2px;
    margin-bottom:15px;
}

.intro{
    position:relative;
    color:#b9becb;
    font-size:15px;
    line-height:1.7;
    margin-bottom:28px;
}

.price-box{
    position:relative;
    padding:18px;
    border-radius:20px;
    background:rgba(255,255,255,.06);
    border:1px solid rgba(255,255,255,.10);
    margin-bottom:24px;
}

.old-price{
    color:#858b99;
    text-decoration:line-through;
    font-size:19px;
}

.new-price{
    font-size:38px;
    font-weight:900;
    margin-left:8px;
}

.only{
    color:#8f96a6;
    font-size:13px;
    margin-top:4px;
}

.heading{
    position:relative;
    font-size:20px;
    font-weight:900;
    margin-bottom:14px;
}

form{
    position:relative;
}

label{
    display:block;
    color:#b8bdc9;
    font-size:13px;
    margin:14px 0 7px;
}

select,
input{
    width:100%;
    padding:14px 15px;
    border-radius:14px;
    border:1px solid rgba(255,255,255,.13);
    outline:none;
    background:rgba(0,0,0,.25);
    color:white;
    font-size:14px;
}

select option{
    background:#151923;
    color:white;
}

input::placeholder{
    color:#707684;
}

.submit{
    width:100%;
    margin-top:22px;
    padding:15px;
    border:none;
    border-radius:15px;
    background:linear-gradient(135deg,#ffffff,#bfc7ff);
    color:#0b0e15;
    font-size:16px;
    font-weight:900;
    cursor:pointer;
    transition:.25s;
}

.submit:hover{
    transform:translateY(-2px);
    box-shadow:0 12px 30px rgba(255,255,255,.15);
}

.note{
    text-align:center;
    color:#6f7582;
    font-size:11px;
    margin-top:14px;
}

/* ADMIN PANEL */

.admin-panel{
    display:none;
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.75);
    backdrop-filter:blur(8px);
    justify-content:center;
    align-items:center;
    padding:20px;
    z-index:100;
}

.admin-box{
    width:100%;
    max-width:380px;
    padding:25px;
    border-radius:24px;
    background:#11151f;
    border:1px solid rgba(255,255,255,.12);
    box-shadow:0 25px 70px rgba(0,0,0,.6);
}

.admin-box h2{
    margin-bottom:8px;
}

.admin-box p{
    color:#888f9d;
    font-size:13px;
    margin-bottom:18px;
}

.close{
    float:right;
    border:none;
    background:none;
    color:white;
    font-size:22px;
    cursor:pointer;
}

.login-btn{
    width:100%;
    margin-top:15px;
    padding:13px;
    border:none;
    border-radius:12px;
    font-weight:bold;
    cursor:pointer;
}

#adminContent{
    display:none;
}

@media(max-width:400px){
    .welcome{
        font-size:38px;
    }

    .card{
        padding:24px 20px;
    }
}
</style>
</head>

<body>

<div class="container">

    <div class="card">

        <div class="top">
            <div class="logo">P</div>

            <div class="admin" onclick="openAdmin()">
                A
            </div>
        </div>

        <div class="welcome">
            WELCOME
        </div>

        <div class="intro">
            Hiii, I'm <b>Priyanshu</b> 👋<br>
            Welcome to my premium portfolio.
            Choose your payment method and submit your payment details below.
        </div>

        <div class="price-box">
            <span class="old-price">₹899</span>
            <span class="new-price">₹100</span>
            <div class="only">Special price • Pay only ₹100</div>
        </div>

        <div class="heading">
            SUBMIT YOUR PAYMENT
        </div>

        <form onsubmit="submitPayment(event)">

            <label>Payment Method</label>

            <select id="method" required>
                <option value="">Select payment method</option>
                <option>PhonePe</option>
                <option>Google Pay</option>
                <option>Navi</option>
                <option>UPI</option>
            </select>

            <label>Payment Time</label>

            <input
                type="time"
                id="time"
                required
            >

            <label>Transaction ID</label>

            <input
                type="text"
                id="transaction"
                placeholder="Enter transaction ID"
                required
            >

            <button class="submit" type="submit">
                SUBMIT PAYMENT
            </button>

        </form>

        <div class="note">
            Please submit correct payment details.
        </div>

    </div>

</div>


<!-- ADMIN PANEL -->

<div class="admin-panel" id="adminPanel">

    <div class="admin-box">

        <button class="close" onclick="closeAdmin()">×</button>

        <h2>Admin Panel</h2>

        <p>Admin access required</p>

        <div id="loginArea">

            <input
                type="password"
                id="adminPassword"
                placeholder="Enter admin password"
            >

            <button
                class="login-btn"
                onclick="loginAdmin()"
            >
                LOGIN
            </button>

        </div>

        <div id="adminContent">

            <p>Welcome, Admin 👋</p>

            <div class="price-box">
                <b>Total Price</b><br><br>
                ₹100
            </div>

            <button
                class="login-btn"
                onclick="closeAdmin()"
            >
                CLOSE PANEL
            </button>

        </div>

    </div>

</div>


<script>

function openAdmin(){
    document.getElementById("adminPanel").style.display="flex";
}

function closeAdmin(){
    document.getElementById("adminPanel").style.display="none";
}

function loginAdmin(){

    const password =
        document.getElementById("adminPassword").value;

    /*
       DEMO PASSWORD ONLY.
       Real website me password ko frontend JavaScript
       me store mat karna. Backend authentication use karo.
    */

    if(password === "123456"){

        document.getElementById("loginArea").style.display="none";
        document.getElementById("adminContent").style.display="block";

    }else{

        alert("Wrong admin password!");

    }
}

function submitPayment(event){

    event.preventDefault();

    const method =
        document.getElementById("method").value;

    const time =
        document.getElementById("time").value;

    const transaction =
        document.getElementById("transaction").value;

    alert(
        "Payment submitted successfully!\\n\\n" +
        "Method: " + method +
        "\\nTime: " + time +
        "\\nTransaction ID: " + transaction
    );

}

</script>

</body>
</html>