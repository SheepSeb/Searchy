<script lang="ts">
    import Button, { Label } from '@smui/button';
    import TopAppBar, { Row, Section, Title } from '@smui/top-app-bar';
    import IconButton ,{ Icon }from '@smui/icon-button';
    import Textfield from '@smui/textfield';
    import HelperText from '@smui/textfield/helper-text';
    import Card, {
    Content,
    Actions,
    ActionButtons,
    ActionIcons,
  } from '@smui/card';
  import Dialog from '@smui/dialog';
  import Fab from '@smui/fab'
    let secondaryColor = false;
    let open = false;
    let open2 = false;
    let title ='';
    let decription = '';
    let random_val = '';

    //TODO: Implement sending msg to server
    function sendMessage() {
      alert('Sending message...');
    }
</script>

<style>
  .footer{
    position: fixed;
    left: 0;
    bottom: 1rem;
    width: 100%;
    color: white;
    text-align: center;
  } 
</style>

<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/icon?family=Material+Icons"/>
<!-- Roboto -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,600,700"/>
<!-- Roboto Mono -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto+Mono"/>

<link rel="stylesheet" href="node_modules/svelte-material-ui/bare.css" />
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/svelte-material-ui@6.0.0/bare.min.css"/>

<TopAppBar
      variant="static"
      color={secondaryColor ? 'secondary' : 'primary'}
    >
      <Row>
        <Section>
          <IconButton class="material-icons">menu</IconButton>
          <Title>Searchy</Title>
        </Section>
        <Section align="end" toolbar>
          <IconButton class="material-icons" aria-label="AccountCircleIcon">
              account_circle</IconButton>
        </Section>
      </Row>
</TopAppBar>

<Dialog
  bind:open
  aria-labelledby="large-scroll-title"
  aria-describedby="large-scroll-content"
  surface$style="width: 850px; max-width: calc(100vw - 32px);"
  >
  <Title id="large-scroll-title">A Brief Selection of Placeholder Text</Title>
  <Content id="large-scroll-content">
      Some content here
      Put some sugar in the water
      I'll be ok
  </Content>
  <Actions>
      <Button on:click={() => (open = false)}>
      <Label>Done</Label>
      </Button>
  </Actions>
</Dialog>
<div class="center">
  <Dialog
  bind:open={open2}
  aria-labelledby="label_aria"
  aria-describedby="description_aria"
  surface$style="width: 850px; max-width: calc(100vw - 32px);"
  >
  <br>
  <Title id="post_title">Add a post</Title>
  <br>
  <Content id="content_id">
    <Textfield     style="width: 100%;"
    helperLine$style="width: 100%;" variant="outlined" bind:value={title} label="Title" type="text">
      <HelperText slot="helper">title</HelperText>
    </Textfield>
    <Textfield     style="width: 100%;"
    helperLine$style="width: 100%;" variant="outlined" bind:value={decription} label="Description" type="text">
      <HelperText slot="helper">breif description</HelperText>
    </Textfield>
  </Content>
  <Actions>
      <Button on:click={() => (open2 = false)}>
      <Label>Done</Label>
      </Button>
  </Actions>
  </Dialog>
</div>

    <Card>
      <Content>A card with Both.</Content>
      <Actions>
        <ActionButtons>
          <Button on:click={() => sendMessage()}>
            <Label>Send Message</Label>
          </Button>
          <Button on:click={() => (open = true)}>
            <Label>More</Label>
          </Button>
        </ActionButtons>
        <ActionIcons>
          <IconButton
            toggle
            aria-label="Add to favorites"
            title="Add to favorites"
          >
            <Icon class="material-icons" on>favorite</Icon>
            <Icon class="material-icons">favorite_border</Icon>
          </IconButton>
          <IconButton
            class="material-icons"
            title="Share">share</IconButton
          >
        </ActionIcons>
      </Actions>
    </Card>
<div class="footer">
  <div class="flexy">
    <div class="margins">
      <Fab color="primary" on:click={() => open2 = true}>
        <Icon class="material-icons">add</Icon>
      </Fab>
    </div>
  </div>
</div>

