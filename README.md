Django-Avatar-Crop
==================

Introduction
------------

This is a simple application, which adds ability
to crop your avatar images and works with django-avatar.

If you choose to crop your current avatar, it will create a
new Avatar model from the cropped image, and will make it your
primary avatar

![Screenshot](http://zen4ever.s3.amazonaws.com/avatar_crop_screenshot.png)

Django-Avatar Installation
--------------------------

### Install django-avatar. 

The easy way is just:
    pip install django-avatar

I had some issues with django-avatar and the way it handled relative paths so I created a fork with some small changes which you can find here: https://github.com/mliu7/django-avatar

### Add 'avatar' to your installed apps:

    # settings.py

    INSTALLED_APPS = (
        # ...
        'avatar',
    )

### Add the URLs to your project

    # settings.py

    urlpatterns = patterns('',
        # ...
        (r'^avatar/', include('avatar.urls')),
    )

### Create the tables for avatar

    python manage.py syncdb

Django-Avatar-Crop Installation
-------------------------------
### Download and unpack this repository, putting it on your python path.
### Add it to your installed apps:

    # settings.py

    INSTALLED_APPS = (
        # ...
        'avatar_crop',
    )

### Add the URLs to your project

    # settings.py

    urlpatterns = patterns('',
        # ...
        (r'^avatar_crop/', include('avatar_crop.urls')),
    )

Getting Started
---------------

### Configure parameters in your settings.py

    ##############################################################################
    # Avatar Crop
    AVATAR_CROP_MIN_SIZE = 8

    ##############################################################################
    # Avatar 
    AVATAR_MAX_SIZE = 1024 * 1024 * 5
    AVATAR_STORAGE_DIR = 'avatars'
    AVATAR_ALLOWED_FILE_EXTS = ['.jpg', '.png', '.JPG']
    AVATAR_URL_PATH = '/media/'

You can find more parameters that you can configure in /avatar/settings.py

### Copy the `avatar_crop` static files to your `STATIC_ROOT` folder

### Optionally create templates

Both django-avatar and django-avatar-crop have sample templates you can use for this

### Point your browser at the correct URLs

Try:
    /avatar/add/
    /avatar/change/
    /avatar/delete/
    /avatar_crop/crop/
