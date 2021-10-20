<!-- App.svelte -->
<script>
	import { Router, Route } from "svelte-routing";
	import Index from "./views/Index.svelte";
	import Start from "./views/Start.svelte";
	import Free from "./views/Free.svelte";
  
	export let url = "";
  </script>
  <Router url="{url}">
	<Route path="/" component="{Index}" />
	<Route path="/start" component="{Start}" />
	<Route path="/freedom" component="{Free}" />
  </Router>
  