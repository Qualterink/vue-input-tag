# input-tag
## Use
```
<InputTag
  :min-length="minLength"
  :max-length="maxLength"
  :max-quantity-tags="maxQuantityTags"
  :show-notyfication="showNotyfication"
  :placeholder="placeholder"/>
```
## Properties

| Properties | Type | Default | Required |
| --- | --- | --- | --- |
| `min-length` | Number | 1 | false |
| `max-length` | Number | 50 | false |
| `max-quantity-tags` | Number | 15 | false |
| `show-notyfication` | Boolean | true | false |
| `placeholder` | String | *Add tag* | false |

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
