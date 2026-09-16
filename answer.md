## Lab 1 - Answers
### Faruq Awliya Labiib - 5024241020

### Question 1. How many subscribers, publishers and service servers does /turtlesim have?
 
2 Subscriber
4 Publisher
13 Publisher

### Question 2. At approximately what rate does /turtle1/pose publish? Why does /turtle1/ ,→ cmd_vel have no steady rate at all?

62 Hz, cmd_vel have no steady rate because it is event-driven, it send message when command are present.

### Question 3. A Twist message holds six numbers. A di erential-drive robot on a  at  oor can obey only two of them. Which two, and what physical property of the platform rules out linear.y?

linear.x and angular.z, linear.y is 0 cause it can’t move to the side without rotating first.

### Question 4. The echo node vanishes from the graph the moment you press Ctrl+C, and turtlesim carries on publishing exactly as before. Explain what turtlesim knew about that subscriber, and what it had to do when the subscriber left.
/turtlesim didn’t know the identity of the subscriber specifically. /turtlesim only publish messages to the topic /turtle1/pose. When the subscriber left, /turtlesim don’t need to do anything and keep publish message as it was before.

### Question 5. Name the two capabilities an action provides that a service does not. Which of the four mechanisms would you use for the command  navigate to the kitchen , and why?

Service is unable to do continous feedback and cancellation. For command “navigate to the kitchen” use action cause navigation need long time, it also need position value and able to cancel at any time if something happen to exists.

### Question 6. You edited circle_driver.py, re-ran ros2 run without rebuilding, and the change took effect. Why? What would have happened if lab1_turtle were an ament_cmake C++ package? 

Cause --symlink-install create an executeable file linked to .py file instead of copying it. Meanwhile C++ file need to rebuild.


### Question 7. You open a fresh terminal and ros2 run lab1_turtle circle_driver fails with No executable found. Give two different causes and the fix for each.

- The terminal haven't sourced the file overlay. -> Run "source install/setup.bash"
- The file hasn't been build yet. -> Run "colcon build --symlink-install --packages-select lab1_turtle"