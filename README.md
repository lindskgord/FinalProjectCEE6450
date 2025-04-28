Modeling Ferrous Iron (Fe²⁺) Transport in Groundwater 
Using PFLOTRAN: Study of Solute Migration 
Lindsay Gordon1 
1Utah State University, (L.Gordon@usu.edu) 

Abstract 
	This study presents a numerical investigation of ferrous iron (Fe2+) transport in a groundwater 
system using PFLOTRAN, focusing on solute migration influenced by different and hypothetical geologic 
settings. The model was configured to simulate a 2D domain incorporating Richards flow and non
reactive transport (GIRT), using Fe2+ as a conservative tracer to observe potential transport patterns in 
simplified hydrogeologic settings. The conceptual models are based on an Acid Mine Drainage (AMD) 
scenario in which water flows over mine tailing and enters an aquifer. One conceptual model included a 
point source injection of Fe2+ on the western boundary, representing a contaminant source, with specified 
recharge and discharge zones to simulate natural groundwater gradients. The second conceptual model 
included a point source at the surface of the aquifer, representing a more realistic AMD scenario. Results 
highlight the importance of flow dynamics in controlling solute migration, especially under varying 
permeability conditions. The simulation results provide insight into the movement of heavy metals acting 
as a dense tracer and suggest pathways for future work using reactive transport models for more 
complex geochemical interactions. 
 

Introduction 
	Groundwater contamination of heavy metals is a significant environmental concern, particularly in 
areas in which there are existing heavy metal mines, or coal mines. The results of water's interaction with 
mine tailings is referred to as “Acid Mine Drainage”. This is due to the fact that when minerals with heavy 
metals, such as pyrite (which contain iron and sulfur), react with water and oxygen, the resulting product 
is sulfuric acid and ferrous iron (Fe2+) (Younger et al., 2020) which significantly lowers the pH of the water, 
and this low pH allows for the continued leaching of other heavy metals into the groundwater system 
which may eventually contaminate a surface water system.  

	The mechanisms of the contamination are important for predicting plume migration and for 
designing remediation strategies. The purpose of this study is to explore these processes in increasingly 
complex geologic systems and to make observations of movement.  This project aims to simulate the 
transport of Fe2+ in a variable subsurface environment using PFLOTRAN. The objective is to observe the 
behavior of Fe2+ as a conservative tracer under non-reactive conditions and to evaluate how flow 
dynamics and changing geology influence contaminant migration.  


Methods 
Model Description 

	Seven different simulations were conducted using PFLOTRAN. All of the models used the 
Richards flow process and the GIRT model for solute transport. Although Fe2+ is a reactive species, it was 
modeled as non-reactive for simplicity and for focus on the physical transport mechanisms. A 2D grid 
represents a cross-section of a groundwater system. The domain was 100m in length, and 10m in depth. 
The different scenarios all include the same basic flow regime, with the flow from the west to the east, a 
no flow boundary at the bottom of the model, a specific head boundary which represents a theoretical 
river, and a seepage boundary to the west which represents a theoretical recharge area. The different 
models shown are:  


1.) Fe2+introduced from the entire west face with a uniform aquifer 
2.) Fe2+ introduced from the entire west face with an aquifer of four different layers with different 
permeabilities.  
3.) Fe2+ introduced from the entire west face with an aquifer of four different layers with different 
permeabilities, and a 10m “fault” at 45-55m which is a vertical section with an increased permeability 
4.) Fe2+ introduced from the entire west face with an aquifer of four different layers with different 
permeabilities, and two 10m “faults” at 15-25m and 45-55m which are vertical sections with an increased 
permeability 
5.) Fe2+ introduced at the surface between 0-10m in a uniform aquifer 
6.) Fe2+ introduced at the surface with an aquifer of four different layers with a confining layer 
7.) Fe2+ introduced at the surface with an aquifer of four different layers, and two 10m “faults” at 15-25m 
and 45-55m which are vertical sections with an increased permeability 


Model Setup 
Hydraulic and Transport Properties 
• Saturated Hydraulic Conductivity (Ksat): 1 × 10⁻⁵ m/s (base case for uniform layer, modified in 
layered scenarios) 
• Porosity: 0.35 (varied in stratified cases) 
• Van Genuchten Parameters: α = 0.04, n = 1.6 
• Diffusion Coefficient: 1 × 10⁻⁹ m²/s 
• Longitudinal Dispersivity: 10 m (base case) 
• Transverse Dispersivity (horizontal/vertical): 5 m / 1 m (base case) 

