This repository is for the submission to Shell.ai's
<a href="https://www.shell.com/what-we-do/digitalisation/collaboration-and-open-innovation/shell-ai-hackathon-for-sustainable-and-affordable-energy.html#vanity-aHR0cHM6Ly93d3cuc2hlbGwuY29tL2hhY2thdGhvbi5odG1s"> Hackathon for Sustainable and Affordable Energy 2024</a>
<hr>



# Problem Statement
The problem is explained the problems statement <a href="Problem Statement - Detailed_final 3f65d376.pdf'>document</a> in this repository.

# Approach
The approach in this repository defines the problem as a Mixed Integer Linear Program and uses the <a href="https://github.com/mit-wu-lab/learning-to-configure-separators">learning-to-configure-separators</a> repository to augment the speed of the solver.

In order to formulate the problem as a MILP, the decision variables were defined as all possible combinations of the following variables:
-	veh_id: – defined by the ID column in the dataset defined in vehicles.csv
-	purchase_year: – availability constrained according to vehicles.csv
-	sell_year – for any given year up to 10 years after vehicle was purchased
-	demand_year – for any year after vehicle was purchased and before it was sold.
-	fuel_type – constrained according to vehicles_fuels.csv
-	demand_distance – Distance identifier constrained according to Constraints section of problem definition.
-	size – Constrained to match demand.csv
The concatenation of the decision possibilities enumerates the possible decision space creating 43688 variables. 

# Methodology
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
 




