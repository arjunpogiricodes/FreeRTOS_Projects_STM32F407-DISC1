# FreeRTOS_Projects_STM32F407-DISC1
Characteristics of a 'Task'
In brief: A real time application that uses an RTOS can be structured as a set of independent tasks. Each task executes within its own context with no coincidental dependency on other tasks within the system or the RTOS scheduler itself. Only one task within the application can be executing at any point in time and the real time RTOS scheduler is responsible for deciding which task this should be. The RTOS scheduler may therefore repeatedly start and stop each task (swap each task in and out) as the application executes. As a task has no knowledge of the RTOS scheduler activity it is the responsibility of the real time RTOS scheduler to ensure that the processor context (register values, stack contents, etc) when a task is swapped in is exactly that as when the same task was swapped out. To achieve this each task is provided with its own stack. When the task is swapped out the execution context is saved to the stack of that task so it can also be exactly restored when the same task is later swapped back in. See the How FreeRTOS Works section for more information.

Task Summary
	Simple.
	No restrictions on use.
	Supports full preemption.
	Fully prioritised.
	Each task maintains its own stack resulting in higher RAM usage.
	Re-entrancy must be carefully considered if using preemption.
 
