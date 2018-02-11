## Create a five star rating widget

_HTML: _

```HTML
<div class="rating-div">
  <span class="star">*</span>
  <span class="star">*</span>
  <span class="star">*</span>
  <span class="star">*</span>
  <span class="star">*</span>
</div>

<div class="button-div" >
  <button class="button">Reset</button>
</div>

```

_CSS :_

```CSS
.rating-div {
    font-size: 5rem;
}

.star { 
  margin: 0px;
  padding-left: 2px;
  cursor: pointer;
  display: inline-block;
  float: left;
}

/* hover functionality*/
.rating-div:hover {
   color: red;
}

.star:hover ~.star{
  color: black;
}


.selected {
  color: yellow;
}

.button {
  width: 100px;
  border-radius: 15%;
  font-size: 20px;
  color: green;
}

.button-div {
  clear: left;
}

```

_jQuery:_ 

```javascript

$('.star').click(function() { 

		var index = $('.star').index(this);

		$('.star').removeClass("selected");

		for(var i = 0; i <= index; i++) {
				$($('.star')[i]).addClass("selected");        
		}

});

$('button').click(function() {
	$('.star').removeClass("selected");	
});

```