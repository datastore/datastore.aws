# datastore-aws

## datastore implementation for aws

See [datastore](https://github.com/datastore/datastore).


### Install

From pypi (using pip):

    sudo pip install datastore.aws

From pypi (using setuptools):

    sudo easy_install datastore.aws

From source:

    git clone https://github.com/datastore/datastore.aws/
    cd datastore.aws
    sudo python setup.py install


### License

datastore.aws is under the MIT License.

### Contact

datastore.aws is written by [Juan Batiz-Benet](https://github.com/jbenet).
It was extracted from [datastore](https://github.com/datastore/datastore)
in Feb 2013.

Project Homepage:
[https://github.com/datastore/datastore.aws](https://github.com/datastore/datastore.aws)

Feel free to contact me. But please file issues in github first. Cheers!


### Hello World

    >>> import datastore.aws
    >>> from boto.s3.connection import S3Connection
    >>>
    >>> s3conn = S3Connection('<aws access key>', '<aws secret key>')
    >>> s3bucket = s3conn.get_bucket('<bucket name>')
    >>> ds = datastore.aws.S3BucketDatastore(s3bucket)
    >>>
    >>> hello = datastore.Key('hello')
    >>> ds.put(hello, 'world')
    >>> ds.contains(hello)
    True
    >>> ds.get(hello)
    'world'
    >>> ds.delete(hello)
    >>> ds.get(hello)
    None
