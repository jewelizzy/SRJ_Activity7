<mxfile host="app.diagrams.net">
  <diagram name="Page-1" id="BRbE-pgdBSSTi809ZW9T">
    <mxGraphModel dx="852" dy="476" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <UserObject label="" mermaidData="{&#xa;  &quot;data&quot;: &quot;flowchart TB\n\n    Student[\&quot;Student&lt;br/&gt;Person&lt;br/&gt;Off-campus SORSU student who needs a ride to school\&quot;]\n\n    Driver[\&quot;Tricycle Driver&lt;br/&gt;Person&lt;br/&gt;Local driver who accepts student bookings\&quot;]\n\n    Coordinator[\&quot;Coordinator&lt;br/&gt;Person&lt;br/&gt;Manages drivers and reviews usage metrics\&quot;]\n\n    SRJ[\&quot;SRJ Ride Booking&lt;br/&gt;Software System&lt;br/&gt;Web app for booking rides to campus with live trip updates\&quot;]\n\n    Maps[\&quot;Maps Provider&lt;br/&gt;External System&lt;br/&gt;Converts places to coordinates and returns distance and ETA\&quot;]\n\n    Notify[\&quot;Notification Provider&lt;br/&gt;External System&lt;br/&gt;Delivers email or SMS alerts about booking changes\&quot;]\n\n    Student --&gt;|\&quot;Books a ride, cancels it, and follows the ride&lt;br/&gt;HTTPS\&quot;| SRJ\n    Driver --&gt;|\&quot;Sets availability, accepts rides,&lt;br/&gt;and updates trip status&lt;br/&gt;HTTPS\&quot;| SRJ\n    Coordinator --&gt;|\&quot;Manages drivers and reviews&lt;br/&gt;booking metrics&lt;br/&gt;HTTPS\&quot;| SRJ\n\n    SRJ --&gt;|\&quot;Asks for distance and ETA of a trip&lt;br/&gt;HTTPS / JSON\&quot;| Maps\n    SRJ --&gt;|\&quot;Asks to alert users about booking changes&lt;br/&gt;HTTPS / JSON\&quot;| Notify\n```&quot;,&#xa;  &quot;config&quot;: null,&#xa;  &quot;version&quot;: &quot;12&quot;&#xa;}" id="r17lKq7YGrd7BqiICL2F-1">
          <mxCell connectable="0" parent="1" style="group;transparentBounds=1;editIcon=1;lockedGroup=0;groupPadding=10 79 114 90;" vertex="1">
            <mxGeometry as="geometry" />
          </mxCell>
        </UserObject>
        <UserObject label="Student&#xa;Person&#xa;Off-campus SORSU student who needs a ride to school" mermaidId="n:Student" mermaidBaseStyle="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;" mermaidBaseValue="Student&#xa;Person&#xa;Off-campus SORSU student who needs a ride to school" id="r17lKq7YGrd7BqiICL2F-2">
          <mxCell parent="r17lKq7YGrd7BqiICL2F-1" style="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;labelWidth=120;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" vertex="1">
            <mxGeometry height="150" width="152" x="100" y="40" as="geometry" />
          </mxCell>
        </UserObject>
        <UserObject label="Tricycle Driver&#xa;Person&#xa;Local driver who accepts student bookings" mermaidId="n:Driver" mermaidBaseStyle="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;" mermaidBaseValue="Tricycle Driver&#xa;Person&#xa;Local driver who accepts student bookings" id="r17lKq7YGrd7BqiICL2F-3">
          <mxCell parent="r17lKq7YGrd7BqiICL2F-1" style="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;labelWidth=120;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" vertex="1">
            <mxGeometry height="129" width="152" x="386" y="61" as="geometry" />
          </mxCell>
        </UserObject>
        <UserObject label="Coordinator&#xa;Person&#xa;Manages drivers and reviews usage metrics" mermaidId="n:Coordinator" mermaidBaseStyle="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;" mermaidBaseValue="Coordinator&#xa;Person&#xa;Manages drivers and reviews usage metrics" id="r17lKq7YGrd7BqiICL2F-4">
          <mxCell parent="r17lKq7YGrd7BqiICL2F-1" style="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;labelWidth=120;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" vertex="1">
            <mxGeometry height="129" width="152" x="619" y="61" as="geometry" />
          </mxCell>
        </UserObject>
        <UserObject label="SRJ Ride Booking&#xa;Software System&#xa;Web app for booking rides to campus with live trip updates" mermaidId="n:SRJ" mermaidBaseStyle="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;" mermaidBaseValue="SRJ Ride Booking&#xa;Software System&#xa;Web app for booking rides to campus with live trip updates" id="r17lKq7YGrd7BqiICL2F-5">
          <mxCell parent="r17lKq7YGrd7BqiICL2F-1" style="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;labelWidth=120;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" vertex="1">
            <mxGeometry height="150" width="152" x="386" y="333" as="geometry" />
          </mxCell>
        </UserObject>
        <UserObject label="Maps Provider&#xa;External System&#xa;Converts places to coordinates and returns distance and ETA" mermaidId="n:Maps" mermaidBaseStyle="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;" mermaidBaseValue="Maps Provider&#xa;External System&#xa;Converts places to coordinates and returns distance and ETA" id="r17lKq7YGrd7BqiICL2F-6">
          <mxCell parent="r17lKq7YGrd7BqiICL2F-1" style="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;labelWidth=120;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" vertex="1">
            <mxGeometry height="150" width="152" x="200" y="606" as="geometry" />
          </mxCell>
        </UserObject>
        <UserObject label="Notification Provider&#xa;External System&#xa;Delivers email or SMS alerts about booking changes" mermaidId="n:Notify" mermaidBaseStyle="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;" mermaidBaseValue="Notification Provider&#xa;External System&#xa;Delivers email or SMS alerts about booking changes" id="r17lKq7YGrd7BqiICL2F-7">
          <mxCell parent="r17lKq7YGrd7BqiICL2F-1" style="html=1;whiteSpace=wrap;strokeWidth=2;fillColor=#ffffff;strokeColor=#28253D;fontColor=#28253D;fontFamily=Recursive;fontSize=14;shadow=1;shadowColor=#000000;shadowOffsetX=4;shadowOffsetY=4;shadowBlur=0;shadowOpacity=6;labelWidth=120;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" vertex="1">
            <mxGeometry height="150" width="152" x="489" y="606" as="geometry" />
          </mxCell>
        </UserObject>
        <UserObject label="Books a ride, cancels it, and follows the ride&#xa;HTTPS" mermaidId="e:Student-&gt;SRJ#0" mermaidBaseStyle="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=16;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.5;exitY=1;entryX=0.28;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;" mermaidBaseValue="Books a ride, cancels it, and follows the ride&#xa;HTTPS" id="r17lKq7YGrd7BqiICL2F-8">
          <mxCell edge="1" parent="r17lKq7YGrd7BqiICL2F-1" source="r17lKq7YGrd7BqiICL2F-2" style="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=14;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.5;exitY=1;entryX=0.28;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" target="r17lKq7YGrd7BqiICL2F-5">
            <mxGeometry relative="1" x="-0.3579" as="geometry">
              <mxPoint as="offset" />
              <Array as="points">
                <mxPoint x="176" y="313" />
                <mxPoint x="429" y="313" />
              </Array>
            </mxGeometry>
          </mxCell>
        </UserObject>
        <UserObject label="Sets availability, accepts rides,&#xa;and updates trip status&#xa;HTTPS" mermaidId="e:Driver-&gt;SRJ#0" mermaidBaseStyle="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=16;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.5;exitY=1;entryX=0.5;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;" mermaidBaseValue="Sets availability, accepts rides,&#xa;and updates trip status&#xa;HTTPS" id="r17lKq7YGrd7BqiICL2F-9">
          <mxCell edge="1" parent="r17lKq7YGrd7BqiICL2F-1" source="r17lKq7YGrd7BqiICL2F-3" style="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=14;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.5;exitY=1;entryX=0.5;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" target="r17lKq7YGrd7BqiICL2F-5">
            <mxGeometry relative="1" x="-0.1608" as="geometry">
              <mxPoint as="offset" />
              <Array as="points" />
            </mxGeometry>
          </mxCell>
        </UserObject>
        <UserObject label="Manages drivers and reviews&#xa;booking metrics&#xa;HTTPS" mermaidId="e:Coordinator-&gt;SRJ#0" mermaidBaseStyle="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=16;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.5;exitY=1;entryX=0.72;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;" mermaidBaseValue="Manages drivers and reviews&#xa;booking metrics&#xa;HTTPS" id="r17lKq7YGrd7BqiICL2F-10">
          <mxCell edge="1" parent="r17lKq7YGrd7BqiICL2F-1" source="r17lKq7YGrd7BqiICL2F-4" style="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=14;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.5;exitY=1;entryX=0.72;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" target="r17lKq7YGrd7BqiICL2F-5">
            <mxGeometry relative="1" as="geometry">
              <Array as="points">
                <mxPoint x="695" y="313" />
                <mxPoint x="495" y="313" />
              </Array>
            </mxGeometry>
          </mxCell>
        </UserObject>
        <UserObject label="Asks for distance and ETA of a trip&#xa;HTTPS / JSON" mermaidId="e:SRJ-&gt;Maps#0" mermaidBaseStyle="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=16;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.36;exitY=1;entryX=0.5;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;" mermaidBaseValue="Asks for distance and ETA of a trip&#xa;HTTPS / JSON" id="r17lKq7YGrd7BqiICL2F-11">
          <mxCell edge="1" parent="r17lKq7YGrd7BqiICL2F-1" source="r17lKq7YGrd7BqiICL2F-5" style="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=14;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.36;exitY=1;entryX=0.5;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" target="r17lKq7YGrd7BqiICL2F-6">
            <mxGeometry relative="1" x="0.6107" y="-16" as="geometry">
              <mxPoint as="offset" />
              <Array as="points">
                <mxPoint x="440" y="504" />
                <mxPoint x="276" y="504" />
              </Array>
            </mxGeometry>
          </mxCell>
        </UserObject>
        <UserObject label="Asks to alert users about booking changes&#xa;HTTPS / JSON" mermaidId="e:SRJ-&gt;Notify#0" mermaidBaseStyle="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=16;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.64;exitY=1;entryX=0.5;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;" mermaidBaseValue="Asks to alert users about booking changes&#xa;HTTPS / JSON" id="r17lKq7YGrd7BqiICL2F-12">
          <mxCell edge="1" parent="r17lKq7YGrd7BqiICL2F-1" source="r17lKq7YGrd7BqiICL2F-5" style="edgeStyle=orthogonalEdgeStyle;rounded=1;curved=0;startArrow=none;endArrow=block;endSize=8;jumpStyle=arc;jumpSize=12;strokeColor=#000000;html=1;fontSize=14;labelBackgroundColor=#cccccc;fontFamily=Recursive;fontColor=#28253D;exitX=0.64;exitY=1;entryX=0.5;entryY=0;strokeWidth=2;targetPerimeterSpacing=4;fontSource=https%3A%2F%2Ffonts.googleapis.com%2Fcss%3Ffamily%3DRecursive;" target="r17lKq7YGrd7BqiICL2F-7">
            <mxGeometry relative="1" x="0.5506" y="35" as="geometry">
              <mxPoint as="offset" />
              <Array as="points">
                <mxPoint x="484" y="504" />
                <mxPoint x="565" y="504" />
              </Array>
            </mxGeometry>
          </mxCell>
        </UserObject>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
