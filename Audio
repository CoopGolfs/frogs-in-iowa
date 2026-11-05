/* Iowa Frog Sounds: small audio player.
   Each [data-player] block holds one <audio> element and our own play button,
   so recordings play on the page without sending visitors anywhere else. */
(function () {
  var players = document.querySelectorAll('[data-player]');
  if (!players.length) return;

  function fmt(seconds) {
    if (!isFinite(seconds) || seconds < 0) return '0:00';
    var m = Math.floor(seconds / 60);
    var s = Math.floor(seconds % 60);
    return m + ':' + (s < 10 ? '0' : '') + s;
  }

  players.forEach(function (box) {
    var audio = box.querySelector('audio');
    var btn = box.querySelector('.play-btn');
    var seek = box.querySelector('.seek');
    var time = box.querySelector('.player-time');
    var note = box.querySelector('.player-note');
    var name = box.getAttribute('data-name') || 'recording';
    var dragging = false;

    function updateTime() {
      var total = audio.duration;
      time.textContent = isFinite(total) && total > 0
        ? fmt(audio.currentTime) + ' / ' + fmt(total)
        : fmt(audio.currentTime);
    }

    function showUnavailable() {
      btn.disabled = true;
      seek.disabled = true;
      box.classList.remove('is-playing');
      note.textContent = 'This recording could not be loaded.';
      var url = box.getAttribute('data-fallback');
      if (url) {
        note.appendChild(document.createTextNode(' '));
        var link = document.createElement('a');
        link.href = url;
        link.target = '_blank';
        link.rel = 'noopener';
        link.textContent = 'Listen on YouTube instead';
        note.appendChild(link);
      }
      note.hidden = false;
    }

    btn.addEventListener('click', function () {
      if (audio.paused) {
        players.forEach(function (other) {
          var otherAudio = other.querySelector('audio');
          if (otherAudio !== audio) otherAudio.pause();
        });
        var started = audio.play();
        if (started && started.catch) {
          started.catch(function (err) {
            if (err && err.name === 'NotSupportedError') showUnavailable();
          });
        }
      } else {
        audio.pause();
      }
    });

    audio.addEventListener('play', function () {
      box.classList.add('is-playing');
      btn.setAttribute('aria-label', 'Pause ' + name);
    });

    audio.addEventListener('pause', function () {
      box.classList.remove('is-playing');
      btn.setAttribute('aria-label', 'Play ' + name);
    });

    audio.addEventListener('ended', function () {
      audio.currentTime = 0;
      seek.value = 0;
      updateTime();
    });

    audio.addEventListener('loadedmetadata', updateTime);

    audio.addEventListener('timeupdate', function () {
      if (!dragging && audio.duration) {
        seek.value = (audio.currentTime / audio.duration) * 100;
      }
      updateTime();
    });

    audio.addEventListener('error', showUnavailable);

    seek.addEventListener('input', function () {
      dragging = true;
      if (audio.duration) {
        audio.currentTime = (seek.value / 100) * audio.duration;
      }
    });
    seek.addEventListener('change', function () { dragging = false; });
  });
})();
