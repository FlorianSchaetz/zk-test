# zk-test
Test Utils for typically hard to unit test zk stuff

While ZK produces nice results without having to delve deeper into HTML/JavaScript,
it's notoriously hard to unit test, since it a) often relies on a huge framework around 
your classes (for example mvvn binding) or b) relies heavily on static method calls 
that access the environment.

An example are ZK's MVVM ViewModels. While they are advertised as "pojos" (plain old 
java objects), they tend to rely heavily on specific annotations (@NotifyChange,
@Command, etc.). Without testing the correctness of these annotations, we are only
testing a small part of the class - and have to rely on integration of ui tests to 
test the whole thing. It would be preferable to be able to test those in a unit test, 
too.
