## Theoretical part
https://api.jquery.com/parents/
http://api.jquery.com/show/
http://api.jquery.com/hide/
http://api.jquery.com/html/
http://api.jquery.com/on/


## Practical part
### 1. There should be a reaction when click on type label
```javascript
  $(document).on('click', '.abilities div', function(){
    alert("hey!")
  })
```

### 2. When click on type lable we need a type
```javascript
  $(document).on('click', '.abilities div', function(event){
    curentType = $(event.target).html();
    alert("hey! " + curentType)
  })
```

### 3. All the cards should be hidden and then all
required should be shown back
```javascript
  $(document).on('click', '.abilities div', function(event){
    curentType = $(event.target).html();
    $(".rectangle").hide()
    $("."+curentType).parents('.rectangle').show()
  })
```

### 4. When second click is fired on the same type label, all cards should be shown
```javascript
var displayedType = ''

$( document ).ready(function() {
  for(var i=1; i<19; i++){
   renderPokemonFromAPI(i)
  }
  $(".pokemon").click(renderProfile)
  $(document).on('click', '.abilities div', function(event){
    curentType = $(event.target).html();
    if (displayedType == curentType) {
       $(".rectangle").show()
       displayedType = ''
    } else {
      $(".rectangle").hide()
      $("."+curentType).parents('.rectangle').show()
      displayedType = curentType
    }
  })
});
```

