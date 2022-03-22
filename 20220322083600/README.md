# Should `util.ReplaceSelf` Delete Previous?

Having a dilemma deciding if the `util.ReplaceSelf` function should
actually permanently delete the previous version or keep it around and
just add a suffix to it. Initially, I thought keeping it around would be
a good idea. Then I realized one of the reasons to get rid of it is
because of security vulnerabilities, in which case you want no sign of
the previous file anywhere on the system. I have to get over my fear
that something could go wrong during the replacement. Got knows that
other software --- even firmware --- doesn't care.
