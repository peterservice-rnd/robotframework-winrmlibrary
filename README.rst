Robot Framework Windows Remote Library
=======================================

|Build Status|

Short Description
-----------------

`Robot Framework`_ library for Windows Remote Management, based on `pywinrm`_.

Installation
------------

::

    pip install robotframework-winrmlibrary

Documentation
-------------

Keyword documentation for robotframework-winrmlibrary library: docs_.

Example
-------

.. code:: robotframework

    *** Settings ***
    Library    WinRMLibrary
    
    *** Test Cases ***
    Get ip on windows host
        Create Session    server    windows-host   Administrator    1234567890 
        ${params}=   Create List    "/all" 
        ${result}=    Run cmd    server    ipconfig    ${params} 
        Log    ${result.status_code} 
        Log    ${result.std_out} 
        Log    ${result.std_err} 

::

    0
    Windows IP Configuration
       Host Name . . . . . . . . . . . . : WINDOWS-HOST
       Primary Dns Suffix  . . . . . . . :
       Node Type . . . . . . . . . . . . : Hybrid
       IP Routing Enabled. . . . . . . . : No
       WINS Proxy Enabled. . . . . . . . : No
    
        
License
-------

Apache License 2.0

.. _Robot Framework: http://www.robotframework.org

.. _pywinrm: https://pypi.python.org/pypi/pywinrm

.. |Build Status| image:: https://travis-ci.org/peterservice-rnd/robotframework-winrmlibrary.svg?branch=master
   :target: https://travis-ci.org/peterservice-rnd/robotframework-winrmlibrary
   
.. _docs: https://rawgit.com/peterservice-rnd/robotframework-winrmlibrary/master/docs/WinRMLibrary.html   
