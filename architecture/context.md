<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>SRJ Student Ride Booking - System Context</title>

    <style>

        body {
            margin: 0;
            padding: 20px;
            font-family: Arial, Helvetica, sans-serif;
            background-color: white;
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

        svg {
            width: 100%;
            height: auto;
            border: 1px solid #cccccc;
            background-color: white;
        }

        /* SYSTEM */

        .system {
            fill: #ffffff;
            stroke: #245b8f;
            stroke-width: 3;
        }

        /* ACTORS */

        .actor {
            fill: #eef5fb;
            stroke: #245b8f;
            stroke-width: 2;
        }

        /* EXTERNAL SYSTEMS */

        .external {
            fill: #eeeeee;
            stroke: #777777;
            stroke-width: 2;
        }

        /* CONNECTIONS */

        .connection {
            stroke: #35566f;
            stroke-width: 2;
            fill: none;
        }

        /* TEXT */

        .title {
            font-size: 26px;
            font-weight: bold;
            text-anchor: middle;
        }

        .name {
            font-size: 19px;
            font-weight: bold;
            text-anchor: middle;
        }

        .description {
            font-size: 15px;
            text-anchor: middle;
        }

        .protocol {
            font-size: 13px;
            text-anchor: middle;
            fill: #555;
        }

    </style>

</head>

<body>

<div class="diagram">

    <h1>
        SRJ Student Ride Booking
        <br>
        C4 System Context Diagram
    </h1>

    <svg viewBox="0 0 1400 850">

        <!-- ================================================= -->
        <!-- TITLE -->
        <!-- ================================================= -->

        <text
            x="700"
            y="45"
            class="title">
            SRJ Student Ride Booking System
        </text>


        <!-- ================================================= -->
        <!-- STUDENT -->
        <!-- ================================================= -->

        <rect
            x="70"
            y="150"
            width="270"
            height="120"
            rx="15"
            class="actor">
        </rect>

        <text
            x="205"
            y="185"
            class="name">
            Student
        </text>

        <text
            x="205"
            y="215"
            class="description">
            SORSU student
        </text>

        <text
            x="205"
            y="240"
            class="description">
            Books and follows rides
        </text>


        <!-- ================================================= -->
        <!-- SRJ SYSTEM -->
        <!-- ================================================= -->

        <rect
            x="565"
            y="135"
            width="270"
            height="150"
            rx="15"
            class="system">
        </rect>

        <text
            x="700"
            y="175"
            class="name">
            SRJ Ride Booking
        </text>

        <text
            x="700"
            y="210"
            class="description">
            Student Ride Booking
        </text>

        <text
            x="700"
            y="235"
            class="description">
            Web Application
        </text>

        <text
            x="700"
            y="260"
            class="description">
            Booking + Live Updates
        </text>


        <!-- ================================================= -->
        <!-- DRIVER -->
        <!-- ================================================= -->

        <rect
            x="1060"
            y="150"
            width="270"
            height="120"
            rx="15"
            class="actor">
        </rect>

        <text
            x="1195"
            y="185"
            class="name">
            Tricycle Driver
        </text>

        <text
            x="1195"
            y="215"
            class="description">
            Accepts bookings
        </text>

        <text
            x="1195"
            y="240"
            class="description">
            Updates trip status
        </text>


        <!-- ================================================= -->
        <!-- COORDINATOR / ADMIN -->
        <!-- ================================================= -->

        <rect
            x="565"
            y="390"
            width="270"
            height="120"
            rx="15"
            class="actor">
        </rect>

        <text
            x="700"
            y="425"
            class="name">
            Coordinator / Admin
        </text>

        <text
            x="700"
            y="455"
            class="description">
            Manages drivers
        </text>

        <text
            x="700"
            y="480"
            class="description">
            Reviews usage metrics
        </text>


        <!-- ================================================= -->
        <!-- MAPS PROVIDER -->
        <!-- ================================================= -->

        <rect
            x="180"
            y="650"
            width="270"
            height="110"
            rx="15"
            class="external">
        </rect>

        <text
            x="315"
            y="685"
            class="name">
            Maps Provider
        </text>

        <text
            x="315"
            y="715"
            class="description">
            Distance calculation
        </text>

        <text
            x="315"
            y="740"
            class="description">
            ETA information
        </text>


        <!-- ================================================= -->
        <!-- NOTIFICATION PROVIDER -->
        <!-- ================================================= -->

        <rect
            x="950"
            y="650"
            width="270"
            height="110"
            rx="15"
            class="external">
        </rect>

        <text
            x="1085"
            y="685"
            class="name">
            Notification Provider
        </text>

        <text
            x="1085"
            y="715"
            class="description">
            Email / SMS
        </text>

        <text
            x="1085"
            y="740"
            class="description">
            Ride notifications
        </text>


        <!-- ================================================= -->
        <!-- STUDENT → SYSTEM -->
        <!-- ================================================= -->

        <line
            x1="340"
            y1="210"
            x2="565"
            y2="210"
            class="connection">
        </line>

        <text
            x="450"
            y="195"
            class="protocol">
            HTTPS
        </text>


        <!-- ================================================= -->
        <!-- DRIVER → SYSTEM -->
        <!-- ================================================= -->

        <line
            x1="1060"
            y1="210"
            x2="835"
            y2="210"
            class="connection">
        </line>

        <text
            x="950"
            y="195"
            class="protocol">
            HTTPS
        </text>


        <!-- ================================================= -->
        <!-- SYSTEM → COORDINATOR -->
        <!-- ================================================= -->

        <line
            x1="700"
            y1="285"
            x2="700"
            y2="390"
            class="connection">
        </line>

        <text
            x="735"
            y="345"
            class="protocol">
            HTTPS
        </text>


        <!-- ================================================= -->
        <!-- SYSTEM → MAPS -->
        <!-- ================================================= -->

        <line
            x1="565"
            y1="470"
            x2="450"
            y2="650"
            class="connection">
        </line>

        <text
            x="480"
            y="570"
            class="protocol">
            HTTPS / JSON
        </text>


        <!-- ================================================= -->
        <!-- SYSTEM → NOTIFICATION -->
        <!-- ================================================= -->

        <line
            x1="835"
            y1="470"
            x2="950"
            y2="650"
            class="connection">
        </line>

        <text
            x="900"
            y="570"
            class="protocol">
            HTTPS / JSON
        </text>


        <!-- ================================================= -->
        <!-- LEGEND -->
        <!-- ================================================= -->

        <rect
            x="500"
            y="600"
            width="400"
            height="80"
            fill="#f7f7f7"
            stroke="#999"
            stroke-width="1">
        </rect>

        <text
            x="700"
            y="625"
            class="name">
            System Context
        </text>

        <text
            x="700"
            y="650"
            class="description">
            People interact with SRJ;
            external providers support
        </text>

    </svg>

</div>

</body>

</html>
