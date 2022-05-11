<script lang="ts">
    import Button, { Label } from '@smui/button';  
    import Textfield from '@smui/textfield';
    import HelperText from '@smui/textfield/helper-text';

    let value_email = '';
    // MARE SECURITY BUG AICISEA
    let value_pswd = '';
</script>

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
  margin-top: 4rem;
  margin-bottom: 4rem;
  width: 50%;
  }
</style>



<div class="center">
  <img src="https://picsum.photos/200" class="center" />
  <Textfield style="width: 100%;"
  helperLine$style="width: 100%;" variant="outlined" bind:value={value_email} label="Email" type="email">
    <HelperText slot="helper">user@psw.com</HelperText>
  </Textfield>
  <br>
  <br>
  <div>
    <Textfield style="width: 100%;"
    helperLine$style="width: 100%;" variant="outlined" bind:value={value_pswd} label="Password" type="password">
      <HelperText slot="helper">Choose a strong password</HelperText>
    </Textfield>
  </div>
  <br>
  <br>
  <Button style="width: 100%;"
  helperLine$style="width: 100%;">
    <Label>Login</Label>
  </Button>
</div>