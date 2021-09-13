<script>
</script>

<div class="hero-banner">
	<!-- FIXME: Is this img div necessary?-->
	<img class="hidden" src="https://res.cloudinary.com/dhfr8kgzr/image/upload/f_auto,q_auto/v1621024500/hero-banner-small_nymmz8.jpg" />
	<div class="hero-banner-img">
	</div>

	<div class="copy-container">
		<h1 class="title">
			Design Made Easy with <strong>Ready-To-Use</strong> Templates!
		</h1>
		<h2 class="subtitle" style="">
			Subscribe Now For Unlimited Downloads!
		</h2>
		<a class="cta" href="#" style="">
			Go Unlimited!
		</a>
	</div>
</div>

<style lang="css">
  .hidden {
    display: none;
  }
  .hero-banner {
    font-size: 14px;
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    color: #303030;
    height: 215px;
    border-bottom: 1px solid #f0f0f0;
    position: relative;
    line-height: 1.33;
  }

  .hero-banner > .hero-banner-img {
    background-image: url("https://res.cloudinary.com/dhfr8kgzr/image/upload/f_auto,q_auto/v1621024500/hero-banner-small_nymmz8.jpg");
    background-position: unset;
    background-repeat: no-repeat;
    background-size: cover;
    height: 100%;
    position: absolute;
    top: 0;
    left: 60%;
    width: 50%;
  }

  .hero-banner > .copy-container {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    height: 100%;
    justify-content: center;
    padding: 0 20px;
    position: relative;
    max-width: 332px;
  }

  .hero-banner > .copy-container .title {
    margin: 0.67em 0;
    font-size: 25px;
    font-weight: 700;
    color: #000;
    margin-bottom: 2px;
    margin-top: 0;
    z-index: 1;
  }

  .hero-banner > .copy-container .title strong {
    font-size: 25px;
    box-sizing: border-box;
    font-weight: bold;
    color: #8e59cf;
  }

  .hero-banner > .copy-container .subtitle {
    font-size: 11px;
    font-weight: 400;
    color: #303030;
    line-height: 1.38;
    margin-bottom: 6px;
    margin-top: 0;
    z-index: 1;
  }

  .hero-banner > .copy-container .cta {
    line-height: 1.42857;
    border-radius: 6px;
    background-color: #8e59cf;
    color: #fff;
    flex-grow: 0;
    font-size: 12px;
    font-weight: 500;
    padding: 7px 10px;
    text-decoration: none;
    z-index: 1;
  }
</style>