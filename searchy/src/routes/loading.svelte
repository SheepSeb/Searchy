<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
/>
<!-- Roboto -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,600,700"
/>
<!-- Roboto Mono -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto+Mono"
/>

<link rel="stylesheet" href="node_modules/svelte-material-ui/bare.css" />
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/svelte-material-ui@6.0.0/bare.min.css"
/>
<style>
    .center{
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-top: 20rem;
    margin-bottom: 20rem;
    width: 50%;
    }
  </style>

<div style="display: flex; justify-content: center" class="center">
    <CircularProgress style="height: 150px; width: 150px;" indeterminate />
</div>
  
<script lang="ts">
    import CircularProgress from '@smui/circular-progress';
</script>
  

