# Math-Box

from flask import Flask, render_template, request, url_for

app = Flask(__name__)
# d = 0
# s = 3+5
# a = int(input())
# if a == s:
#     d += 1
#@app.route('/')
@app.route('/home')
def index():
    return render_template('home.html')


@app.route('/about')
def about():
    return render_template('about.html')


@app.route('/user/<string:name>/<int:id>')
def user(name,id):
    return "Данные пользователя - " + name + "возрост - " + str(id)


if __name__ == '__main__':
    app.run(debug=True)


#HTML

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <link rel="stylesheet" href="{{url_for('static', filename='style.css')}}">
    <link rel="stylesheet" href="style.css">
</head>
<body>
<h2>Math Box</h2>
    <div class="ser">
    </div>

    <img src="static/images/Math_box.jpg" height="150">
    <hr>
    <ul class="nav nav-pills flex-column mb-auto">
      <li class="nav-item">
        <a href="/home" class="nav-link active" aria-current="page">
          <svg class="bi pe-none me-2" width="16" height="16"><use xlink:href="#home"></use></svg>
          Главная
        </a>
      </li>
      <li>
        <a href="/about" class="nav-link text-white">
          <svg class="bi pe-none me-2" width="16" height="16"><use xlink:href="#grid"></use></svg>
          О нас
        </a>
      </li>
      <li>
        <a href="/index" class="nav-link text-white">
          <svg class="bi pe-none me-2" width="16" height="16"><use xlink:href="#people-circle"></use></svg>
          Предложения
        </a>
      </li>
    </ul>

    <h1>Добро пожаловать!</h1>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <h1> Про нас!</h1>
</body>
</html>

#test

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<h1> {{qw}}</h1>
<h2> 4 * 4 =</h2>
</body>
</html>
