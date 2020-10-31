<script>
    import Accordion from './Accordion.svelte';
    import Navbar from './Navbar.svelte';
</script>

<style>
.welcome {
    text-align: center;
    font-size: 2rem;
}

 @media screen and (max-width: 800px) {
    .welcome {
        font-size: 1rem;
    }
}
</style>
<div>
    <b><p class="welcome">Welcome! <br />Here are some examples of svelte.js components</p></b><br />
    <Navbar />
    <br /><br />
    <Accordion />
</div>