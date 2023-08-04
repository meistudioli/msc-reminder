# msc-reminder

[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/msc-reminder) [![DeepScan grade](https://deepscan.io/api/teams/16372/projects/25226/branches/785830/badge/grade.svg)](https://deepscan.io/dashboard#view=project&tid=16372&pid=25226&bid=785830)

&lt;msc-reminder /> provides a notification features for user. It applied slot to open a tunnel let developers put LightDOM elements into ShadowDOM. That means developers could use any design they like as content to display.


![<msc-reminder />](https://blog.lalacube.com/mei/img/preview/msc-reminder.png)


## Basic Usage

&lt;msc-reminder /> is a web component. All we need to do is put the required script into your HTML document. Then follow &lt;msc-reminder />'s html structure and everything will be all set.

- Required Script

```html
<script
  type="module"
  src="https://your-domain/wc-msc-reminder.js">        
</script>
```

- Structure

Put &lt;msc-reminder /> into HTML document. It will have different functions and looks with attribute mutation.

```html
<msc-reminder>
  <script type="application/json">
    {
      "l10n": {
        "confirm": "OK",
        "cancel": "CANCEL"
      },
      "confirm": false,
      "cancel": false,
      "sound": false,
      "vibrate": false,
      "show": false
    }
  </script>

  <!-- content -->
  <div class="content">
    ...
    ...
    ...
  </div>
</msc-reminder>
```

Otherwise, developers could also choose remoteconfig to fetch config for &lt;msc-reminder />.

```html
<msc-reminder
  remoteconfig="https://your-domain/api-path"
>
</msc-reminder>
```

## JavaScript Instantiation

&lt;msc-reminder /> could also use JavaScript to create DOM element. Here comes some examples.

```html
<script type="module">
import { MscReminder } from 'https://your-domain/wc-msc-reminder.js';

const template = document.querySelector('.my-template');

// use DOM api
const nodeA = document.createElement('msc-reminder');
document.body.appendChild(nodeA);
nodeA.appendChild(template.content.cloneNode(true));
nodeA.l10n = {
  confirm: 'Confirm',
  cancel: 'Cancel'
};
nodesA.confirm = true;
nodesA.show = true;

// new instance with Class
const nodeB = new MscReminder();
document.body.appendChild(nodeB);
nodeB.appendChild(template.content.cloneNode(true));
nodesB.confirm = true;
nodesB.cancel = true;
nodesB.sound = true;
nodesB.show = true;

// new instance with Class & default config
const config = {
  l10n: {
    confirm: 'OK',
    cancel: 'CANCEL'
  },
  confirm: true,
  cancel: true,
  sound: true,
  vibrate: true
};

const nodeC = new MscReminder(config);
document.body.appendChild(nodeC);
nodeC.appendChild(template.content.cloneNode(true));
nodeC.show = true;
</script>
```

## Style Customization

Developers could apply styles to decorate &lt;msc-reminder />'s looking.

```html
<style>
msc-reminder {
  --msc-reminder-margin: 16px;
  --msc-reminder-padding: 24px;
  --msc-reminder-shadow-color: 0 0 0; /* r g b */
}
</style>
```

## Attributes

&lt;msc-reminder /> supports some attributes to let it become more convenience & useful.

- **l10n**

Set localization for &lt;msc-reminder />. It will replace button text to anything you like. It should be JSON string Developers could set `confirm` and `cancel` here.

- `confirm`：Set confirm button text. Default is `OK`.
- `cancel`：Set cancel button text. Default is `CANCEL`.

```html
<msc-reminder
  l10n='{"confirm":"OK","cancel":"CANCEL"}'
>
  ...
</msc-reminder>
```

- **confirm**

Set confirm button display or not. Once turn on, &lt;msc-reminder /> will display 「confrim」 button. Default is `false` (not set).

```html
<msc-reminder confirm>
  ...
</msc-reminder>
```

- **cancel**

Set cancel button display or not. Once turn on, &lt;msc-reminder /> will display 「cancel」 button. Default is `false` (not set).

```html
<msc-reminder cancel>
  ...
</msc-reminder>
```

- **sound**

Set sound for &lt;msc-reminder />. Once turn on, &lt;msc-reminder /> will have sound effect when it showed. Default is `false` (not set).

```html
<msc-reminder sound>
  ...
</msc-reminder>
```

- **vibrate**

Set vibrate for &lt;msc-reminder />. Once turn on, &lt;msc-reminder /> will have vibrate effect when it showed. Default is `false` (not set).

```html
<msc-reminder vibrate>
  ...
</msc-reminder>
```

- **show**

Set show for &lt;msc-reminder />. Once turn on, &lt;msc-reminder /> will show. Default is `false` (not set).

```html
<msc-reminder show>
  ...
</msc-reminder>
```

## Properties

| Property Name | Type | Description |
| ----------- | ----------- | ----------- |
| l10n | Object | Getter / Setter for l10n. It will replace some UI text to anything you like. Developers could set `confirm` and `cancel`. |
| confirm | Boolean | Getter / Setter for confirm. Once true, &lt;msc-reminder /> will display 「confirm」 button. Default is `false`. |
| cancel | Boolean | Getter / Setter for cancel. Once true, &lt;msc-reminder /> will display 「cancel」 button. Default is `false`. |
| sound | Boolean | Getter / Setter for sound. Once true, &lt;msc-reminder /> will have sound effect when it showed. Default is `false`. |
| vibrate | Boolean | Getter / Setter for vibrate. Once turn, &lt;msc-reminder /> will have vibrate effect when it showed. Default is `false`. |
| show | Boolean | Getter / Setter for show. Once true, &lt;msc-reminder /> will show. Default is `false`. |

## Events

| Event Signature | Description |
| ----------- | ----------- |
| msc-reminder-confirm | Fired when user press confirm. |
| msc-reminder-cancel | Fired when user press cancel. |

## Reference

- [&lt;msc-reminder />](https://blog.lalacube.com/mei/webComponent_msc-reminder.html)
- [WEBCOMPONENTS.ORG](https://www.webcomponents.org/element/msc-reminder)
- [YouTube](https://youtube.com/shorts/Dy2Ev1XoDCs)
