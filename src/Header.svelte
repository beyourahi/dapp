<script>
    import { username, user } from "./user";

    function signout() {
        user.leave();
        username.set("");
    }
</script>

<header>
    {#if $username}
        <div class="user-bio">
            <span style="font-size:1.5rem;font-weight:700">{$username}</span>
            <img
                src={`https://avatars.dicebear.com/api/initials/${$username}.svg`}
                alt="avatar"
            />
        </div>

        <button
            class="signout-button"
            on:click={signout}
            style="font-weight:700;font-size:1rem;padding:1rem 1.8rem;border-radius: 0.5rem;letter-spacing: 0.05em"
            >Sign Out</button
        >
    {/if}
</header>