Initial Conditions 
• Liquid Pressure: Hydrostatic, with a datum at 10 m elevation, and a pressure gradient of -0.02 
Pa/m or -0.05 Pa/m.  
• Fe²⁺ Concentration: Background concentration initialized at 1 × 10⁻¹⁰ mol/L across the domain. 

Boundary Conditions: 
• Left boundary: Seepage boundary to act as a recharge area, unable to make the code work using 
the recharge transport condition, so a lake transport condition was used in an attempt to mimic a 
recharge area.  
• Point source injection of Fe²⁺ at 1 mg/L over the entirety of the western boundary for Scenarios 1
4, for Scenarios 5-7 the Fe²⁺ was injected at the surface from 0-10m. 
• Right boundary: Constant head representing a discharge zone or a theoretical river. 
• Bottom boundary: No-flow. 

Chemistry Setup 
• Fe2+ was used as the “Primary species” in the chemistry block 
• The use of the chemistry block in PFLORTRAN allowed for the properties of iron to be simulated.  

Scenario-Specific Modifications 
Each scenario introduced structural complexity to the aquifer to investigate the influence of heterogeneity 
and preferential flow paths. 

Scenario 1: Uniform Aquifer 
• Aquifer Material: Single homogeneous layer (soil1) 
• Permeability: 1 × 10⁻¹² m² 
• Porosity: 0.25 

Scenario 2: Four-Layered Aquifer 
• The domain was divided into four horizontal layers with varying hydraulic properties: 
o Layer 1 (0–2.5 m): soil1 – K = 1 × 10⁻¹² m², φ = 0.25 
o Layer 2 (2.5–5 m): soil2 – K = 5 × 10⁻¹³ m², φ = 0.35 
o Layer 3 (5–7.5 m): soil3 (confining layer) – K = 1 × 10⁻¹⁴ m², φ = 0.1 
o Layer 4 (7.5–10 m): soil4 – K = 2 × 10⁻¹² m², φ = 0.3 

Scenario 3: Four-Layered Aquifer with Single Fault 
• Same stratigraphy as Scenario 2. 
• Fault Zone (45–55 m horizontal extent, full depth 0–10 m): 
• Material: faultzone – K = 1 × 10⁻¹¹ m², φ = 0.1 
o The fault region provided a vertical high-permeability pathway, embedded centrally within 
the domain. 

Scenario 4: Four-Layered Aquifer with Two Faults 
• Same stratigraphy as Scenario 2. 
• Fault Zones: 
o Fault 1 (15–25 m): Vertical fault with high permeability (same as above). 
o Fault 2 (45–55 m): Vertical fault, same properties as Fault 1. 
o These faults created additional preferential pathways, enhancing vertical connectivity and 
enabling partial lateral movement in the upper layers. 

Simulation Control 
• Final Simulation Time: 15 years 
• Initial Timestep: 0.1 hours 
• Maximum Timestep: 30 days 
• Output Frequency: Every 100 days (0–2 years), every 30 days (2–15 years) 

Scenario 5: 
• Same simulation as Scenario 1, except the iron is introduced immediately, and the source of the 
iron is located at the surface between x=0 and x=10.  

Scenario 6: 
• Same simulation as Scenario 2, except the iron is introduced immediately, and the source of the 
iron is located at the surface between x=0 and x=10. 

Scenario 7:  
• Same simulation as Scenario 4, except the iron is introduced immediately, and the source of the 
iron is located at the surface between x=0 and x=10. 

Simulation Control for Scenarios 5-7 
• Final Simulation Time: 10-15 years 
• Initial Timestep: 0.1 hours 
• Maximum Timestep: 30 days 
• Output Frequency: Every 100 days (0–2 years), every 30 days (2–15 years) 

 
Results 

	This section presents the observations of the transport behavior of Fe²⁺ across four different 
hydrogeological scenarios simulated over a 10–15-year period. The movement of Fe²⁺ was influenced by 
both the layering of the aquifer and the introduction of high-permeability fault zones. Across all scenarios, 
Fe²⁺ displayed a strong tendency to migrate rapidly downward through the aquifer, indicating behavior 
consistent with a dense tracer influenced by gravity due to its heavier molecular weight. 

Scenario 1: Uniform Aquifer with Fe²⁺ Introduced Along the West Face 
	In the uniform aquifer scenario, where Fe²⁺ was introduced along the entire west face, the iron 
plume exhibited an initial downward vertical migration pattern, moving quickly to the bottom of the 
domain, which it then began to spread laterally with the movement of the flow. This behavior supports the 
hypothesis that Fe²⁺, acting as a dense tracer, sinks rapidly in homogeneous conditions without 
stratigraphic or structural barriers to impede its flow. 
https://www.youtube.com/watch?v=9NtXHwFAwWo 

