Picture Editor (module for Omeka S)
================================


[IIIF Server] is a module for [Omeka S] that integrates the [IIIF specifications]
and a simple image server (similar to a basic [IIP Image]) to allow to process
and share instantly images of any size and medias (pdf, audio, video, 3D...) in
the desired formats.



Installation
------------


* From the zip

Download the last release [`PictureEditor.zip`] from the list of releases (the
master does not contain the dependencies), uncompress it in the `modules`.

* From the source and for development:

If the module was installed from the source, check if the name of the folder of
the module is `PictureEditor`, go to the root of the module, and run either:

```
    composer install
```

Then install it like any other Omeka module.


Notes
-----

Note: To keep old options from [Universal Viewer], upgrade it to version 3.4.3
before enabling of IiifServer. Else, simply set them in the config form.

When you need to display big images (bigger than 10 to 50 MB according to your
server), it is recommended to upload them as "Tile", so tiles will be
automatically created (see below).

Options for the IIIF server can be changed in the helpers "IiifCollection.php",
"IiifManifest.php" and "IiifInfo.php" of the module, and via the events.

See below the notes for more info.

* Using externally supplied IIIF manifest and images

If you are harvesting data (via OAI-PMH, for instance) from another system where
images are hosted and exposed via IIIF, you can use a configurable metadata
field to supply the manifest to the Universal Viewer. In this case, no images
are hosted in the Omeka record, but one of the metadata fields has the URL of
the manifest hosted on another server.

For example, you could set the alternative manifest element to "Dublin Core:Has Format"
in the module configuration, and then put a URL like "https://example.com/iiif/HI-SK20161207-0009/manifest"
in the specified element of a record. The Universal Viewer included on that
record’s display page will use that manifest URL to retrieve images and metadata
for the viewer.

* Filtering data of manifests [TODO]

The module creates manifests with all the metadata of each record. The event
`uv.manifest` can be used to modify the exposed data of a manifest for items and
collections. For example, it is possible to modify the citation, to remove some
metadata or to change the thumbnail.


IIIF Server
-----------

All routes of the IIIF server are defined in `config/module.config.php`.
They follow the recommandations of the [IIIF specifications].

To view the json-ld manifests created for each resources of Omeka S, simply try
these urls (replace :id by a true id):

- https://example.org/iiif/collection/:id for item sets;
- https://example.org/iiif/collection/:id,:id,:id,:id... for multiple resources;
- https://example.org/iiif/:id/manifest for items;
- https://example.org/iiif-img/:id/info.json for images files;
- https://example.org/iiif-img/:id/:region/:size/:rotation/:quality.:format for
  images, for example: https://example.org/iiif-img/1/full/full/270/gray.png;
- https://example.org/ixif-media/:id/info.json for other files;
- https://example.org/ixif-media/:id.:format for the files.

By default, ids are the internal ids of Omeka S, but it is recommended to use
your own single and permanent identifiers that don’t depend on an internal
pointer in a database. The term `Dublin Core Identifier` is designed for that
and a record can have multiple single identifiers. There are many possibilities:
named number like in a library or a museum, isbn for books, or random id like
with ark, noid, doi, etc. They can be displayed in the public url with the
modules [Ark] and/or [Clean Url].

If item sets are organized hierarchically with the plugin [Collection Tree], it
will be used to build manifests for item sets.



TODO / Bugs
-----------

- When a item set contains non image items, the left panel with the index is
  displayed only when the first item contains an image.
- Separate IIIF Server (creation of manifests and media infos) and image server
  (tiling and display compliant with iiif specifications).
- Create thumbnails from the tiled image, not from the original.
- Support curl when allow_url_fopen and allow_url_include are forbidden.


Warning
-------

The module is still in development, use it at your own risk.

It’s always recommended to backup your files and your databases and to check
your archives regularly so you can roll back if needed.


Troubleshooting
---------------




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

The module uses the [Deepzoom library] and [Zoomify library], the first based on
[Deepzoom] of Jeremy Buggs (license MIT) and the second of various authors
(license [GNU/GPL]). See files inside the folder `vendor` for more information.


Contact
-------

Current maintainers of the module for Omeka S:
* Aurélien Le Ferrand (see [Daniel-KM])


Copyright
---------

* Copyright Aurélien Le Ferrand, 2018-2019



[Omeka S]: https://omeka.org/s

[Omeka Classic]: https://omeka.org

[Aurelien-LF]: https://github.com/Dnareffel "Aurélien Le Ferrand"


