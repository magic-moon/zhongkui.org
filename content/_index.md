---
title: Home
---


当你老了，头发白了，睡思昏沉，

When you are old and grey and full of sleep, 

炉火旁打盹，请取下这部诗歌，

And nodding by the fire, take down this book And slowly read, 

慢慢读，回想你过去眼神的柔和，

and dream of the soft look Your eyes had once, 

回想它们昔日浓重的阴影；

and of their shadows deep; 

多少人爱你青春欢畅的时辰，

How many loved your moments of glad grace,

爱慕你的美丽，假意或真心，

And loved your beauty with love false or true,

只有一个人爱你那朝圣者的灵魂，

But one man loved the pilgrim soul in you, 

爱你衰老了的脸上痛苦的皱纹；

And loved the sorrows of your changing face; 

垂下头来，在红色蒲公英的草地上，

And bending down beside the glowing bars,

凄然地轻轻诉说那爱情的消逝，

Murmur, a little sadly, 

在头顶的山上它缓缓踱着步子，

how love fled And paced upon the mountains overhead

在一群牛羊中间隐藏着脸庞。

 And hid his face amid a crowd of stars.

<script src="js/three.js"></script>
<div>
<script>
			// Our Javascript will go here.
var scene = new THREE.Scene();
var camera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 1000 );

var renderer = new THREE.WebGLRenderer();
renderer.setSize( window.innerWidth/2, window.innerHeight/2 );
document.body.appendChild( renderer.domElement );

var geometry = new THREE.BoxGeometry();
var material = new THREE.MeshBasicMaterial( { color: 0x00ff00 } );
var cube = new THREE.Mesh( geometry, material );
scene.add( cube );

camera.position.z = 5;

function animate() {
	requestAnimationFrame( animate );
	renderer.render( scene, camera );
	
    cube.rotation.x += 0.01;
    cube.rotation.y += 0.01;
}
animate();
</script>
</div>