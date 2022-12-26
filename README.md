# b4x20221226
B4X實驗: 用B4X產生網站篇-BANano和PHP 如何交互應用??
B4X實驗: 用B4X產生網站篇-BANano和PHP 如何交互應用??
參考資料:
https://www.b4x.com/android/forum/threads/banano-inline-php-server-code.101224/#content


1.WebServer挑選(JServer/UsbWebServer...其他)
UsbWebServer 
https://www.usbwebserver.net/webserver/

 


2.AppStart
BANano.PHP_NAME = "myapi.php"
BANano.PHPHost = "http://localhost"
BANano.PHPAddHeader("Access-Control-Allow-Origin: *")


----------------------------------------------------------
public Sub ButtonClicked(event As BANanoEvent)
   ' function name and params are Case Sensitive!
   Dim res As String = BANano.CallInlinePHPWait("SayHello", CreateMap("Name": "BANano"))
   log(res)
End Sub

' a simple php method which says hello!
#if PHP
function SayHello($Name) {
   $ret = Array("answer" => "Hello " .$Name. "!");
   echo json_encode($ret);  
}
#End If



3.t41




9.結語:到底用b4x產生網站.會不會更加簡單方便???
這點.因我還在學習BaNano.我還沒辦法給出答案
未來幾個月.我將會以一個簡單哦 line購物車為主題.做出一個網頁網站
這樣才能評估出BaNano它的價值

 







