<script lang="ts">
    function setTheme(theme: string) {
        console.log(theme)
        document.body.setAttribute('data-theme', theme)
    }
</script>

<div>
    <button class="btn hover:variant-soft-primary">Theme</button>
</div>