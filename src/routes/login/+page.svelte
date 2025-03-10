<script>
    import { goto } from '$app/navigation';
    import user from '../../user';
    import Login from '../../lib/Login.svelte';

    $: isLoggedIn = $user !== null;

    $: if (isLoggedIn) {
        goto('/home');
    }
</script>

<div class="login-container">
    <div class="login-box">
        <h1>Welcome to Blue</h1>
        <p class="subtitle">Share your knowledge with the world</p>
        <Login />
    </div>
</div>

<style>
    .login-container {
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
    }

    .login-box {
        background: white;
        padding: 2.5rem;
        border-radius: 1rem;
        box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        text-align: center;
        width: 100%;
        max-width: 400px;
        margin: 1rem;
    }

    h1 {
        color: #1e3c72;
        margin-bottom: 0.5rem;
        font-size: 2.5rem;
    }

    .subtitle {
        color: #666;
        margin-bottom: 2rem;
    }
</style> 