<script>
    import { FaEye, FaEyeSlash } from 'svelte-icons/fa';
    let newPassword = "";
    let confirmPassword = "";
    let showNewPassword = false;
    let showConfirmPassword = false;
  </script>
  
  <div class="container">
    <h2>Create a New Password</h2>
    <p>Enter a new password to complete the password reset process.</p>
  
    <form>
      <div class="form-group">
        <label for="newPassword">New Password</label>
        <div class="password-input">
          {#if showNewPassword}
            <input 
              type="text" 
              id="newPassword" 
              bind:value={newPassword} 
              placeholder="New Password" 
              required 
            />
          {:else}
            <input 
              type="password" 
              id="newPassword" 
              bind:value={newPassword} 
              placeholder="New Password" 
              required 
            />
          {/if}
          <!-- <button type="button" on:click={() => showNewPassword = !showNewPassword}>
            {#if showNewPassword}
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
              placeholder="Confirm Password" 
              required 
            />
          {:else}
            <input 
              type="password" 
              id="confirmPassword" 
              bind:value={confirmPassword} 
              placeholder="Confirm Password" 
              required 
            />
          {/if}
          <!-- <button type="button" on:click={() => showConfirmPassword = !showConfirmPassword}>
            {#if showConfirmPassword}
              <FaEye />
            {:else}
              <FaEyeSlash />
            {/if}
          </button> -->
        </div>
      </div>
  
      <button type="submit" class="submit-btn">Set New Password</button>
    </form>
  
    <div class="navigation">
      <a href="/" class="login-link">Return to Login</a>
    </div>
  </div>
  
  <style>
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
    h2 {
      text-align: center;
      margin-bottom: 10px;
    }
    p {
      text-align: center;
      margin-bottom: 20px;
      color: #666;
    }
    .form-group {
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-bottom: 5px;
      font-size: 16px;
      font-weight: 500;
    }
    .password-input {
      display: flex;
      align-items: center;
    }
    .password-input input {
      width: calc(100% - 40px);
      padding: 14px;
      border: 1px solid #ccc;
      border-radius: 10px;
      outline: none;
      font-size: 16px;
    }
    .password-input button {
      background: none;
      border: none;
      cursor: pointer;
      margin-left: -30px;
    }
    .submit-btn {
      outline: none;
      width: 98%;
      padding: 15px;
      border-radius: 10px;
      background-color: #1a73e8;
      color: white;
      cursor: pointer;
      border: none;
    }
    .navigation {
      text-align: center;
      margin-top: 20px;
    }
    .login-link {
      color: #1a73e8;
      text-decoration: none;
      font-weight: 500;
    }
    .login-link:hover {
      text-decoration: underline;
    }
  </style>
  