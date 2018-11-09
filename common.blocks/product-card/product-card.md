# Product Card block

Product card is a logically and functionally independent reusable page component ([block](https://en.bem.info/methodology/key-concepts/#block)) which allows the user to add the product to the cart and navigates to the product page.

By default, the product card layout contains three parts: the image section, the header section and the offer section (which includes the price and the "Add to cart" button).

HTML implementation:

```
<div role="listitem" class="product-card" itemscope itemtype="http://schema.org/Product">
    <div class="product-card__text">
        <h3 class="product-card__header" itemprop="name">
            <a href="#" class="product-card__header-link">Product</a>
        </h3>
        <!-- Additional custom block here -->
    </div>
    <div class="product-card__offer" itemprop="offers" itemscope itemtype="http://schema.org/Offer">
        <!-- Additional custom block here -->
        <span class="product-card__price-wrap" aria-label="$99.9">        
            <span class="product-card__price-currency" itemprop="priceCurrency" content="USD" aria-hidden="true">$</span>
            <span class="product-card__price" itemprop="price" aria-hidden="true">99.9</span>
        </span>           
        <button class="product-card__offer-button">Add to cart</button>
    </div>
    <div class="product-card__image-wrapper">
        <img class="product-card__image" src="img2.jpg" alt="Image description" itemprop="image">
        <!-- Additional custom block here -->
    </div>
</div>

```

> Product card has a vertical layout by default.

## Using

Add `@import "product-card.css";` file to your CSS or `@import "product-card-export.css";` if you need modifiers.

## Modification methods

The default behavior and appereance of the product card block can be modified using next BEM [modification methods](https://en.bem.info/methodology/block-modification/):

*   [Modifiers](https://en.bem.info/methodology/block-modification/#using-a-modifier-to-change-a-block)
*   [Mixes](https://en.bem.info/methodology/block-modification/#using-a-mix-to-change-a-block)
*   [Redefinition levels](https://en.bem.info/methodology/block-modification/#using-redefinition-levels-to-change-a-block)

### Modification by modifiers

Use a [modifier](https://en.bem.info/methodology/block-modification/#using-a-modifier-to-change-a-block) to change one specific instance of a block without affecting surrounding blocks.

The product card block has pedefined modifiers:

```
.product-card_horizontal-row     /* three blocks (image, header, offer) in line */
.product-card_horizontal-col     /* product card is still horisontal but it has two columns: 
                                    image section on the left, header and offer sections on the right */
```

Let's change the product card layout to horizontal with three blocks in line by adding `.product-card_horizontal-row` modifier.

HTML implementation:

```
<div role="listitem" class="product-card product-card_horizontal-row" itemscope itemtype="http://schema.org/Product">
    <!-- BLOCK CONTENT -->
</div>
```

You can add your custom modifiers by [redefinition levels](#Modification%20by%20redefinition%20levels).

### Modification by mixes

Use a [mix](https://en.bem.info/methodology/block-modification/#using-a-mix-to-change-a-block) to place additional BEM entities on the same DOM node as the block to combine the behavior and style of multiple entities without duplicating code and affecting surrounding blocks.

### Modification by redefinition levels

Use a [redefinition levels](https://ru.bem.info/methodology/redefinition-levels) to change the default look of the product card block to fit your project design.

Changes are made to the block by combining the block custom and regular properties from different redefinition levels. Blocks can be [extended and redefined](https://en.bem.info/methodology/redefinition-levels/#changing-the-block-implementation) on a separate level and applied during assembly.

Redefining is the changing the existing (predefined) custom properties of the product card block while extending is the adding new properties to it.

File structure with the new rules for the product card (product-card.css) on the project.blocks level:

```
project/
    library.blocks/
        product-card/
            product-card.css  # original CSS implementation of the product card in the library
    project.blocks/
        product-card/
            product-card.css  # redefinition on the project level
```

The product card block has next predefined custom properties:

```
  /* Layout */
  --product-card-template-colums
  --product-card-layout

  /* Typographic */
  --product-card-font-size
  --product-card-font-weight
  --product-card-font-family
  --product-card-line-height

```

As a result, rules from both redefinition levels should be compiled by your build script and applied to the product card block.
