# Select the rating block

**Select the rating** is a logically and functionally independent reusable page component ([block](https://en.bem.info/methodology/key-concepts/#block)), which add ability for user to select item`s rating

HTML implementation for use outside the form:

```html
<form action="#" class="select-rating">
  <div class="select-rating"  role="group" aria-labelledby="star-rating">
      <b class="select-rating__head" id="star-rating">Star rating:</b>
      
      <input class="select-rating__input" type="radio" id="rate5" name="rating" value="5">
      <label class="select-rating__label" for="rate5" title="Amazing">5 stars</label>

      <input class="select-rating__input" type="radio" id="rate4" name="rating" value="4">
      <label class="select-rating__label" for="rate4" title="Very good">4 stars</label>

      <input class="select-rating__input" type="radio" id="rate3" name="rating" value="3">
      <label class="select-rating__label" for="rate3" title="Average">3 stars</label>

      <input class="select-rating__input" type="radio" id="rate2" name="rating" value="2">
      <label class="select-rating__label" for="rate2" title="Not good">2 stars</label>

      <input class="select-rating__input" type="radio" id="rate1" name="rating" value="1">
      <label class="select-rating__label" for="rate1" title="Terrible">1 star</label>
  </div>
</form>
```

HTML implementation for use into the other form:

```html
<div class="select-rating" role="group" aria-labelledby="star-rating">
    <b class="select-rating__head" id="star-rating">Star rating:</b>
    
    <input class="select-rating__input" type="radio" id="rate5" name="rating" value="5">
    <label class="select-rating__label" for="rate5" title="Amazing">5 stars</label>

    <input class="select-rating__input" type="radio" id="rate4" name="rating" value="4">
    <label class="select-rating__label" for="rate4" title="Very good">4 stars</label>

    <input class="select-rating__input" type="radio" id="rate3" name="rating" value="3">
    <label class="select-rating__label" for="rate3" title="Average">3 stars</label>

    <input class="select-rating__input" type="radio" id="rate2" name="rating" value="2">
    <label class="select-rating__label" for="rate2" title="Not good">2 stars</label>

    <input class="select-rating__input" type="radio" id="rate1" name="rating" value="1">
    <label class="select-rating__label" for="rate1" title="Terrible">1 star</label>
</div>
```
