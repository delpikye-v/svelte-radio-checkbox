<div align="center">
    <h1>svelte-radio-checkbox-z</h1>
    <strong>
        <a href="https://github.com/delpikye-v/svelte-radio-checkbox">svelte-radio-checkbox-z</a>
    </strong>
    <br />
    <br />
    <a href="https://codesandbox.io/s/svelte-radio-checkbox-z-p64uf">LIVE EXAMPLE</a>
</div>

---
<span>You can customize <b>icon</b>, <b>theme</b> or <b>color</b> for <b>Checkbox/Radio</b></span>

<b><small>Vue /React/ Svelte</small></b>

---
### Usage
Install the package
```js
npm install --save svelte-radio-checkbox-z
```

Import the module in the place you want to use:
```js
import RadioCheckBox from "svelte-radio-checkbox-z";
```

### Snippet
```js
    // js
    // let selected = ['Radio', ...]  // radio || checkbox
    let selected = 'Radio' // radio
	let options = [
                'Radio',
                'Radio2',
                { label: 'Radio5', value: 'object', disabled: true },
                { label: 'Radio6', value: 'object1', disabled: true, className: "abcd", labelClassName: "addd" },
                // .... more
	]

	const setSelectedValue = ({ detail }) => {
            selected = detail
	}

    // default => style html
    <RadioCheckBox bind:value={selected} bind:options={options} on:change={setSelectedValue}/>

    // theme custom
    <RadioCheckBox
		bind:value={selected}
		bind:options={options}
		on:change={setSelectedValue}
		theme='tick'
		selectColor='red'
		tickColor='blue'
	/>

    <!--
    // more =>
    // groupName="item-group-template" // default random unique
    // height="30"          // min-height option
    // boxSize="16"         // box-size 16 x 16
    // className=className
    // disabled=true        // disabled all
    // checkBox=true        // input="checkbox"
    // displayBox=true      // display like checkbox
    // vertical=true        // display vertical
    // selectColor=any      // color when selected
    // unSelectColor=any    // color when no selected
    // hoverColor=any       // color when hover (default like selectColor)
    // tickColor=any        // only theme (type `tick/x`)
    // tabFocusColor        // keypress tab (shawdow box: #000)
    // checkedIcon          // custom icon

    // (boxSize is affected by: `box-sizing: border-box`)
    -->
```


### Props

The following props are accepted:

#### value (`Array` || `String`)

Selected value.

#### change (`Function`)
Update value

#### groupName (`String`)
<p>groupName of radio/checkbox. Default (random) unique of RadioCheckBox</p>

<small>if you want to use multiple RadioCheckBox(same name), you can set the group name</small>
```js
    <RadioCheckBox groupName="groupabc" theme="in" ... />
    <RadioCheckBox groupName="groupabc" theme="fill" ... />
```

#### options (`Array`)
list data like. `[Object, String, ...]`
```js
[
    {
        label: 'Display', value: 'value', disabled: false,  // disabled option
        className: 'itemClass', labelClassName: 'labelClass',
        htmlData, // you change display label by htmlData
        checkedIcon // passing custom checked icon (special)
    },
    ...,
    'value' // => make option { label: value, value: value }
]
```

#### disabled (`boolean`)
Disabled all options. Default `false`

#### checkBox (`boolean`)
Type is checkbox. Default `false` (radio)


#### displayBox (`boolean`)
Show check mark icon like a checkbox. Default `false` (radio)


#### vertical (`boolean`)
Display vertical `true`. Defaut `false`


#### theme (`String`)
```js
    // default (nothing): html
    in: [
        'fill', 'in', 'out',
        'tick', 'tick-fill', 'tick-fill-in',
        'x', 'x-fill', 'x-fill-in'
    ]
```

#### selectColor (`String`)

color when checked. Default <span style="color: #4169E1">#4169E1</span>

#### unSelectColor (`String`)
color when unchecked. Default <span style="color: #cbd1d8;">[#cbd1d8]</span>

#### hoverColor (`String`)
color when hover. Default using (selectColor)


#### tickColor (`String`)
Use when `theme` type = `tick..` || `x..`

`Color of tick when check.`


#### tabFocusColor (`String`)
box shadow color when focus by tab. (`#000`)

#### height (`number` or `number_px`)
min-height of line-options. (default: `24px`)

#### boxSize (`number` or `number_px`)
size of check. (default: `16px`)

#### className
The className added to group.

#### checkedIcon

customize checked icon (see live example)


<br />

###### customize icon check (another solution)
`You should refrain from using this method.`

<small>
With theme: `x...` || `tick...` <br />You can override css to see custom tick.
</small>

```css
/* set your className(.itemClass) for selector unique */
.itemClass.ldk-sv-radio-checkbox .sv-option-checked .sv-option-icon {
    background: url('./assets/images/cal.png') no-repeat center;
}
.itemClass.ldk-sv-radio-checkbox .sv-option-checked .sv-option-icon::before {
    content: '' !important;
}
```

### Example
<a href="https://codesandbox.io/s/svelte-radio-checkbox-z-p64uf">LIVE EXAMPLE</a>

A working example can be found in the `example` directory.

```js
npm install
```
```js
npm run dev
npm run start
```

### License
MIT
