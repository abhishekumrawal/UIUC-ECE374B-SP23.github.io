---
layout: resource
title: "Subset Construction"

description: Manim is a powerful animation tool that is used extensibly by STEM youtubers to animate mathematical concepts. It's integration with python allows you to calculate and display examples within the same script. This is a quickstart guide on how to create Manim animations. 

icon: star-o
people:
  - mikem
---


<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="/js/subsetConstruction.js"></script>

<button onclick="subsetConstruction()">Transform</button>
<button onclick="setConstants()">Transform Options</button>
<button onclick="delNode()">Delete State</button>
<button onclick="addNode()">Add State</button>
<button onclick="addTransition()">Add Transition</button>
<button onclick="rmTransition()">Remove Transition</button>
<button onclick="changeStarting()">Change Starting Node</button>
<button onclick="toggleAccepting()">Toggle Accepting node</button>
<div id="options" hidden>
    <div>
        <label for="HOLD_TIME">how long will groups of highlighted nodes stay in milliseconds:</label>
        <input id="HOLD_TIME" type="number">
    </div>
    <div>
        <label for="TIME_BETWEEN_NODES">how long of a delay between highlighting nodes in milliseconds:</label>
        <input id="TIME_BETWEEN_NODES" type="number">
    </div>
    <button id="optionsButton" onclick="sendOptions()">Confirm Options</button>
</div>
<div id="text" style="font-size: 150%;"></div>
<div style = "text-align:center;">
    <canvas id="canvas1"></canvas>
</div>
<div style = "text-align:center;">
    <canvas id="canvas2"></canvas>
</div>
