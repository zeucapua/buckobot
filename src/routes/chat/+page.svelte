<script lang="ts">
  import tmi from "tmi.js";
  import ChatMessage from "$lib/ChatMessage.svelte";

  type Message = {
    user: string | undefined,
    content: string | undefined,
  }
  
  let messages : Message[] = [];
  const client = new tmi.Client({
    channels: ['zeu_dev']
  });

  client.connect();
  
  client.on("message", (channel, tags, message, self) => {
    messages = [...messages, { user: tags['display-name'], content: message }];
  });
</script>

<div class="flex flex-col w-full h-full min-w-screen min-h-screen bg-transparent p-8">
  <div class="mx-auto flex flex-col gap-4 w-full max-w-xl">
    {#each messages as msg}
      <ChatMessage message={msg} />
    {/each}
  </div>
</div>
