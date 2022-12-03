<script>
    import { user } from "./user";

    let username;
    let password;

    function login() {
        user.auth(username, password, ({ err }) => err && alert(err));
    }

    function signup() {
        user.create(username, password, ({ err }) => {
            if (err) {
                alert(err);
            } else {
                login();
            }
        });
    }
</script>

<div
    style="height:100%;display:flex;flex-direction:column;justify-content:center;align-items:center;padding:0 7rem;"
>
    <h1 style="color:white;font-size:3.5rem">DAPP 💬</h1>

    <input
        name="username"
        bind:value={username}
        minlength="3"
        maxlength="16"
        placeholder="Username"
        style="margin:1rem 0;padding:1rem 1.5rem;border-radius:0.7rem"
    />

    <input
        name="password"
        bind:value={password}
        type="password"
        placeholder="Password"
        style="margin:1rem 0;padding:1rem 1.5rem;border-radius:0.7rem"
    />

    <div>
        <button
            class="login"
            on:click={login}
            style="border-radius:0.7rem;margin-right:1.5rem;padding:1rem 2.3rem"
            >Login</button
        >
        <button
            class="login"
            on:click={signup}
            style="border-radius:0.7rem;padding:1rem 2.3rem">Sign Up</button
        >
    </div>
</div>
