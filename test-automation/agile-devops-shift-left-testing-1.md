# Agile/DevOps Shift-left Testing

**Shift-left testing** is an approach to software testing and system testing in which testing is performed earlier in the life-cycle \(i.e., moved left on the project timeline\). It is the first half of the maxim "Test early and often."

Shift-left testing is important because it helps to prevent the following types of harm due to late testing:

* Testers may be less involved in initial planning, often resulting in insufficient resources being allocated to testing.
* Many requirements, architecture, and design defects are not uncovered and fixed until after significant effort has been wasted on their implementation.
* Debugging \(including identifying, localizing, fixing, and regression testing defects\) becomes harder as more software is produced and integrated.
* Encapsulation \(object-oriented programming\) makes it harder to perform white box testing and to achieve high levels of code coverage during testing.
* There is less time to fix defects found by testing, thereby increasing the likelihood that they will be postponed until later increments or versions of the system, which creates a “bow wave” of technical debt that can sink projects if it grows too large.

#### Agile/DevOps shift-left testing Model: <a id="agile-devops-shift-left-testing-model"></a>

As illustrated in the following figure, Agile and DevOps projects have numerous short duration Vs \(sprints\) in lieu of a single or small number of V as in the previous two examples of shift-left testing. These small Vs would also be modified if one or more early sprints are used to block out the basic requirements and architecture or if test-first and Test Driven Development \(TDD\) are being performed. The shift-left occurs because the types of testing on the right sides of the earliest of these tiny Vs are to the left of the corresponding types of testing on right side of the larger V\(s\) they replace. While the following figure appears remarkably the same for Agile and DevOps, Agile testing is typically restricted to developmental testing and does not include operational testing, which occurs once the system is placed into operation. The transition to Agile/DevOps shift-left testing is currently popular and ongoing.![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lm5QiXfvtgvTV6GtS-u%2F-Lo6HaP2rQD0zkUI5jJf%2F-Lo6I_F0TFp2jDU0D5ty%2Fimage.png?alt=media&token=9a274276-e701-456b-aedc-f6f7b057565c)

