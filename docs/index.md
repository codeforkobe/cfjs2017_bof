---
<ul id="issues">
</ul>
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script>
axios.get("https://api.github.com/repos/codeforkobe/cfjs2017_bof").then(function(o){
	var url = "https://api.github.com/repos/codeforkobe/cfjs2017_bof/issues?page=1&per_page="+o.data.open_issues_count;
	axios.get(url).then(function(o){
		var base = document.getElementById("issues");
		o.data.forEach(function(d){
			if(d.url){
				li = document.createElement("li");
				a = document.createElement("a");
				a.text = d.title;
				a.href = d.html_url;
				li.appendChild(a);
				base.appendChild(li);
			}
		});
	});
});
</script>

