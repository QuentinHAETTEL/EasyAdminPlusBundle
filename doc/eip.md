
### Edit In place
Use "edit_in_place" in show or list
```yaml
- { property: title, label: title, edit_in_place: true}
```

Work with date, datetime, time, entity and string in show, list and sublist but if you want to create another type you can.

Eip is customable, here an exemple of String edit in place:

Create your class
```php
<?php
class StringEipType extends AbstractEipType{
    
    public function getTemplate(): string{
        return '@EasyAdmin/edit_in_place/_string.html.twig';
    }

    public function getType(): string{ 
        return 'string'; 
    }
}
``` 

Create your template
```twig
    <input  class="eap-edit-in-place-input" id="input-{{ id }}" type="text" value="{{ valueRaw }}"/>
```

The type is calculated but if you want to use your own type use edit_in_place.type
```yaml
- { property: title, label: title, edit_in_place: {'type': 'string'} }
```

This module comes from prestigeJo / lego but without 
- the deep edit in place
- reload of the line or the list (In easyadminplus you just can reload the field)
- the customization of the list of choice of the entity type. 

These features will come later
