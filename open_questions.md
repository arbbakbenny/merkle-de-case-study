# Open questions

- What steps are missing to industrialize such solution further.
> Determine the actual business use case (why this dataset is needed). Determine the scheduling, write mode. 

> Figure out scheduling and required availability.

> Enforce schema by having proper data contract for input data. Provide strategy (or agreement) regarding missing data. 

> Implement error handling and recovery, reingestion logic.

> Proper monitoring and infrastructure, CI/CD, deployment and version control, rollback strategy.

- If the solution was implemented in dbt-core, how would the overall architecture change? Would
there be another cloud resources needed?

> Overal architecture would be split between several SQL scripts that will tackle specific processing logic. That in turn brings decoupling which makes it easier to maintain and follow logic. Resource wise, that would require and orchestrator to execute dbt.


- What would implementation in dbt-core bring to the project. What would be the upsides and
downsides.

> Mainly decoupling and would bring migration to SQL as main tooling without Python scaffolding. Proper tests would be easier to implement which brings confirmation of correctness of the solution. 
Downsides would be fragmentation due to modularity - if the logic is a result of several scripts interacting it would be harder to debug and follow. Debugging itself in case of error would be a bit demanding (v.s. errors thrown in the code with the ability to debug step by step).

- Please estimate the effort you’d request to implement the solution in dbt-core.
> Didn't have actual experience with dbt, an uneducated guestimation would be less than a sprint to set up orchestrator, split the code logic, confirm interaction etc. For the same functionality that was in the assignment, two or three days top, for correctly designed approach would be more but still no more than a full two week sprint.