[mdn button](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)

## 知识点

- form表单提交 注意button的type要赋值
- ajax + new FormData 手动提交file

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<form id="form" >
    <p>姓名：</p>
    <input type="text" name="stuName" value="wang"><br>
    <p>学号：</p>
    <input type="text" name="stuNo" value="1234"><br>
    <p>爱好：</p>
    <input type="text" name="hobby" value="play"><br>

    <p>选择文件</p>
    <input type="file" name="file"><br>
    <br>
    <button type="button" id="btn">提交</button>
</form>
<script>
    window.onload = function() {
        document.querySelector("#btn").onclick = function() {
            //创建xhr对象
            var xhr;
            if(window.XMLHttpRequest){
                xhr = new XMLHttpRequest();
            }else{
                xhr = new ActiveXObject('Microsoft.XMLHTTP');
            }
            //发送请求
            xhr.open('post','/form/data',true);
            var file = document.querySelector("form [name=file]").files[0];//获取文件

            var formData = new FormData();

            var stuName = document.querySelector("[name=stuName]").value;
            var stuNo = document.querySelector("[name=stuNo]").value;
            var hobby = document.querySelector("[name=hobby]").value;

            formData.append("file", file);
            formData.append("stuName",stuName);//添加学生的id
            formData.append("stuNo",stuNo);//添加学生的id
            formData.append("hobby",hobby);//添加学生的id


            xhr.send(formData);
            //同步接受响应
            if(xhr.readyState == 4){
                if(xhr.status == 200){
                    console.log(xhr.responseText)
                    //实际操作
                    result.innerHTML += xhr.responseText;
                }
            }
        }
    }
</script>
</body>
</html>

```
