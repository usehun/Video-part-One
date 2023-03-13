# Video-part-One
nomard Youtube Code Challenge 10

```
(1) <script src="./src/index.js" defer></script>
    html의 head 태그 안에 스크립트를 작성하여 index.js가 작동될 수 있게 합니다.
    보통 body 태그 하단에 외부 스크립트를 작성합니다. head 태그에 스크립트를 작성할 경우에는 defer 속성을 추가하여 페이지가 모두 로드된 후에 해당 script가 실행되게 하면 됩니다.

(2) <input type="range" step="0.1" value="0.5" min="0" max="1" id="volumeRange" />
    비디오 컨트롤러에 필요한 모든 input과 버튼(혹은 아이콘)을 html에서 마크업으로 작성하고 각각에 id를 할당합니다.

(3) document.querySelector(), document.getElementById()
    각 요소들을 위와 같은 선택자를 사용하여 javascript로 가져옵니다.

(4) Play 버튼
    psBtn.addEventListener("click", handlePlayAndStop)
    click 이벤트는 클릭할 때 이벤트가 실행됩니다.
    play 버튼을 클릭했을 핸들러를 실행하기 위해 click 이벤트를 사용하면 됩니다.
    handlePlayAndStop 핸들러에서는 if else 구문을 사용하여 video.paused인 경우 video.play() 메서드를 사용해 비디오를 재생되게 한 후, 버튼 모양을 Pause 모양으로 바꿔 줍니다.
    video.paused가 아닌 경우 video.pause() 메서드를 사용해 비디오를 일시정지시키고, 버튼 모양을 play 모양으로 바꿔주면 됩니다.

(5) Mute 버튼
    volumeBtn.addEventListener("click", handleSound);
    Mute 버튼을 클릭했을 때 핸들러를 실행하기 위해 click 이벤트를 사용하면 됩니다.
    handleSound 핸들러에서는 if else 구문을 사용하여 video.muted인 경우, (즉, 음소거 상태인 경우) video.muted = false가 되게 하여 음소거를 해제합니다.
    그리고 volumeRange.value = volumeValue라고 작성하여 볼륨의 range 값을 업데이트하고, 버튼 모양을 음소거 해제된 모양으로 바꿔줍니다.
    video.muted가 아닌 경우, (즉, 음소거 상태가 아닌 경우) video.muted = true로 음소거시킵니다.
    volumeRange.value = 0이라고 작성하여 볼륨의 range 값을 0으로 업데이트하여 음량이 0이 되게 하고, 버튼 모양을 음소거 모양으로 바꿔주면 됩니다.

(6) Volume Control의 input
    Volume Control (볼륨 조절)의 input 값을 조절하면 조절된 값에 따라 소리 크기가 달라집니다.
    volumeRange.addEventListener("input", handleVolume);
    input 이벤트는 드래그를 할 때마다, 즉 밸류 값이 바뀔 때마다 이벤트가 실행됩니다.
    input(type="range")인 volumeRange는 range를 드래그해서 옮길 때마다 value 값이 바뀌기 때문에 input 이벤트를 사용하면 됩니다.
    let volumeValue = 0.5
    먼저 볼륨 값을 조절할 수 있도록 volumeValue를 전역변수로 설정합니다.
    video.volume = volumeValue
    비디오의 볼륨이 사용자가 조절하는 값이 될 수 있도록 설정합니다.
    handleVolume 핸들러에서는 event를 인자로 받아 event.target.value 값을 사용하여 사용자가 조절하는 range 값을 받아 옵니다.
    if 구문을 사용하여 video.muted인 경우, (즉, 음소거 상태인 경우) video.muted = false가 되게 하여 음소거를 해제하고 볼륨 버튼의 모양을 음소거 모양으로 바꿔줍니다.
    if else 구문을 사용하여 value === "0"인 경우, (즉, 음량이 0인 경우) 볼륨 버튼의 모양을 볼륨 off 모양으로 바꿔주고, 아닌 경우는 원래 볼륨 버튼의 모양으로 바꿔줍니다.
    그리고 video.volume = volumeValue = value라고 작성하여 비디오의 볼륨 값과 사용자가 조절한 볼륨 값과 음량 값을 같게 하면 됩니다.
```
