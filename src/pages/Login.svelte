<script>
  import { FaEye, FaEyeSlash } from 'svelte-icons/fa'; // Icons for visibility toggle
  import { Link } from 'svelte-routing';
  
  let email = "";
  let password = "";
  let showPassword = false;
  export let navigate;
</script>

<form>
  <h2>Create an account</h2>
  <p>Kindly enter the details to get started</p>

  <div class="form-group">
    <label for="email">Email Address</label>
    <input 
      type="email" 
      id="email" 
      bind:value={email} 
      placeholder="Email address" 
      required 
    />
  </div>

  <div class="form-group">
    <label for="password">Password</label>
    <div class="password-input">
      <!-- Conditionally render input based on showPassword -->
      {#if showPassword}
        <input 
          type="text" 
          id="password" 
          bind:value={password} 
          placeholder="Password" 
          required 
        />
      {:else}
        <input 
          type="password" 
          id="password" 
          bind:value={password} 
          placeholder="Password" 
          required 
        />
      {/if}
      <!-- <button type="button" class="toggle-icon" on:click={() => showPassword = !showPassword}>
        {#if showPassword}
          <FaEye />
        {:else}
          <FaEyeSlash />
        {/if}
      </button> -->
    </div>
  </div>

  <div class="forgot-password">
    <Link to="/forgot-password">Forgot password?</Link>
  </div>

  <button type="submit" class="submit-button">Log in</button>

  <p class="sign-link">
    Don&apos;t have an account? 
    <Link to="/signup">Sign up</Link>
  </p>
</form>

<style>
  form {
    max-width: 700px;
    width: 500px;
    margin: auto;
    padding: 2rem;
    background: white;
    border-radius: 10px;
    box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.1);
    text-align: left;
  }

  h2 {
    margin-bottom: 0.5rem;
    font-size: 1.8rem;
    color: #333;
  }

  p {
    margin-bottom: 1.5rem;
    font-size: 1rem;
    color: #666;
  }

  .form-group {
    margin-bottom: 1.5rem;
    display: flex;
    flex-direction: column;
  }

  label {
    margin-bottom: 0.5rem;
    font-weight: bold;
    color: #333;
  }

  input {
    padding: 0.8rem 2.5rem 0.8rem 0.8rem; /* Add extra right padding for icon */
    border-radius: 5px;
    border: 1px solid #ddd;
    font-size: 1rem;
    width: 100%;
    box-sizing: border-box;
    outline: none;
    transition: border-color 0.3s ease;
  }

  input:focus {
    border-color: #007bff;
  }

  .password-input {
    position: relative;
  }

  .password-input .toggle-icon {
    position: absolute;
    right: 10px;
    top: 50%;
    transform: translateY(-50%);
    background: none;
    border: none;
    cursor: pointer;
  }

  .toggle-icon svg {
    width: 5px;
    height: 5px;
    color: #888;
  }

  .forgot-password {
    text-align: right;
    margin-bottom: 1.5rem;
  }

  .submit-button {
    width: 100%;
    padding: 1rem;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .submit-button:hover {
    background-color: #0056b3;
  }

  .sign-link {
    text-align: center;
  }
</style>
