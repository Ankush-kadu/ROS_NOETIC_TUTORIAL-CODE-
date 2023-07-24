# ROS_NOETIC_TUTORIAL-CODE-
1. ROS Master: Before starting any ROS nodes, ensure that the ROS Master is running with "roscore" command.
2. Starting a Node: Nodes can be launched using the "rosrun" command, followed by the package name and node name. For example, "rosrun package_name node_name".
3. Avoid Duplicate ROS Master: Only one ROS Master can be active at a time. Trying to start another ROS Master while one is running will result in an error.
4. Visualizing ROS Graph: Use the "rqt_graph" command to get a graphical view of the ROS graph, showing nodes and their communication relationships.
5. Multiple Nodes Communication: Demonstrated communication between two nodes using "rosrun" to launch "talker" and "listener" nodes, which send data to each other via a topic.
6. Turtle Simulation: Used "rosrun" to start "turtlesim" and "teleop_turtle" nodes for controlling a turtle in a graphical window.
7. Definition of a ROS Node: A ROS node is a program that can be executed, performing tasks and utilizing ROS functionalities and communication capabilities.

REFERENCE :

https://www.youtube.com/watch?v=4aUp2703FFY&list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q&index=2

# **Summary (related to creating the Catkin workspace):**

1. Purpose of Catkin Workspace: A Catkin workspace is used to organize and package ROS applications, making it easy to collaborate and share code with others.
2. Creating the Workspace: To create a Catkin workspace, navigate to the desired location and use the command "mkdir catkin_ws" (or any preferred name).
3. Adding Source Folder: Inside the Catkin workspace, create a folder named "src" using the command "mkdir src."
4. Compiling the Workspace: To compile the workspace and generate necessary files, run the command "catkin_make" inside the Catkin workspace. The build and devel folders will be created.
5. Sourcing the Setup.bash Script: To use the code from the Catkin workspace, source the "setup.bash" script. Use the command "source ~/catkin_ws/devel/setup.bash" to source the workspace.
6. Updating Bashrc: To ensure that the Catkin workspace is sourced every time a new terminal is opened, add the "source ~/catkin_ws/devel/setup.bash" line to the .bashrc file.
7. Multiple Workspaces: When using multiple workspaces, make sure to source both the global ROS installation and the Catkin workspace in the correct order, with the custom workspace being sourced after the global one.

By following these steps, the Catkin workspace is set up and ready for writing custom ROS code and applications.

![Screenshot from 2023-07-21 14-04-20.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/815e383a-e6ed-4ba5-b927-17360551aa9e/Screenshot_from_2023-07-21_14-04-20.png)

REFERENCE :

https://www.youtube.com/watch?v=8uxd9RBQvmQ&list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q&index=3

# **Summary (related to creating the ROS package):**

1. Purpose of ROS Package: A ROS package provides a way to organize and package nodes and code within the Catkin workspace, making it easier to manage and share.
2. Package Creation: To create a new package, use the "catkin_create_pkg" command, followed by the desired package name. For example, "catkin_create_pkg my_robot_controller". here i use ibot name as my_robot_controller i.e "catkin_create_pkg ibot_controller"
3. Package Dependencies: Specify package dependencies when creating the package using the "catkin_create_pkg" command. These dependencies are the other packages that the new package will utilize.
4. package.xml File: The package.xml file contains information about the package, such as name, version, description, maintainer, author, and license. It also lists the package's dependencies.
5. Building the Package: After creating the package and modifying the package.xml file (if necessary), use "catkin_make" in the Catkin workspace to build the package and initialize it.
6. Dependencies Updates: Later, if you need to add or modify package dependencies, update the package.xml file and rebuild the workspace using "catkin_make."

By following these steps, the ROS package is created and ready to be populated with nodes and code for controlling the robot (in this case, the turtle).

![Screenshot from 2023-07-21 14-58-54.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e420797f-e939-46db-bbd4-1514fb628455/Screenshot_from_2023-07-21_14-58-54.png)

