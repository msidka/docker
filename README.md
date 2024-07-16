## **Docker Container Administration | An Introduction & Principle Concept**<br>

## &nbsp;&nbsp;**Table of Contents**
- [Technological Transformation](https://github.com/msidka/docker/blob/main/README.md#technological-transformation)
   - [Bare Metal](https://github.com/msidka/docker/blob/main/README.md#bare-metal)
   - [Key Reasons for Transition](https://github.com/msidka/docker/blob/main/README.md#key-reasons-for-transition)
- [Virtualization](https://github.com/msidka/docker/blob/main/README.md#virtualization)
   - [KVM Virtualization](https://github.com/msidka/docker/blob/main/README.md#kvm-virtualization)
       - [KVM Features](https://github.com/msidka/docker/blob/main/README.md#kvm-features)
   - [OS Virtualization](https://github.com/msidka/docker/blob/main/README.md#os-virtualization)
      - [Container](https://github.com/msidka/docker/blob/main/README.md#container)
         - [More Defination](https://github.com/msidka/docker/blob/main/README.md#more-defination)
         - [Different Container or Container runtimes provider](https://github.com/msidka/docker/blob/main/README.md#different-container-or-container-runtimes-provider)
         - [What is Docker](https://github.com/msidka/docker/blob/main/README.md#docker)
          - [Docker Features](https://github.com/msidka/docker/blob/main/README.md#docker-features)
          - [Why We should use Docker Container](https://github.com/msidka/docker/blob/main/README.md#why-use-docker-container)
          - [Docker Architecture and Components](https://github.com/msidka/docker/blob/main/README.md#docker-architecture-and-components)




### 🚀Technological Transformation

 - #### 🔥**Bare Metal**
   - Performance: Direct access to hardware, no virtualization overhead.
   - Control: Full control over the hardware and software stack.
   - Use Case: High-performance computing, gaming servers, financial trading systems.


<img src="https://github.com/user-attachments/assets/0e0656c0-5e68-4a18-8b3e-6a00815ce0c0" alt="Technological Transformation" width="800"/>


 - #### 🔥**Key Reasons for Transition:**
   - **Bare Metal to Virtualization:** To improve resource utilization, flexibility, and isolation while maintaining control over the hardware.
   - **Virtualization to Cloud:** To leverage scalability, cost efficiency, reduced maintenance, and global accessibility, enabling faster innovation and business agility.
   - **Example:** Instead of having ten servers each running at 10% capacity, virtualization can consolidate them into one or two servers running at 80-90% capacity.

### 🚀Virtualization

**Virtualization is software technology that separates physical infrastructures to create multiple virtual machine (VM) or virtual environments on a single server.**

This software technology of virtualization system is known as a virtual machine monitor (VMM) or virtual manager, which separates compute environments from the actual physical infrastructure–this makes it possible to run several operating systems on one computer at the same time. 
**A virtual machine monitor or VMM, also known as a hypervisor, is software that creates, runs and manage virtual machines (VMs).**

- **Resource Utilization:** Better utilization of physical hardware by running multiple VMs.
- **Isolation:** Strong isolation between applications.
- **Flexibility:** Easier to create, manage, and scale VMs.
- **Use Case:** Server consolidation, development and testing environments.


<img src="https://github.com/user-attachments/assets/9d570ca5-1d54-410e-a388-91507c479233" alt="Technological Transformation" width="800"/>




There are **two** main types of virtualization technology — 

   - **KVM Virtualization**
   - **OS Virtualization**

 #### 🔥KVM Virtualization

**KVM (Kernel-Based Virtual Machine) Is An Open-Source Virtualization Technology That Allows You To Run Multiple Virtual Machines (VMs) On A Linux/Windows Host**. A Kernel-based Virtual Machine (KVM) allows you to turn Linux or Windows Server into a hypervisor, allowing your operating system to produce multiple virtual machines and isolated virtual environments.

 - **Type 1 - hypervisor** is running on **bare-metal hardware**. Such hypervisors are VMWare ESXi, Linux KVM, Hyper-V
 - **Type 2 - hypervisor** is running inside **Host OS**. Such hypervisors are VMWare Workstation are Oracle VirtualBox

##### 📌KVM Features
 - Security
 - Storage
 - Hardware support
 - Memory management
 - Live migration
 - Performance and scalability
 - Scheduling and resource control
 - Lower latency and higher prioritization

#### 🔥OS Virtualization

**একটি কার্নেলের ওপর একাধিক isolated ইউসার স্পেইসের অস্তিত্বকে অপারেটিং সিস্টেম লেভেল ভার্চুয়ালাইজেসন বলে.**
প্রতিটা ইউসার স্পেইসের রানটাইম এনভায়রনমেন্ট, ইউসার সেটিংস, ইত্যাদি ভিন্ন। আর একটা ইউসার স্পেইসের প্রসেস আরেকটা ইউসার স্পেইসে প্রবেশ করতে পারে না। মানে মেমোরি প্রটেকশন.

**User Space and Kernel Space**

অপারেটিং সিস্টেমে কিছু প্রসেস আছে যাদের সিস্টেম রিসোর্সগুলো (System Resource) সরাসরি অ্যাক্সেস করার প্রিভিলেজ (Privilege) থেকে থাকে। এই প্রসেসগুলো সাধারণত কার্নেল (Kernel) এবং ডিভাইস ড্রাইভার (Device Drivers) হয়ে থাকে। এসমস্ত প্রিভিলেজসম্পন্ন প্রসেসসমুহের মেমোরি প্রটেকশনের জন্যে ভার্চুয়াল মেমোরি স্পেইসের একাংশকে dedicate করে দেয়া হয় । এর কারনে ভার্চুয়াল মেমোরি দ্বিখণ্ডিত হয় । একটি খণ্ডে চলে কার্নেল আর ডিভাইস ড্রাইভারদের মত প্রিভিলেজ সম্পন্ন প্রসেসসমুহ আর এই খণ্ডটা কার্নেল স্পেইস (Kernel Space) নামে পরিচিত। আরেকটি খণ্ডে চলে বাকি সব সাধারণ প্রসেস যেমন ব্রাউসার, টেক্সট এডিটর, গেমস, ইত্যাদি আর এই খণ্ডটা ইউসার স্পেইস (User Space) নামে পরিচিত।

##### 📌**Container**
Let's revisit the different ways of deploying applications we talked about—locally, On-prem, and in the cloud. Imagine a friend, like another developer, wants to work with your code. They'd need to get their own "copy" of it. They'd go to a platform like GitHub and download your project files. Then, they'd install any extra tools needed to run your code smoothly. But sometimes, their computer might have different settings that make it hard for your code to work right. That's where containers come in handy. They wrap up your code with all the settings and tools it needs to run, no matter where it's put.

   - ###### 📌**More Defination**
      - **Containers are like pre-packaged sets of tools and code. You just plug them in, and they start working without any fuss.**
      - **Containers are predefined configurations and dependencies, along with the code files that make it possible for the code to run seamlessly.**
      - **একটা কার্নেলের ওপর আলাদা isolated ইউসার স্পেইসগুলোকে (User Space) কন্টেইনার (Container)বলা হয়.**
      - **Container is Runnable instance of the image, basically it is an isolated process.**
      - **Container is package of software that includes all dependencies: code, runtime, configuration, and system libraries so that it can run on any host system.**


<img src="https://github.com/user-attachments/assets/d91c7e3b-b50b-4612-96d7-893f0ae3ef4d" alt="Technological Transformation" width="600"/>




###### 📌**Different Container or Container runtimes provider**

- Docker
- Podman
- Containerd
- CRI-O
- LXC

https://www.linkedin.com/posts/mmumshad_kodekloud-devops-kubernetes-activity-7153377989160751105-viax/?utm_source=share&utm_medium=member_desktop

### 🚀**Docker**

Docker is a **daemon-based** software platform that uses **OS-level virtualization** to **build, deploy, and manage applications within containers**. Containers are built from images, which in turn are constructed from Dockerfiles, providing an abstraction layer for application deployment.

So Docker is an open-source lightweight containerization technology. It allows you to automate the deployment of applications in lightweight and portable containers


<img src="https://github.com/user-attachments/assets/013d6a23-7c08-43de-affe-ccad76fd5adc" alt="Technological Transformation" width="600"/>


#### 🔥**Docker Features**
- **Building**
- **Shipping**
- **Run and managing Application**
- **Compatibility**
- **Dependences**
- **Rapid Scaling**
- **Easy  and Faster Configuration**
- **Increase Productivity**
- **Application Isolation**

#### 🔥**Why Use Docker Container**
- Shifting from Monolithic to Microservices Architecture.
- Sometimes Software Does Not Work in Another System.
- Cross-platform Consistency (Windows/Linux).
- DevOps and Continuous Delivery.
- Enables faster software delivery cycles.
- Docker enables efficiency and reduces operational overheads so that any developer, in any development environment
- To help automate the deployment of applications inside containers.
- Docker enables more efficient use of system resources.
- Simplifies the application development and deployment process.
- **Collaboration’ with Docker**

<img src="https://github.com/user-attachments/assets/67334d6a-99b0-49ec-a643-dda317c298e1" alt="Technological Transformation" width="600"/>


- **Also, the Agile Development without Docker culture results in many issues as shown in the below picture.**

<img src="https://github.com/user-attachments/assets/ee094d19-07ae-47ce-9a6b-e23cd5da8272" alt="Technological Transformation" width="600"/>


- **To overcome all these situations the need for containerization with Docker arises.**

<img src="https://github.com/user-attachments/assets/a4a7fd8f-b218-4839-b4f3-2e7fb16f04b4" alt="Technological Transformation" width="600"/>



#### 🔥Docker Architecture and Components

<img src="https://github.com/user-attachments/assets/09636ab5-d30a-4716-9ac9-f6bc55e70b1e" alt="Technological Transformation" width="600"/>


