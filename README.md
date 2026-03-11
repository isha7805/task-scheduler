# Concurrent Task Scheduler

This project implements a simplified job orchestration system similar to a build tool like Make.

It schedules tasks based on:
- dependencies
- priority
- simulated execution time

## Features

- Task dependency resolution
- Priority based scheduling
- Topological execution order
- Simulated execution with threads
- Real-time task logs

## Task Structure

Each task contains:

id  
name  
priority (1 = highest)  
depends_on (list of task IDs)  
duration_ms  

Example:

A -> Compile  
B -> UnitTest (depends on A)  
C -> IntegrationTest (depends on A)  
D -> Deploy (depends on B and C)

## Scheduling Logic

1. Build dependency graph
2. Calculate indegree for each task
3. Use priority queue for ready tasks
4. Execute tasks when dependencies are satisfied

## Execution

Compile:

g++ main.cpp -o scheduler

Run:

./scheduler

## Output

Real-time logs for task start and completion.

Example:

START A  
END A  
START C  
END C  
START B  
END B  
START D  
END D  

All tasks completed

## Future Improvements

- JSON parsing support
- worker pool concurrency
- retry mechanism
- critical path calculation
- graph visualization
