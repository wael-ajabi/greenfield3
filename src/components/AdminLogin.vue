<template>
<body>
	<h1>
		<span>A</span>dmin
		<span>S</span>ide
        <br>

	</h1>
	<!-- //title -->
	<!-- content -->
	<div class="sub-main-w3">
        <video autoplay loop id="video-background" muted plays-inline>
    <source src="https://static.videezy.com/system/resources/previews/000/015/734/original/Tree_Branches_With_Several_Pink_Flowers.mp4" type="video/mp4">
 </video>
		<form id="demo" novalidate @submit.prevent="login">
            <h3 id="error">{{this.error}}</h3>
			<h2>Login to Your Account</h2>
            <br>
			<div class="form-group">
				<input type="text" class="form-control textbox" name="username" placeholder="username" required="" v-model="username">
			</div>
			<div class="form-group">
				<input type="password" class="form-control textbox" name="password" placeholder="Password" required="" v-model="password">
			</div>
			<div class="form-group-2">
			<button class="btn btn-default btn-osx btn-lg"  type="submit">
				<p>Submit</p>
				</button>
			</div>
		</form>
		<!-- //switch -->
	</div>
	<!-- //content -->

	<!-- copyright -->
	
	

</body>

	</template>
<script>
import axios from 'axios';

export default {
    name:"Admin",
data(){
    return {
        username:'',
        password:'',
		error:"",
        }    
},
    methods:{
        login(){
        console.log(this.username)
        axios.post('http://localhost:5000/admin/login',{username:this.username,password:this.password})
       .then(({data}) => {
        if (data === "this user does not exist") {
          this.error=data
        } else if (data === 'password is wrong') {
          this.error=data
        } else {
            this.$router.push({name:"ProductsAdmin",params: { data: JSON.stringify(data)
 }})
		}})}}}

</script>
<style scoped>
    #video-background {
    position: fixed;
    right: 0;
    bottom: 0;
    min-width: 100%;
    min-height: 75%;
    width: auto;
    height: auto;
    z-index: -1;
}
#error{color: red;
font-size: 20pt;
}
html,
body,
div,
span,
applet,
object,
iframe,
h1,
h2,
h3,
h4,
h5,
h6,
p,
blockquote,
pre,
a,
abbr,
acronym,
address,
big,
cite,
code,
del,
dfn,
em,
img,
ins,
kbd,
q,
s,
samp,
small,
strike,
strong,
sub,
sup,
tt,
var,
b,
u,
i,
dl,
dt,
dd,
ol,
nav ul,
nav li,
fieldset,
form,
label,
legend,
table,
caption,
tbody,
tfoot,
thead,
tr,
th,
td,
article,
aside,
canvas,
details,
embed,
figure,
figcaption,
footer,
header,
hgroup,
menu,
nav,
output,
ruby,
section,
summary,
time,
mark,
audio,
video {
    z-index: 10;
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font: inherit;
    vertical-align: baseline;
}

article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section {
    display: block;
}

ol,
ul {
    list-style: none;
    margin: 0px;
    padding: 0px;
}

blockquote,
q {
    quotes: none;
}

blockquote:before,
blockquote:after,
q:before,
q:after {
    content: '';
    content: none;
}

table {
    border-collapse: collapse;
    border-spacing: 0;
}

/* start editing from here */

a {
    text-decoration: none;
}

.txt-rt {
    text-align: right;
}

/* text align right */

.txt-lt {
    text-align: left;
}

/* text align left */

.txt-center {
    text-align: center;
}

/* text align center */

.float-rt {
    float: right;
}

/* float right */

.float-lt {
    float: left;
}

/* float left */

.clear {
    clear: both;
}

/* clear float */

.pos-relative {
    position: relative;
}

/* Position Relative */

.pos-absolute {
    position: absolute;
}

/* Position Absolute */

.vertical-base {
    vertical-align: baseline;
}

/* vertical align baseline */

.vertical-top {
    vertical-align: top;
}

/* vertical align top */

nav.vertical ul li {
    display: block;
}

/* vertical menu */

nav.horizontal ul li {
    display: inline-block;
}

/* horizontal menu */

img {
    max-width: 100%;
}

/*end reset*/

body {
    background-size: cover;
    background-position: center;
    font-family: 'Open Sans', sans-serif;
    font-size: 100%;
    position: relative;
    min-height: 100vh;
}

/*-- title --*/

h1 {
    font-size: 3.5em;
    color: #fff;
    letter-spacing: 2px;
    text-align: center;
    font-style: italic;
    margin: 3vw 1vw 5.5vw;
    font-family: 'Nova Round', cursive;
    text-shadow: 0px 1px 1px #000;
}

h1 span {
    color: #5cb85c;
}

h2 {
    color: #fff;
    font-size: 32px;
    font-weight: 600;
    margin-bottom: 1em;
    text-shadow: 1px 1px 2px #000;
}

/*-- //title --*/

/*-- content --*/

.sub-main-w3 {
    display: -webkit-flex;
    display: -webkit-box;
    display: -moz-flex;
    display: -moz-box;
    display: -ms-flexbox;
    display: flex;
    align-items: center;
    -webkit-box-pack: center;
    -moz-box-pack: center;
    -ms-flex-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
}

.sub-main-w3 form {
    max-width: 600px;
    margin: 0 5vw;
    background: rgba(255, 255, 255, 0.6);
    padding: 3.5vw;
    box-sizing: border-box;
    display: -webkit-flex;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    box-shadow: 0px 0px 7px 1px rgba(0, 0, 0, 0.33);
}

