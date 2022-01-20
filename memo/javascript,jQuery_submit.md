# 자바스크립트 jQuery submit
### 자바스크립트 form tag 사용
[자바스크립트(Javascript) form 의 submit (전송)을 자바스크립트로 실행하는 방법](https://mainia.tistory.com/3850)
```html
<form action="action.jsp" id="frm">
	<input type="hidden" name="x" id="x" value="0">
</form>
```

```javascript
var x = 10

document.getElementById('x').value = x;
document.getElementById('frm').submit();
```

server.py
```python
@app.route('/url', methods=['GET', 'POST'])
def angle_detail():
    try:
        print(request.method)
        if request.method == 'POST':
            check = request.form['x']
```

### 자바스크립트 form tag 미사용
[javascript XMLHttpRequest를 사용하여 POST 데이터 보내기 - 리뷰나라](http://daplus.net/javascript-xmlhttprequest%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-post-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EB%82%B4%EA%B8%B0/)
```javascript
var frm = new formData();
frm.append("x", 10);

var xhr = new XMLHttpRequest();
xhr.open("POST", "/url", true);
xhr.send(frm);
```


### jQuery form tag 사용
```html
<form action="/url" method="post" id="frm">
  <input type="hidden" name="x" id="x" value="0">
</form>
```

```javascript
var x = 10;
$('#x').val(x);
$('#frm').submit();
```

server.py
```python
@app.route('/url', methods=['GET', 'POST'])
def url():
    try:
        print(request.method)
        if request.method == 'POST':
            check = request.form['x']
```

### jQuery form tag 미사용
