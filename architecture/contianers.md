<title>SRJ Student Ride Booking - C4 Container</title>

<style>
body {
    margin: 0;
    padding: 20px;
    font-family: Arial, Helvetica, sans-serif;
}

h1 {
    text-align: center;
}

svg {
    display: block;
    margin: auto;
}

.person {
    fill: #075394;
    stroke: #444;
    stroke-width: 2;
}

.container {
    fill: #438fd0;
    stroke: #444;
    stroke-width: 2;
}

.external {
    fill: #888;
    stroke: #444;
    stroke-width: 2;
}

.database {
    fill: #2375b8;
    stroke: #444;
    stroke-width: 2;
}

.system {
    fill: none;
    stroke: #777;
    stroke-width: 2;
    stroke-dasharray: 8 6;
}

.text {
    fill: white;
    text-anchor: middle;
}

.dark {
    fill: #222;
}

.line {
    stroke: #555;
    stroke-width: 2;
    fill: none;
    marker-end: url(#arrow);
}
</style>

<h1>Diagram 2 - C4 Container: SRJ Student Ride Booking (MVP)</h1>

<svg width="1400" height="900"
     xmlns="http://www.w3.org/2000/svg">

<defs>
<marker id="arrow"
        markerWidth="10"
        markerHeight="10"
        refX="9"
        refY="3"
        orient="auto">
<path d="M0,0 L10,3 L0,6 Z" fill="#555"/>
</marker>
</defs>

<!-- People -->

<rect x="80" y="60" width="230" height="100"
      rx="15" class="person"/>

<text x="195" y="100" class="text">Student</text>
<text x="195" y="125" class="text">[Person]</text>
<text x="195" y="145" class="text">Books rides</text>

<rect x="585" y="60" width="230" height="100"
      rx="15" class="person"/>

<text x="700" y="100" class="text">Tricycle Driver</text>
<text x="700" y="125" class="text">[Person]</text>
<text x="700" y="145" class="text">Accepts rides</text>

<rect x="1090" y="60" width="230" height="100"
      rx="15" class="person"/>

<text x="1205" y="100" class="text">Coordinator</text>
<text x="1205" y="125" class="text">[Person]</text>
<text x="1205" y="145" class="text">Reviews metrics</text>

<!-- System Boundary -->

<rect x="300" y="210" width="800" height="500"
      class="system"/>

<text x="700" y="235"
      font-weight="bold"
      text-anchor="middle">
SRJ Ride Booking
</text>

<!-- UI -->

<rect x="480" y="270" width="440" height="120"
      rx="15" class="container"/>

<text x="700" y="305" class="text"
      font-weight="bold">
Web App (UI)
</text>

<text x="700" y="330" class="text">
Container: Next.js / React in browser
</text>

<text x="700" y="355" class="text">
Booking, driver and coordinator pages
</text>

<!-- API -->

<rect x="480" y="470" width="440" height="120"
      rx="15" class="container"/>

<text x="700" y="505" class="text"
      font-weight="bold">
API
</text>

<text x="700" y="530" class="text">
Next.js route handlers on Node.js
</text>

<text x="700" y="555" class="text">
Booking rules and trip status
</text>

<!-- Database -->

<ellipse cx="400" cy="790"
         rx="160" ry="65"
         class="database"/>

<text x="400" y="790"
      class="text"
      font-weight="bold">
Database
</text>

<text x="400" y="815"
      class="text">
PostgreSQL
</text>

<!-- External systems -->

<rect x="1000" y="470" width="250" height="100"
      rx="15" class="external"/>

<text x="1125" y="510" class="text">
Maps Provider
</text>

<text x="1125" y="540" class="text">
Distance and ETA
</text>

<rect x="1000" y="610" width="250" height="100"
      rx="15" class="external"/>

<text x="1125" y="650" class="text">
Notification Provider
</text>

<text x="1125" y="680" class="text">
Email or SMS alerts
</text>

<!-- Connections -->

<path d="M195 160 L480 310" class="line"/>
<path d="M700 160 L700 270" class="line"/>
<path d="M1205 160 L920 310" class="line"/>

<path d="M700 390 L700 470" class="line"/>

<path d="M480 530 L400 725" class="line"/>

<path d="M920 530 L1000 520" class="line"/>
<path d="M920 560 L1000 660" class="line"/>

</svg>
