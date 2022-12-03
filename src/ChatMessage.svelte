<script>
    export let message;
    export let sender;

    const messageClass = message.who === sender ? "sent" : "received";

    const avatar = `https://avatars.dicebear.com/api/initials/${message.who}.svg`;

    const ts = new Date(message.when);
</script>

<div class={`message ${messageClass}`}>
    <img src={avatar} alt="avatar" style="padding:0.5rem" />
    <div class="message-text">
        <p style="margin-bottom:0.5rem;border-radius:1rem">{message.what}</p>

        <time>{ts.toLocaleTimeString()}</time>
    </div>
</div>
