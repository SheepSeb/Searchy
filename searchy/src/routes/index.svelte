<script lang="ts">
    import Button, { Label } from '@smui/button';
    import TopAppBar, { Row, Section, Title } from '@smui/top-app-bar';
    import IconButton ,{ Icon }from '@smui/icon-button';
    import Card, {
    Content,
    Actions,
    ActionButtons,
    ActionIcons,
  } from '@smui/card';

  import Dialog from '@smui/dialog';

    let secondaryColor = false;
    let open = false;
</script>


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
          <IconButton class="material-icons" aria-label="Download"
            >file_download</IconButton>
          <IconButton class="material-icons" aria-label="Print this page"
            >print</IconButton>
          <IconButton class="material-icons" aria-label="Bookmark this page"
            >bookmark</IconButton>
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
    <Card>
      <Content>A card with Both.</Content>
      <Actions>
        <ActionButtons>
          <Button>
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
