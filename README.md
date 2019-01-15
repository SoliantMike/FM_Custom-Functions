FileMaker Custom Functions
==========================

This is a repository of custom functions publicly available.



Instructions for adding new language support from online help pages:

Using a tool like BBEdit, copy the table of error codes from the web page, then do a find and replace with the following steps. This should give you a set you can copy/paste to update the custom function should you want to for specific versions.

Step 1 (without grep)
  find:
  "
  replace:
  \"

Step 2 (with grep)
  find:
  ([0-9])\r\r
  replace:
  \1" ; "

Step 3 (without grep)
  find:
  \r\r
  replace:
  " ; JSONString ]\r    ; ["


Step 4
  Add to beginning of first line:
  ; ["
  Add to end of last line:
  " ; JSONString ]

Step 5
  Correct for ranges like "1552-1559" by creating a line for each value in the range.

Step 6
  Add new custom function and update the Case statement in the base CF to return the correct set.

