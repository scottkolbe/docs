Adding to this documentation
============================

This documentation is generated using Sphinx which is a document generator 
based on python. To add to this documentation you can edit the existing
files and even make your own pages. The documentation pages are made 
using a markdown language called reStructuredText (.rst file http://docutils.sourceforge.net/rst.html). RST files 
make it easy to make you text look nice, add links or images.
They also have some nice features for linking between pages. 
Here is an excellent video that shows how to get started:

https://youtu.be/oJsUvBQyHBs

To obtain the code that this documentation is based on please speak to Scott 
to get a link to the Git repository. You can then edit the files yourself
and commit your changes using Git, then the documentation can easily be 
rebuilt and the changes will be seen on the website.

Editing RST files and building HTML pages
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you are using Mac or Linux (Windows might work with cygwin but I have no idea and have 
no intention of figuring it out) you will need to install sphinx:

.. code-block:: bash

   $ pip install sphinx

It's also useful to have a good code writing environment. 
I'm using Visual Studio Code that you can download for free at https://code.visualstudio.com.

Finally, I use the Git App to clone the repository and manage my change commits:
https://desktop.github.com

Now you can start!

Clone the repository scottkolbe/docs to your local computer. Edit the .rst files in the source directory.
Once you are happy you can build new HTML files and view them in your web browser:

.. code-block:: bash

   $ cd GitHub/docs
   $ make html
   $ open bin/html/index.html

Once you are happy with your changes you can commit the repository back to the central github repository. 
Then it's just a case of rebuilding the documentation on ReadTheDocs. Please ask Scott to do this for now.




