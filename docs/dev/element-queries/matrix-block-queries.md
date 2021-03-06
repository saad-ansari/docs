# Matrix Block Queries

Matrix block queries are a type of [element query](README.md) used to fetch your project’s Matrix blocks.

They are implemented by <api:craft\elements\db\MatrixBlockQuery>, and the elements returned by them will be of type <api:craft\elements\MatrixBlock>.

## Creating Matrix Block Queries

You can create a new Matrix block query from Twig by calling `craft.matrixBlocks()`, or from PHP by calling <api:craft\elements\MatrixBlock::find()>.

::: code
```twig
{% set blocks = craft.matrixBlocks()
    .ownerId(100)
    .fieldId(10)
    .type('text')
    .all() %}

{% for block in blocks %}
    <p>{{ block.text }}</p>
{% endfor %}
```
```php
/** @var \craft\elements\MatrixBlock[] $blocks */
$blocks = \craft\elements\MatrixBlock::find()
    ->ownerId(100)
    ->fieldId(10)
    ->type('text')
    ->all();
```
:::

::: warning
In order for the returned Matrix block(s) to be populated with their custom field content, you will need to either set the [fieldId](#fieldid) or [id](#id) parameter.
:::

## Parameters

Matrix block queries support the following parameters:

<!-- BEGIN PARAMS -->

### `archived`

Allowed types

:   [boolean](http://php.net/language.types.boolean)

Defined by

:   [ElementQuery::$archived](api:craft\elements\db\ElementQuery::$archived)

Settable by

:   [archived()](api:craft\elements\db\ElementQuery::archived())



Whether to return only archived elements.


### `asArray`

Allowed types

:   [boolean](http://php.net/language.types.boolean)

Defined by

:   [ElementQuery::$asArray](api:craft\elements\db\ElementQuery::$asArray)

Settable by

:   [asArray()](api:craft\elements\db\ElementQuery::asArray())



Whether to return each element as an array. If false (default), an object
of [$elementType](https://docs.craftcms.com/api/v3/craft-elements-db-elementquery.html#property-elementtype) will be created to represent each element.


### `dateCreated`

Allowed types

:   `mixed`

Defined by

:   [ElementQuery::$dateCreated](api:craft\elements\db\ElementQuery::$dateCreated)

Settable by

:   [dateCreated()](api:craft\elements\db\ElementQuery::dateCreated())



When the resulting elements must have been created.


### `dateUpdated`

Allowed types

:   `mixed`

Defined by

:   [ElementQuery::$dateUpdated](api:craft\elements\db\ElementQuery::$dateUpdated)

Settable by

:   [dateUpdated()](api:craft\elements\db\ElementQuery::dateUpdated())



When the resulting elements must have been last updated.


### `enabledForSite`

Allowed types

:   [boolean](http://php.net/language.types.boolean)

Defined by

:   [ElementQuery::$enabledForSite](api:craft\elements\db\ElementQuery::$enabledForSite)

Settable by

:   [enabledForSite()](api:craft\elements\db\ElementQuery::enabledForSite())



Whether the elements must be enabled for the chosen site.


### `fieldId`

Allowed types

:   [integer](http://php.net/language.types.integer), [integer](http://php.net/language.types.integer)[], [string](http://php.net/language.types.string), [false](http://php.net/language.types.boolean), [null](http://php.net/language.types.null)

Defined by

:   [MatrixBlockQuery::$fieldId](api:craft\elements\db\MatrixBlockQuery::$fieldId)

Settable by

:   [fieldId()](api:craft\elements\db\MatrixBlockQuery::fieldId())



The field ID(s) that the resulting Matrix blocks must belong to.


### `fixedOrder`

Allowed types

:   [boolean](http://php.net/language.types.boolean)

Defined by

:   [ElementQuery::$fixedOrder](api:craft\elements\db\ElementQuery::$fixedOrder)

Settable by

:   [fixedOrder()](api:craft\elements\db\ElementQuery::fixedOrder())



Whether results should be returned in the order specified by [id()](https://docs.craftcms.com/api/v3/craft-elements-db-elementquery.html#method-id).


### `id`

Allowed types

:   [integer](http://php.net/language.types.integer), [integer](http://php.net/language.types.integer)[], [false](http://php.net/language.types.boolean), [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$id](api:craft\elements\db\ElementQuery::$id)

Settable by

:   [id()](api:craft\elements\db\ElementQuery::id())



The element ID(s). Prefix IDs with `'not '` to exclude them.


### `inReverse`

Allowed types

:   [boolean](http://php.net/language.types.boolean)

Defined by

:   [ElementQuery::$inReverse](api:craft\elements\db\ElementQuery::$inReverse)

Settable by

:   [inReverse()](api:craft\elements\db\ElementQuery::inReverse())



Whether the results should be queried in reverse.


### `ownerId`

Allowed types

:   [integer](http://php.net/language.types.integer), [integer](http://php.net/language.types.integer)[], [null](http://php.net/language.types.null)

Defined by

:   [MatrixBlockQuery::$ownerId](api:craft\elements\db\MatrixBlockQuery::$ownerId)

Settable by

:   [ownerId()](api:craft\elements\db\MatrixBlockQuery::ownerId()), [owner()](api:craft\elements\db\MatrixBlockQuery::owner())



The owner element ID(s) that the resulting Matrix blocks must belong to.


### `ownerSiteId`

Allowed types

:   [integer](http://php.net/language.types.integer), [string](http://php.net/language.types.string), [null](http://php.net/language.types.null)

Defined by

:   [MatrixBlockQuery::$ownerSiteId](api:craft\elements\db\MatrixBlockQuery::$ownerSiteId)

Settable by

:   [ownerSiteId()](api:craft\elements\db\MatrixBlockQuery::ownerSiteId()), [ownerSite()](api:craft\elements\db\MatrixBlockQuery::ownerSite())



The site ID that the resulting Matrix blocks must have been defined in, or ':empty:' to find blocks without an owner site ID.


### `ref`

Allowed types

:   [string](http://php.net/language.types.string), [string](http://php.net/language.types.string)[], [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$ref](api:craft\elements\db\ElementQuery::$ref)

Settable by

:   [ref()](api:craft\elements\db\ElementQuery::ref())



The reference code(s) used to identify the element(s).

This property is set when accessing elements via their reference tags, e.g. `{entry:section/slug}`.


### `relatedTo`

Allowed types

:   [integer](http://php.net/language.types.integer), [array](http://php.net/language.types.array), [craft\base\ElementInterface](api:craft\base\ElementInterface), [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$relatedTo](api:craft\elements\db\ElementQuery::$relatedTo)

Settable by

:   [relatedTo()](api:craft\elements\db\ElementQuery::relatedTo())



The element relation criteria.

See [Relations](https://docs.craftcms.com/v3/relations.html) for supported syntax options.


### `search`

Allowed types

:   [string](http://php.net/language.types.string), [array](http://php.net/language.types.array), [craft\search\SearchQuery](api:craft\search\SearchQuery), [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$search](api:craft\elements\db\ElementQuery::$search)

Settable by

:   [search()](api:craft\elements\db\ElementQuery::search())



The search term to filter the resulting elements by.

See [Searching](https://docs.craftcms.com/v3/searching.html) for supported syntax options.


### `siteId`

Allowed types

:   [integer](http://php.net/language.types.integer), [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$siteId](api:craft\elements\db\ElementQuery::$siteId)

Settable by

:   [site()](api:craft\elements\db\ElementQuery::site()), [siteId()](api:craft\elements\db\ElementQuery::siteId())



The site ID that the elements should be returned in.


### `slug`

Allowed types

:   [string](http://php.net/language.types.string), [string](http://php.net/language.types.string)[], [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$slug](api:craft\elements\db\ElementQuery::$slug)

Settable by

:   [slug()](api:craft\elements\db\ElementQuery::slug())



The slug that resulting elements must have.


### `status`

Allowed types

:   [string](http://php.net/language.types.string), [string](http://php.net/language.types.string)[], [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$status](api:craft\elements\db\ElementQuery::$status)

Settable by

:   [status()](api:craft\elements\db\ElementQuery::status())



The status(es) that the resulting elements must have.


### `title`

Allowed types

:   [string](http://php.net/language.types.string), [string](http://php.net/language.types.string)[], [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$title](api:craft\elements\db\ElementQuery::$title)

Settable by

:   [title()](api:craft\elements\db\ElementQuery::title())



The title that resulting elements must have.


### `typeId`

Allowed types

:   [integer](http://php.net/language.types.integer), [integer](http://php.net/language.types.integer)[], [null](http://php.net/language.types.null)

Defined by

:   [MatrixBlockQuery::$typeId](api:craft\elements\db\MatrixBlockQuery::$typeId)

Settable by

:   [type()](api:craft\elements\db\MatrixBlockQuery::type()), [typeId()](api:craft\elements\db\MatrixBlockQuery::typeId())



The block type ID(s) that the resulting Matrix blocks must have.


::: code
```twig
{# fetch the entry's text blocks #}
{% set blocks = entry.myMatrixField
    .type('text')
    .all() %}
```

```php
// fetch the entry's text blocks
$blocks = $entry->myMatrixField
    ->type('text')
    ->all();
```
:::
### `uid`

Allowed types

:   [string](http://php.net/language.types.string), [string](http://php.net/language.types.string)[], [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$uid](api:craft\elements\db\ElementQuery::$uid)

Settable by

:   [uid()](api:craft\elements\db\ElementQuery::uid())



The element UID(s). Prefix UIDs with `'not '` to exclude them.


### `uri`

Allowed types

:   [string](http://php.net/language.types.string), [string](http://php.net/language.types.string)[], [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$uri](api:craft\elements\db\ElementQuery::$uri)

Settable by

:   [uri()](api:craft\elements\db\ElementQuery::uri())



The URI that the resulting element must have.


### `with`

Allowed types

:   [string](http://php.net/language.types.string), [array](http://php.net/language.types.array), [null](http://php.net/language.types.null)

Defined by

:   [ElementQuery::$with](api:craft\elements\db\ElementQuery::$with)

Settable by

:   [with()](api:craft\elements\db\ElementQuery::with()), [andWith()](api:craft\elements\db\ElementQuery::andWith())



The eager-loading declaration.

See [Eager-Loading Elements](https://docs.craftcms.com/v3/eager-loading-elements.html) for supported syntax options.



<!-- END PARAMS -->
