<p>div</p>
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
