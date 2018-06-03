# TURN BACK NOW - THIS BRANCH HAS SPOILERS

Or check `workshop.py` for example solutions - that's why you're here, right?

# An Interactive Introduction to Hypothesis

*This tutorial was written for Pycon Asia-Pacific 2018, in Singapore.*


[Hypothesis](https://hypothesis.readthedocs.io) is a library for property-based testing.
In short:

1. You write a parametrised test.
2. Instead of (or as well as) providing a list of specific inputs to test,
   you describe what a valid input *is*.
3. Hypothesis tries hundreds of inputs, and reports the smallest possible
   example that makes your tests fail.
4. Failing examples are saved to disk and will be checked next time,
   so your build stays broken or the bug stays fixed.

The core algorithm is essentially a smart, coverage-guided fuzzing tool,
which is *really* powerful when pointed at a test with assertions about correct behaviour.
For the sake of time, today we're just going to use it for unit testing.

(There are plenty of other use-cases, from checking that your web API matches
the schema to writing an adversarial scheduler to test a concurrent program.
This tutorial is just an introduction to the most common uses, so come talk to
me or get in touch later if you're interested in advanced uses.
That includes anyone who reads this, even if you're not at Pycon!)


## Setup

Clone this repository, so you have a local copy of all the code, then run

    pip install pytest hypothesis

to install the dependencies.

That's it!  Hypothesis works on every current version of Python
(at time of writing, that's 2.7 and 3.4+; we always match upstream)
and every test runner that we know of including the standard library
`unittest`, though I recommend `pytest` for both beginners and experts.


## Tutorial

Open a terminal in this directory (and virtualenv if you used one), and run

    pytest workshop.py

The tests should pass.  Now, open `workshop.py` in your preferred editor.
Try to fix the `# TODO` comments in each section, and run the tests
regularly to make sure it's working.  Once you're happy with both tests
and features, you're done with this part of the workshop!

You should now have a decent idea of how to use Hypothesis, and the benefits
it can deliver for your code (and your tests).


## The next step

This is a good place to stop if you'd like to move on to another workshop.
If you want to keep going, you could:

* Try a harder problem from [David's all-day workshop](https://github.com/DRmacIver/hypothesis-training).
  These are small but tricky functions that give you useful experience
  in working out what kind of property-based tests will be useful.

* Bring some real code that you want to test, and apply Hypothesis to it!
  Talk to Zac in person for specific suggestions on how to test your code
  and/or feedback on tests you've written.
  (or contact me later; assistance is free for open source
  and reasonably priced for proprietary projects)

* Contribute to Hypothesis itself!  [We have plenty of starter issues](https://github.com/HypothesisWorks/hypothesis-python/labels/good%20first%20issue),
  and actively mentor new contributors - which is even better in person.
  You don't need any previous experience to make a useful contribution!
