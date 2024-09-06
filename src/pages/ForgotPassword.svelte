<script>
  import { Link } from "svelte-routing";

  let email = "";

  const onSubmit = (event) => {
    event.preventDefault();
    // Handle forgot password logic here
  };
</script>

<div class="container">
  <div class="go-home">
    <a href="/" class="home-link">← Go Home</a>
  </div>

  <form on:submit={onSubmit}>
    <div class="form-group">
      <label for="email">Email</label>
      <input
        type="email"
        id="email"
        bind:value={email}
        placeholder="johndoe@example.com"
        required
      />
    </div>

    <button type="submit" class="submit-btn">
      <Link to="/new-password">Reset password</Link>
      </button>
  </form>
</div>

<style>
  * {
    box-sizing: border-box;
  }

  body,
  html {
    margin: 0;
    padding: 0;
    font-family: "Arial", sans-serif;
  }

  .container {
    max-width: 700px;
    width: 500px;
    margin: 100px auto;
    background-color: white;
    padding: 2rem;
    border-radius: 16px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
    text-align: left;
  }

  .go-home {
    margin-bottom: 20px;
    text-align: center;
  }

  .home-link {
    text-decoration: none;
    color: #1a73e8;
    font-weight: 500;
    font-size: 14px;
  }

  .form-group {
    margin-bottom: 20px;
  }

  label {
    display: block;
    margin-bottom: 8px;
    font-size: 16px;
    color: #555;
    font-weight: 600;
  }

  input {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 10px;
    font-size: 16px;
    color: #333;
    transition: border-color 0.3s ease;
  }

  input:focus {
    border-color: #1a73e8;
    outline: none;
  }

  .submit-btn {
    width: 100%;
    padding: 15px;
    border-radius: 10px;
    background-color: #1a73e8;
    color: white;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    border: none;
    outline: none;
    transition: background-color 0.3s ease;
  }

  .submit-btn a {
    color: white;
  }
  .submit-btn:hover {
    background-color: #0c59c4;
  }

  .submit-btn:active {
    background-color: #084298;
  }
</style>
