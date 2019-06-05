# easyValidator
Easy JQuery validator

## Getting Started
This is a way to validate your form, from an easy way.

### Prerequisites
* JQuery
* Bootstrap
* Popper

### Installing

First, you need to put the JQuery, the Bootstrap, and the Popper references on the head of your HTML.

Then you need to create your form, like this:

```html
<form class="testform">
    <div>
      <label>InputTest</label>
      <div>
        <input type="text" id="InputTest" placeholder="Test">
      </div>
    </div>
    <div>Checkbox</div>
      <div class="checkbox-group tres">
        <div>
          <input type="checkbox" class="gridCheck1 dsds">
          <label for="gridCheck1">
            Example checkbox
          </label>
         <div>
           <input type="checkbox" class="gridCheck2 dsds">
           <label for="gridCheck2">
            Example checkbox
           </label>
          </div>
        </div>
      </div>
    <div>
      <button class="button" type="submit">Validate</button>                
    </div>
</form>
```
Then, create a javascript file, and reference it in your html head too, under the other references,
and call your div with the easyMenu method.
```javascript
$('.testform').easyValidator({
    options: {
        inputs: {
           text: {
              type: 'input',
              reference: 'id',
              referencevalue: 'InputTest',
              msg: 'The input can not be null.',
              showtype: 'popover',
              placement: 'right'
           },
           checkbox: {
              type: 'group',
              parenttype: 'class',
              parentvalue: 'checkbox-group',                    
              msg: 'You must select a checkbox.',
              showtype: 'p'
           },
           button: {
              reference: 'class',
              referencevalue: 'button',
           }
        }
     }
});
```
If you press the button, and the input is blank, the message will be show.

This plugin don't need you to create an onclick event to work, this plugin is able to find the button that you put inside the method easyValidator and create the event for you.

The names for every input inside the inputs object, can be whatever you want, but it can not be repeated.

This are all the objects inside the easyValidator method:

| Command | Description |
| --- | --- |
| options | This is the main object. It's required to work. |
| inputs | This object contains all the input objects. |
| style | This value contains the style for the validation, this can be only blinked or normal. | 
| separator | In this variable you specify the main character you will use to separate a text. |
    
Inside the input object, are the inputs that you need to validate, this objects need the next values to work:

| Command | Description |
| --- | --- |
| type | This value has the type of input that you show on the form, it can be a group or a input, for example for group of checkbox you need to put group and on an input type email you need to put input.|

If your type value is input, the values for the object would be: 

| Command | Description |
| --- | --- |
| reference | This is the type of attribute that you use to reference your input on the validator, only can be id or class. This is only used when your type value is input |
| referencevalue | This is the value that you use to reference your input. This is only used when your type value is input |
| msg | This is the message that you will show when the validation event shows.  |
| showtype | This is the type of your message would be show on the form. It can be p or popover. |
| showtype > p | This will create a p element under the input with the message that you put on the msg value.   |
| showtype > popover | This will show a popover tooltip inside your input, the place that you can put the tooltip is variable inside the value named placement. |
| placement | This value only works with the popover element, if you don't create this value the default placement will be right.  |

If your type value is group, the values for the object would be: 

| Command | Description |
| --- | --- |
| parenttype | This is the type of attribute that you use to reference the parent of your group of inputs to catch it on the validator, only can be id or class. This is only used when your type value is group. |
| parentvalue | This is the value that you use to reference your group of inputs. This is only used when your type value is group |
| msg | This is the message that you will show when the validation event shows.  |
| showtype | This is the type of your message would be show on the form. It can be p or popover. |
| showtype > p | This will create a p element under the input with the message that you put on the msg value.   |
| showtype > popover | This will show a popover tooltip inside your input, the place that you can put the tooltip is variable inside the value named placement. |
| placement | This value only works with the popover element, if you don't create this value the default placement will be right.  |


## Creating a standard validator

This is the way to create a standard validator with an input and a group of checkbox, and the button for the form:
```javascript
$('.testform').easyValidator({
    options: {
        inputs: {
           text: {
              type: 'input',
              reference: 'id',
              referencevalue: 'InputTest',
              msg: 'The input can not be null.',
              showtype: 'popover',
              placement: 'right'
           },
           checkbox: {
              type: 'group',
              parenttype: 'class',
              parentvalue: 'checkbox-group',                    
              msg: 'You must select a checkbox.',
              showtype: 'p'
           },
           button: {
              reference: 'class',
              referencevalue: 'button',
           },
        }
     }
});
```
If you need to validate more elements included in the html form, you need to put the reference for that input or that group of inputs on the easyValidator method.

## Deployment
This is a complete example of the navbar working, you only need to set the jquery and bootstrap cdn on your head, and then put the easyMenu.js.

```html
<html>
    <head>
    <script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
    <script src="js/easyValidator.js"></script>
    <link rel="stylesheet" href="css/easyValidator.css" />        
    <script>
       $(document).ready(function() {
          $('.testform').easyValidator({
            options: {
                inputs: {
                   text: {
                      type: 'input',
                      reference: 'id',
                      referencevalue: 'InputTest',
                      msg: 'The input can not be null.',
                      showtype: 'popover',
                      placement: 'right'
                   },
                   checkbox: {
                      type: 'group',
                      parenttype: 'class',
                      parentvalue: 'checkbox-group',                    
                      msg: 'You must select a checkbox.',
                      showtype: 'p'
                   },
                   button: {
                      reference: 'class',
                      referencevalue: 'button',
                   },
                }
             }
          });
       });
   </script>
   </head>
   <body>
      <form class="testform">
        <div>
          <label>InputTest</label>
          <div>
            <input type="text" id="InputTest" placeholder="Test">
          </div>
        </div>
        <div>Checkbox</div>
          <div class="checkbox-group tres">
            <div>
              <input type="checkbox" class="gridCheck1 dsds">
              <label for="gridCheck1">
                Example checkbox
              </label>
             <div>
               <input type="checkbox" class="gridCheck2 dsds">
               <label for="gridCheck2">
                Example checkbox
               </label>
              </div>
            </div>
          </div>
        <div>
          <button class="button" type="submit">Validate</button>                
        </div>
    </form>
  </body>
</html>
```

## Built With

* [JQuery](https://jquery.com/) - The web framework used
* [Bootstrap](https://getbootstrap.com/docs/4.3/components/navbar/) - The Bootstrap Tooltip
* [Bootstrap Popover](https://getbootstrap.com/docs/4.0/components/popovers/) The Bootstrap Popover

## Contributing

If you detect any problem, please let me know, any comments will be welcome.

## Versioning

See the [tags on this repository](https://github.com/Mantixd/easyValidator/tags). 

## Authors

* **Ricardo Pérez** - *Initial work* - [Mantixd](https://github.com/Mantixd)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details

## Donation

If my work likes you or helps you a little, i will apreciate it your help with this project and others coming:

<a href="https://www.buymeacoffee.com/ricardoperez" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/black_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>


<a href="https://paypal.me/MantixSystems" target="_blank"><img width="150" height="150" src="http://chittagongit.com/images/paypal-donate-icon/paypal-donate-icon-15.jpg"></a>