![Screenshot from 2023-07-21 14-59-03.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/46b45e17-2605-4569-be8c-1551ebf8e475/Screenshot_from_2023-07-21_14-59-03.png)

![Screenshot from 2023-07-21 15-07-03.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ee8fac06-e6bc-451a-b5e1-7dca5f4194f8/Screenshot_from_2023-07-21_15-07-03.png)

REFERENCE :

https://www.youtube.com/watch?v=A-1DBhWF_64&list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q&index=4

# **Summary (related to creating a Python file for the ROS node):**

1. Python Script Creation: To create a new Python script for the ROS node, navigate to the "scripts" folder inside the ROS package and create a new file using the "touch" command.
2. ROS Node Initialization: The ROS node needs to be initialized with `rospy.init_node("node_name")`. The "node_name" is the unique name for the node, which can be different from the name of the Python file.
3. Auto-completion and Syntax Highlighting: To enable auto-completion and syntax highlighting for ROS functionalities, install the necessary extensions (Python, ROS, and CMake) in Visual Studio Code or your preferred IDE.
4. ROS Log Function: Use `rospy.loginfo()`, `rospy.logwarn()`, and `rospy.logerr()` to print messages in the terminal with different log levels (info, warning, error).
5. ROS Rate and Loop: The `rospy.Rate()` function helps control the frequency at which a loop runs. Inside the loop, use `rate.sleep()` to pause the program for the specified frequency.
6. ROS Node Execution: To execute the Python script as a ROS node, run it using Python directly (`python3 my_first_node.py`) or use `rosrun package_name node_name.py`.
7. ROS Node List and Shutdown: Use `rosnode list` to view all running ROS nodes, and `rosnode kill node_name` to shut down a specific node. Nodes with the same name cannot be running simultaneously.
    
    ![Screenshot from 2023-07-21 16-50-01.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a356baef-8c3f-48b7-8770-4f26332c83c0/Screenshot_from_2023-07-21_16-50-01.png)
    

By following these steps and using the basic ROS functionalities, you have created a simple ROS node and interacted with it using the terminal commands. This structure provides a foundation for more complex ROS nodes that can interact with other nodes and sensors.

![Screenshot from 2023-07-21 16-39-12.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f39a0568-f058-4431-92a2-40ffba57208f/Screenshot_from_2023-07-21_16-39-12.png)

![Screenshot from 2023-07-21 16-39-22.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/45edc1aa-7316-446b-a8e5-9e0551e3cc73/Screenshot_from_2023-07-21_16-39-22.png)

![Screenshot from 2023-07-21 16-38-34.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7066a715-48b0-47e7-9f93-72722eb04ef3/Screenshot_from_2023-07-21_16-38-34.png)

REFERENCE:

https://www.youtube.com/watch?v=jWtkzDbez9M&list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q&index=5

# **Summary (related to ROS topics and talker/listener example):**

1. ROS Topics: ROS Topics are a way for nodes to communicate with each other by publishing and subscribing to messages on named channels.
2. Publisher-Subscriber Model: Nodes act as either publishers (sending data) or subscribers (receiving data) for specific topics.
3. `rostopic list`: Use `rostopic list` command to view all available ROS topics.
4. `rostopic info <topic_name>`: Use `rostopic info <topic_name>` command to get information about a specific ROS topic, including its data type, publishers, and subscribers.
5. `rosmsg show <message_type>`: Use `rosmsg show <message_type>` command to display the structure of a specific ROS message type.
6. `rostopic echo <topic_name>`: Use `rostopic echo <topic_name>` command to monitor the messages being published on a specific ROS topic in real-time.
7. Turtle Example: Demonstrated how to use ROS topics with the TurtleSim package, where a "draw_square" node publishes the turtle's position, and the TurtleSim node subscribes to it, enabling the turtle to draw a square.

