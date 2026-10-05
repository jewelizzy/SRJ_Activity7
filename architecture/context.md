<title>SRJ Student Ride Booking - System Context</title>

<style>
body {
    margin: 0;
    padding: 20px;
    font-family: Arial, Helvetica, sans-serif;
    background: white;
    color: #222;
}

h1 {
    text-align: center;
    margin-bottom: 25px;
}

.diagram {
    width: 1400px;
    margin: auto;
}

.box {
    stroke: #555;
    stroke-width: 2;
}

.person {
    fill: #075394;
}

.system {
    fill: #1976c5;
}

.external {
    fill: #888;
}

.label {
    fill: white;
    text-anchor: middle;
    font-weight: bold;
}

.small {
    fill: white;
    text-anchor: middle;
    font-size: 14px;
}

.line {
    stroke: #555;
    stroke-width: 2;
    fill: none;
    marker-end: url(#arrow);
}

.protocol {
    font-size: 13px;
    fill: #333;
}
</style>

<h1>Diagram 1 - C4 System Context: SRJ Student Ride Booking (MVP)</h1>

<div class="diagram">

<svg width="1400" height="850" xmlns="http://www.w3.org/2000/svg">

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

<!-- Student -->
<rect x="80" y="80" width="250" height="110"
      rx="15" class="box person"/>

<text x="205" y="115" class="label">Student</text>
<text x="205" y="140" class="small">[Person]</text>
<text x="205" y="165" class="small">
    Off-campus SORSU student
</text>

<!-- Driver -->
<rect x="575" y="80" width="250" height="110"
      rx="15" class="box person"/>

<text x="700" y="115" class="label">Tricycle Driver</text>
<text x="700" y="140" class="small">[Person]</text>
<text x="700" y="165" class="small">
    Local driver who accepts
</text>

<!-- Coordinator -->
<rect x="1070" y="80" width="250" height="110"
      rx="15" class="box person"/>

<text x="1195" y="115" class="label">Coordinator</text>
<text x="1195" y="140" class="small">[Person]</text>
<text x="1195" y="165" class="small">
    Manages drivers and metrics
</text>

<!-- Main System -->
<rect x="500" y="330" width="400" height="140"
      rx="15" class="box system"/>

<text x="700" y="370" class="label">
    SRJ Ride Booking
</text>

<text x="700" y="400" class="small">
    [Software System]
</text>

<text x="700" y="430" class="small">
    Web app for booking rides to campus
</text>

<!-- Maps -->
<rect x="350" y="610" width="250" height="110"
      rx="15" class="box external"/>

<text x="475" y="645" class="label">
    Maps Provider
</text>

<text x="475" y="675" class="small">
    [External System]
</text>

<text x="475" y="700" class="small">
    Distance and ETA
</text>

<!-- Notification -->
<rect x="800" y="610" width="250" height="110"
      rx="15" class="box external"/>

<text x="925" y="645" class="label">
    Notification Provider
</text>

<text x="925" y="675" class="small">
    [External System]
</text>

<text x="925" y="700" class="small">
    Email or SMS alerts
</text>

<!-- Connections -->

<path d="M205 190 L570 330" class="line"/>

<text x="350" y="250" class="protocol">
    Books a ride, cancels it
</text>

<text x="350" y="268" class="protocol">
    and follows trip [HTTPS]
</text>

<path d="M700 190 L700 330" class="line"/>

<text x="720" y="255" class="protocol">
    Sets availability,
</text>

<text x="720" y="273" class="protocol">
    accepts rides [HTTPS]
</text>

<path d="M1195 190 L830 330" class="line"/>

<text x="1000" y="250" class="protocol">
    Manages drivers and
</text>

<text x="1000" y="268" class="protocol">
    reviews metrics [HTTPS]
</text>

<path d="M590 470 L475 610" class="line"/>

<text x="400" y="535" class="protocol">
    Asks for distance and ETA
</text>

<text x="400" y="553" class="protocol">
    [HTTPS/JSON]
</text>

<path d="M810 470 L925 610" class="line"/>

<text x="850" y="535" class="protocol">
    Asks it to alert users
</text>

<text x="850" y="553" class="protocol">
    [HTTPS/JSON]
</text>

</svg>

</div>
