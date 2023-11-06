---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Research
---

<div id="onecol">
            <div id="subheader">Publications</div>
            {% for pub in site.data.publications %}
            <table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor">{{ pub.author}}</div>
						<div id="pubTitle">{{ pub.title }}</div>
						{{ pub.venue }}
					</td>
					
			        <td id="rightcol">
					{% if pub.image %}
					<img src='assets/images/teasers/{{ pub.image}}'>
					{% endif %}
					</td>
			    </tr>
			</table>
			<div id="paperlink">
                {% if pub.paper %}
				<a href="assets/papers/{{ pub.paper }}">preprint</a>
                {% endif %}
                {% if pub.appendix %}
				<a href="{{pub.appendix}}">appendix</a>
                {% endif %}
                {% if pub.link %}
				<a href="{{pub.link}}">link</a>
                {% endif %}
                {% if pub.slide %}
                <a href="assets/slides/{{pub.slide}}">slides</a>
                {% endif %}
                {% if pub.video %}
                <a href="assets/videos/{{pub.video}}">video</a>
                {% endif %}
                {% if pub.talk %}
                <a href="assets/videos/{{pub.talk}}">talk</a>
                {% endif %}
			</div>
            {% endfor %}
            <!-- <table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor"><u>Gromit Yeuk-Yin Chan</u>, Tung Mai, Anup Rao, Ryan Rossi, Fan Du, Cláudio T. Silva and Juliana Freire</div>
						<div id="pubTitle">Interactive Audience Expansion On Large Scale Online Visitor Data</div>
						International Conference on Knowledge Discovery & Data Mining (KDD 2021)
					</td>
			        <td id="rightcol"><img src='images/teasers/chan-kdd2021.png'></td>
			    </tr>
			</table>
			<div id="paperlink">
				<a href="papers/chan-kdd2021.pdf">preprint</a>
			</div>
            <table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor"><u>Gromit Yeuk-Yin Chan</u>, Fan Du, Ryan Rossi, Anup Rao, Eunyee Koh, Cláudio T. Silva and Juliana Freire</div>
						<div id="pubTitle">Real-Time Clustering for Large Sparse Online Visitor Data</div>
						The Web Conference (WWW 2020) (Accepted for <strong>Oral Presentation</strong>)
					</td>
			        <td id="rightcol"><img src='images/teasers/chan-www2020.png'></td>
			    </tr>
			</table>
			<div id="paperlink">
				<a href="papers/chan-www2020.pdf">preprint</a>
				<a href="https://dl.acm.org/doi/abs/10.1145/3366423.3380183">link</a>
				<a href="slides/WWW2020.pdf">slides</a> 
			</div>
            <table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor"><u>Gromit Yeuk-Yin Chan</u>, Luis Gustavo Nonato, Alice Chu, Preeti Raghavan, Viswanath Aluru and Cláudio T. Silva</div>
						<div id="pubTitle">Motion Browser: Visualizing and Understanding Complex Upper Limb Movement Under Obstetrical Brachial Plexus Injuries</div>
						IEEE Transactions on Visualization and Computer Graphics (VIS 2019)
					</td>
			        <td id="rightcol"><img src='images/teasers/chan-vast2019.png'></td>
			    </tr>
			</table>
			<div id="paperlink">
				<a href="papers/chan-vast2019.pdf">preprint</a>
				<a href="videos/video_vast19.mp4">video</a>
				<a href="videos/talk_vast19.mp4">talk@VIS</a>
			</div>	
			<table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor"><u>Gromit Yeuk-Yin Chan</u>, Panpan Xu, Zeng Dai and Liu Ren</div>
						<div id="pubTitle">ViBr: Visualizing Bipartite Relations at Scale with the Minimum Description Length Principle</div>
						IEEE Transactions on Visualization and Computer Graphics (VIS 2018)
					</td>
			        <td id="rightcol"><img src='images/teasers/chan-vast2018.jpg'></td>
			    </tr>
			</table>
			<div id="paperlink">
				<a href="papers/chan-vast2018.pdf">preprint</a>
				<a href="papers/chan-vast2018-appendix.pdf">supplementary materials</a>
				<a href="videos/video_vast18.mp4">video</a>
				<a href="videos/talk_vast18.mp4">talk@VIS</a>
			</div>	
			<table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor"><u>Yeuk-Yin Chan</u>, Fernando Chirigati, Harish Doraiswamy, Cláudio T. Silva, and Juliana Freire</div>
						<div id="pubTitle">Querying and Exploring Polygamous Relationships in Urban Spatio-Temporal Data Sets.</div>
						Proceedings of the 2017 ACM International Conference on Management of Data (SIGMOD)
					</td>
			        <td id="rightcol"><img src='images/teasers/chan-sigmod2017.png'></td>
			    </tr>
			</table>			
			<div id="paperlink">
				<a href="http://dl.acm.org/citation.cfm?id=3058741">link</a>
				<a href="papers/chan-sigmod2017.pdf">preprint</a>
			</div>
			<table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor">Quan Li, Peng Xu, <u>Yeuk Yin Chan</u>, Yun Wang, Zhipeng Wang, Huamin Qu, and Xiaojuan Ma</div>
						<div id="pubTitle">A Visual Analytics Approach for Understanding Reasons behind Snowballing and Comeback in MOBA Games</div>
						IEEE Transactions on Visualization and Computer Graphics (VIS 2016)
					</td>
			        <td id="rightcol"><img src='images/teasers/li-vast2016.png'></td>
			    </tr>
			</table>
			<div id="paperlink">
				<a href="http://ieeexplore.ieee.org/abstract/document/7534855/">link</a>
				<a href="papers/li-vast2016.pdf">preprint</a>
			</div>
			<table>
			    <tr>
			        <td id="leftcol">
			        	<div id="pubAuthor"><u>Yeuk Yin Chan</u>, and Huamin Qu</div>
						<div id="pubTitle">FinaVistory: Using Narrative Visualization to explain social and Economic relationships in financial news.</div>
						2016 International Conference on Big Data and Smart Computing (BigComp)
					</td>
			        <td id="rightcol"><img src='images/teasers/chan-bigcomp2016.png'></td>
			    </tr>
			</table>
			<div id="paperlink">
				<a href="http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=7425798&url=http%3A%2F%2Fieeexplore.ieee.org%2Fxpls%2Fabs_all.jsp%3Farnumber%3D7425798">link</a>
				<a href="papers/chan-bigcomp2016.pdf">preprint</a>
			</div>
			<table>
			    <tr>
			        <td id="leftcol">
					<div id="pubAuthor">Abishek Puri, Dongyu Liu, Shaoyu Chen, Siwei Fu, Tianyu Wang, <u>Yeuk-Yin Chan</u> and Huamin Qu</div>
					<div id="pubTitle">ParkVis: A visual analytic system for anomaly detection in DinoFun World</div>
					Visual Analytics Science and Technology (VAST) Challenge 2015
					</td>
			        <td id="rightcol"><img src='images/teasers/puri-vast2015.png'></td>
			    </tr>
			</table> 
			<div id="paperlink">
				<a href="http://ieeexplore.ieee.org/xpl/articleDetails.jsp?reload=true&arnumber=7347641" id="paperlink">link</a>
				<a href="papers/puri-vast2015.pdf">preprint</a>
			</div> -->


			<!-- <div id="subheader">Services</div>
            <div id="subsubheader">Reviewer</div>
            <div>IEEE VIS (InfoVis) 2019</div>
            <div>EuroVis 2017,2019</div>
            <div>IEEE CG&A</div>

			<div id="subheader">Media Coverage</div>
			<div><a href="http://engineering.nyu.edu/news/2016/11/03/student-hackers-team-manhattan-da-fight-human-trafficking">Student Hackers Team Up with Manhattan DA to Fight Human Trafficking</a></div>
			<div><a href="news/newsdetail1690.html">科網雲圖：財經新聞大數據 (in Chinese)</a></div>
			<div><a href="http://www.takungpao.com.hk/hongkong/text/2016/0803/13662.html">科大生研大數據 獲邀海外演講 (in Chinese)</a></div> -->

		</div>
<!--end Content-->