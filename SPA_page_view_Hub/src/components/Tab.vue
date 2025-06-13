<script setup>
import { onMounted } from 'vue';

function stretch(contentId, iconId) {
    const element = document.getElementById(contentId);
    const icon = document.getElementById(iconId);
 
    if ( icon.innerText == "Extend" ) {

      element.style.height = '1000px';
      element.style.overflowY = "auto";
      icon.innerText = "Shorten";
   } else if (icon.innerText == "Shorten") {
      element.style.height = '500px';
      element.style.overflowY = "hidden";
      icon.innerText = "Extend";
   }
   
   console.log("Stretch function is called.");
}

function hide(contentId, iconId) {
    const element = document.getElementById(contentId);
    const icon = document.getElementById(iconId);

      const isOverflowing = element.scrollHeight > element.clientHeight || element.scrollWidth > element.clientWidth;

      if (isOverflowing) {
        console.log('コンテンツがオーバーフローしています！');
      } else {
        console.log('オーバーフローしていません。');
        icon.style.display = "none";
      }
}

</script>

<template>
    <div class="cp_tab">
	<input type="radio" name="cp_tab" id="tab4_1" @click="hide('cp_content4_1', 'stretch-icon4_1')">
	<label for="tab4_1"><slot name="FirstTabTitle">First Tab</slot></label>
	<input type="radio" name="cp_tab" id="tab4_2" @click="hide('cp_content4_2', 'stretch-icon4_2')">
	<label for="tab4_2"><slot name="SecondTabTitle">Second Tab</slot></label>
	<input type="radio" name="cp_tab" id="tab4_3" @click="hide('cp_content4_3', 'stretch-icon4_3')">
	<label for="tab4_3"><slot name="ThirdTabTitle">Third Tab</slot></label>
	<input type="radio" name="cp_tab" id="tab4_4" @click="hide('cp_content4_4', 'stretch-icon4_4')">
	<label for="tab4_4"><slot name="ForthTabTitle">Force Tab</slot></label>
	<input type="radio" name="cp_tab" id="tab4_5" @click="hide('cp_content4_5', 'stretch-icon4_5')">
	<label for="tab4_5"><slot name="FifthTabTitle">Fifth Tab</slot></label>
	<div class="cp_tabpanels">
		<div class="cp_tabpanel">
            <div class="cp_content" ref="cpContent" id="cp_content4_1">
            <slot name="FirstTab">
	    		<h2>First Tab</h2>
    			<p>First Tab text</p>
            </slot>
            </div>
            <button class="stretch-icon" id="stretch-icon4_1" @click="stretch('cp_content4_1', 'stretch-icon4_1')"> Extend </button>
		</div>
		<div class="cp_tabpanel">
            <div class="cp_content" ref="cpContent" id="cp_content4_2">
            <slot name="SecondTab">
    			<h2>Second Tab</h2>
	    		<p>Second Tab text</p>
            </slot>
            </div>
            <button class="stretch-icon" id="stretch-icon4_2" @click="stretch('cp_content4_2', 'stretch-icon4_2')"> Extend </button>
		</div>
		<div class="cp_tabpanel">
            <div class="cp_content" ref="cpContent" id="cp_content4_3">
            <slot name="ThirdTab">
    			<h2>Third Tab</h2>
    			<p>Third Tab text</p>
            </slot>
            </div>
            <button class="stretch-icon" id="stretch-icon4_3" @click="stretch('cp_content4_3', 'stretch-icon4_3')"> Extend </button>
		</div>
		<div class="cp_tabpanel">
            <div class="cp_content" ref="cpContent" id="cp_content4_4">
            <slot name="ForthTab">
    			<h2>Force Tab</h2>
    			<p>Force Tab text</p>
            </slot>
            </div>
            <button class="stretch-icon" id="stretch-icon4_4" @click="stretch('cp_content4_4', 'stretch-icon4_4')"> Extend </button>
		</div>
   		<div class="cp_tabpanel">
            <div class="cp_content" ref="cpContent" id="cp_content4_5">
            <slot name="FifthTab">
    			<h2>Fifth Tab</h2>
    			<p>Fifth Tab text</p>
            </slot>
            </div>
            <button class="stretch-icon" id="stretch-icon4_5" @click="stretch('cp_content4_5', 'stretch-icon4_5')"> Extend </button>
		</div>

	</div>
</div>
</template>

<style scoped>
.cp_tab *, .cp_tab *:before, .cp_tab *:after {
	-webkit-box-sizing: border-box;
	        box-sizing: border-box;
}
.cp_tab ::selection {
	background-color: #4EC6DE;
}
.cp_tab {
	margin: 1em 1em;
}
.cp_tab input[type='radio'] {
	margin: 0;
	padding: 0;
	border: none;
	border-radius: 0;
	outline: none;
	background: none;
	-webkit-appearance: none;
	        appearance: none;
	display: none;
}
.cp_tab > label {
	display: block;
	float: left;
	margin-right: 5px;
	padding: 12px 20px;
	cursor: pointer;
	transition: background-color 0.3s;
}
.cp_tab > label:hover,
.cp_tab > input:checked + label {
	border-radius: 6px 6px 0 0;
	background: #DCEDC8;
}
.cp_tab .cp_tabpanels {
	clear: both;
	perspective: 600px;
	/*min-height: 150px;*//* エリアの高さ */
    min-height: 550px;
}

.cp_tab .cp_tabpanels .cp_tabpanel {
	line-height: 1.4em;
	/*position: absolute;*/
    display: none;
	z-index: 0;
	width: 100%;
	padding: 10px 30px 40px;
	transition: opacity 0.3s, transform 1s;
	transform: rotateX(-20deg);
	transform-origin: top center;
	opacity: 0;
	border: 1px solid #DCEDC8;
	background: #DCEDC8;
}
.cp_tab #tab4_1:checked ~ .cp_tabpanels .cp_tabpanel:nth-of-type(1),
.cp_tab #tab4_2:checked ~ .cp_tabpanels .cp_tabpanel:nth-of-type(2),
.cp_tab #tab4_3:checked ~ .cp_tabpanels .cp_tabpanel:nth-of-type(3),
.cp_tab #tab4_4:checked ~ .cp_tabpanels .cp_tabpanel:nth-of-type(4),
.cp_tab #tab4_5:checked ~ .cp_tabpanels .cp_tabpanel:nth-of-type(5) {
    display: block;
	z-index: 1;
	transform: rotateX(0);
	opacity: 1;
}
@media screen and (max-width: 480px) {
	.cp_tab {
		width: 100%;
	}
	.cp_tab > label {
		display: none;
	}
	.cp_tab .cp_tabpanels .cp_tabpanel {
	position: relative;
	margin-bottom: 1em;
	padding: 0.5em;
	transform: none;
	opacity: 1;
	border: none;
	}
	.cp_tab .cp_tabpanels .cp_tabpanel h2 {
		border-bottom: 1px solid #7CB342;
		padding-bottom: 0.5em;
	}
}

.cp_content{
    height: 500px;
    overflow-y:hidden;
    overflow-x:hidden;
}

.stretch-icon {
    text-align:center;
}
</style>
