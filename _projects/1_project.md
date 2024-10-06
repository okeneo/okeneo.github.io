---
layout: page
title: Unmanned Arial Systems
description: A university club building autonomous drones
img: assets/img/generic-drone.jpg
importance: 1
category: current
---

### GitHub Repository

Check out our [GitHub organization](https://github.com/UMUAS/) to explore our code, projects, and contributions.

### About UMUAS

University of Manitoba Unmanned Arial Systems (UMUAS) is a club focused on building autonomous drones for the [AEAC competition](https://www.aerialevolution.ca/) and spreading the passion for engineering drones. Here is our [website](https://umuas.ca/), [Instagram](https://www.instagram.com/um_uas/) and [LinkedIn](https://www.linkedin.com/company/university-of-manitoba-unmanned-aerial-systems-team/) pages.

### 2023-24

The task for the 2023-24 competition was to navigate to different targets autonomously using object detection while carrying four passengers (barbie dolls). Our spectacular structure, electrical and communication, and power and propulsion teams built a hexacopter (six arms) drone for the competition, seen below:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/hexacopter.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Here is a [video](https://www.instagram.com/reel/C5dvbBPuIl0/?utm_source=ig_web_button_share_sheet) from one of our flight tests.

I generally focus on the software side of things and worked as the flight termination lead with the primary responsibility of ensuring the safe landing of the drone in the event this is required. I used a combination of [`MAVLink`](https://mavlink.io/en/) messaging (using the `pymavlink` library), `QGrooundControl` (our Ground Control Station software) and `Gazebo` (for software simulations). Below is a code snippet for arming the drone using `pymavlink`, for example:

```python
def arm(conn):
    conn.mav.command_long_send(
        conn.target_system,
        conn.target_component,
        mavutil.mavlink.MAV_CMD_COMPONENT_ARM_DISARM,
        0,
        1,
        0,
        0,
        0,
        0,
        0,
        0,
    )
    logger.info("Initiating vehicle arm procedure...")
    conn.motors_armed_wait()
    logger.info("Vehicle successfully armed.")
```

I also helped set up our GitHub repository and conducted code reviews. The repository can be found [here](https://github.com/UMUAS/Nav2023-2024).

### 2024-25

Next year's competition is in Medicine Hat, Alberta. Our task is first to spot fires and map the environment, and second, to put out the fires. We are building two drones, one for each task.

I returned as the flight termination lead. This year, we are introducing `ROS2` and `Docker` to our stack to aid better communication between the different components and systems of our drone and to allow portability and consistency between all our various environments. We are also switching our Ground Control Station software from `QGrooundControl` to `Mission Planner` and the firmware of our flight controller from `PX4` to `Ardupilot`. The repository can be found [here](https://github.com/UMUAS/).