Scenario 2: Four-Layered Aquifer with Fe²⁺ Introduced Along the West Face 
When the aquifer was divided into four distinct layers of varying permeability, the transport 
dynamics of Fe²⁺ changed subtly. Initially, it was expected that the confining layer near the surface would 
inhibit vertical movement and promote lateral dispersion along the uppermost permeable layer. However, 
the simulation showed that Fe²⁺ still migrated quickly downward and flowed primarily below the confining 
layer. This is likely due to the fact that the iron was introduced along the entire west face, but it is still 
interesting that there was no lateral movement along the top layer above the confining layer.  
https://www.youtube.com/watch?v=pTd0NMnYrlo&t=16s 

Scenario 3: Four-Layered Aquifer with a Single Fault at 45–55 m 
Introducing a vertical high-permeability fault between 45 m and 55 m depth resulted in localized 
vertical movement of Fe²⁺ transport. The fault zone acted as a preferential flow path, and when the iron 
encountered the fault zone, it displayed some upward movement, but was unable to move far enough to 
rise above the confining layer, and did not exhibit lateral movement in the uppermost layers. The overall 
plume shape remained similar to previous simulations, with the iron still showing favorability to the bottom 
layer due to its density.   
https://www.youtube.com/watch?v=Y0v0qOs5QXU 

Scenario 4: Four-Layered Aquifer with Two Faults at 15–25 m and 45–55 m 
In the fourth scenario, two vertical high-permeability fault zones at 15–25 m and 45–55 m depths 
produced more complex transport behavior. The presence of the upper fault (15–25 m) facilitated greater 
vertical communication between the upper layers of the aquifer, allowing Fe²⁺ to exhibit some lateral flow 
along the topmost layer by the end of the simulation period. The second fault (45–55 m) continued to 
promote deep vertical migration. Compared to previous scenarios, the plume was slightly more dispersed 
laterally in the upper layers, though the general trend of downward movement remained dominant. The 
dual-fault system created enough vertical heterogeneity to produce limited but notable horizontal 
spreading, particularly late in the simulation timeframe. 
https://www.youtube.com/watch?v=rNysI1ux-9g&t=2s 

Scenario 5: Uniform aquifer with Fe²⁺ Introduced Along the surface (x=0-10m): 
This scenario introduces the iron tracer at the surface with the assumption that the point source is 
10m wide, from x=0 to x=10m. This scenario is more like what we may expect from an actual point source 
contamination. Tracer is introduced immediately and very quickly contaminates the aquifer. In general, the 
permeability of the aquifer is quite high, which may be the cause for the quick movement of the iron 
tracer.  
https://www.youtube.com/watch?v=MrC_VhGThWc 

Scenario 6: Four-Layered Aquifer with Fe²⁺ Introduced Along the Surface 
In this scenario, the iron is introduced at the surface, but the aquifer becomes a bit more complex 
by the introduction of four different layers within the aquifer, including a confining layer near the top of the 
aquifer. The results from this scenario show what would be expected, with the majority of the iron 
remaining above the confining layer. However, there is some seepage that occurs across the confining 
layer as the flow moves towards the middle of the aquifer, then the iron travels beneath the confining 
layer along the higher permeability sandy gravel layer that makes up the bottom layer.  
https://www.youtube.com/watch?v=0r9Y84_aG6o&feature=youtu.be 

Scenario 7: Four-layered aquifer with Fe2+ Introduced Along the Surface and Two Faults at 15–25 m and 
45–55 m 
This final scenario incorporates two different “fault zones” or areas in which the permeability is 
much lower vertically. With the iron being introduced immediately to the system at the surface, the model 
almost immediately shows movement along both faults, which causes a very sudden drop of the iron 
tracer into the lowermost layer. This is consistent with some of the patterns that we saw in the earlier 
simulations, one again highlighting the movement of a dense tracer such as iron. 
https://www.youtube.com/watch?v=6qMybp5FD0I 


Model Performance 
The models ran with an average runtime of ~2 hours per simulation on a local machine. Some oscillatory 
convergence was noted at early timesteps, but stabilized as the model progressed. 
 

Discussion 
	The results of this study give clues into the patterns of movement of iron. Earlier scenarios 
