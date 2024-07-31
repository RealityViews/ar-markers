<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>AR.js Model Selector</title>
    <!-- A-Frame library -->
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
    <!-- AR.js library for A-Frame -->
    <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/3.3.2/aframe/build/aframe-ar.js"></script>
    <script>
        // Function to get URL parameters
        function getQueryParam(name) {
            const params = new URLSearchParams(window.location.search);
            return params.get(name);
        }

        // Function to set the model URL based on query parameter
        function setModelUrl() {
            const modelName = getQueryParam('model') || 'Scaniverse_2024-07-15_170330.glb'; // Default model if no parameter
            const modelUrl = `https://raw.githubusercontent.com/yourusername/yourrepo/main/models/${modelName}`;
            document.getElementById('model').setAttribute('gltf-model', `url(${modelUrl})`);
        }

        // Set model URL on page load
        window.onload = setModelUrl;
    </script>
</head>
<body style='margin : 0px; overflow: hidden;'>

<a-scene embedded arjs>
    <!-- Marker -->
    <a-marker preset="kanji">
        <!-- GLB Model -->
        <a-entity 
            id="model"
            scale="0.5 0.5 0.5"
            position="0 0 0">
        </a-entity>
    </a-marker>

    <a-entity camera></a-entity>
</a-scene>

</body>
</html>