ROS Topics facilitate communication between nodes in ROS applications, allowing for decentralized, asynchronous data exchange. Publishers and subscribers remain anonymous to each other, allowing for flexible communication patterns. This mechanism is crucial for building complex robotics systems in ROS.

![Screenshot from 2023-07-21 17-55-38.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/184681d2-33aa-42e8-9e0d-fdae95aa0212/Screenshot_from_2023-07-21_17-55-38.png)

![Screenshot from 2023-07-21 17-55-27.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/77552071-2953-48d0-b506-6e1bf8c2a5b6/Screenshot_from_2023-07-21_17-55-27.png)

![Screenshot from 2023-07-21 17-55-21.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ac464182-47c8-4673-84d6-c752b4f88494/Screenshot_from_2023-07-21_17-55-21.png)

![Screenshot from 2023-07-21 17-55-14.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e8163388-5b81-41a7-9062-035b7fdb5893/Screenshot_from_2023-07-21_17-55-14.png)

![Screenshot from 2023-07-21 17-59-01.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ca7cbfed-552a-4ac6-af7e-c4768e8edaf5/Screenshot_from_2023-07-21_17-59-01.png)

REFERENCE :

https://www.youtube.com/watch?v=GAJ3c5XmJSA&list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q&index=6

# **Summary(related to creating a ROS publisher node):**

1. Publisher Node: A publisher node in ROS is responsible for sending data/messages to a specific topic.
2. Import Necessary Libraries: Import the necessary ROS libraries (`rospy`), as well as the message type you want to publish.
3. Initialize Node: Before creating the publisher, initialize the ROS node using `rospy.init_node("node_name")`.
4. Create a Publisher: Create a publisher object using `rospy.Publisher("topic_name", message_type, queue_size)`. Provide the topic name, the message type, and optionally specify a queue size for buffering.
5. Define the Message: Create an instance of the message type and fill in the necessary data fields with the desired values.
6. Publish the Message: Use the `publish()` method of the publisher object to send the message to the specified topic.
7. Use Rate Control: Use a `Rate` object to control the publishing frequency. This ensures that the publisher does not send messages too rapidly.
8. Consistency: Ensure that the topic name and message type used in the publisher match the topic name and message type expected by the subscriber.

By creating a ROS publisher node, you can send data to a specific topic, enabling other nodes (subscribers) to receive and process that data accordingly. This mechanism allows for communication and coordination among different components in a ROS system.

![Screenshot from 2023-07-21 19-05-22.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3d2e34ac-6c67-43f7-b4aa-2dec3a8da52b/Screenshot_from_2023-07-21_19-05-22.png)

![Screenshot from 2023-07-21 19-05-37.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2a56932b-916b-4dd4-aee4-3aaf3f23ceb9/Screenshot_from_2023-07-21_19-05-37.png)

![Screenshot from 2023-07-21 19-05-49.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6a7a19f4-f282-4bea-b07f-706da000cd89/Screenshot_from_2023-07-21_19-05-49.png)

![Screenshot from 2023-07-21 19-05-57.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/63ef8704-b634-4f06-a6ea-210f5977a3b3/Screenshot_from_2023-07-21_19-05-57.png)

![Screenshot from 2023-07-21 19-05-42.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6af05717-d1f7-4269-8836-7a9ff701efc8/Screenshot_from_2023-07-21_19-05-42.png)

![Screenshot from 2023-07-21 19-06-13.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/56ee6fdd-8a2f-4a3f-b0a6-620b57953b23/Screenshot_from_2023-07-21_19-06-13.png)

![Screenshot from 2023-07-21 19-06-16.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/564613bf-3a3e-4c4d-bbce-9bb64a1e0bc3/Screenshot_from_2023-07-21_19-06-16.png)

![Screenshot from 2023-07-21 19-12-32.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/97cb08f1-b960-4370-bdf4-ee987a224278/Screenshot_from_2023-07-21_19-12-32.png)

