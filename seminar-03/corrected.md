## jBPM HW 0 - DeliveryProject

Result (Information from notebooks):
```txt
PASS
```

Notes (Email):
```txt
You can find your result (PASS/FAIL) in the jBPM HW 0 notebook. I would like
to point out most common mistakes which I noticed. I didn't penalize them as
they were minor and caused most probably due to inattention.

* Missing source for HT data input
Human Task data input variable was created but the source (process variable to
map the HT input variable to) was missing.

* Default route on a gateway not specified
This worked even if this step was omitted. The reason is that every outgoing
flow which doesn't have a guard condition (in this case the one going to the
Manual Delivery human task) is automatically marked as active (evaluated to
true). So this route was activated and the other one, which had the guard
condition for drone delivery, was evaluated to false. Moreover, in the case of
a XOR (exclusive OR) gateway exactly one outgoing route has to be taken, so it
was satisfied and your projects worked. But still, it is a good convention to
explicitly specify which route is the default one.

* String "order" used as a HT data input source
Here we wanted the HT data input variable to be sourced from the process
variable order, not a string constant "order"

* Missing HT input completely
Still, I didn't penalize it if the project was otherwise implemented
correctly

* Unnecessary HT output provided
Human Task output was not required by the instructions but some of you have
included it anyway. This is not an issue but bear in mind that jBPM will in
this case generate a task form that will be editable when completing a task. If
just the input was provided, the form would be read-only. So in future when you
don't want your human task form to have editable fields, don't provide the
human task output.
```
