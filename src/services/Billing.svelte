<script>
  import { onMount } from "svelte";
  import { notifications } from "../stores/notifications.js";

  let modal;
  let card = {
    number: null,
    cvv: null,
    expiration: null
  };

  function showModal() {
    modal.style.display = "block";
  }

  function hideModal() {
    modal.style.display = "none";
  }

  function pay() {
    console.log("paying with " + JSON.stringify(card));
    notifications.warning("Your payment method failed, try again later.", 5000);
  }

  onMount(() => {
    // When the user clicks anywhere outside of the modal, close it
    window.onclick = function(event) {
      if (event.target == modal) {
        modal.style.display = "none";
      }
    };
  });
</script>

<div class="login-form">
	<button on:click={showModal} style="width:auto;">Billing</button>
	<div bind:this={modal} class="modal">
		<form class="modal-content animate" method="post" action="">
			<div class="imgcontainer">
				<span on:click={hideModal} class="close" title="Close Modal">&times;</span>
			</div>

			<div class="container">
				<label for="cardNumber"><b>Card Number</b></label>
				<input type="text" placeholder="XXXX XXXX XXXX XXXX" name="cardNumber" bind:value={card.number} />

				<label for="cvv"><b>CVV</b></label>
				<input type="password" placeholder="XXX" name="cvv" required bind:value={card.cvv}>

        				<label for="expiration"><b>Expiration date</b></label>
				<input type="text" placeholder="XX/XX" name="expiration" required bind:value={card.expiration}>

				<button type="button" on:click={pay}>Pay</button>
			</div>

			<div class="container" style="background-color:#f1f1f1">
				<button type="button" on:click={hideModal} class="cancelbtn">Cancel</button>
			</div>
		</form>
	</div>
</div>

<style>
  body {
    font-family: Arial, Helvetica, sans-serif;
  }

  /* Full-width input fields */
  input[type="text"],
  input[type="password"] {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    box-sizing: border-box;
  }

  /* Set a style for all buttons */
  button {
    background-color: #04aa6d;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    cursor: pointer;
    width: 100%;
  }

  button:hover {
    opacity: 0.8;
  }

  /* Extra styles for the cancel button */
  .cancelbtn {
    width: auto;
    padding: 10px 18px;
    background-color: #f44336;
  }

  /* Center the image and position the close button */
  .imgcontainer {
    text-align: center;
    margin: 24px 0 12px 0;
    position: relative;
  }

  img.avatar {
    width: 40%;
    border-radius: 50%;
  }

  .container {
    padding: 16px;
  }

  span.psw {
    float: right;
    padding-top: 16px;
  }

  /* The Modal (background) */
  .modal {
    display: none; /*Hidden by default */
    position: fixed; /* Stay in place */
    z-index: 2; /* Sit on top */
    left: 0;
    top: 0;
    width: 100%; /* Full width */
    height: 100%; /* Full height */
    overflow: auto; /* Enable scroll if needed */
    background-color: rgb(0, 0, 0); /* Fallback color */
    background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
    padding-top: 60px;
  }

  /* Modal Content/Box */
  .modal-content {
    background-color: #fefefe;
    margin: 5% auto 15% auto; /* 5% from the top, 15% from the bottom and centered */
    border: 1px solid #888;
    width: 80%; /* Could be more or less, depending on screen size */
  }

  /* The Close Button (x) */
  .close {
    position: absolute;
    right: 25px;
    top: 0;
    color: #000;
    font-size: 35px;
    font-weight: bold;
  }

  .close:hover,
  .close:focus {
    color: red;
    cursor: pointer;
  }

  /* Add Zoom Animation */
  .animate {
    -webkit-animation: animatezoom 0.6s;
    animation: animatezoom 0.6s;
  }

  @-webkit-keyframes animatezoom {
    from {
      -webkit-transform: scale(0);
    }
    to {
      -webkit-transform: scale(1);
    }
  }

  @keyframes animatezoom {
    from {
      transform: scale(0);
    }
    to {
      transform: scale(1);
    }
  }

  /* Change styles for span and cancel button on extra small screens */
  @media screen and (max-width: 300px) {
    span.psw {
      display: block;
      float: none;
    }
    .cancelbtn {
      width: 100%;
    }
  }
</style>
