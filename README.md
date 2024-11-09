java c
MECH6480: Computational Fluid Dynamics (S2, 2024)
> Hypersonic flow over double cones
Assignment 2: Simulation of Compressible Flow
There are 25 MARKS total for this assignment.
1 Introduction
In this assignment, you will simulate the hypersonic flow over double-cone geometries using Eilmer. Double-cones in hypersonic flow have long been studied experimentally, theoretically and compu-tationally because they are a good representative geometry for the fluid mechanics of control flaps on a hypersonic vehicle. The relatively simple geometry gives rise to complex flow behaviour. One such behaviour is unsteady flow. We study this unsteady flow to understand it, and ultimately to accommodate the behaviour (in control system design) or avoid it altogether in design. An image of the geometry of a double-cone and one possible flow field is shown in Figure 1.

Figure 1: Double-cone geometry with a representative flow field sketch.
2 Task overview
You have two configurations two study. At a high-level, we want to answer the question:
Which flow and geometry configurations give rise to steady or unsteady flow behaviours?
The assignment activities are designed sequentially to follow good CFD practice. We will begin with some verification and grid convergence on a simpler geometry: a single cone. Next, we will extend the single cone simulations to look at simulating flow over a double-cone in a steady flow configuration. Finally, with those pieces in place and using the experience gained, we will look at flow unsteadiness flows over the same class of geometry.
Read through all the tasks before beginning. It will help you plan your domain topology so that it is easy to extend or re-use as you move through the tasks.
3 Geometry and flow conditions
The axially-symmetric geometry is depicted in Figure 1. The geometry is parameterised by four quantities: l1, l2, θ1 and θ2. l1 is the length along the first cone. l2 is the length along the second cone. θ1 is the half-angle of the first cone (from axis to cone surface). θ2 is the half-angle of the second cone, measured from the horizontal as indicated in Figure 1.
For all simulations in this assignment, you will use the free stream conditions given in Table 1. The test gas is ideal nitrogen. Assume inviscid flow for all simulations in this assignment.
Table 1: Free stream conditions for simulations.

4 Tasks
Task 1: Simulate flow over first cone (8 Marks)
For this task, simulate the flow over a single cone using the flow conditions in Table 1. The geometric parameters are:

Record the flow history at two points on the cone surface: halfway along the cone and at the base. Use that flow history to determine if the simulation has reached a steady state. Take the steady state value for coefficient of pressure and compare this to an analytical estimate for coefficient of pressure on a cone. Compare this estimate on successively refined grids to demonstrate grid convergence.
To calculate coefficient of pressure, use the definition:

where pc is the pressure on the cone, p∞ is the free stream pressure, and q∞ is the dynamic pressure computed as  The analytical estimate for the coefficient of pressure on the cone comes from solving the Taylor-Maccoll equations. An Eilmer script. to do this is provided in the MECH6480 repo in the assignment-2 folder. The script. is called cone-cp.lua. It can be executed at the command line using Eilmer in custom-script. mode:
$ e4shared --custom-script. --script-file=cone-cp.lua
Produce images, tables or text as appropriate to address the following:
(a) Show an image of your topology.
(b) Show an image of a representative mesh.
(c) Show the history of Cp at the two points on the surface (preferably on a single plot).
(d) Demonstrate an approach to a grid converged result at the two locations for the history recorder by comparing to the analytical Cp. Produce a plot of error between the analytical estimate and CFD-derived value (Cp,T-M − Cp,CFD) as代 写MECH6480: Computational Fluid Dynamics (S2, 2024) Assignment 2: Simulation of Compressible FlowMatlab
代做程序编程语言 a function of average cell size. We would expect the error to diminish as cell size gets smaller.
(e) For your finest grid, show a contour plot of the temperature field and the Mach number field.
Task 2: Simulate flow over a double-cone (7 Marks)
In Task 1, you should have established some idea of cell size for an accurate CFD result. In this task (Task 2), extend your simulation domain to simulate the flow over a double-cone. You will need to think about an appropriate topology. Use the following geometric parameters:

This time record the flow history halfway along the first cone and halfway along the second cone. Use these locations as determiners of having reached a steady state.
Produce images, tables or text as appropriate to address the following:
(a) Show an image of your topology.
(b) Show an image of a representative mesh.
(c) Show the history of Cp at the two points on the surface (preferably on a single plot).
(d) Show that the flow field on the first cone is approaching a grid converged result.
(e) For your finest grid, show a contour plot of the temperature field and the Mach number field.
(f ) For your finest grid, produce a plot of Cp along the surface of both cones. You may choose x-coordinate or running length as the independent variable in your plot.
Task3: Simulate possibly unsteady flow over a double-cone (10 Marks)
In this task, you will continue to simulate flow over a double-cone. However, each student in the class has been given two geometries to simulate: you will each get a case (A) and case (B) which are combinations of (θ1, θ2) for each case. For all students, the lengths of the cones remain the same:

In the MECH6480 repository, find your particular cases for the cone angles in the text file mech6480-double-cone-list.txt. The list will contain two cases, (A) and (B), each with values for θ1 and θ2 in units of degrees. Ensure that θ1 < θ2.
For some combinations of cone angles, the flow will be unsteady. The unsteadiness could be small scale, or it could be large. You will need to experiment with extending your domain so that you can capture all flow features as it moves through its cyclic unsteadiness. An example flow field over several time instances in shown in Figure 2.
For some other combinations, the flow will be steady. The goal of your simulations is determine which of your flow cases produces a steady or unsteady flow. Again, record flow history at the halfway points on each cone.
Produce images, tables or text as appropriate to address the following:
(a) Show an image of your topology.
(b) Show an image of a representative mesh.
(c) For each case, show the history of Cp at the two points on the surface (preferably on a single plot).
(d) Demonstrate that your simulations are approaching a grid converged result.
(e) State whether your flow fields exhibit unsteadiness or if it is a steady flow configuration.

Figure 2: An example of pulsating unsteadiness. Panels are separated by 35µs.
(f ) If your flow field is unsteady, determine the frequency of any cyclic behaviour. Produce images of the temperature field at several snapshots within one period of the unsteadiness (similar to what was done in Figure 2).
(g) If your flow field is steady, compute an estimate of the cumulative drag force exerted on the cone surfaces. Describe your process for computing the drag estimate.
5 Submission requirements
You do NOT need to submit a report for this assignment. You should submit figures and text to address each of the tasks. Make sure you label your submitted work clearly by subtask so that the tutors have an easy time marking your work. You can add brief text descriptions to clarify results that might need some additional explanation beyond just figures and plots.
Also include a zip file of your simulation scripts and any post-processing scripts that you created. Do not include flow field data in the zip file.







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
