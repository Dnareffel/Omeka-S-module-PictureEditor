Picture Editor (module for Omeka S)
================================


[Picture Editor] is a module for [Omeka S] that integrates the JavaScript library [Leaflet.js]
to enable users to modify picture.


Notes
-----

This module is still in developement and it's not working yet, all the feature coming below are not implemented.


Installation
------------


* From the zip

Download the last release `PictureEditor.zip` from the list of releases (the
master does not contain the dependencies), uncompress it in the `modules`.

* From the source and for development:

If the module was installed from the source, check if the name of the folder of
the module is `PictureEditor`, go to the root of the module, and run either:

```
    composer install
```

```
    npm install
```

Then install it like any other Omeka module.


How it works (TODO) 
-----------

- When an image is imported in the creation of an item add an option 'Picture Editor' to use the module.

![screenshot1]

- In editor mode a window appears with the picture imported in it.

![screenshot2]

- In this mode user will have acces to multiple button that allow him to change the color, the size or add some note on the picture.



Warning
-------

The module is still in development, use it at your own risk.

It’s always recommended to backup your files and your databases and to check
your archives regularly so you can roll back if needed.



License
-------

This module is published under the [CeCILL v2.1] licence, compatible with
[GNU/GPL] and approved by [FSF] and [OSI].

In consideration of access to the source code and the rights to copy, modify and
redistribute granted by the license, users are provided only with a limited
warranty and the software’s author, the holder of the economic rights, and the
successive licensors only have limited liability.

In this respect, the risks associated with loading, using, modifying and/or
developing or reproducing the software by the user are brought to the user’s
attention, given its Free Software status, which may make it complicated to use,
with the result that its use is reserved for developers and experienced
professionals having in-depth computer knowledge. Users are therefore encouraged
to load and test the suitability of the software as regards their requirements
in conditions enabling the security of their systems and/or data to be ensured
and, more generally, to use and operate it in the same conditions of security.

This Agreement may be freely reproduced and published, provided it is not
altered, and that no provisions are either added or removed herefrom.



Contact
-------

Current maintainers of the module for Omeka S:

* Aurélien Le Ferrand (see [Aurelien-LF])


Copyright
---------

* Copyright Aurélien Le Ferrand, 2018-2019

[CeCILL v2.1]: https://www.cecill.info/licences/Licence_CeCILL_V2.1-en.html

[GNU/GPL]: https://www.gnu.org/licenses/gpl-3.0.html

[FSF]: https://www.fsf.org

[OSI]: http://opensource.org

[screenshot1]: https://github.com/Dnareffel/Omeka-S-module-PictureEditor/blob/master/img/step1.png

[screenshot2]:https://github.com/Dnareffel/Omeka-S-module-PictureEditor/blob/master/img/step2.png

[leaflet.js]: https://leafletjs.com/reference-1.3.4.html

[Omeka S]: https://omeka.org/s

[Picture Editor]: https://github.com/Dnareffel/Omeka-S-module-PictureEditor

[Omeka Classic]: https://omeka.org

[Aurelien-LF]: https://github.com/Dnareffel "Aurélien Le Ferrand"


