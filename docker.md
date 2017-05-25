# Benchmark Docker's Resource Isolation

### Overview
In this project, you benchmark the resource isolation facilities
of [Docker](https://www.docker.com/), an open-source containerization
software, and compare them with
[Seattle Testbed](https://github.com/SeattleTestbed) whose
[Repy](https://github.com/SeattleTestbed/repy_v2/README.md) sandbox
you have likely used before in Prof. Cappos' classes.


### Background
Docker manages and hosts application containers, so that apps in
different containers don't interfere in their usage of OS resources.
Ensuring isolation is important in multi-user and server machines,
where Customer A's web server instance must not harm Customer B's
database, etc. Setups like these are widespread, because setting
up separate server machines for different customers is less efficient
in terms of hardware cost, utilization, and administration. On the
other hand, overbooking issues can arise, or resource scheduling might
unduly impact one type of workload while favoring another.

Seattle Testbed manages and hosts a *different* type of container
which we call "sandbox". The RepyV2 sandbox that you have probably
used before is designed to limit its resource consumption to
prescribed values. These limits also hold if the machine is idle
otherwise, which is in stark contrast to *work conserving scheduling*
that operating systems usually employ.

We have shown in our paper
["Fence: Protecting Device Availability with Uniform Resource Control"](https://ssl.engineering.nyu.edu/papers/li-usenix-fence-2015.pdf).
that RepyV2's techniques do a better job at limiting resource consumption
than every single legacy tool we tested (`nice`, `ionice`, `ulimit`,
`cpufreq_set`), *and also* the combination of all of them! Furthermore,
our techniques work across operating systems and platforms, a feature
that no other tool offers.
New tools have evolved since; for example, Docker on Linux uses `cgroups`
to isolate resources. It's your task to find out how Docker fares in
experiments like the ones in our paper.


### Your Task
Devise a setup similar to what was used in the *Fence* paper to
test Docker's and Repy's resource limiting capabilities. You can
reuse existing benchmark implementations, and you are not required
to implement your own scheduler for these tests (but feel free to do so!).

At the end of your project, we would like to see sound data showing
how well, on a current operating system and machine, Docker and Repy
are able to contain the resource consumption of various "hog"
processes (that consume resources as fast as they can), so that
a second process (whose output the user is really interested in,
like a video player) can run uninterrupted.


### Milestones And Deliverables (meta-information)
1. Make a plan, describe what you will do, and when you will do it.
  Do this on a public GitHub repo.
2. If you are a summer research student, follow NYU's requirements
  for handing in an abstract and project description, attending the
  poster presentation, etc.
3. Share all code and data, notes, plans, online so that your supervisors
  can view and comment on them. Attend the regular group/individual meetings,
  see [the top-level README](README.md) for details.


