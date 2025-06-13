

<template>
    <div class="article01">
      <h1><slot name="title">Article title</slot></h1>
      <h2><slot name="subtitle">Article subtitle</slot></h2>
      <p><slot name="content">text.</slot></p>
    </div>
</template>

<style scoped>
.article01 {
    position:relative;
    margin: 1em 1em;
    background: #ffffff;
}

.article01 h1 {
    padding: 10px;
	font-size: 1.4em;
	line-height: 1em;
}

.article01 h2 {
    padding: 10px;
	font-size: 1em;
	line-height: 1.2em;
    color: #9b9b9b;
}

.article01 p {
    padding: 10px;
}

.article01 p::after {
	position: absolute;
	top: 5em;
	left: 0;
	width: 20%;
	height: 6px;
	content: '';
	background: #283593;
}

</style>