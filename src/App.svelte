<script>
  import { Router, Route, Link } from 'svelte-routing';
  import Login from './pages/Login.svelte';
  import ForgotPassword from './pages/ForgotPassword.svelte';
  import Signup from './pages/Signup.svelte';
  import NewPassword from './pages/NewPassword.svelte';

  let navigate = null;
</script>

<Router>
  <main>
    <Route path="/" component={Login} />
    <Route path="/forgot-password" component={ForgotPassword} />
    <Route path="/signup" component={Signup} />
    <Route path="/new-password" component={NewPassword} />
  </main>
</Router>
