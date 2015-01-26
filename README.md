phpThumb
========

phpThumb for CakePHP.

By default, phpThumb isn't set up as a class to work with CakePHP.  This is an older version of phpThumb, but it has been designed to work with CakePHP.

Last tested on CakePHP 2.6.1

# How to Install

1) Place this folder in your app/Vendor (or vendors) folder
   app/Vendor/phpThumb

2) Where you want to use phpThumb, just use:

```
App::import('Vendor', 'phpThumb', array('file' => 'phpThumb' . DS . 'phpthumb.php'));
```

For example:

```
App::import('Vendor', 'phpThumb', array('file' => 'phpThumb' . DS . 'phpthumb.php'));

$phpThumb = new phpthumb();
$phpThumb->setSourceFilename($pathToFile);
$phpThumb->setCacheDirectory(CACHE);
$phpThumb->setParameter('w', $options['width']);
$phpThumb->setParameter('h', $options['height']);
$phpThumb->setParameter('f', $format);

if ($phpThumb->generateThumbnail()) {
	if ($phpThumb->RenderToFile($destination)) {
        chmod($destination, 0644);
		return true;
	} else {
        return false;
    }
} else {
	return false;
}
```

Where
$pathToFile is the current path to the file - if uploading an image, this could be the tmp_name

$destination is where you want to save the image too.