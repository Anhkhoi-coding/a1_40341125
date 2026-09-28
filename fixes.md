1. Line 11: <img src="logo.png" alt="Neighbourhood Bake Sale logo">
    It was missing the alt attribut, the screen
    readers have nothing to read for the logo. FIX: <img src="logo.png" alt="Neighbourhood Bake Sale logo">

2. Line 24:   <font color="red">Saturday, October 18 — 10 a.m. to 2 p.m.</font>
    Deprecated presentational tags, because <center> and <font> are obsolete and invalid in HTML5 and has to be in CSS instead. Replace that line in HTML to : <p class="event-date">Saturday, October 18 — 10 a.m. to 2 p.m.</p>
    And add this in CSS after main: .event-date { text-align: center; color: #b00020; }

3. Line 27:  <h3>What we are selling</h3>
    Heading level skipped from <h1> to <h3>. Users navigate by heading level, and the missing <h2> breaks the page outline.
    FIX: change <h3> to <h2>