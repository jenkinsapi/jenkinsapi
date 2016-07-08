How to release this project
===========================

These instructions are intended for package maintainers who want to make a new public release (e.g. to PyPi). These instructions
are not intended for regular users. If you just want to use JenkinsAPI you can safely ignore these instructions.

The release requirements for this project are more specific than the runtime requirments. Please ensure that the following
packages are installed. Other components will be installed within the Python virtual environment and do not need to be
installed system-wide.

Requirements:
 - Python 3.x
 - Python 2.x
 - Ant
 - Virtualenv

1. Create a "working directory", this is the folder which will contain your source code and some of the release scripts.

2. The project code should exist in a directory called 'src' that's within your working directory:

~~~~
cd <working directory>
git clone <project url> src
~~~~

3. Copy the make_venv.sh script into the working directory:

~~~~
cd <working directory>
cp -sf src/misc/make_venv.sh ./
~~~~

4. Run the make_venv script and then activate the virtual environment:

~~~
./make_venv.sh
source ./venv/bin/activate
~~~

4. Increment the version number in setup.py

0. Verify that all tests are passing on Travis and locally. The easiest way to run all tests is:

~~~
cd src
python setup.py test
~~~

5. Run the release script

~~~
./release.sh
~~~
