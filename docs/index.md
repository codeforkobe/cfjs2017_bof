
Code for Japan SUMMIT 2017 の BoF の枠で、話したいトピックを募集しています。

新規テーマは[こちら](https://github.com/codeforkobe/cfjs2017_bof/issues/new)から登録をお願いします！

「お！このテーマ参加するぞ！」と思った方は「LGTM」など適当に反応して頂けると、人数にカウントします。

補足で話したいことをコメントで追記するなども大歓迎！

---
現在登録されているトピック

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