consistently showed Fe2+ acting as a dense tracer, and migrating rapidly downwards due to gravitational 
forces, particularly in a uniform aquifer. The presence of low-permeability fault zones facilitated vertical 
movement and some lateral movement along different layers of the aquifer. Essentially, this study is 
somewhat useful for an introduction into modeling with a dense tracer, however, it seems to be lacking in 
mimicking the real-life scenario this study had originally hoped to model. The models of Scenario 5-7 
released the tracers at the surface from 0-10m on the x-axis, and these particular scenarios seem to be 
the most realistic out of all of the scenarios. However, the adjustments that were made with the purpose 
of simulating surface-based contamination, reflecting typical AMD conditions where contaminants enter 
the system from near-surface mining sources, introduced convergence issues within the model, 
highlighting the challenges of simulating more realistic boundary conditions. Despite these difficulties, 
shifting to a surface injection scenario more accurately reflects the processes of AMD and could serve as 
a valuable direction for future research, especially with improved numerical stability and model 
refinement. 

Use of Fe²⁺ as a Tracer in a Non-Reactive Model 
	Fe²⁺ was selected as the tracer for this study to represent heavy metal contamination commonly 
associated with acid mine drainage (AMD). While Fe2+ is a relevant choice in context of AMD scenarios, it 
is important to recognize that in natural systems its behavior is highly reactive. The redox reactions of 
Fe2+, lead to the formation of iron oxides. These secondary minerals precipitate and clog pore spaces, 
which lowers the permeability of the aquifer system. However, in these models, Fe²⁺ was treated as a 
non-reactive species using the General Integrated Reactive Transport (GIRT) mode to simplify the 
simulation and isolate the effects of physical transport processes. 
This simplification, while useful for understanding baseline transport behavior, does not fully 
capture the complexity of Fe2+ dynamics in natural systems. In reality, reactive transport models would be 
necessary to simulate changes in chemical speciation, pH effects, and mineral formation, all of which 
could significantly influence contaminant mobility and aquifer properties. Future iterations of this project 
could incorporate reactive transport to better represent the geochemical interactions associated with Fe2+ 
and similar metals. 

Modeling Potential 
	This study demonstrates that PFLOTRAN is capable of modeling heavy metal transport under 
complex hydrogeologic conditions, even in a simplified non-reactive framework. Fe2+ served as a proxy 
for heavy metal contamination, but the modeling approach can be extended to other contaminants. For 
example, previous exercises, such as the copper leaching simulation presented Leone et al. 2024, 
display PFLOTRAN’s capability to incorporate a wide range of heavy metals with detailed geochemical 
processes. Additionally, this model focused on a 2D representation, future studies could benefit from 
extending the analysis into three dimensions to capture more realistic flow and transport behavior. 

Study Limitations: 
• The model’s 2D nature restricts its ability to fully simulate 3D flow patterns and spatial variability. 
• Non-reactive transport does not account for key geochemical processes affecting Fe²⁺ mobility. 
• Simplified boundary conditions were necessary for model convergence but may limit real-world 
applicability. 
Despite these constraints, the study provides a foundational understanding of how structural features, 
such as stratification and fault zones, influence the movement of dense, non-reactive tracers in 
groundwater systems. 

Conclusions 
	This project demonstrated the use of PFLOTRAN to simulate Fe2+ transport under increasingly 
complex hydrogeologic conditions. The use of a non-reactive transport model allowed for a focused 
investigation of physical transport mechanisms, revealing that solute migration is closely tied to the flow 
regime, yet displays a clear tendency to act as a dense tracer, displaying continuous patterns of dropping 
quickly to the bottom of the aquifer in every scenario. These models are very simplified in relation to the 
reality of a natural system, however, they can potentially serve as a foundation for more complex studies 
that incorporate reactive processes. The findings of this study contribute to a better understanding of the 
movement of heavy metal contaminants in groundwater systems and highlight the use of PFLOTRAN for 
environmental modeling applications. 


Data Availability Statement 
All input files for the PFLORTRAN simulations are available at:  
https://github.com/lindskgord/FinalProjectCEE6450 


References 
Leone, R., Park, H., Fukuyama, D., & Hammond, G. (2024). 2024 PFLOTRAN UT Austin short course: 
Course materials. Zenodo. https://doi.org/10.5281/zenodo.11165130 
PFLOTRAN Development Team. (2024). PFLOTRAN user guide (Version 6.0). PFLOTRAN 
Documentation. https://documentation.pflotran.org/user_guide/user_guide.html 
Younger, P. L., Wolkersdorfer, C., & Weisener, C. (2020). Acid mine drainage: Advances in modeling and 
treatment. Applied Geochemistry, 119, 104632. https://doi.org/10.1016/j.apgeochem.2020.104632 
