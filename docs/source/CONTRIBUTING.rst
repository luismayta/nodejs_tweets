How To Contribute
=================

.. contents::
   :local:

Contributions to node-tweets are welcome.

Getting Started
---------------

.. _commits:

Commits
^^^^^^^

Follow `semantic commits`_ to make :command:`git log` a little easier to follow.

chore
   something just needs to happen, e.g. versioning
docs
   documentation pages in :file:`_docs/` or docstrings
feat
   new code in :file:`src/`
fix
   code improvement in :file:`src/`
refactor
   code movement in :file:`src/`
style
   aesthetic changes
test
   test case modifications in :file:`test/`

Examples commit messages:

* (CF-698) chore: 0.1.0
* (CF-698) docs: Add configuration setting
* (CF-698) feat: Create Lambda function
* (CF-698) fix: Retry upload on failure
* (CF-698) refactor: Extract duplicate code
* (CF-698) style: isort, YAPF
* (CF-698) test: Coverage around add permissions

.. _semantic commits: https://seesparkbox.com/foundry/semantic_commit_messages

Branches
^^^^^^^^

Use `slash convention`_ with the same leaders as :ref:`commits`, e.g.:

* (prefix-task)

Documentation
^^^^^^^^^^^^^

* Use reStructuredText for docstrings and documentation
* For docstrings, follow :ref:`napoleon:example_google`
* For documentation pages, follow the strong guidelines from Python with
  :ref:`pythondev:documenting`

.. note::

   * Use :file:`.rst` for regular pages
   * Use :file:`.rest` for pages included using ``.. include:: file.rest``
     (fixes a Sphinx issue that thinks references are duplicated)

Testing
^^^^^^^

Run all unit tests

.. code-block:: bash

    make test.all

Run unit tests specified

.. code-block:: bash

    make test run={{path}}


Code Submission
---------------

Code Improvement
^^^^^^^^^^^^^^^^

#. See if an `Issue`_ exists

   * Comment with any added information to help the discussion

#. Create an `Issue`_ if needed

Code Submission
^^^^^^^^^^^^^^^

#. See if a `Pull Request`_ exists

   * Add some comments or review the code to help it along
   * Don't be afraid to comment when logic needs clarification

#. Create a Fork and open a `Pull Request`_ if needed

Code Review
^^^^^^^^^^^

* Anyone can review code
* Any `Pull Request`_ should be closed or merged within a week

Code Acceptance
^^^^^^^^^^^^^^^

Try to keep history as linear as possible using a `rebase` merge strategy.

#. One thumb up at minimum, two preferred
#. Request submitter to `rebase` and resolve all conflicts

   .. code:: bash

      # Update `develop`
      git checkout develop
      git pull origin develop

      # Update `CF-698` Branch
      git flow feature start CF-698
      git rebase develop

      # Update remote Branch and Pull Request
      git push -f

#. Merge the new feature

   .. code:: bash

      # Merge `CF-698` into `develop`
      git checkout develop
      git merge --ff-only feature/CF-698
      git push

#. Delete merged Branch

.. _Issue: https://endustria.atlassian.net/projects/CF/issues
.. _Pull Request: https://github.com/luismayta/node-tweets/pull-requests/
