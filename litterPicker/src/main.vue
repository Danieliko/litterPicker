<template>
	<!-- App -->
	<div id="app">
		
		<!-- Main Views -->
		<f7-views>
				<f7-pages>
                        <div id='map'></div>
				</f7-pages>
		</f7-views>
		
	</div>
</template>

<script>
	export default {
        data: function () {
            return {
                map: null
                }
        },
        mounted: function () {
            var host = 'http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png';

            var attribution = '&copy; 2017 &middot; <a href="https://maps.omniscale.com/">Omniscale</a> ' +
                '&middot; Map data: <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>';
            this.map = L.map('map').setView([53.14, 8.22], 13);
            L.tileLayer(host, {
                id: 'your-api-key',
                attribution: attribution
              }).addTo(this.map);
            this.map.attributionControl.setPrefix(false);
        },
    }
</script>