# **Summary (related to ROS Subscriber setup):**

1. Purpose of ROS Subscriber: A ROS Subscriber allows a node to receive data from a specific topic published by another node.
2. Topic Selection: Before creating a Subscriber, use "ros topic list" to identify the topic to which you want to subscribe. In this case, the topic is "/turtle1/pose" published by the "turtle_sim" node.
3. Create the Subscriber: To create a Subscriber in Python, use the "rospy.Subscriber()" function. Provide the topic name and the message type to be received. The message type can be imported from the corresponding package's ".msg" module.
4. Create a Callback Function: Create a function to handle the data received from the topic. This function will be called each time a new message is received. The message data can be accessed via the "msg" argument of the callback function.
5. Initialize and Process Callbacks: After creating the Subscriber and the callback function, use "rospy.init_node()" to initialize the node. Then, use "rospy.spin()" to start the infinite loop that listens for messages and processes them using the callback function.
6. Additional Topics and RQT Graph: You can use "rostopic info" to check the details of a specific topic, and "rqt_graph" to visualize the ROS nodes and their interactions.

With the Subscriber set up, your ROS node can now receive and process messages published on the specified topic, making it possible to interact with other ROS nodes and perform tasks based on the received data.

![Screenshot from 2023-07-21 22-56-20.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8fbd8016-3440-4717-ba6d-a252c8eae52e/Screenshot_from_2023-07-21_22-56-20.png)

![Screenshot from 2023-07-21 22-55-12.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/609b9faa-ef44-4e25-9aef-70115eabf032/Screenshot_from_2023-07-21_22-55-12.png)

![Screenshot from 2023-07-21 22-55-20.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a117a44e-5235-4d44-b5a5-37a5e870684e/Screenshot_from_2023-07-21_22-55-20.png)

![Screenshot from 2023-07-21 22-54-59.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6c7d3fcf-4909-4446-8bfa-5282ed6c3c36/Screenshot_from_2023-07-21_22-54-59.png)

![Screenshot from 2023-07-21 22-55-29.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9704e38a-39c5-4ce8-9861-27988c4d51b7/Screenshot_from_2023-07-21_22-55-29.png)

REFERENCE :

https://www.youtube.com/watch?v=eciuB0p8bK0&list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q&index=8

# **Summary(Combine Publisher and Subscriber in a Closed Loop System):**

1. The video discusses setting up a closed-loop control system for a turtle simulation using ROS Noetic.
2. The goal is to create a single node that contains both a subscriber and a publisher, which allows the turtle to move in a controlled manner.
3. The turtle controller node subscribes to the "pose" topic, which provides the current position of the turtle.
4. It publishes to the "cmd_vel" topic, which controls the linear and angular velocities of the turtle.
5. The turtle controller uses a simple control strategy to avoid hitting the walls. When the turtle is close to a wall (within a danger zone), it slows down and turns in the opposite direction.
6. The danger zone is defined with margins around the edges of the simulation area (e.g., x > 9, x < 2, y > 9, y < 2).
7. The "geometry_msgs/Twist" message type is used for publishing to the "cmd_vel" topic.
8. The closed-loop control system ensures the turtle continuously moves while avoiding collisions with the walls.

Commands:

1. `rosscore` - Starts the ROS core.
2. `roslaunch` or `rosrun` - Used to launch ROS nodes and packages.
3. `rostopic list` - Lists all available topics in the ROS environment.
4. `rostopic info <topic_name>` - Displays information about a specific topic, such as its message type.
5. `rospy.Subscriber(<topic_name>, <message_type>, <callback_function>)` - Sets up a subscriber for a specific topic.
6. `rospy.Publisher(<topic_name>, <message_type>, queue_size=<queue_size>)` - Sets up a publisher for a specific topic.
7. `rospy.spin()` - Keeps the node running and allows callbacks to be executed.

