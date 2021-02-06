# htmlify

## This repository is full of bad decisions. I'm leaving it here as a reminder of what not to do.


An ultra-basic, human-friendly templating system for doing CGI with Python for less 😕 and more 🎉

htmlify is powerful enough to drive small web projects, while lightweight enough that you don't feel like you're learning a whole new language. Here's how it works:

<table>
  <tr>
    <th><pre>example.cgi</pre></th>
    <th><pre>templates/exampleTemplate.html</pre></th> 
  </tr>
  <tr>
    <td><pre>exampleTemplate = Template("exampleTemplate")
    
exampleTemplate.getHTML(
    favFood="spam", 
    favDrink="carrot juice",
    magicNumberOne=17, 
    magicNumberTwo=30
)</pre></td>
    <td><pre><p>I like to eat \_%(favFood)
I like to drink \_%(favDrink)
2875 plus 3495 is equal to \_%[2875+3495]
Concatenating "hello" and " there" gives \_%["hello" + " there"]
Adding the magic numbers gives \_%[\_%(magicNumberOne)+\_%(magicNumberTwo)]</pre></td> 
  </tr>
</table>

The result:

<table>
  <tr>
    <td>http://localhost/example.cgi</td>
  </tr>
  <tr>
  <td>
I like to eat spam<br>
I like to drink carrot juice)<br>
2875 plus 3495 is equal to 6370<br>
Concatenating "hello" and " there" gives hello there

Adding the magic numbers gives 47
  </td>
  </tr>
</table>
