<script>
  import { FaEye, FaEyeSlash } from 'svelte-icons/fa';
  import { Link } from 'svelte-routing';

  let fullName = "";
  let email = "";
  let password = "";
  let confirmPassword = "";
  let showPassword = false;
  let showConfirmPassword = false;
  let rememberMe = false;
  export const navigate = null;
</script>

<form>
  <h2>Create an Account</h2>
  <p>Kindly enter the details to get started</p>

  <div class="form-group">
    <label for="fullname">Full Name</label>
    <input 
      type="text" 
      id="fullname" 
      bind:value={fullName} 
      placeholder="Full Name" 
      required 
    />
  </div>

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

  <div class="form-group">
    <label for="confirmPassword">Confirm Password</label>
    <div class="password-input">
      {#if showConfirmPassword}
        <input 
          type="text" 
          id="confirmPassword" 
          bind:value={confirmPassword} 
          placeholder="Confirm password" 
          required 
        />
      {:else}
        <input 
          type="password" 
          id="confirmPassword" 
          bind:value={confirmPassword} 
          placeholder="Confirm password" 
          required 
        />
      {/if}
      <!-- <button type="button" class="toggle-icon" on:click={() => showConfirmPassword = !showConfirmPassword}>
        {#if showConfirmPassword}
          <FaEye />
        {:else}
          <FaEyeSlash />
        {/if}
      </button> -->
    </div>
  </div>

  <!-- <div class="form-group remember-me">
    <label>
      <input type="checkbox" bind:checked={rememberMe} />
      <p>Remember me</p>
    </label>
  </div> -->

  <button type="submit" class="submit-button">Sign up</button>

  <p class="login-link">
    Have an account? 
    <Link to="/">Log in</Link>
  </p>
</form>

<style>
body {
  font-family: 'Roboto', sans-serif;
  background-color: #f4f4f9;
}

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
  width: 20px;
  height: 20px;
  color: #888;
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

.remember-me {
  display: flex;
  align-items: flex-start;
  width: 200px;
}
.remember-me label {
  display: flex;
  align-items: flex-start;
}

.login-link {
  text-align: center;
  font-size: 0.9rem;
  margin-top: 1rem;
  color: #333;
}

.login-link a {
  color: #007bff;
  text-decoration: none;
}

.login-link a:hover {
  text-decoration: underline;
}
</style>