Note: The specific Python code used in the tutorial for subscribing, publishing, and controlling the turtle may vary slightly based on individual preferences or customizations. The key concept is the closed-loop control approach to ensure the turtle moves safely and intelligently within the simulation area.

![Screenshot from 2023-07-21 23-43-35.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/25195044-593e-4fa7-ba64-66bc1dc0a767/Screenshot_from_2023-07-21_23-43-35.png)

![Screenshot from 2023-07-21 23-43-48.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0b30d48e-e20f-4bfd-a2e5-7b10941b35c2/Screenshot_from_2023-07-21_23-43-48.png)

![Screenshot from 2023-07-21 23-44-13.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/13bdb953-9721-4e0e-af5b-8b8a46ece06a/Screenshot_from_2023-07-21_23-44-13.png)

![Screenshot from 2023-07-21 23-44-17.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/33f24666-c5f7-481c-a925-4a4fc1543ae1/Screenshot_from_2023-07-21_23-44-17.png)

![Screenshot from 2023-07-21 23-44-37.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2f6ea0f9-52e1-40d6-869f-75f95412926a/Screenshot_from_2023-07-21_23-44-37.png)

![Screenshot from 2023-07-21 23-44-43.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c096c41e-4ea4-48bd-9907-4a1940d7647f/Screenshot_from_2023-07-21_23-44-43.png)

REFERENCE:

https://www.youtube.com/watch?v=rtcnHzpjArM&list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q&index=9

# **Summary (Understand What is a ROS Service):**

1. ROS services facilitate client-server interactions between nodes in ROS, allowing specific request-response communication.
2. Topics are used for sending continuous data streams between nodes, while services are ideal for structured client-server interactions.
3. ROS services consist of two parts: the server (providing the service) and the client (sending a request and receiving a response).
4. The `rosservice list` command lists all available services in the ROS environment.
5. The `rosservice info <service_name>` command provides information about a specific service, including its advertised node and message type.
6. The `rossrv show <service_type>` command displays the structure of a service message type, which includes a request and a response.
7. ROS services are suitable for computations or changing specific settings in nodes.
8. Ensure that the server node providing the service is running and accessible when using ROS services.

When to Use Topics vs. Services:

1. Topics: Use for continuous data streams, like sensor data or robot control commands, in one-to-many communication scenarios.
2. Services: Use for client-server interactions, where nodes need to make specific requests and receive responses in one-to-one communication scenarios.

Commands:

