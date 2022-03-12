<script>
  const src = '/images/background.jpg'
  const countDownDate = new Date(2022, 2, 20, 13, 0, 0, 0).getTime()
  let countDown = {}
  setInterval(() => {
    const today = new Date().getTime()
    const timer = countDownDate - today
    countDown['days'] = Math.floor(timer / (1000 * 60 * 60 * 24))
    countDown['hours'] = Math.floor((timer % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
    countDown['minutes'] = Math.floor((timer % (1000 * 60 * 60)) / (1000 * 60))
    countDown['seconds'] = Math.floor((timer % (1000 * 60)) / 1000)
  }, 1000)
</script>

<main>
  <img {src} alt='tea' />
  <h1>Odlet na Sri Lanku!</h1>
  <div class="wrapper">
    <span class="description">respective do odjezdu na letiste ;)</span>
    <div class="timer">
      <strong>{countDown.days}</strong>d
      <strong>{countDown.hours}</strong>h
      <strong>{countDown.minutes}</strong>m
      <strong>{countDown.seconds}</strong>s
    </div>
  </div>
</main>

<style>
	main {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    height: 100%;
    max-height: 100%;
		text-align: center;
		max-width: 240px;
		margin: 0 auto;
	}

  img {
    position: absolute;
    max-height: 100%;
    width: 100%;
    opacity: .4;
    z-index: -1;
    object-fit: cover;
    height: 100%;
  }

	h1 {
    padding: 24px;
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
    background-color: #fff;
	}

  .description {
    padding-bottom: 12px;
    font-size: 12px;
    font-style: italic;
    display: inline-block;
  }

  .wrapper {
    width: 300px;
    padding: 12px;
    background-color: #fff;
    border-radius: 6px;
  }

  .timer {
    font-size: 32px;
  }

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>