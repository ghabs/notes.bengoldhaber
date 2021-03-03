---
layout: post
title: Vaccine Distribution Simulation
canonical_url: https://hash.ai/blog/vaccine-distribution-scenario-modeling
---

__[Originally published on the HASH blog](https://hash.ai/blog/vaccine-distribution-scenario-modeling)__

Optimizing vaccine allocation is a critical task - improving the distribution of vaccines could save tens of thousands of lives over the coming months. In partnership with researchers at the [Virginia Modeling, Analysis, and Simulation Center](https://www.odu.edu/vmasc), we created a simulation of the vaccine distribution process. 

Our goal is to provide decision and policymakers in health departments and emergency management with a tool for understanding and optimizing the distribution of COVID-19 vaccines at this current moment - focusing on allocation policies for storage and assignment of first and second doses from both vaccine manufacturers. Utilizing this model, policymakers are able to build a representative model of their community at scale and test various configurations, policies and structures to explore their impact on distribution, vaccine reserve utilization, and population immunity.

> When our customers came to us with an emergent question, HASH made it incredibly simple to get down to work and create a model that could serve as a a foundation for sharing knowledge and even hooking in our data. What would normally take weeks took hours. 
>
> Alex Nielsen, Team Lead, VMASC

## Business Logic

The simulation models distributor agents - pharmacies, hospitals, clinics - administering vaccines to patients. Every timestep represents one day. A stochastic number of patients arrive each day to the distributors to receive a vaccine, and as the simulation runs these same patients return for a second dose.

A distributor is characterized by its **throughput**, the number of patients it can treat in a day, and **vaccines on hand**, the number of vaccines it has in stock. Each distributor has a primary vaccine they provide, either Moderna or Pfizer. Vaccines are kept in general storage, or they’re reserved separately for use as a second dose (e.g. reserving vaccines for patients' second appointment).

The key decisions the distributor needs to make:

- If more people arrive than can be treated (because the distributor agent has a limited number of staff to administer vaccines), who should be turned away? People who haven’t received a vaccine, or people coming for their second dose? 
- Should the distributor set vaccines aside in reserve storage for patients who need a second dose, or should vaccines be available for any patient? If setting aside vaccines, how many should be reserved?

These decisions, or **scenarios**, can be set through global parameters (in globals.json)

![This image has an empty alt attribute; its file name is hOPEB-dObetcHAD8HksCReJ7u8fc43Dio7yO76-kgDgZMJ_COhOU5bBp1YuN2ZEP1ihZhVkuZDlNoutzZwyTB_27ZfSFWO1KIjFn_9lxgFoLArlmbU0MPYMvMU8ea_7XwdPPGxn-](https://lh3.googleusercontent.com/hOPEB-dObetcHAD8HksCReJ7u8fc43Dio7yO76-kgDgZMJ_COhOU5bBp1YuN2ZEP1ihZhVkuZDlNoutzZwyTB_27ZfSFWO1KIjFn_9lxgFoLArlmbU0MPYMvMU8ea_7XwdPPGxn-)

### Scenario Configuration

The simulation has many configurable parameters (visit the HASH Index page or the README for an explanation of each one); however, two ‘scenario’ options determine the two decisions related to second dose storage and patient prioritization.

Patient prioritization is set in the prioritize_group_option. There are two groups of patients - those who haven’t received their first dose and those who have. “Num_of_first_dose” represent the former, “second_dose_moderna” and “second_dose_pfizer” the second.

![This image has an empty alt attribute; its file name is yxG0kzglj10zuHem6ZX_Vy1Ca6R1hMmvfuiq3k2ZyaAghJxsJTci7t0ONLgSlVPZ-OlhQIlnmPqrGmddxFJPlIrFP-7lkifh4xG1-49DUxKR8S8EaiJ0CAV73pt4hR1-5OkDZHBx](https://lh6.googleusercontent.com/yxG0kzglj10zuHem6ZX_Vy1Ca6R1hMmvfuiq3k2ZyaAghJxsJTci7t0ONLgSlVPZ-OlhQIlnmPqrGmddxFJPlIrFP-7lkifh4xG1-49DUxKR8S8EaiJ0CAV73pt4hR1-5OkDZHBx)

![This image has an empty alt attribute; its file name is nXhyukiJJMB6Rs3uut01X_l972pkeAy2ZyiIKrec7wkLOoT3bmn-RgJxGFk0491JrQq6gMN59WoDVxQYXx5EtCcxlZiZYxvg4FpIx633joub5Pw4HKGxzIbpOvjc6ydZ-Xd8hLZa](https://lh5.googleusercontent.com/nXhyukiJJMB6Rs3uut01X_l972pkeAy2ZyiIKrec7wkLOoT3bmn-RgJxGFk0491JrQq6gMN59WoDVxQYXx5EtCcxlZiZYxvg4FpIx633joub5Pw4HKGxzIbpOvjc6ydZ-Xd8hLZa)

The vaccine reserve policies are set through three options.

![This image has an empty alt attribute; its file name is VHhBzmi4mfuCI-i8LTIRREYEGYAnBU6E8E933J-WPx8ox2wsPIBTKRPbiKXnHzEul5s832b-53-uThylILmZFMU92kaGMRHFCgT5s5ZR6ZosPCS2RcXsjq3X8a0a9XIZVmqDowUs](https://lh3.googleusercontent.com/VHhBzmi4mfuCI-i8LTIRREYEGYAnBU6E8E933J-WPx8ox2wsPIBTKRPbiKXnHzEul5s832b-53-uThylILmZFMU92kaGMRHFCgT5s5ZR6ZosPCS2RcXsjq3X8a0a9XIZVmqDowUs)

If `second_dose_separate_storage` is set as true for secondary appointments the distributor will first check if there are vials stored in secondary storage. These vials will **not** be used for first appointments.

![This image has an empty alt attribute; its file name is dN6d-Obz9j-0MdRarXTb7PEKKe5s7njc5kjzYe7EQCcVyPvQ1oydEKrISMiew2Wxu6ZZIRaJ7Xu1HTGlozVYu6gZX2s-iOLKtqqOPi88lGn2mWpPVVeZWydF5kDd2rQPFarNFXa3](https://lh4.googleusercontent.com/dN6d-Obz9j-0MdRarXTb7PEKKe5s7njc5kjzYe7EQCcVyPvQ1oydEKrISMiew2Wxu6ZZIRaJ7Xu1HTGlozVYu6gZX2s-iOLKtqqOPi88lGn2mWpPVVeZWydF5kDd2rQPFarNFXa3)

Setting `second_dose_divert_to_storage` to a positive integer is option B. Vaccine vials equivalent to the number specified in `second_dose_storage` will be diverted to secondary storage.

![This image has an empty alt attribute; its file name is SLKE2zyfnglDZjxq85B_XB1dAc9RpO-uU42haNjGDlI-mFgtfy2AGyj7TdYqvBKj-0Jgk3SiAzkoJ9dAefzfBCMcd6B9dV0E8taTX7k1jksvvCyHMw9GRqspBm3ZbQaTli03l3sn](https://lh5.googleusercontent.com/SLKE2zyfnglDZjxq85B_XB1dAc9RpO-uU42haNjGDlI-mFgtfy2AGyj7TdYqvBKj-0Jgk3SiAzkoJ9dAefzfBCMcd6B9dV0E8taTX7k1jksvvCyHMw9GRqspBm3ZbQaTli03l3sn)

Setting `second_dose_matching` as true is equivalent to option A, where the distributor will set vials in secondary storage equivalent to the number of vials administered on that day.

## Key Assumptions

The units of vaccines are **vials** and **doses**. A vial contains five doses. Every patient is administered one dose per visit. Short term spoilage occurs when there is a mismatch between the number of patients served and the number of vials/doses retrieved from storage. For instance, if four patients arrive at a distributor, one vial will be used and four doses from that vial will be administered. The extra dose goes unused, and spoils at the end of the day. **Long term spoilage** occurs when the age of a vaccine exceeds its storage life. At that point the vaccine is considered spoiled and removed from the distributor's reserves.

Currently the vaccine distributors receive a weekly shipment of their vaccine type from the shipping agent. For example, one distributor agent would receive 20 vials (100 doses) of the Moderna vaccine on time step 1, and then another 20 vials on timestep 8, etc. Another distributor agent would receive 20 vials of the Pfizer vaccine on timestep 2, then timestep 9, and so on. The number of vials received is fixed - they always receive the same amount.

The population agent stores second dose appointments. After a patient gets the first dose of the vaccine, they are scheduled to return to the distributor after a set number of timesteps (configurable in appt_delay). If the distributor is at capacity, they are turned away.

## Metrics and Plots

![This image has an empty alt attribute; its file name is ITkZV0L2iV-RILxG0u4gaWLrtKbfYCYsFdBMlpOmqQL3yCfCwW0kL1IzexmmVVxGr-h5Yc2lZcR-xI0pfSHZRU8-gPTjF8OMmPsyPAgCViNqOFKd3Q7kdO7H1ibTB1L95QtKDR7i](https://lh5.googleusercontent.com/ITkZV0L2iV-RILxG0u4gaWLrtKbfYCYsFdBMlpOmqQL3yCfCwW0kL1IzexmmVVxGr-h5Yc2lZcR-xI0pfSHZRU8-gPTjF8OMmPsyPAgCViNqOFKd3Q7kdO7H1ibTB1L95QtKDR7i)

Plots, in the Analysis tab, provide insight into what’s happening during the simulation.

There are six default charts:

- Vaccinations: Track the number of Moderna and Pfizer vaccinations administered
- Reserves: The aggregate number of vaccines distributors have in storage, split between first and second doses.
- Vaccination Rate: The average number of vaccinations administered every timestep
- Total Wasted Doses: The short and long term spoilage of vaccines on hand
- Total Vaccines: The number of vaccines shipped
- Population Immunity: The percentage of the population (set in globals) level immunity, expressed as number of one dose patients * 0.5, + number of second dose * .95, divided by total population.

## Extensions

We envision this simulation as a jumping off point for more detailed and tailored distribution models. There are numerous directions that users can take this; some potentially high value features:

- Additional heterogeneity: Different distributor agents could receive different amounts of vaccines, could have different throughputs, could receive drastically different numbers of patients, etc.
- Feedback loops for vaccine requests: Vaccine allocators are likely responsive to increased demand and shortages from specific distributors - expand the shipping agent behaviors and logic to deliver more vaccines to distributors that are short on vaccines.
- Appointment logic: Customize the sim so that patients pre-schedule appointments and vaccine reserve rates depend on upcoming appointments. Second dose appointments could be pushed, not entirely cancelled.