MTP
==================================================

Description (TBA)

Getting the tool
----------------

The code of 'MTP' is contained in a GIT repository on GitHub, whose URL is
https://github.com/daniel-gaina/MTP. To get a copy of the repository you only
have to write in your Linux/MacOS console:

    $ git clone https://github.com/XXX

This will create an MTP folder containing the source code of the tool as well as
several examples.

MTP syntax
----------

MTP follows sevaral syntax elements from Maude (XXX) but it also provides
particular elements to closely represent hybrid specifications. In particular,
MTP modules are defined with the following syntax, where elements in square
brackets are optional:

* **spec! SPEC-NAME[{PARAMS}] = DEFS end** This syntax defines a specification
with tight semantics.

or

* __spec* SPEC-NAME[{PARAMS}] = DEFS end__ This syntax defines a specification
with loose semantics.

In both cases parameters are optional and defined as follows:

* **PARAM-NAME :: SPEC-NAME [, PARAMS]** Note that the specification used as
parameter must be defined beforehand with loose semantics.

The **DEFS** element above includes the following elements:

* **pr SPEC-NAME .**, which imports the specificacion **SPEC-NAME** in *protecting*
mode, that is, no junk and no confusion are allowed for the sorts in the imported
module.

* **ex SPEC-NAME .**, which imports the specificacion **SPEC-NAME** in *extending*
mode, which allows junk but no confusion.

* **inc SPEC-NAME .**, which imports the specificacion **SPEC-NAME** in *including*
mode, which allows both junk and confusion.

* **rigid sort[s] SORT-NAME-LIST .**, for specifying rigid sorts.

* **nominal sort[s] SORT-NAME-LIST .**, for specifying nominal sorts.

* **sort[s] SORT-NAME-LIST .**, for specifying flexible sorts.

* **subsort SORT-NAME-LIST < SORT-NAME**, for defining subsort relations between
sorts.

* **op OP-NAME : ARITY -> COARITY [[ATT-LIST]] .**, where the attribute list
**ATT-LIST** includes the **ctor** (constructor), **comm** (commutative), and **assoc**
(associative) attributes.