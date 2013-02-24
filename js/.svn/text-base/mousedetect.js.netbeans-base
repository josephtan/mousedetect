/* 
 * Mouse coordinates detection script. Yeap no jquery. O_o huzzah?
 * Works on IE7,IE8 and IE9 as well as modern browsers. Works on Android Chrome too.
 * Author: Joseph Tan
 */
var ieversion = new Number(RegExp.$1);
var userAgent = window.navigator.userAgent;

function ieDocLoad(){    
  document.write("<script id=__ie_onload defer src=javascript:void(0)><\/script>");
  var script = document.getElementById("__ie_onload");
  script.onreadystatechange = function() {
    if (this.readyState == "complete") {
      init(); // call the onload handler
    }
  };
    
}

if (/MSIE (\d+\.\d+);/.test(userAgent)){ 
   if (ieversion<=9){  
           ieDocLoad(init,false);
    }
}else{ 
  document.addEventListener("DOMContentLoaded", init, false);
}

function init(){
    var body = document.getElementsByTagName("body")[0];
    if (/MSIE (\d+\.\d+);/.test(userAgent)){ 
    if (ieversion<=9){  
        body.attachEvent("onclick", getMousePosition,false);
    }
    }else{
         body.addEventListener("mousedown", getMousePosition, false);
    }
    
}
function getMousePosition(e){        
        mouseX = new Number();
        mouseY = new Number();
        
        var body = document.getElementsByTagName("body")[0];
        
         if (e.mouseX != undefined && e.mouseY != undefined){
          mouseX = e.mouseX;
          mouseY = e.mouseY;
        }
         else 
        {
          mouseX = e.clientX + document.body.scrollLeft +
              document.documentElement.scrollLeft;
          mouseY = e.clientY + document.body.scrollTop +
              document.documentElement.scrollTop;
        }
        
        mouseX -= body.offsetLeft;
        mouseY -= body.offsetTop;
        alert("x:" + mouseX + " y:" + mouseY);    
        
}

