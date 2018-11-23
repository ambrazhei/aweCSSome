# Rating block

**Rating** is a logically and functionally independent reusable page component ([block](https://en.bem.info/methodology/key-concepts/#block)), which reflect an item`s (product, article and etc.) rating

HTML implementation:

```html
<!-- If you use schema.org you should using rating block in object of review. See example below  -->

<section class="product-card" itemscope itemtype="https://schema.org/Product">
  <h1 class="product-card__heading" itemprop="name">Example product</h1>

  <div class="rating" itemprop="aggregateRating" itemscope itemtype="http://schema.org/AggregateRating">
    <span class="rating__value" aria-label="Rating 4.5 from 5 based on 10 reviews">
      <!--- Set here you rating image for visualizition. -->
    </span>
    <a class="rating__review-count-wrap" href="#see-all-reviews" aria-label="See all reviews">
      <span class="rating__review-count" itemProp="reviewCount" aria-hiden="true">10</span>
      <span class="rating__review-count-text" aria-hiden="true">reviews</span>
    </a>
    <meta itemProp="bestRating" content="5">
    <meta itemProp="worstRating" content="4">
    <meta itemProp="ratingValue" content="4.5">
  </div>
  ... <!-- Remaining product  card code -->
</section>
```

HTML implementation without microdata:

```html
<div class="rating">
    <span class="rating__value" aria-label="Rating 4.5 from 5 based on 10 reviews">
      <!--- Set here you rating image for visualizition. -->
    </span>
    <a class="rating__review-count" href="#see-all-reviews" aria-label="See all reviews">
        <span class="rating__review-count" aria-hiden="true">10 reviews</span>
    </a> 
</div>
```
