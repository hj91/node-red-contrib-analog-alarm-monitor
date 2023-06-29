# Analog Alarm Node for Node-RED

This Node-RED node, `analog-alarm`, allows you to monitor, identify, and log alarm conditions for continuous analog data in your Node-RED flows.

## Overview

Monitoring analog data for specific conditions and identifying when these conditions are met is a common requirement in many real-world systems. These systems may range from industrial processes, environmental monitoring systems, to IoT devices. In such systems, it's crucial to raise alarms when monitored parameters exceed or drop below certain thresholds.

The `analog-alarm` node allows your Node-RED flow to perform this operation. It enables real-time monitoring of analog data against user-configured Hi, HiHi, Lo, and LoLo limits along with a set deadband. It provides a user-friendly interface to input these limits and updates the node's status to reflect the current alarm state.

## How It Works

This node continually receives numeric input which is compared against the predefined limits. If the value exceeds the Hi or HiHi limits or falls below the Lo or LoLo limits, the node generates an alarm status output. 

A deadband value is also set to handle minor fluctuations or noise in the input data, ensuring that temporary spikes or drops do not trigger unnecessary alarms. Alarm checks are only enabled when an incoming message with a Boolean `true` and a topic `enable` is received.

The node only sends an output message when the alarm status changes, which reduces repetitive alarms. Once an alarm is cleared (i.e., the parameter returns to its normal range), the node logs the cleared alarm for easy tracking.

## Use Case: Industrial Process Monitoring

In industrial processes, the condition of machinery or the state of the process often needs to be continuously monitored. A particular set of values might represent normal operation, whereas deviations from this range could indicate potential issues or critical failures.

The `analog-alarm` node allows you to model such monitoring mechanisms. Each limit could represent a specific condition, and the incoming data can be continuously checked against these conditions. 

By integrating real-time sensor data into the `analog-alarm` node, your Node-RED flow can track the process parameters in real-time and react to any deviations, thereby ensuring safe and efficient operations.

## Usage

1. Drag and drop the `analog-alarm` node into your flow.

2. Double-click on the node to open the node editor.

3. In the node editor, you can configure the alarm limits (Hi, HiHi, Lo, LoLo) and the deadband value, as well as provide an Area Name and Alarm Description. 

4. The node reacts to incoming messages containing the parameter value that needs to be monitored.

5. The node will output a message with a payload containing the alarm description, current value, and alarm status (Hi, HiHi, Lo, LoLo, or Normal) whenever the alarm status changes.

6. The node's status will display the current alarm state.

7. Additionally, a message with a Boolean `true` and a topic `enable` is required to enable the alarm checks.

## Contributing

Contributions are welcome. Please raise an issue for bugs, features, or suggestions.

## License

GPL-3.0

## Author 

Harshad Joshi @ Bufferstack.IO Analytics Technology LLP, Pune
