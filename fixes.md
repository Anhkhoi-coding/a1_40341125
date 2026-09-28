1. Line 11: <img src="logo.png" alt="Neighbourhood Bake Sale logo">
    It was missing the alt attribut, the screen
    readers have nothing to read for the logo. FIX: <img src="logo.png" alt="Neighbourhood Bake Sale logo">

2. Line 24:   <font color="red">Saturday, October 18 — 10 a.m. to 2 p.m.</font>
    Deprecated presentational tags, because <center> and <font> are obsolete and invalid in HTML5 and has to be in CSS instead. Replace that line in HTML to : <p class="event-date">Saturday, October 18 — 10 a.m. to 2 p.m.</p>
    And add this in CSS after main: .event-date { text-align: center; color: #b00020; }

3. Line 27:  <h3>What we are selling</h3>
    Heading level skipped from <h1> to <h3>. Users navigate by heading level, and the missing <h2> breaks the page outline.
    FIX: change <h3> to <h2>

4. Line 28: <div>All items are homemade and nut-free.</div>
    <div> cannot be a direct child of <ul> (invalid in HTML). <ul> element can only contain <li> elements.
    FIX: I moved the whole line above the <ul> and changed <div> to <p>: <p>All items are homemade and nut-free.</p>

5. Line 37: <tr><td>Item</td><td>Price</td></tr>
    Headers of a cell (Item and Price) is written as <td> which is an accessibility mistake. Screen readers only treat a cell as a column header if its a <th>.
    FIX: <tr><th scope="col">Item</th><th scope="col">Price</th></tr>

6. Line 43-44: 
    <label>Your name</label>
    <input type="text" name="name">
    The label isn't linked to the input and is an accessibility mistake. Missing for/id pair, cannot distinguish which label belongs to which input.
    FIX: 
    <label for="resname">Your name</label>
    <input type="text" id="resname" name="name">

7. Line 45: <button>Reserve</button>
    The input and button aren't inside a <form>. without a form, the Reserve button doesnt do anything and the input's name is never submitted.
    FIX: 
    <form action="#" method="post"></form>
      <label for="resname">Your name</label>
      <input type="text" id="resname" name="name">
      <button type="submit">Reserve</button>
    </form>

8. Lines 22 and 48: <div id="main">
    the same id is used twice (invalid HTML). an id must be unique on the page and duplicates are invalid.
    FIX: <div class="main">
    in CSS: change #main to .main

9. Line 10, 15 and 54: <div id="header">, <div id="nav">, <div id="footer">
    Generic <div> is not a good practice where semetic elements belong. <header>, <nav> and <footer> screen readers jump between page regions.
    FIX: <header id="header">, <nav id="nav">, <footer id="footer">

----------CSS--------- 
10. Line 14: .manu {}
    CSS bug, misspelled. HTML uses class="menu", so .manu matches nothing and the nav never gets its button styling.
    FIX: .menu{}

11. Line 23: width: 300;
    Error because there is no unit. Missing the pixel justification (px)
    FIX: width: 300px;

12. Line 22 and 32: #main {} and td{}
    Error of ponctuation. #main becomes .main and td becomes th, td so the header cells keep the same padding (related to error 5)
