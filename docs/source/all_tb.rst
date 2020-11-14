Why all the tracebacks?
=========================

.. todo::

    Add explanation as to why we include all possible tracebacks.
    Short answer: we created a separate repository for documentation.
    When we update the documentation, we can check the commit diff to
    spot any changes that should be flagged as an error and was not
    captured in a unit test. Note that this is also why we
    simplified functions repr.
