<script>
	let m = { x: 0, y: 0 };
	let normalImage = 'https://i.ibb.co/Ph9MCB2/template.png'
	let zoomedImage = 'https://i.ibb.co/vhL5kH2/image-14.png'
	let bg = normalImage;
	function handleMousemove(event) {
		m.x = -(event.clientX);
		m.y = -(event.clientY);
		bg = zoomedImage
	}
	function handleMouseOut(event) {
		m.x = 0;
		m.y = 0;
		bg = normalImage
	}
</script>

<div class="container">
     <div class="zoom-handler"
					on:mousemove={handleMousemove}
					on:mouseout={handleMouseOut}
					on:click
					style="--bgx:{m.x}px; --bgy:{m.y}px;--bg: url({bg})">
     </div>
</div>

<style>
	.container {
		 max-width: 670px;
		 height: 377px;
	}
	.zoom-handler {
		max-width: 100%;
		height: 100%;
		cursor: crosshair;
		background-repeat: no-repeat;
		background-image: var(--bg);
		background-position-x: var(--bgx);
		background-position-y: var(--bgy);
	}
</style>