.form-group {
    margin-bottom: 1.5em;
    flex-basis: 100%;
    -webkit-flex-basis: 100%;
}
.sub-main-w3 input[type="text"],
.sub-main-w3 input[type="password"] {
    width: 100%;
    color: #fff;
    outline: none;
    font-size: 14px;
    letter-spacing: 1px;
    padding: 15px 15px;
    box-sizing: border-box;
    border: none;
    background: rgba(4, 4, 4, 0.61);
    border: 3px solid #477427;
    box-shadow: 1px 5px 12px 0px rgba(0, 0, 0, 0.46);
}

.sub-main-w3 input[type="submit"] {
    color: #fff;
    background: #38bcfb;
    border: none;
    padding: 13px 0;
    margin-top: 30px;
    outline: none;
    width: 100%;
    font-size: 16px;
    cursor: pointer;
    letter-spacing: 2px;
    -webkit-transition: 0.5s all;
    -o-transition: 0.5s all;
    -moz-transition: 0.5s all;
    -ms-transition: 0.5s all;
    transition: 0.5s all;
    box-shadow: 2px 2px 6px rgba(0, 0, 0, 0.49);
}

.sub-main-w3 input[type="submit"]:hover {
    background: #000;
    -webkit-transition: 0.5s all;
    -o-transition: 0.5s all;
    -moz-transition: 0.5s all;
    -ms-transition: 0.5s all;
    transition: 0.5s all;
}

/*--placeholder-color--*/

::-webkit-input-placeholder {
    color: #fff;
}

:-moz-placeholder {
    /* Firefox 18- */
    color: #fff;
}

::-moz-placeholder {
    /* Firefox 19+ */
    color: #fff;
}

:-ms-input-placeholder {
    color: #fff;
}

/*-- //placeholder-color --*/

/* Asmit's style */

@keyframes shake {
    0% {
        transform: translateX(0);
    }
    12.5% {
        transform: translateX(-6px) rotateY(-5deg)
    }
    37.5% {
        transform: translateX(5px) rotateY(4deg)
    }
    62.5% {
        transform: translateX(-3px) rotateY(-2deg)
    }
    87.5% {
        transform: translateX(2px) rotateY(1deg)
    }
    100% {
        transform: translateX(0)
    }
}

.shake {
    -webkit-animation: shake 400ms ease-in-out;
    /* Chrome, Safari, Opera */
    animation: shake 400ms ease-in-out;
}

.validifyError {
    border: 1px solid #e85546 !important;
}

.validifySuccess {
    border: 1px solid #2ecc71 !important;
}

.form-group-2 {
    text-align: center;
}

.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
    cursor: not-allowed;
    opacity: .65;
}

button[disabled],
html input[disabled] {
    cursor: default;
}

.btn-default {
    margin-top: 1em;
    color: #fff;
    background-color: #477427;
}

.btn {
    display: inline-block;
    padding: 6px 40px;
    margin-bottom: 0;
    font-size: 24px;
    text-align: center;
    cursor: pointer;
    border: 1px solid transparent;
    border-radius: 4px;
}
.btn hover {
 background-color:#000;
}

.hidden {
    display: none !important;
}

.alert-success {
    color: #3c763d;
    background-color: #dff0d8;
    border-color: #d6e9c6;
    padding: 18px;
    font-size: 15px;
    width: 100%;
    letter-spacing: 1px;
    text-align: center;
    margin-top: 20px;
}

/* //Amit's style */

/*-- copyright --*/

.footer {
    margin: 6vw .3vw 2vw;
}

.footer p {
    font-size: 14px;
    color: #fff;
    letter-spacing: 2px;
    text-align: center;
    line-height: 1.8;
}

.footer p a {
    color: #FFC107;
    -webkit-transition: 0.5s all;
    -o-transition: 0.5s all;
    -moz-transition: 0.5s all;
    -ms-transition: 0.5s all;
    transition: 0.5s all;
}

.footer p a:hover {
    color: #fff;
    -webkit-transition: 0.5s all;
    -o-transition: 0.5s all;
    -moz-transition: 0.5s all;
    -ms-transition: 0.5s all;
    transition: 0.5s all;
}

/*-- //copyright --*/

/*-- responsive-- */
@media(max-width: 1920px) {
    h1 {
        font-size: 3.5vw;
    }
}

@media(max-width: 1080px) {
    h1 {
        font-size: 4.5vw;
    }
}

@media(max-width: 800px) {
    h1 {
        font-size: 6vw;
    }
}

@media(max-width: 667px) {
    h1{
        margin: 5vw 1vw 7.5vw;
    }
    .footer {
        margin: 8vw .3vw 2vw;
    }
}

@media(max-width: 568px) {
    h1 {
        font-size: 2.5em;
        letter-spacing: 1px;
    }
}

@media(max-width: 480px) {
    h1 {
        font-size: 2.2em;
        margin: 7vw 1vw 9.5vw;
    }
    h2 {
        font-size: 27px;
    }
}

@media(max-width: 384px) {
    h1 {
        font-size: 2em;
        margin: 9vw 1vw 10.5vw;
        letter-spacing: 0px;
    }
    .footer p {
        letter-spacing: 1px;
    }
}

@media(max-width: 320px) {
    h1 {
        font-size: 1.8em;
        margin: 9vw 1vw 12.5vw;
    }
    h2 {
        font-size: 22px;
    }
    .footer {
        margin: 9vw .3vw 2vw;
    }
}

/*--//responsive--*/
 
</style>