console.log("welcome to spotify");

let songIndex=0;
let audioElement = new Audio('./image_resource/Musics/1.mp3');
let masterPlay = document.getElementById("masterPlay");
let progressBar = document.getElementById("myProgressBar");
let gif = document.getElementById("gif");
let songItems = Array.from(document.getElementsByClassName('songItem'));

let songs=[
{songName:"Elektronomia - Sky High", filePath:"./image_resource/Musics/1.mp3", coverPath:"./image_resource/thumbnils/1.jpg"},
{songName:"Lost Sky - Fearless pt. II (feat. Chris Linton) ", filePath:"./image_resource/Musics/2.mp3", coverPath:"./image_resource/thumbnils/2.jpg"},
{songName:"Different Heaven & EH!DE - My Heart", filePath:"./image_resource/Musics/3.mp3", coverPath:"./image_resource/thumbnils/3.jpg"},
{songName:"Cartoon - On & On (feat. Daniel Levi)", filePath:"./image_resource/Musics/4.mp3", coverPath:"./image_resource/thumbnils/4.jpg"}, 
{songName:"Tobu - Hope", filePath:"./image_resource/Musics/5.mp3", coverPath:"./image_resource/thumbnils/5.jpg"}, 
{songName:"Jim Yosef - Firefly)", filePath:"./image_resource/Musics/6.mp3", coverPath:"./image_resource/thumbnils/6.jpg"} 
];

songItems.forEach((element,i) =>{
		element.getElementsByTagName("img")[0].src = songs[i].coverPath;
		element.getElementsByClassName("songName")[0].innerText = songs[i].songName;
})
 
//handle play/pause click
masterPlay.addEventListener('click',()=>{
	if(audioElement.paused || audioElement.currentTime <= 0){
		audioElement.play();
		masterPlay.classList.remove("fa-play");
		masterPlay.classList.add("fa-pause");
		gif.style.opacity=1;
	}else{
		audioElement.pause();
		masterPlay.classList.remove("fa-pause");
		masterPlay.classList.add("fa-play");
		gif.style.opacity=0;
	}
});

audioElement.addEventListener('timeupdate',()=>{	
	progress=parseInt((audioElement.currentTime/audioElement.duration) * 100);
	progressBar.value=progress;
});

progressBar.addEventListener('change',()=>{
	audioElement.currentTime = (progressBar.value * audioElement.duration)/100;
});

const makeAllPlays=()=>{
	Array.from(document.getElementsByClassName('fa-sharp-duoton')).forEach((element)=>{
	element.classList.add("fa-pause");
	element.classList.add("fa-play");
}); 
}



Array.from(document.getElementsByClassName('fa-sharp-duoton')).forEach((element)=>{
	element.addEventListener("click",(e)=>{
	makeAllPlays();
	songIndex = parseInt(e.target.id)
	e.target.classList.remove("fa-play");
	e.target.classList.add("fa-pause");
	audioElement.src = `./image_resource/Musics/${songIndex}.mp3`;
	audioElement.currentTime = 0;
	audioElement.play();
	masterPlay.classList.remove("fa-play");
		masterPlay.classList.add("fa-pause");
	});
});


document.getElementById('next').addEventListener('click',()=>{
	if(songIndex>=9){
		songIndex = 0;
	}
	else{
		songIndex +=1;
	}
	audioElement.src = `./image_resource/Musics/${songIndex}.mp3`;
	audioElement.currentTime = 0;
	audioElement.play();
	masterPlay.classList.remove("fa-play");
		masterPlay.classList.add("fa-pause");
});


document.getElementById('previous').addEventListener('click',()=>{
	if(songIndex<=0){
		songIndex = 0;
	}
	else{
		songIndex -=1;
	}
	audioElement.src = `./image_resource/Musics/${songIndex}.mp3`;
	audioElement.currentTime = 0;
	audioElement.play();
	masterPlay.classList.remove("fa-play");
		masterPlay.classList.add("fa-pause");
});