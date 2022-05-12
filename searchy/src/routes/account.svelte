<script lang="ts">
    import Button, { Label } from '@smui/button';
    import TopAppBar, { Row, Section, Title } from '@smui/top-app-bar';
    import IconButton ,{ Icon }from '@smui/icon-button';
    import Card, { Content } from '@smui/card';
    let secondaryColor = false;
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
  margin-top: 1rem;
  margin-bottom: 1rem;
  width: 50%;
  }
  .maring_card{
    margin-top: 1rem;
    margin-bottom: 1rem;
  }
</style>
<TopAppBar
      variant="static"
      color={secondaryColor ? 'secondary' : 'primary'}
    >
      <Row>
        <Section>
          <IconButton class="material-icons" href=".">menu</IconButton>
          <Title>Searchy</Title>
        </Section>
        <Section align="end" toolbar>
          <IconButton class="material-icons" aria-label="AccountCircleIcon">
              account_circle</IconButton>
        </Section>
      </Row>
</TopAppBar>
<div class="center">
    <img src="https://picsum.photos/200" class="center" alt="account_img"/>
</div>
      <Card class="maring_card" variant="outlined" padded>
        Nume : Maria
      </Card>
      <Card variant="outlined" padded>
        Prenume : Popescu
      </Card>
      <Card variant="outlined" padded>
        Email : mariap@gmail.com
      </Card>
      <Card variant="outlined" padded>
        Posts : 3
      </Card>

      <!-- <div class="center">
        <Button style="width: 100%;">
          Edit detials
        </Button>  
      </div> -->
 