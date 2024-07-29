#shell_ai <br>
This repository is for the submission to Shell.ai's
<a href="https://www.shell.com/what-we-do/digitalisation/collaboration-and-open-innovation/shell-ai-hackathon-for-sustainable-and-affordable-energy.html#vanity-aHR0cHM6Ly93d3cuc2hlbGwuY29tL2hhY2thdGhvbi5odG1s"> Hackathon for Sustainable and Affordable Energy 2024</a>
<br>
Cost is defined according to the problem definition rules as the sum of fuel cost, vehicle purchase cost, ownership costs (insurance and maintenance) minus sales costs. The objective is to minimize costs without violating the constraints which are also defined in the supplied problem definition document.

Once the problem is formulated with an objective, variable definitions and constraints, the problem is saved to file and then the possible separator space is enumerated. 
1.	Define variables
2.	Define objective function
3.	Define Constraints
4.	Using defined model, enumerate separator space 
5.	Train a neural network using deep-reinforcement learning to estimate time savings of separators.
6.	Perform standard branch and cut algorithm with additional AI acceleration.

Steps 1 – 3 are defined using standard Python Linear Programming format. The output of this step is a standard Mixed Integer Linear Program.
Steps 4 and 5 are performed using code provided by the learning to configure separators project. The output of step 4 is a sample of the configuration space of separators.
 