1. `rosservice list` - Lists all available services in the ROS environment.
2. `rosservice info <service_name>` - Provides information about a specific service, such as its advertised node and message type.
3. `rossrv show <service_type>` - Displays the structure of a service message type, including request and response fields.
4. `rosservice call <service_name> <request_data>` - Calls a ROS service and sends a request message to the server.
5. `rosservice call <service_name>` - Calls a ROS service with no request data (useful when the request doesn't require any input).
6. 

![Screenshot from 2023-07-22 15-02-41.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1c2a91cb-a700-440d-9c41-925164fff2fc/Screenshot_from_2023-07-22_15-02-41.png)

![Screenshot from 2023-07-22 15-02-36.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2a31f110-6c6d-4fba-81ef-ede9e8f530ec/Screenshot_from_2023-07-22_15-02-36.png)

![Screenshot from 2023-07-22 15-02-30.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/68dbaa4b-e05b-43fd-a066-f1a25070bc14/Screenshot_from_2023-07-22_15-02-30.png)

![Screenshot from 2023-07-22 15-02-33.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5900e068-209e-410f-8ed9-354f98699e77/Screenshot_from_2023-07-22_15-02-33.png)

![Screenshot from 2023-07-22 15-02-21.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e85e19d0-2bb0-46c4-b54b-a73b5c832d31/Screenshot_from_2023-07-22_15-02-21.png)

![Screenshot from 2023-07-22 15-16-26.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7dde8847-1d34-443d-a675-5abca1ccbbb4/Screenshot_from_2023-07-22_15-16-26.png)

![Screenshot from 2023-07-22 15-02-25.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/079caa1a-1886-4ee0-9d72-6fdb25839af7/Screenshot_from_2023-07-22_15-02-25.png)

![Screenshot from 2023-07-22 15-02-11.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7d29e4c3-34c6-465a-abcb-e8b2b7bdaf3b/Screenshot_from_2023-07-22_15-02-11.png)

![Screenshot from 2023-07-22 15-11-35.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/12af5b38-56ef-4a0a-b2cf-0405bda44e86/Screenshot_from_2023-07-22_15-11-35.png)

REFERENCE :

https://www.youtube.com/watch?v=0nGzvefzl-U

# **Summary (ROS Service Client with Python):**

- The goal is to create a service client in Python to change the color of a turtle's pen when it moves on the screen.
- ROS provides functionalities like publishers, subscribers, and services to communicate between nodes.
- The `rospy` library is used for Python programming in ROS.
- To wait for a service to be available, use `rospy.wait_for_service()`.
- To create a service client, use `rospy.ServiceProxy()` with the name and type of the service.
- The `try-except` structure is used for error handling when calling services.
- The `setpen` service is used to change the color of the turtle's pen, and it takes parameters for RGB values and pen width.
- A global variable, `previous_x`, is used to track the turtle's previous x-coordinate.
- The pen color is changed only when the turtle crosses a specific x-coordinate (in this case, 5.5) from left to right or right to left.
- A better approach is taken to avoid calling the service too frequently and only change the color when necessary.
1. Use `rospy.ServiceProxy` to create a service client in Python to call a service in ROS.
2. Handle service exceptions with `try``except` using `rospy.ServiceException`.
3. Test each functionality (subscriber, publisher, service) separately to ensure proper functioning.
4. Use global variables to store previous states and call the service only when needed.
5. Avoid frequent service calls as it can slow down the application.
6. To list available services: `rosservice list`.
7. To call a service from the terminal: `rosservice call`.
8. To get information about a specific service: `rosservice info`.
9. Use `rospy.loginfo` for printing log messages in ROS nodes.
10. Keep the node alive and running with `rospy.spin`.

Commands and functions used:

- `rospy.ServiceProxy`
- `try``except` with `rospy.ServiceException`
- `rosservice list`
- `rosservice call`
- `rosservice info`
- `rospy.loginfo`
- `rospy.spin`
    
    ![Screenshot from 2023-07-22 16-50-33.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/53ec120a-6f26-44e7-8cc7-9b9a9d26492b/Screenshot_from_2023-07-22_16-50-33.png)
    

![Screenshot from 2023-07-22 16-36-56.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/19df8dcd-351a-47bf-97ec-70255efcde77/Screenshot_from_2023-07-22_16-36-56.png)

![Screenshot from 2023-07-22 16-36-21.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d3492eb8-a7e7-48ad-863a-adaf63d54080/Screenshot_from_2023-07-22_16-36-21.png)

![Screenshot from 2023-07-22 16-36-01.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c8728655-cc27-4deb-ba75-d9d66da2c656/Screenshot_from_2023-07-22_16-36-01.png)

![Screenshot from 2023-07-22 16-36-08.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4576f8fa-4a7e-4e68-b227-5df54e673242/Screenshot_from_2023-07-22_16-36-08.png)

![Screenshot from 2023-07-22 16-35-49.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f66b43d8-4374-47ba-8acd-8abeb3e3c693/Screenshot_from_2023-07-22_16-35-49.png)

![Screenshot from 2023-07-22 15-16-26.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/74908f08-aea7-428b-a410-39bada39d73a/Screenshot_from_2023-07-22_15-16-26.png)

![Screenshot from 2023-07-22 16-37-05.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/adafc75c-7769-4791-8700-ce29c24bff71/Screenshot_from_2023-07-22_16-37-05.png)

REFERENCE :

https://www.youtube.com/watch?v=ezTzQFULZGo
