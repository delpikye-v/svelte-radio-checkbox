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


### Usage
Install the package 
```js
npm install --save svelte-radio-checkbox-z

```

Import the module in the place you want to use:
```js
import RadioCheckBox from "svelte-radio-checkbox-z";
```

#### Snippet
```js
    // js 
    // let selected = ['Radio']  // radio || checkbox
    let selected = 'Radio'
	let options = [
		'Radio',
        'Radio2',
        { label: 'Radio5', value: 'object', disabled: true },
        { label: 'Radio6', value: 'object1', disabled: true, className:"abcd", labelClassName:"addd" },
        // ....
	]

	const setSelectedValue = ({ detail }) => {
		selected = detail
	}

    // html
    <SimpleGroupCheck bind:value={selected} bind:options={options} on:change={setSelectedValue}
	/> // default => style html

    // theme custom
    <SimpleGroupCheck
		bind:value={selected}
		bind:options={options}
		on:change={setSelectedValue}
		theme='tick'
		selectColor='red' 
		tickColor='blue'
	/>
    <!-- 
        /*
        more prop... =>
        theme='in' (see props) =>  theme display
        selectColor='anyColor' => color when selected (label, checkbox)
        tickColor='anyColor' => tick color (only for theme: x/tick)
        unSelectColor='anyColor' => color when no selected
        className = 'className'
        groupName = 'groupName' => default random unique
        disabled={true} => disabled all
        boxSize={16} =>  height of box (default: 14px)
        height={24} => min-heigt option (default 24px)
        vertical={true} => display vertical
        displayBox={true} => display like checkbox (default all: radio)
        checkBox={true}  => input="checkbox"
        */
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
        className: 'itemClass', labelClassName: 'labelClass'
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


#### tickColor (`String`)
Use when `theme` type = `tick` || `x`

`Color of tick when check.`
<small>see demo</small>

#### height
min-height of line-options. `px`. (default: `24px`)

#### boxSize
size of 'radio/checkbox' `px`. (default: `14px`)

#### className
The className added to group.


### Example
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
