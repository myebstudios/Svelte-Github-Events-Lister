<script>
  export let name = "";
  export let date = "";
  export let url = "";
</script>

<!-- Event card -->
<div class="demo-card-event mdl-card mdl-shadow--2dp mdl-cell mdl-cell--4-col">
  <div class="mdl-card__title mdl-card--expand">
    <h4>
      {name}<br>
      {date}<br>
      <!-- 7-11pm -->
    </h4>
  </div>
  <div class="mdl-card__actions mdl-card--border">
    <a href="http://www.github.com/{url}" target="_blank" class="mdl-button mdl-button--colored mdl-js-button mdl-js-ripple-effect">
      Visit Repo
    </a>
    <div class="mdl-layout-spacer"></div>
    <i class="material-icons">link</i>
  </div>
</div>

<style>
  .demo-card-event.mdl-card {
    width: 256px;
    height: 256px;
    background: #3e4eb8;
    margin: 10px;
  }
  .demo-card-event > .mdl-card__actions {
    border-color: rgba(255, 255, 255, 0.2);
  }
  .demo-card-event > .mdl-card__title {
    align-items: flex-start;
  }
  .demo-card-event > .mdl-card__title > h4 {
    margin-top: 0;
  }
  .demo-card-event > .mdl-card__actions {
    display: flex;
    box-sizing: border-box;
    align-items: center;
  }
  .demo-card-event > .mdl-card__actions > .material-icons {
    padding-right: 10px;
  }
  .demo-card-event > .mdl-card__title,
  .demo-card-event > .mdl-card__actions,
  .demo-card-event > .mdl-card__actions > .mdl-button {
    color: #fff;
  }
</style>