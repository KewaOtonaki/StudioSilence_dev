
<template>
    <div class="cp_card01">
        <div class="photo"><slot name="photo"><div class="photo1" style="background: url('/src/assets/img/background49.png') center no-repeat;"></div></slot></div>
        <ul class="details">
            <li class="author"><a href="#"><slot name="author">音無 恠環</slot></a></li>
            <li class="date"><slot name="date">xxxx/xx/xx</slot></li>
            <li class="tags">
                <slot name="tags">
                  <ul>
                      <li><a href="#">dummy</a></li>
                      <li><a href="#">dummy</a></li>
                  </ul>
                </slot>
            </li>
        </ul>
        <div class="description">
            <h1><slot name="title">記事タイトル</slot></h1>
            <h2><slot name="subtitle">サブタイトルやキャッチコピーなど</slot></h2>
            <p class="text"><slot>テキスト..</slot></p>
            <slot name="ReadMore"><a href="#">Read More</a></slot>
            <div class="hidden"><slot name="article">test article text.</slot></div>
        </div>
    </div>
</template>

<style>
.cp_card01 {
	font-size: 14px;
	line-height: 1.45em;
	position: relative;
	overflow: hidden;
	margin: 0 auto 1.6%;
	-webkit-transition: height 0.3s ease;
	        transition: height 0.3s ease;
	border-radius: 3px;
	background: #ffffff;
	-webkit-box-shadow: 0 3px 7px -3px rgba(0, 0, 0, 0.3);
	        box-shadow: 0 3px 7px -3px rgba(0, 0, 0, 0.3);
}
.cp_card01::after {
	font-family: FontAwesome;
	content: '\f1b0';
	position: absolute;
	bottom: 60px;
	right: -20px;
	color: rgba(236, 239, 241, 0.7);
	font-size: 180px;
	transform: rotate(-26deg);
	z-index: 0;
}
.cp_card01:hover .details {
	left: 0;
}
.cp_card01 .photo {
	position: relative;
	height: 200px;
	overflow: hidden;
}
.cp_card01:hover .photo1 {
	-webkit-transform: rotate(5deg) scale(1.3);
	        transform: rotate(5deg) scale(1.3);
}
.cp_card01 .photo .photo1 {
	height: 100%;
	background: url('images.jpg') center no-repeat;
	background-size: cover;
	-webkit-transition: all 0.5s ease;
	        transition: all 0.5s ease;
}
.cp_card01 .details {
	font-family: 'Open Sans';
	position: absolute;
	top: 0;
	left: -100%;
	-webkit-box-sizing: border-box;
	        box-sizing: border-box;
	height: 200px;
	margin: 0;
	padding: 10px 15px;
	list-style: none;
	-webkit-transition: all 0.3s ease;
	        transition: all 0.3s ease;
	color: #ffffff;
	background: rgba(40,53,147, 0.6);
}
.cp_card01 .details > li {
	padding: 3px 0;
}
.cp_card01 .details li::before,
.cp_card01 .details .tags ul::before {
	font-family: FontAwesome;
	margin-right: 10px;
	vertical-align: middle;
}
.cp_card01 .details .author::before {
	content: '\f007';
}
.cp_card01 .details .date::before {
	content: '\f133';
}
.cp_card01 .details .tags ul {
	margin: 0;
	padding: 0;
	list-style: none;
}
.cp_card01 .details .tags ul::before {
	content: '\f02b';
}
.cp_card01 .details .tags li {
	display: inline-block;
	margin-right: 3px;
}
.cp_card01 .details a {
	color: inherit;
}
.cp_card01 .details a:hover {
	color: #283593;
}
.cp_card01 .description {
	position: relative;
	padding: 10px;
	z-index: 1;
}
.cp_card01 .description h1 {
	font-size: 1.4em;
	line-height: 1em;
	margin: 0 0 10px 0;
}
.cp_card01 .description h2 {
	font-size: 1em;
	line-height: 1.2em;
	margin: 1.2% 0;
	color: #9b9b9b;
}
.cp_card01 .description p {
	position: relative;
	margin: 0;
	padding-top: 20px;
}
.cp_card01 .description p::after {
	position: absolute;
	top: 6px;
	left: 0;
	width: 20%;
	height: 6px;
	content: '';
	background: #283593;
}
.cp_card01 .description a {
	float: right;
	margin-bottom: 10px;
	color: #283593;
	text-decoration: none;
}
.cp_card01 .description a::after {
	font-family: FontAwesome;
	margin-left: -10px;
	content: '\f061';
	-webkit-transition: all 0.3s ease;
	        transition: all 0.3s ease;
	vertical-align: middle;
	opacity: 0;
}
.cp_card01 .description a:hover::after {
	margin-left: 5px;
	opacity: 1;
}

.hidden {
    display:none;
}
</style>