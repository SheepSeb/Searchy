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
  import Fab from '@smui/fab';
  import CircularProgress from '@smui/circular-progress';
    let secondaryColor = false;
    let open = false;
    let open2 = false;
    let title ='';
    let decription = '';
    let random_val = '';
    let open3 = false;
    let open4 = false;
    let open5 = false;
    //TODO: Implement sending msg to server
    let shown = false;
    let show_not = true;
    setTimeout(() => {
      shown = true;
      show_not = false;
    }, 10000);

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
          <IconButton class="material-icons" href="localhost:3000">menu</IconButton>
          <Title>exChange</Title>
        </Section>
        <Section align="end" toolbar>
          <IconButton class="material-icons" aria-label="AccountCircleIcon" href="/account">
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
  <Title id="large-scroll-title">Help for Frontend</Title>
  <Content id="large-scroll-content">
    <ul>
      <li>Skills: Svelte, Node.js, Firebase, Material-UI</li>
      <li>Working hours: 4 days a week</li>
      <li>Want : Backend</li>
    </ul>  
  </Content>
  <Actions>
      <Button on:click={() => (open = false)}>
      <Label>Done</Label>
      </Button>
  </Actions>
</Dialog>
<Dialog
  bind:open = {open3}
  aria-labelledby="large-scroll-title"
  aria-describedby="large-scroll-content"
  surface$style="width: 850px; max-width: calc(100vw - 32px);"
  >
  <Title id="large-scroll-title">Help for Backend</Title>
  <Content id="large-scroll-content">
    <ul>
      <li>Skills: Express, Node.js, Firebase, Postman, Python</li>
      <li>Working hours: 4 days a week</li>
      <li>Want : Frontend</li>
    </ul>  
  </Content>
  <Actions>
      <Button on:click={() => (open3 = false)}>
      <Label>Done</Label>
      </Button>
  </Actions>
</Dialog>
<Dialog
  bind:open = {open4}
  aria-labelledby="large-scroll-title"
  aria-describedby="large-scroll-content"
  surface$style="width: 850px; max-width: calc(100vw - 32px);"
  >
  <Title id="large-scroll-title">Help for Fullstack</Title>
  <Content id="large-scroll-content">
    <ul>
      <li>Skills: Svelte, Material-UI</li>
      <li>Skills: Express, Node.js, Firebase, Postman, Python</li>
      <li>Working hours: 4 days a week</li>
      <li>Want : Database Admin</li>
    </ul>  
  </Content>
  <Actions>
      <Button on:click={() => (open4 = false)}>
      <Label>Done</Label>
      </Button>
  </Actions>
</Dialog>

<div class="center">
  <Dialog
  bind:open={open5}
  aria-labelledby="label_aria"
  aria-describedby="description_aria"
  surface$style="width: 850px; max-width: calc(100vw - 32px);"
  >
  <br>
  <Title id="post_title">Sending help</Title>
  <br>
  <Content id="content_id">
    <div style="display: flex; justify-content: center" class="center">
      {#if show_not}
      <CircularProgress style="height: 150px; width: 150px;" indeterminate id="to_hide"/>
      {/if}
      {#if shown}
      <h1 id="to_show">User accepted</h1>
    {/if}

  </div>
  </Content>
  <Actions>
      <Button on:click={() => (open5 = false)}>
      <Label>Done</Label>
      </Button>
  </Actions>
  </Dialog>
</div>

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
      <Button on:click={() => (open2 = false)} href="/new">
      <Label>Done</Label>
      </Button>
  </Actions>
  </Dialog>
</div>

<br>
<br>
    <Card>
      <Title>Help Frontend</Title>
      <Actions>
        <ActionButtons>
          <Button on:click={() => open5 = true}>
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
            title="Share" href="https://www.facebook.com/">share</IconButton
          >
        </ActionIcons>
      </Actions>
    </Card>
<br>
<br>
    <Card>
      <Title>Help Backend</Title>
      <Actions>
        <ActionButtons>
          <Button on:click={() => (open5 = true)}>
            <Label>Send Message</Label>
          </Button>
          <Button on:click={() => (open3 = true)}>
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
            title="Share" href="https://www.facebook.com/">share</IconButton
          >
        </ActionIcons>
      </Actions>
    </Card>
<br>
<br>
    <Card>
      <Title>Help Fullstack</Title>
      <Actions>
        <ActionButtons>
          <Button on:click={() => (open5 = true)}>
            <Label>Send Message</Label>
          </Button>
          <Button on:click={() => (open4 = true)}>
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
            title="Share" href="https://www.facebook.com/">share</IconButton
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

