<script lang="ts">
  type Message = {
    user: string | undefined,
    content: string | undefined
  };

  export let message : Message;
</script>

<div class="relative w-full">
  <div class="px-4 py-2 border border-white rounded-xl -rotate-12 absolute -left-12 bg-white border-red-100 w-fit h-fit">
    {message.user}
  </div>
  <div class="px-8 py-4 border-2 border-black rounded-xl bg-white text-center w-full">
    {message.content}
  </div>
</div>

