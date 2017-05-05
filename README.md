<!DOCTYPE html>
<html lang="zh_cn">
<head>
	<meta charset="UTF-8">
	<title>register</title>
	<style type='text/css'>

	  body
	  {        
              font-family: 楷书;
              line-height:1.8;   
	  }
      *{
       	 margin:0;
       	 padding:0;
       } 
       /*引入矢量图标*/
       @font-face{
                 font-family: 'iconfont';
                 src: url('font/iconfont.eot');
                 src: url('font/iconfont.eot?#iefix') format('embedded-opentype'),
                 url('font/iconfont.woff') format('woff'),
                 url('font/iconfont.ttf') format('truetype'),
                 url('font/iconfont.svg#iconfont') format('svg');
       }
        /*给JS的提示加样式*/
      .msg
      {
      	color:gray;
        font-size:10px;
      }

      .msg2
      {
      	color:#ff3333;
      	background-color: #ffcc99;
      	border: 1px  solid gray; 
        line-height: 1.3;
      }
      /*矢量飞机*/
     .icon-feiji
      { 
          font-family:"iconfont";
          font-size:16px;
          font-style:normal;
          -webkit-font-smoothing: antialiased;
          -webkit-text-stroke-width: 0.2px;
          -moz-osx-font-smoothing: grayscale;
      }
      .icon-feiji:before
      {
             content:"\e655";       
          
      }
      /*注册板块*/
	  .login_main_mid
      {  
      	
          font-size:16px;
       	  margin:8% auto;   	 
       	  width:60%;       	
          border:1px solid gray;	  
      }
       /*注册内容的样式*/
       .login_main_content
	   {  
	     padding: 5px 100px;
		 position: relative;
	   }
	   /*注册内容每行的板块*/
       .login_main_content dl
       {
         	clear:left;
			margin:10px auto;
       }
        /*注册内容的要求*/
       .login_main_content dl dt
       {
         margin: 10px 8px;
      	 width:100px;
         float:left;
         text-align: right;
       }
       /*统一各控件的格式*/
      .login_main_content dl dd
       {
         margin:10px 10px;	    
         float:left;
       }
       /*此处给选取性别男女样式分开*/
       .login_main_content dl .blockStyle input
      {
           background-color:#CCFFCC;
           display:block;
           height:20px;         
      	   width:200px;
       }
       /*给提交按钮设置格式*/
	   .login_main_content dl  .btn1
	   {
	       position:absolute;
           bottom:15px; 
		   left:400px;	 
	   }
        /*给提示内容固定格式*/
       .login_main_content dl span
        {
        	margin:10px 0 0;
        	float: left;
        }
       /*注册标题的格式*/
     .login_main_title
      {
         font-size: 24px;
         font-weight: bold;
         font-family: 华文新魏;
         margin:10px  auto 2px;
         text-align: center;
      }
	</style>
	<script type="text/javascript">
	 
	 //邮箱的交互式相应
       function  focusEmail()
       {
          var  obj=document.getElementById("emailMSG");
          obj.innerHTML="这个账号是关于邮箱的，请保管好";
          obj.className="msg";
       }
       function blurEmail()
       {
           var Email1=document.getElementById("email").value;
           var EmailMSG=document.getElementById("emailMSG");
           if(Email1=="")
           {
                 EmailMSG.innerHTML="email地址不能为空";
                 EmailMSG.className="msg2";
                 return false;
           }
           else if(Email1.indexOf("@")==-1)
           {
 			    EmailMSG.innerHTML="email地址格式不正确";
                EmailMSG.className="msg2";
                return false;
           }
           else
           {
           	   EmailMSG.className="icon icon-feiji";
           	   EmailMSG.innerHTML="";
              
           	   return  true;
           }
      }
      //昵称的交互式相应
      function  focusName()
      {
         var  obj1=document.getElementById("NameMsg");
          obj1.innerHTML="昵称的长度必须在2个字或2个字以上";
          obj1.className="msg";
      }
     function blurName()
     {
           var Vname=document.getElementById("Myname").value;
           var VNameMSG=document.getElementById("NameMsg");
           if(Vname=="")
           {
                 VNameMSG.innerHTML="昵称不能为空";
                 VNameMSG.className="msg2";
                 return false;
           }
           else if(Vname.length<2)
           {
 			    VNameMSG.innerHTML="昵称的设置格式不正确";
                VNameMSG.className="msg2";
                return false;
           }
           else
           {
           	  VNameMSG.className="icon icon-feiji";
           	  VNameMSG.innerHTML="";  
           	   return  true;
           }
      }
     //获取密码的交互式相应
      function  focuspwd()
      {
         var  obj=document.getElementById("pwdMsg");
          obj.innerHTML="密码设置在6字以上，请输入密码并保管好";
          obj.className="msg";
      }
     function blurpwd()
     {
           var Vpwd=document.getElementById("Pwd").value;
           var VpwdMSG=document.getElementById("pwdMsg");
           if(Vpwd=="")
           {
                 VpwdMSG.innerHTML="密码不能为空";
                 VpwdMSG.className="msg2";
                 return false;
           }
           else if(Vpwd.length<6)
           {
 			    VpwdMSG.innerHTML="密码的设置格式不正确";
                VpwdMSG.className="msg2";
                return false;
           }
           else
           {
           	  VpwdMSG.className="icon icon-feiji";
           	  VpwdMSG.innerHTML="";  
           	   return  true;
           }
      }

     //再次获取密码的交互式相应
     function  focusrepwd()
      {
            var  obj2=document.getElementById("repwdMsg");
            obj2.innerHTML="密码确认与上次相同";
            obj2.className="msg";
      }
     function blurrepwd()
     {
     	   var pwd=document.getElementById("Pwd").value;
           var repwd=document.getElementById("rePwd").value;
           var repwdMSG=document.getElementById("repwdMsg");
           if(repwd=="")
           {
                 repwdMSG.innerHTML="密码为空,输入错误";
                 repwdMSG.className="msg2";
                 return false;
           }
           else if(repwd!= pwd)
           {
 			    repwdMSG.innerHTML="两次密码输入不一致";
                repwdMSG.className="msg2";
                return false;
           }
           else
           {
           	  repwdMSG.className="icon icon-feiji";
           	  repwdMSG.innerHTML="";  
           	   return  true;
           }
      }

      //检测性别
      function checksex()
      {
           var vsex  =document.getElementsByName("sex");

           var sexMsg=document.getElementById("radioMsg");
           if(vsex[0].checked==true||vsex[1].checked==true)
           {
           	 	sexMsg.className="icon icon-feiji";
           	    sexMsg.innerHTML="";  
           	    alert("此处运行吗");
            	return ture;
            }
           else 
           {
               sexMsg.innerHTML="请选择性别";
               sexMsg.className="msg2";
                return false;
           }
     }

       //总的检测函数
	   function  checkForm()
	   {
	    if( blurEmail()==false||blurpwd()==false||blurName()==false||blurrepwd()==false|| 
	       checksex()==false) 
	 	      return false;
	      else 
	     { 
	 	   return ture;
	 	 }
	    }
	</script>
 </head> 

 <body>
 <!--登陆表单开始-->

	   <div class='login_main_mid'>

	        <div  class="login_main_title">欢迎来到注册界面! </div>

           <div  class="login_main_content">
		 
		   <form action="login.php" method="post" id="Myfrom"  onsubmit="return checkForm()">
           <!--Email地址-->
             <dl>
             <dt>Email地址:</dt>
             <dd class="blockStyle">
               <input type="text"  ID="email"  onfocus= "focusEmail()" 
		         onblur= "blurEmail()"/>  
             </dd>
                <span Id="emailMSG"></span>
             </dl>
        <!--设置昵称-->
            <dl>
              <dt>设置昵称:</dt>
               <dd class="blockStyle">
                <input type="text" name="Myname" ID="Myname"  onfocus= "focusName()" 
                onblur= "blurName()"  maxlength="20">
               </dd>
                <span  Id="NameMsg"></span>
            </dl>

        <!--设置密码-->
            <dl>
            <dt>请设置密码:</dt>
            <dd class="blockStyle">
            <input type="password" name="pwd_resister" ID="Pwd" maxlength="20" onfocus= "focuspwd()"   onblur= "blurpwd()" />
             </dd>
             <span  Id="pwdMsg"></span>
            </dl>
       <!--再次输入密码-->
            <dl>
            <dt>再次输入密码:</dt>
            <dd class="blockStyle">
              <input type="password" name="repwd_reister"  ID="rePwd" maxlength="20" onfocus= "focusrepwd()" onblur= "blurrepwd()"/>
              </dd>
              <span  Id="repwdMsg">  </span>
            </dl>
     <!--性别选择-->
             <dl>
             <dt>性别:</dt>
             <dd > 
                 <input type="radio" name="sex" value="男"/><lable> 男</lable><dd/>
		     <dd> 
		        <input type="radio"   name="sex" value="女"/><lable> 女</lable> </dd>

               <span id="radioMsg"> </span>
             </dl>
      <!--提交按钮-->
              <dl>
		          <br/>
		          <span class="btn1">
                  <input type="submit"   name="submit"  value="提交注册" />
                 </span>
             </dl>
        
         </form>
        </div>

	  </div>

<!--登录表单开始-->
  </body>

</html>
