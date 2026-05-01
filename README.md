# Daedalus-Dashboard
>A good smart home interface doesn’t leave you lost within a maze of devices.
>It guides you out.

### Design Philosophy

The Daedalus Dashboard is built around a simple principle:  
a smart home interface should adapt to the way people think, not to the way devices are technically structured.

Instead of exposing integrations, entities, and infrastructure, the interface focuses on **user intent** and **predictable navigation**.  
The goal is to reduce cognitive load and allow users to interact with their home naturally, without needing to remember where devices or functions are located.

## Contents

- Purpose of the Project
- Scope of the Project
- Architecture Overview
	- Interface Hierarchical Structure
	- Dynamic View Structure
	- Conceptual Content Distribution Methodology
- Core Design Principles

___
### Purpose of the Project 

After years of integrations, apps (previously add-ons), and incremental development, custom Home Assistant dashboards often turn into fragmented collections of loosely connected views. Eventually, every new addition reveals the need for a complete redesign. This is often postponed, because without a scalable structure, the same cycle will inevitably repeat itself.

Home Assistant is also under constant development. While this continuous evolution brings new capabilities, it makes it difficult to anticipate future features and design an interface that remains consistent over time. 

An inconsistent dashboard also impacts usability. Without a coherent structure, users struggle to locate what they need and must rely on learned behavior. A well-structured and consistent interface, instead, supports intuitive navigation, allowing users to predict where the functions they need are likely to be after moving through only a few taps.

A more sustainable approach is to design the dashboard around user intent and maintain semantic consistency. Designing around user intent means organizing the interface according to what users want to do, rather than how devices or integrations are technically structured. Semantic consistency ensures that the same types of actions, concepts, and elements are always presented in the same way and in the same context. For example, lighting controls, climate settings, and security features follow consistent visual patterns and placement logic, so users can anticipate where functions are and navigate intuitively.

___
### Scope of the Project 

This project aims to design an **interface architecture** for Home Assistant that is:
- built around user intent;
- semantically consistent and predictable;
- scalable and adaptable to different display formats (landscape for wall displays, portrait for mobile);
- suitable for medium to complex home automation systems.

___
### Architecture Overview

The Daedalus Dashboard is based on three complementary design layers:
1. **Hierarchical navigation** – a four-level structure that organizes how users access information.
2. **Dynamic view layout** – views adapt to the current navigation context and progressively reveal information.
3. **Conceptual content distribution methodology** – devices and information are organized according to user intent rather than technical categories.

Together, these layers create an interface that is predictable, scalable, and easy to navigate even as the system grows.

#### Interface Hierarchical Structure

To maintain a **consistent, intuitive, and scalable interface**, the dashboard structure is organized into **four hierarchical levels**, allowing users to reach any function within **a maximum of four steps**.

1. **Level 1**
   This initial level provides a list of domains, which represent the highest level of abstraction in the hierarchical structure. Content is distributed among domains following the Conceptual Content Distribution Methodology (HYPERLINK)

2. **Level 2**
   This level provides a list o sub-domains, which refines the domain selection and allows access to related content.
 
3. **Level 3**
   This is the first level where actual content is presented. It presents the **primary information or overview** that directly relates to the user’s intent. It provides immediate insight and actionable data in a concise, easy-to-understand format.

4. **Level 4**
   This level provides access to additional content. When applicable, it dynamically updates according to the selection made on level 3, providing deeper context while keeping navigation intuitive and semantically consistent. 

This **four-level hierarchical structure** ensures the interface is **predictable, intent-driven, and scalable**, allowing users to efficiently navigate through views without losing orientation or context.

#### Dynamic View Structure

Each view in the Daedalus Dashboard is **dynamic and adaptable**, evolving as the user makes selections through the four hierarchical levels. The layout presents **information progressively and predictably**, guiding users from broad domains to specific contextual details in a clear and intuitive way.

The interface is organized into 3 main distinct areas:

1. **Area A - Navigation, Warnings and Shortcuts**
   Domain and sub-domain navigation (level 1 and 2) is presented in this area as well as warnings and contextual shortcuts. The domain selection collapses to reveal a dynamic sub-domain menu.

2. **Area B - Main Focus**
   Presents the primary information or overview as per level 3, offering immediate insight aligned with the user’s intent. When possible, content in this area is shown in a consistent graphical way using an interactive floor plan. 
   
4. **Area C - Context Panel**
   Provides all additional details as per level 4, that update dynamically based on the level 3 eventual selection.

This structure ensures that users can navigate efficiently, anticipate where functions are located, and access any feature.

![[screen.png]]

#### Conceptual Content Distribution Methodology

The Daedalus Dashboard is organized around **user needs**, ensuring that every domain serves a clear purpose and minimizes cognitive load. Content is distributed according to **functional relevance and user intent**, with each section providing a coherent set of information or controls.
Sub-domains are domain-specific and often include specialized features.  
For this reason they are handled in separate repositories.
Main domains are:

1. **Overview**
   Acts as the **control tower**, offering high-level summaries of home state, alerts, suggestions, and quick access to key functions.

2. **Environment**
   Everything that shapes the **perceived living environment**, such as lights, blinds, atmosphere, and scenes. This is where users _experience_ the home directly.

3. **Climate**
   Tools for understanding and controlling **thermal comfort and air quality**, including sensors, heatmaps, charts, and predictive models.

4. **Activities**
   Domestic processes with start, duration, and end, including appliances, robots, and automated workflows. Users _follow_ ongoing activities in real time.

5. **Utilities**
   Monitoring of energy, water, gas for consumption, production, costs, and loads. Devices like smart plugs are treated as **measurement and control tools**, not as actors in scenes.

6. **Security**
   Active and passive protection systems, including alarms, sensors, cameras, and events.

7. **Media**
   Entertainment control for TV, audio, multiroom setups, and media scenes.

8. **Maintenance**
   System health over time, including batteries, offline devices, errors, and infrastructure. Components here must **work reliably**, rather than being interacted with daily.

___
### Core Design Principles

The Daedalus Dashboard follows a set of **fundamental design principles** to ensure clarity, consistency, and intuitive use:

1. **Experience vs Infrastructure**
   Devices are placed based on _how they are used_, not _what they are_. This ensures the interface reflects **user intent** rather than technical structure.  
   _Example:_
   - a LED light → **Environment**
   - the LED’s power supply → **Maintenance**
   - a smart plug used for power measurement → **Energy**

1. **One Function, One Home**
   Every feature has **a single primary location**. Summaries or shortcuts may appear elsewhere for convenience, but functionality is never duplicated, reducing cognitive load and keeping the interface predictable.

2. **No Redundant Information**
   Visual elements convey multiple layers of information through **color, shape, or animation**, allowing the interface to remain **light and uncluttered** while preserving detail.

These principles guide every design decision, ensuring that users can navigate the system **intuitively**, in line with the scope of the project.

___

>The Daedalus Dashboard is an evolving project. 
>While the core principles and hierarchical structure are established, the interface may be refined over time as new design insights emerge or the framework is further optimized.
