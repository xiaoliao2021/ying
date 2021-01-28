<!DOCTYPE html>
<html>
    <head>
    	<meta charset="utf-8">
    	<title>菜鸟教程(runoob.com)</title>
    </head>
    <body>
        <textarea style="position: absolute;top: 0;left: 0;opacity: 0;z-index: -10;" id="input"></textarea>
        <script type="text/javascript">
        window.onload = myfun;
        function myfun(){
            var data = document.getElementsByClassName("CodeMirror");
            for(var i=0;i<data.length;i++){
                var parent = data[i].parentElement;
                var div = document.createElement("div");
                var span = document.createElement("span");
                div.setAttribute("class", "md-rawblock-tooltip md-rawblock-control");
                div.setAttribute("align", "right");
                div.setAttribute("contenteditable", "false");
                span.setAttribute("class", "md-rawblock-tooltip-btn md-rawblock-tooltip-ok-btn");
                span.style.cursor="pointer";
                span.innerText="复制"
                div.appendChild(span);
                parent.insertBefore(div,data[i])
                span.setAttribute("onclick", "myOnclick(this)");
            }
        }
        function myOnclick(data){
            var nextBrother = data.parentElement.nextElementSibling
            var data = nextBrother.getElementsByClassName("CodeMirror-code");
            console.log(data[0].innerText);
            var text = data[0].innerText;
            var input = document.getElementById("input");
            input.value = text;
            input.select();
            document.execCommand("copy");
            alert("复制成功");
        }
    </script>
    </body>
</html>
# 一键复制脚本测试

```shell
sudo apt-get install openssh-server
```

```c
printf("holle world\n");
```

```javascript
$(function() {
  if ($("#cnblogs_post_body").hasClass("cnblogs-markdown")){
      console.log(111);
    if ($("#post-date")[0]) {
        console.log(222)
      var pres = $("pre");
      if (pres.length) {
          console.log(333)
        pres.each(function() {
          var t = $(this)
            .children("code")
            .text();
          var btn = $('<span class="copy">复制</span>').attr(
            "data-clipboard-text",
            t
          );
          $(this).prepend(btn);
          var c = new ClipboardJS(btn[0]);
          c.on("success", function() {
            btn.addClass("copyed").text("复制成功");
          });
          c.on("error", function() {
            btn.text("复制失败");
          });
          btn.mouseleave(function() {
            btn.text("复制").removeClass("copyed");
          });
        });
      }
    }
  }
});
```





