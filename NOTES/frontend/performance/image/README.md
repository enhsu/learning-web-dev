# Frontend performance: image

## Image optimization

Raster images: constructed by a series of pixels, or individual blocks, to form an image

Vector images: constructed using proportional formulas rather than pixels

| Image format | JPEG   | PNG    | SVG    | WebP |
| ------------ | ------ | ------ | ------ | ---- |
| image type   | raster | raster | vector |      |
| When to use  |        |        |        |      |

- Responsive Image
  - `<img src srcset sizes />`
- Art direction
  - `<picture>` + `<source>`
- Difference between `<img srcset sizes />`, `<picture>`, and `CSS Media Query`
  - CSS Media Query: download all images
  - others: browser downloads needed image
- Image CDN(Content Delivery Network)
- Image optivization with module bundler

## Image Sprites

- CSS Sprites
- SVG Sprites

## References

- [Day6, 圖片最佳化](https://ithelp.ithome.com.tw/articles/10268776)
- [Day7, Image Sprites](https://ithelp.ithome.com.tw/articles/10269639)
