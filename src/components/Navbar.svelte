<script>
import { notifications } from "../stores/notifications.js";
</script>

<div class="header lazy" on:click={() => notifications.info('Wait a INFO...', 1000)}>
	<div class="navigation">
		<div id="menuToggle" class="click" >
			<input type="checkbox" />
			<span></span>
			<span></span>
			<span></span>
			<ul id="menu">
			</ul>
		</div>

		<div class="logo">
			<img loading="lazy" src="https://placeit.net/assets/icons/placeitAndEnvatoNewWhite.svg" alt="" width="74px">
		</div>
		<div data-src="/build/css/modal.css" class="pricing click">
			<button class="click" data-src="/build/js/modal.js">Pricing</button>
		</div>
		<div class="account">
			<button>👤</button>
		</div>
		<nav class="main">
			<ul>
				<li><a href="#">Mockups</a></li>
				<li><a href="#">Design</a>
					<!-- First Tier Drop Down -->
					<ul>
						<li><a href="#">Themes</a></li>
						<li><a href="#">Plugins</a></li>
						<li><a href="#">Tutorials</a></li>
					</ul>
				</li>
				<li><a href="#">Videos</a>
					<!-- First Tier Drop Down -->
					<ul>
						<li><a href="#">Resources</a></li>
						<li><a href="#">Links</a></li>
						<li><a href="#">Tutorials</a></li>
					</ul>
				</li>
				<li><a href="#">Gaming</a></li>
			</ul>
		</nav>
	</div>
	<div class="search">
		<input placeholder="Search Banner, YouTube Banner, OBS Stream Overlay, Fortnite..." />
	</div>
</div>

<style lang="css">
  .header {
    background-color: black;
  }

  .navigation {
    background-color: black;
    display: flex;
    flex-flow: row wrap;
    background-color: black;
    color: white;
    justify-content: flex-start;
    flex-flow: row wrap;
  }

  .navigation > div {
    flex: auto;
  }

  .navigation > .main {
    flex-grow: 1;
  }

  .navigation nav ul {
    padding: 0;
    margin: 0;
    list-style: none;
    position: relative;
  }

  .navigation nav ul li {
    display: inline-block;
    background-color: #000000;
  }

  .navigation nav a {
    display: block;
    padding: 0 10px;
    color: #fff;
    /* 	font-size:20px; */
    line-height: 30px;
    text-decoration: none;
  }

  /* Hide Dropdowns by Default */

  .navigation nav ul ul {
    display: none;
    position: absolute;
    top: 30px;
    /* the height of the main nav */
  }

  /* Display Dropdowns on Hover */

  .navigation nav ul li:hover > ul {
    display: inherit;
  }

  /* Fisrt Tier Dropdown */

  .navigation nav ul ul li {
    width: 170px;
    float: none;
    display: list-item;
    position: relative;
  }

  .navigation,
  .search {
    display: flex;
    background-color: black;
    color: white;
  }

  @media only screen and (max-width: 1024px) {
    .navigation div {
      height: 44px;
    }
    .navigation > .logo {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      order: 2;
    }
    .navigation > .logo img {
      width: 54px;
      height: 37px;
    }
    .navigation > .pricing {
      order: 3;
    }
    .navigation > .pricing button {
      font-family: "Source Sans Pro", sans-serif;
      background-color: #5e16bd;
      background-image: linear-gradient(90deg, #501aa8, #870de8);
      border-radius: 4px;
      border: none;
      color: white;
      overflow: hidden;
      font-size: 14px;
      padding: 6px 9px 5px;
    }
    .navigation > .account {
      order: 4;
    }
    .navigation > .account button {
      font-size: 25px;
      background-color: transparent;
      border: none;
      padding: 0;
    }
    .navigation nav {
      display: none;
    }
    .header > .search {
      font-family: "Helvetica Neue", Helvetica-, Arial, sans-serif;
      color: #2e3133;
      box-sizing: border-box;
      position: relative;
      height: 100%;
    }
    .header > .search > input {
      margin: 0;
      color: #555555;
      width: 100%;
      font-family: "Source Sans Pro", sans-serif;
      font-size: 15px;
      font-display: block;
      height: 100%;
      padding: 10px 16px;
      border-radius: 6px;
      padding-left: 46px;
    }
    .header > .search:before {
      content: "🔎";
      line-height: 1;
      font-size: 24px;
      position: absolute;
      left: 20px;
      top: 12px;
    }
  }

  #menuToggle {
    display: block;
    position: relative;
    min-width: calc(77% - 27px);
    top: 10px;
    left: 10px;
    z-index: 2;
    -webkit-user-select: none;
    user-select: none;
  }

  #menuToggle a {
    text-decoration: none;
    color: #232323;
    transition: color 0.3s ease;
  }

  #menuToggle a:hover {
    color: tomato;
  }

  #menuToggle input {
    display: block;
    width: 40px;
    height: 32px;
    position: absolute;
    top: -7px;
    left: -5px;

    cursor: pointer;

    opacity: 0; /* hide this */
    z-index: 2; /* and place it over the hamburger */

    -webkit-touch-callout: none;
  }

  /*
           * Just a quick hamburger
           */
  #menuToggle span {
    display: block;
    width: 33px;
    height: 4px;
    margin-bottom: 5px;
    position: relative;

    background: #cdcdcd;
    border-radius: 3px;

    z-index: 1;

    transform-origin: 4px 0px;

    transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1),
      background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), opacity 0.55s ease;
  }

  #menuToggle span:first-child {
    transform-origin: 0% 0%;
  }

  #menuToggle span:nth-last-child(2) {
    transform-origin: 0% 100%;
  }

  /* 
           * Transform all the slices of hamburger
           * into a crossmark.
           */
  #menuToggle input:checked ~ span {
    opacity: 1;
    transform: rotate(45deg) translate(-2px, -1px);
    background: #232323;
  }

  /*
           * But let's hide the middle one.
           */
  #menuToggle input:checked ~ span:nth-last-child(3) {
    opacity: 0;
    transform: rotate(0deg) scale(0.2, 0.2);
  }

  /*
           * Ohyeah and the last one should go the other direction
           */
  #menuToggle input:checked ~ span:nth-last-child(2) {
    transform: rotate(-45deg) translate(0, -1px);
  }

  /*
           * Make this absolute positioned
           * at the top left of the screen
           */
  #menu {
    position: absolute;
    width: 300px;
    margin: -100px 0 0 -50px;
    max-height: calc(100vh + 100px);
    padding: 50px;
    padding-top: 125px;
    overflow-y: scroll;

    background: #ededed;
    list-style-type: none;
    -webkit-font-smoothing: antialiased;
    /* to stop flickering of text in safari */

    transform-origin: 0% 0%;
    transform: translate(-100%, 0);

    transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1);
  }

  #menu li {
    padding: 10px 0;
    font-size: 22px;
    font-family: "Source Sans Pro", sans-serif;
    color: black;
  }

  /*
           * And let's slide it in from the left
           */
  #menuToggle input:checked ~ ul {
    transform: none;
  }
</style>