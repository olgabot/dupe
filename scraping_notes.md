# Scraping notes

Notes about how to scrape ingredients lists of products from various websites
 
## Initial Scope

Let's stick to only hair styling products for now. We can add more haircare later.
 
## CVS

CVS has the very expensive [Oribe Impermeable Anti-Humidity Spray](https://www.cvs.com/shop/oribe-impermeable-anti-humidity-spray-5-5-oz-prodid-1560425?skuId=216563)

Ingredients div:

```html
<cvs-content contentpath="selectedSku.p_Product_Ingredients" scope="gb-sub-container"><p>Ingredients: Hydrofluorocarbon 152a, SD Alcohol 40-B (Alcohol Denat.), Butane, Acrylates/Octylacrylamide Copolymer, Isobutane, Isostearyl Alcohol, Cyclopentasiloxane, Cocodimonium Hydroxypropyl Hydrolyzed Keratin, Tocopheryl Acetate, Retinyl Palmitate, Panthenol, Benzophenone-4, Citral, Hexyl Cinnamal, limonene, Linalool, Parfum/Fragrance.</p></cvs-content>
```

### Product categories:

This hairspray is under: 

```
Home > Shop > Beauty > Hair Care > Styling
```

So for now could do everything in the `Hair Care > Styling` category (and maybe skincare but later)

## Sephora

[Example](https://www.sephora.com/product/no-frizz-weightless-styling-spray-P375667?skuId=1459403&icid2=products%20grid:p375667)

For Sephora, first need to click the "Ingredients" tab in the product lists, the button of class `"css-1vn6k0o"`

```html
<button type="button" class="css-1vn6k0o" data-comp="Box"><div class="css-1kiky8z" data-comp="Box">Ingredients</div></button>
```

Then this box will no longer say `display: none`. But I suppose you could just jump to the box with class `"css-8tl366"` regardless of its display variable.

```html
<div class="css-fisw11" data-comp="Box" style=""><div class="css-8tl366" data-comp="Box">  -Patented Healthy Hair Molecule, OFPMA
<br>
<br> Alcohol Denat., Water, Octafluoropentyl Methacrylate (OFPMA), Dipropylene Glycol, C10-40 Isoalkylamidopropylethyldimonium Ethosulfate, Fragrance, PEG-40 Hydrogenated Castor Oil, Citronellol, Butylphenyl Methylpropional, Citral.</div></div>
```

### Product categories

This hairspray is under:

```
Hair > Hair Styling & Treatments > Hair Styling Products
```

So let's do everything under `Hair Styling Products`.

## Ulta

[Example](https://www.ulta.com/smooth-frizzproof-argan-anti-humidity-finishing-spray?productId=xlsImpprod5180335)

```html
<div class="product-catalog-content current-ingredients" style="display: none;">
Alcohol Denat, Hydrofluorocarbon 152a, Butyl Ester of PVM/MA Copolymer, Glycerin, Aminomethyl Propanol, Argania Spinosa (Argan) Kernel Oil, Cyclopentasiloxane, Phenyl Trimethicone, AMP-Isostearoyl Hydrolyzed Wheat Protein, Panthenol, PEG-75 Lanolin, Ethylhexyl Methoxycinnamate, Dimethyl Stearamine, Pentaerythrityl Tetracaprylate Tetracaprate, Triethyl Citrate, PPG-5-Ceteth-20, Fragrance (Parfum).</div>
```

### Product Categories

This hairspray is under

```
Home	/ Hair / Styling Products / Hairspray / Smooth Frizzproof Argan Anti-Humidity Finishing Spray
```