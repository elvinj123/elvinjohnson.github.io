---
layout: page
title: Truck Load Optimization and Automation
description: Truck load optimization and Automation for logistics
img: /assets/img/truck load cover.jpg
importance: 3
category: Internship
---
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/protiviti-logo.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
I completed this project while interning with <a href="https://www.protiviti.com/IN-en">Protiviti</a>. In this project, the focus was on cost optimization for a major steel pipe manufacturing company by efficiently  optimizing the truck loading process of steel pipes, by leveraging the power of Data science (AI/ML). For the comany, once the finished steel pipes were produced by the company, they were stored in their godown. From here, the goods were loaded onto specific trucks and trailers belonging to various vendors, depending on the size of the pipes and the delivery cost estimated by the vendors. 

Until this project, all the pipes were loaded onto trucks in a random, inefficient manner, thus, leading to higher overall spend for resources and transportation. Hence, focus was on cost optimization by efficiently optimizing the truck loading process of steel pipes in two ways. First,  handling of all data which was done via manual entry of excel sheets previously, was streamlined and automated. Second, the transporters available for a particular delivery location were assessed based on factors. Once the vendors were selected, the trucks were loaded in a optimum fashion by efficiently clubbing orders for the same location, thus, saving the number of trucks. The project had other subprojects too, but my job was to work on the above 2 subprojects.

<h5><b>Overview of Truck loading procedure</b></h5>
The steel manufacturing plant receives orders from the sales team a few days before the beginning of each month. These orders are to be delivered to the customer over the entire month, until the order requirement was satisfied. Once the order requirement is received each month, the production team would tally the amount of orders already available in their stockyard and would determine the amount of manufacturing that needs to be done based on the balance amount. Once the month begins, based on the amount of production of each day, the stock that can be liquidated is updated daily. After this, the vendors/trucks are assigned and a person determines who the transporter would be, what would be the destination, how many vehicles would be needed, how much amount of material would be present in each truck, which orders could be combined into on vehicle etc. 

As an intern, I was assigned various tasks in the tream. The truck loading process had to be automated in an optimized fashion and the data obtained had to be handled and put to use in an efficient manner. My initial work was to first, write code to clean, merge and maintain data that was required at each stage. Second, to write code to track the orders that were placed initially throughout, from the time of placing the order uptil the point of dispatch and to keep track pending amount for each order. Third, to write code to check the amount of materials available daily, and accordingly calculate the amount of material that could be sent each day. Fourthly, to write code to automatically assign a vehicle type based on the material to be delivered and to write code to automate the loading of a vehicle in an efficient manner to achieve cost saving, by clubbing orders in an optimized way based on their destinations, which was the crux of the project. These were the major tasks that I did, apart from others. In the end, I had to integrate all these tasks into a single code to bring the project to successful completion. The final automation process would generate a report daily, that would tell them the orders that need to be delivered, specifically how much amount, which vendor, the clubbing etc, thus, resulting a major reduction in resources needed.

<h5><b>Key takeaways from this internship project</b></h5>
1. <b>Data cleaning and that presentation of data into understandable/usable formats requires significant time and effort.</b> In this project, the data received was in the form of numerous excel sheets and majority of them were hand entries and were not system generated. This led to lack of consistency ans preparing was very difficult. 
2. <b>Gather whatever data you can get your hand on. It's better to realize later that some data is not required than to miss out on data that could reduce time and effort at a later stage.</b>

3. <b>Always write code in a way that is understandable to others</b>, which makes it much easier for someone to cross verify your work at crucial points. Simply commenting wherever appropriate helps a lot.

4. <b>Always write code in a way that it can be modified easily</b>, preferably use functions for various tasks. That way, its easier to make changes as and when the client requires, as the project evolves.

5. <b>Keep documenting the client requirements at every meeting (especially details specific to your task)</b>, it helps to be able to refer back to some of the initial meeting documents instead of having to ask them about it again.

6. <b>Always keeps others working on components of the same project updated about your work</b>, this will help eliminate compatibility issues at a later stage, when integrating.

7. I also learnt valuable lessons about <b>presenting the work done at each stage in a way that would be easy to understand</b>, for example, using flowcharts.

8. Apart from the above, I had to put the pandas library for Python to extensive use, and I learnt a lot. I also learnt valuable coding tips from seniors and colleagues.