<script>
function logout() {
  window.location.href = 'https://google.com'
}
</script>

<template>
    <dialog ref="dialogElement">
        <div>
            Möchten Sie sich wirklich abmelden?
        </div>

        <button >Ja</button>
        <button value="Nein">Nein</button>
    </dialog>
</template>
