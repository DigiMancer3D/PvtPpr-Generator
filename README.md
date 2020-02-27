# PvtPpr-Generator
Pass inputs through nodejs to generate a paper type result for the user to publish their thoughts without needing more than their browser. Uses itty.bitty.site and the nodejs encoding for the output results. This generator can also run off itty.bitty.site technology.


The main feature being presented in this generator is passing links through the nodejs ittybittysite encoder because it uses the selector and selects <code><a></code> for the inofrmation to be encoded.
  
  First we bring the make a new variable with an empty inside:
     <code>  var adstuff = ''; </code>
       
  Next we add into the new variable the code directly being inserted into the output location:     
    <code>   adstuff += '< a type="button" align="right;" href="' + document.getElementById('adlink').value + '" target="_blank"; ><span id="adtext" > < sup >< sub > ' + document.getElementById('adtextin').value + ' < / sub>< / sup>< / span>< / a><span id="adtxt" style="font-size:8px" ></br>  < b id="adtxtbottom" >ad< / b></ span>  '; </code>  
   
   In the input of the new variable inline styling may be used but more standard styling should work as well if the output styling is located within the selctor section. 
   
   Now we can apply the new filled variable to the output location:
    <code>   document.getElementById('adhere').innerHTML = adstuff;      </code>
       
       
   Repeating these we can pass images, videos, buttons and maybe more:    
 <code>      var topimg = '';     topimg += '< img src="' + document.getElementById('imglink').value + '" value="Image Link" />';     document.getElementById('img1').innerHTML = topimg;     </code>
 
 <i>A neat trick with the image pass, is if the input value is not a link but just text, the image transfer will become invalid and will not display a broken-link image nor a giant empty box in the output's location.</i>
       
   
The nodejs passing for ittybittysite is as follows:   
    <code>   a = document.querySelector('a'); LZMA.compress(a.outerHTML, 9, function(r) {a.innerText = a.href = 'https://itty.bitty.site/#/?' + btoa(String.fromCharCode.apply(null, new Uint8Array(r)))});}  </code>
    
    
<h2>Why showcase this?</h2>
    This is a fun way to showcase more of what can be done with <a href="https://itty.bitty.site" target="_blank" >itty.bitty.site</a> and allowing anyone to build thier own news-like-paper without having what they write saved on servers.
    
 <h1>Working Version:</h1>
 <h3>&nbsp&nbsp&nbsp&nbspI have a working version running from pasting my codepen.io repo link into itty.bitty.site's encoder and running the generator through itty.bitty.site as an application.</br></br> The links are as follows:</br>
 <li>Short Link: <a href="https://3dd.in/ppgen" target="_blank">3dd.in/ppgen</a></li>
 </br></br>
  <li>Full Link: <a href="https://itty.bitty.site/#/data:text/html;charset=utf-8;bxze64,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" target="_blank">https://itty.bitty.site/#/data:text/html;charset=utf-8;bxze64,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</a></li></h3>
