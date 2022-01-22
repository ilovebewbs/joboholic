<script>
import { each } from "svelte/internal";

import NewsItem from "./components/news_item.svelte";
let news_stuff = [];
(async()=>{
	let res = await fetch("https://api.pushshift.io/reddit/search/submission/?subreddit=javascript_jobs");
	let json = await res.json();
	let stuff = json.data;
	stuff.map((el)=>{
		let title = el.title;
		let id = el.id;
		let author = el.author;
		let url = el.url;
		let score = el.score;
		let time_posted = new Date(el.created_utc*1000).toLocaleString();
		news_stuff = [...news_stuff,{title,author,score,time_posted,url,id}];
	})
})();
</script>
<div class="container text-center">
	<h1> Tech jobs  </h1>
	<p>I built this simple app to learn svelte and will be adding more features to it as i learn more</p>
	<div>
		<a href="https://github.com/ilovebewbs/joboholic">
			<img src="https://img.icons8.com/color/48/000000/github.png" alt="github">
		</a>
		<a href="https://discord.gg/mYbr85WtMN">
			<img src="https://img.icons8.com/color/48/000000/discord.png" alt="discord">
		</a>
	</div>
</div>
<main>
	{#each news_stuff as item (item.id) }
		<NewsItem {item}/>
	{/each}
</main>