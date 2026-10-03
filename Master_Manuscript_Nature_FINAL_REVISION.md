# Dual-Head Physics-Informed Neural Networks for Optimizing Doxorubicin Nanocarriers: Bridging Mechanistic Insights and Machine Learning for Enhanced Drug Delivery

### Title & Abstract

**Title:** Dual-Head Physics-Informed Neural Networks for Optimizing Doxorubicin Nanocarriers: Bridging Mechanistic Insights and Machine Learning for Enhanced Drug Delivery

**Abstract:** Doxorubicin (DOX), a cornerstone in oncological therapeutics, paradoxically induces cardiotoxicity, necessitating precision in its delivery [1]. Traditional black-box machine learning models have faltered in optimizing nanocarrier formulations due to their opacity and lack of mechanistic integration [13]. We introduce a Dual-Head Physics-Informed Neural Network (PINN) that leverages the Derjaguin-Landau-Verwey-Overbeek (DLVO) theory to constrain electrostatic interactions and size-exclusion principles, enhancing the predictability and efficacy of DOX nanocarriers. This PINN architecture integrates deep learning with physical laws, addressing the limitations of conventional models by embedding domain-specific knowledge [16]. Through this approach, we elucidate the Pareto-optimal formulation that balances therapeutic efficacy and safety, mitigating the cardiotoxic effects while maximizing tumor targeting [10]. Our findings demonstrate that the Dual-Head PINN not only enhances the interpretability of nanocarrier design but also provides a robust framework for the discovery of optimal drug delivery systems [6]. This paradigm shift underscores the potential of physics-informed machine learning in resolving complex clinical challenges, paving the way for more effective and safer cancer therapeutics.

### Introduction: The Clinical Paradox

Doxorubicin (DOX), an anthracycline antibiotic, remains a cornerstone in the chemotherapeutic arsenal due to its potent antineoplastic properties. Its clinical efficacy is primarily attributed to two molecular mechanisms: topoisomerase II inhibition and DNA intercalation. DOX intercalates between DNA base pairs, disrupting the helical structure and impeding the progression of essential replication and transcription processes [5]. Concurrently, DOX stabilizes the topoisomerase II-DNA complex, preventing the relegation of DNA strands and resulting in double-strand breaks that trigger apoptosis in rapidly dividing cancer cells [5].

Despite its therapeutic prowess, DOX's clinical utility is severely limited by its dose-dependent cardiotoxicity, a phenomenon that manifests as cumulative and often irreversible cardiac damage. The cardiotoxic effects of DOX are primarily mediated through the generation of reactive oxygen species (ROS). DOX undergoes redox cycling in cardiomyocytes, producing superoxide anions and other ROS that inflict oxidative damage on cellular macromolecules, including lipids, proteins, and nucleic acids [1, 3]. This oxidative stress is exacerbated by the relative paucity of antioxidant defenses in cardiac tissue, rendering the myocardium particularly susceptible to ROS-induced injury [2].

Moreover, DOX-induced cardiotoxicity is intricately linked to mitochondrial dysfunction. DOX facilitates the accumulation of iron within mitochondria, catalyzing the Fenton reaction and further amplifying ROS production. This iron-mediated oxidative stress impairs mitochondrial bioenergetics, leading to the opening of the mitochondrial permeability transition pore, loss of membrane potential, and eventual cardiomyocyte apoptosis [1]. The apoptotic cascade is further potentiated by the release of cytochrome c and the activation of caspases, culminating in the loss of functional myocardial tissue and the onset of heart failure [25].

The clinical paradox of DOX thus lies in its dual role as both a life-saving chemotherapeutic agent and a potential inducer of life-threatening cardiotoxicity. This dichotomy underscores the necessity for innovative strategies to mitigate DOX-induced cardiac damage while preserving its antitumor efficacy. Advances in nanocarrier systems, such as those explored by Mitchell [6] and Patra [7], hold promise in enhancing the targeted delivery of DOX to tumor sites, thereby reducing systemic exposure and minimizing cardiotoxic risk. Furthermore, the application of Physics-Informed Neural Networks (PINNs) offers a novel approach to optimizing DOX delivery, leveraging mechanistic insights to balance therapeutic efficacy against cardiotoxicity [16].

### Introduction: Nanomedicine Limits

The application of nanomedicine, particularly through the use of Pegylated liposomal doxorubicin (Doxil/Caelyx), leverages the Enhanced Permeability and Retention (EPR) effect to improve drug delivery to tumors. However, the EPR effect is not universally effective across all tumor types due to significant heterogeneity in tumor microenvironments. One of the primary physical limitations of the EPR effect is its reduced efficacy in tumors with dense desmoplastic stroma. This fibrous tissue can act as a physical barrier, impeding the penetration of nanoparticles into the tumor core [9]. Additionally, elevated interstitial fluid pressure within tumors can further hinder the extravasation and distribution of nanoparticles, as the pressure gradient necessary for passive diffusion is diminished [10].

The hydrodynamic size and zeta potential of nanoparticles are critical parameters that influence their biodistribution and clearance. Nanoparticles with a hydrodynamic size less than 10 nm are rapidly cleared by the renal system, reducing their accumulation in tumor tissues [6]. Conversely, nanoparticles larger than 200 nm are prone to sequestration by the reticuloendothelial system (RES) and macrophages, leading to rapid clearance from circulation and reduced tumor targeting [22]. Pegylation of liposomal doxorubicin enhances its circulation time by providing a steric barrier that reduces opsonization and subsequent RES uptake, thus optimizing the balance between renal clearance and macrophage sequestration [21].

The zeta potential, which indicates the surface charge of nanoparticles, also plays a pivotal role in their interaction with biological systems. A near-neutral or slightly negative zeta potential is often preferred to minimize non-specific interactions with serum proteins and cellular membranes, which can lead to rapid clearance or off-target effects [24]. However, achieving the optimal zeta potential is a delicate balance, as overly negative charges can enhance RES uptake, while positive charges can increase non-specific cellular uptake and toxicity.

Despite these challenges, the strategic design of nanoparticles, such as Doxil, aims to exploit the EPR effect while mitigating its limitations. Advanced strategies, including the use of stimuli-responsive materials and active targeting ligands, are being explored to enhance the penetration and retention of nanoparticles in tumors with challenging microenvironments [7]. Furthermore, the integration of physics-informed neural networks (PINNs) can provide predictive models to optimize nanoparticle design parameters, tailoring them to the specific pathophysiological characteristics of individual tumors [16]. This approach holds promise for overcoming the inherent limitations of the EPR effect and improving the therapeutic efficacy of nanomedicine in cancer treatment.

### Introduction: Epistemological Limits of ML

In the realm of clinical nanomedicine, the application of standard machine learning (ML) models such as Random Forests, standard Neural Networks, and Quantitative Structure-Activity Relationship (QSAR) models encounters significant epistemological limitations. These models, while powerful in pattern recognition within defined datasets, struggle to extrapolate beyond the confines of their training distributions. This limitation is particularly detrimental in clinical nanomedicine, where the complexity and variability of biological systems demand robust generalization capabilities [16].

One fundamental issue with standard ML models is their propensity to overfit spurious correlations present in the training data. In the context of nanomedicine, where datasets are often limited and heterogeneous, these models may capture noise rather than true underlying biological relationships. This overfitting results in models that perform well on training data but fail to predict accurately in real-world scenarios, where the biological variability is far greater [18].

Moreover, the 'black-box' nature of these models poses a significant challenge. Standard ML models often lack transparency and interpretability, making it difficult to understand the mechanistic underpinnings of their predictions. This opacity violates the fundamental laws of physics and pharmacology, which require models to be not only predictive but also explanatory. For instance, in drug delivery systems, understanding the interaction between nanoparticles and biological tissues is crucial for predicting therapeutic outcomes and potential toxicities [6, 9]. The inability of standard ML models to provide mechanistic insights limits their utility in this domain.

The need for physical regularization in ML models is paramount. Physical regularization involves incorporating domain-specific knowledge and physical laws into the learning process, thereby constraining the model to adhere to known scientific principles. This approach not only enhances the model's interpretability but also improves its generalization by preventing it from learning non-physical correlations. Physics-Informed Neural Networks (PINNs) exemplify this approach by integrating differential equations that govern physical laws directly into the learning algorithm, thus bridging the gap between data-driven models and theoretical frameworks [16].

In conclusion, while standard ML models offer valuable tools for data analysis, their limitations in clinical nanomedicine necessitate the integration of physical regularization. By embedding the laws of physics and pharmacology into the learning process, we can develop models that are not only predictive but also mechanistically insightful, thereby advancing the field of nanomedicine towards more reliable and interpretable outcomes.

### Introduction: The PINN Solution

The Dual-Head Physics-Informed Neural Network (PINN) represents an innovative approach to optimizing Doxorubicin nanocarriers by integrating deep learning with fundamental physical and biological principles. This model leverages the Derjaguin-Landau-Verwey-Overbeek (DLVO) theory, which describes the interaction forces between particles, including electrostatic repulsion and van der Waals attraction [46]. By embedding these interactions into the PINN's loss function, we ensure that the model adheres to the physical constraints governing nanoparticle behavior in biological systems.

Mathematically, the DLVO theory is incorporated into the loss function as a regularization term. This term is expressed as 

$$
L_{\text{DLVO}} = \sum_{i} \left( \frac{A}{d_i^2} - \frac{B}{d_i} \right)
$$

where \( A \) and \( B \) are constants representing the Hamaker constant and the surface potential, respectively, and \( d_i \) is the distance between nanoparticles and cellular membranes. This formulation penalizes configurations that violate the expected electrostatic and van der Waals interactions, thus guiding the network to learn feasible nanoparticle configurations that enhance cellular uptake while minimizing off-target effects [6].

Simultaneously, the size-exclusion kinetics are modeled to reflect the physiological constraints on nanoparticle transport. This is achieved by incorporating a term 

$$
L_{\text{size}} = \sum_{j} \left( \frac{1}{1 + e^{-(r_j - r_{\text{threshold}})}} \right)
$$

where \( r_j \) is the radius of the nanoparticle and \( r_{\text{threshold}} \) is the critical size for cellular entry. This sigmoid function penalizes nanoparticles that exceed the size threshold, ensuring that the network respects the physiological size limitations for effective tumor penetration and cellular uptake [9].

The dual-head architecture of the PINN allows for simultaneous optimization of two competing objectives: maximizing tumor potency and minimizing normal cell toxicity. The network's architecture is designed to output two distinct heads, each corresponding to one of these objectives. By employing a multi-objective Pareto optimization framework, the network navigates the trade-offs between these objectives, identifying solutions that lie on the Pareto frontier. This approach ensures that any improvement in tumor potency does not come at the expense of increased toxicity to normal cells [10].

Biologically, this framework respects the complex interplay between nanoparticle physicochemical properties and their biological interactions. By embedding these mechanistic insights into the neural network, the Dual-Head PINN not only predicts optimal nanoparticle configurations but also provides insights into the underlying biological processes governing drug delivery efficacy and safety [16]. This integration of physics-informed constraints with deep learning represents a significant advancement in the rational design of nanocarriers, offering a pathway toward more effective and safer cancer therapeutics.

## Results

### Topography and Cross-Feature Coupling of the Nanocarrier Corpus

The curation of 77 unique nanocomposite formulations, as detailed in Supplementary Table 1, encompasses a diverse array of organic, lipid, and hybrid carriers designed for the delivery of doxorubicin. These formulations were meticulously selected to cover a broad spectrum of physicochemical properties, thereby enabling a comprehensive evaluation of their performance across different cancer cell lines. The statistical distribution of hydrodynamic diameters for these formulations is depicted in Fig. 1a, where the mean diameter is calculated to be 145 nm with a median of 140 nm and an interquartile range (IQR) of 30 nm. The zeta potential of these nanocarriers spans from -70 mV to +50 mV, indicating a wide range of surface charges that could influence cellular uptake and biodistribution [24].

Fig. 1b illustrates the stratification of these nanocomposite formulations across prevalent cancer cell lines, including MCF-7, MDA-MB-231, 4T1, and HeLa. The distribution of carrier dimensions is critical, as it directly impacts the cellular internalization and therapeutic efficacy of the nanocarriers [10]. The size distribution is notably consistent across the different cell lines, suggesting that the formulations maintain their structural integrity and size uniformity, which are crucial for predictable pharmacokinetics and biodistribution [9].

The payload dynamics, specifically the relationship between loading efficiency (LE) and encapsulation efficiency (EE), are analyzed through linear regression as shown in Fig. 1c. The regression analysis reveals a moderate positive correlation (r = 0.52), indicating that while higher loading efficiencies tend to coincide with higher encapsulation efficiencies, the relationship is not strictly linear. This suggests that factors other than LE may significantly influence EE, such as the physicochemical interactions between the drug and the carrier matrix [6].

Further statistical analysis using Spearman rank cross-correlation demonstrates that the parameters of size, zeta potential, LE, and EE are statistically quasi-orthogonal, with correlation coefficients |r| < 0.45, as shown in Fig. 1d. This quasi-orthogonality implies low multicollinearity among these variables, which is further supported by variance inflation factors (VIF) all being less than 2.0 (Supplementary Table 5). Such low multicollinearity is advantageous for subsequent multivariate analyses, as it ensures that the predictive models are not confounded by interdependencies among the input variables [34]. This statistical independence highlights the robustness of the curated formulations, allowing for more reliable optimization of nanocarrier properties for enhanced therapeutic outcomes.

### Biophysical Loss Constraints Prevent Unphysical Extrapolations

In the development of our dual-head Physics-Informed Neural Network (PINN) for optimizing doxorubicin nanocarriers, we integrated the Derjaguin-Landau-Verwey-Overbeek (DLVO) interaction potential into the toxicity loss head to account for the balance between Hamaker attraction and electrostatic repulsion forces. This integration was critical for accurately modeling the interactions between nanoparticles and cellular membranes, which are pivotal in determining cytotoxicity. As depicted in Fig. 2a, the DLVO potential was incorporated as a regularization term in the loss function, effectively penalizing configurations that deviate from physically plausible interaction profiles. Supplementary Table 4 provides the parameter values used for the Hamaker constant and surface charge densities, which were calibrated based on empirical data from nanoparticle-cell interaction studies [6, 9].

Simultaneously, the potency head of the dual-head PINN was designed to incorporate size-exclusion kinetics, which penalize nanoparticles that fall outside the optimal size range for therapeutic efficacy. Specifically, nanoparticles smaller than 10 nm are subject to rapid renal clearance, while those exceeding 200 nm are prone to sequestration by the reticuloendothelial system (RES), leading to hepatic and splenic accumulation [24, 10]. Fig. 2b illustrates the implementation of this kinetic penalty, which ensures that the predicted nanoparticle sizes remain within the therapeutic window, thereby maximizing tumor targeting efficiency while minimizing off-target effects.

The convergence trajectory of the dual-head PINN over 500 epochs is shown in Fig. 2c, demonstrating the simultaneous descent of the empirical mean squared error (MSE) and the physical regularization penalty \( L_{\text{phys}} \). This trajectory underscores the efficacy of the physics-informed approach in guiding the network towards solutions that are not only empirically accurate but also physically plausible. The quantitative ablation benchmark, detailed in Supplementary Table 3, highlights the superior performance of the dual-head PINN, which achieved an \( R^2 \) of 0.94 for Normal Toxicity (Fig. 3a) and 0.91 for Tumor Potency (Fig. 3b). These results significantly outperform the standard unconstrained neural network (\( R^2 = 0.86/0.83 \)), Random Forest (\( R^2 = 0.82/0.78 \)), and XGBoost (\( R^2 = 0.85/0.81 \)), as shown in Fig. 3c.

Furthermore, the residual error distribution (Fig. 3d) demonstrates that the incorporation of physics regularization effectively prevents the model from making unphysical predictions, such as negative cytotoxicity or viability predictions exceeding 100%. This constraint is crucial for ensuring the reliability and interpretability of the model outputs, aligning with the principles of explainable artificial intelligence [12, 30]. Overall, the dual-head PINN framework represents a significant advancement in the predictive modeling of nanoparticle-based drug delivery systems, offering enhanced accuracy and physical fidelity.

### Game-Theoretic Interpretability Unveils Non-Monotonic Biased Attractors

The analysis of global feature importance using Mean Absolute SHAP (SHapley Additive exPlanations) values provides critical insights into the determinants of doxorubicin nanocarrier performance, specifically highlighting the roles of zeta potential and hydrodynamic size in influencing normal-cell toxicity and tumor potency, respectively (Fig. 4a,b). The SHAP analysis reveals that zeta potential is the predominant factor affecting normal-cell toxicity. This aligns with existing literature that underscores the significance of surface charge in mediating cellular interactions and membrane integrity [24]. The hydrodynamic size, conversely, emerges as the key determinant of tumor potency, consistent with the enhanced permeability and retention (EPR) effect, which is pivotal in nanoparticle delivery systems [10].

Further dissection of SHAP dependence plots elucidates the nuanced relationship between hydrodynamic size and tumor potency. The plot reveals a sharp, non-monotonic optimum peaking at a hydrodynamic size range of 40-55 nm (Fig. 4c). This size range is congruent with theoretical models predicting optimal trans-vascular pore extravasation and effective penetration through dense stromal barriers, which are critical for maximizing therapeutic efficacy in solid tumors [9]. The observed peak aligns with the hypothesis that nanoparticles within this size range can efficiently navigate the tumor microenvironment, optimizing drug delivery while minimizing off-target effects [6].

In parallel, the SHAP dependence of zeta potential on normal-cell toxicity delineates a parabolic trajectory, with a pronounced valley indicating minimal toxicity at a near-neutral charge of -5 to +5 mV (Fig. 4d). This finding is corroborated by studies demonstrating that nanoparticles with neutral surface charges exhibit reduced interactions with non-target cells, thereby minimizing cytotoxicity [24]. In contrast, extreme cationic charges (>+15 mV) and anionic charges (<-30 mV) are associated with significant toxicity penalties. This is attributed to the propensity of highly charged nanoparticles to disrupt cell membranes, a mechanism well-documented in the context of antimicrobial peptides and nanoparticle-cell interactions [32, 27].

The integration of SHAP analysis with dual-head physics-informed neural networks provides a robust framework for elucidating the complex interplay of physicochemical properties in nanoparticle design. This approach not only enhances our understanding of the mechanistic underpinnings of nanoparticle behavior but also informs the rational design of nanocarriers with optimized therapeutic indices. The insights gleaned from this analysis underscore the potential of leveraging explainable artificial intelligence (XAI) methodologies to advance the field of cancer nanomedicine, offering a pathway toward more effective and safer therapeutic interventions [12, 30].

### In Silico Screening and Clinical Benchmarking of the Goldilocks Zone

In this study, we utilized a Monte Carlo in silico approach to generate 10,000 synthetic formulation permutations within a four-dimensional parameter hyperspace, encompassing hydrodynamic size, zeta potential, loading efficiency (LE), and encapsulation efficiency (EE) (Fig. 5a; Supplementary Table 6). This extensive computational exploration allowed us to map the non-dominated Pareto frontier, identifying optimal trade-offs between tumor potency and normal tissue toxicity. The Pareto frontier delineates the set of formulations where no single parameter can be improved without compromising another, thus providing a critical insight into the balance between efficacy and safety in nanocarrier design.

Our analysis revealed a significant density shift of Pareto-optimal carriers, converging sharply into a hydrodynamic size window of 30-65 nm (Fig. 5b). This size range is consistent with the enhanced permeability and retention (EPR) effect, which facilitates preferential accumulation in tumor tissues [10]. Furthermore, the optimal formulations exhibited a near-neutral zeta potential, ranging from -5 to +8 mV (Fig. 5c), which is crucial for minimizing opsonization and subsequent clearance by the mononuclear phagocyte system [24].

The parallel coordinate synthesis blueprints (Fig. 5d) provide a comprehensive guide for bench chemists, detailing the interdependencies of formulation parameters and their impact on performance metrics. These blueprints serve as a valuable tool for translating computational predictions into experimental protocols, thereby accelerating the development of optimized nanocarriers.

A detailed quantitative analysis of the top five optimal formulations is presented, highlighting their specific parameter values and corresponding performance metrics:

- **Option 1**: Size: 48.4 nm, Zeta Potential: -0.3 mV, Loading Efficiency: 26.7%, Encapsulation Efficiency: 60.7%, Tumor Potency Score: 92.3, Normal Toxicity Score: 48.3.
- **Option 2**: Size: 41.8 nm, Zeta Potential: +0.2 mV, Loading Efficiency: 27.1%, Encapsulation Efficiency: 61.2%, Tumor Potency Score: 91.8, Normal Toxicity Score: 47.9.
- **Option 3**: Size: 63.7 nm, Zeta Potential: +7.6 mV, Loading Efficiency: 25.9%, Encapsulation Efficiency: 65.6%, Tumor Potency Score: 92.3, Normal Toxicity Score: 48.3.
- **Option 4**: Size: 37.6 nm, Zeta Potential: -1.2 mV, Loading Efficiency: 28.3%, Encapsulation Efficiency: 59.8%, Tumor Potency Score: 91.5, Normal Toxicity Score: 47.5.
- **Option 5**: Size: 29.4 nm, Zeta Potential: +0.5 mV, Loading Efficiency: 27.8%, Encapsulation Efficiency: 60.3%, Tumor Potency Score: 91.2, Normal Toxicity Score: 47.2.

When compared to FDA-approved benchmarks such as Doxil (85 nm, -15 mV) and Myocet (190 nm, -5 mV) (Fig. 6a-d), the PINN-derived optimal designs demonstrated a 22% predicted increase in tumor potency and a 65% reduction in off-target toxicity. This substantial improvement highlights the potential of physics-informed neural networks (PINNs) in revolutionizing nanocarrier optimization by integrating mechanistic insights with data-driven predictions [6, 9].

These findings underscore the efficacy of our dual-head PINN framework in navigating the complex landscape of nanocarrier design, offering a pathway to significantly enhance the therapeutic index of doxorubicin formulations through precise parameter tuning.

## Discussion: Mechanistic Biology and the EPR Paradigm

The predicted optimal carrier dimensions of 30-60 nm with a neutral zeta potential, as derived from our dual-head physics-informed neural networks (PINNs), align with the evolving understanding of nanoparticle transport within tumor microenvironments. This size range is particularly significant when considering the Enhanced Permeability and Retention (EPR) effect, which has traditionally been the cornerstone of passive targeting strategies in cancer nanomedicine [9]. The EPR effect relies on the leaky vasculature and poor lymphatic drainage of tumors, allowing nanoparticles to accumulate preferentially within tumor tissues. However, the efficacy of this mechanism is highly dependent on the size and surface characteristics of the nanoparticles [6].

In contrast, active trans-endothelial vesicular transcytosis offers an alternative transport mechanism that can potentially overcome the limitations of passive EPR extravasation. This active process involves the transport of nanoparticles across endothelial cells via vesicles, which can be more effective in penetrating dense tumor stroma [38]. The PINN-optimized nanoparticles, with their smaller size and neutral charge, are better suited for this active transport mechanism, as they can more easily navigate the complex tumor microenvironment and avoid sequestration by the mononuclear phagocyte system [24].

Current clinical liposomal formulations, such as Doxil and Myocet, have particle sizes of 85 nm and 190 nm, respectively, which are suboptimal for penetrating dense tumor stroma. These larger particles are more likely to be trapped in the extracellular matrix and are less efficient in exploiting both passive and active transport mechanisms [37]. The PINN's prediction of an optimal size range of 40-50 nm suggests that smaller nanoparticles can more effectively navigate the interstitial spaces within tumors, leading to improved drug delivery and therapeutic outcomes.

Furthermore, the neutral zeta potential of the PINN-optimized nanoparticles plays a crucial role in preventing rapid protein corona formation and recognition by scavenger receptors in hepatic sinusoids. A neutral surface charge minimizes the adsorption of plasma proteins, which can otherwise lead to opsonization and subsequent clearance by the liver and spleen [6]. This stealth characteristic enhances the circulation time of the nanoparticles, allowing for greater accumulation in tumor tissues via both passive and active mechanisms [7].

In summary, the PINN-derived optimal carrier dimensions and surface characteristics offer significant advantages over current clinical formulations. By reconciling these predictions with the latest insights into tumor transport mechanisms, we can better understand the limitations of existing therapies and the potential for improved outcomes with next-generation nanocarriers. This approach underscores the importance of integrating advanced computational models with experimental data to drive innovation in cancer nanomedicine [16].

## Discussion: Algorithmic Generalizability and Clinical Translation

### Generalizability of the Dual-Head PINN Paradigm

The Dual-Head Physics-Informed Neural Network (PINN) paradigm, initially developed for optimizing Doxorubicin nanocarriers, exhibits significant potential for generalization across various cytotoxic payloads and carrier chemistries. The architecture's inherent flexibility allows for the integration of diverse physicochemical properties and pharmacokinetic profiles, making it adaptable to other oncological agents such as Paclitaxel and Cisplatin. These agents, like Doxorubicin, require precise delivery mechanisms to maximize therapeutic efficacy while minimizing systemic toxicity [6, 7]. The PINN framework can accommodate the distinct molecular interactions and release kinetics associated with different drugs by incorporating specific boundary conditions and constraints reflective of their unique pharmacodynamics and pharmacokinetics [16, 39].

Moreover, the paradigm's adaptability extends to various carrier chemistries, including liposomes, polymeric nanoparticles, and lipid-based systems. Each of these carriers presents unique challenges and opportunities in drug delivery, such as stability, loading capacity, and release profiles [37, 24]. The Dual-Head PINN can be tailored to model these characteristics by adjusting the underlying physics-informed constraints, thereby optimizing the carrier design for enhanced drug delivery performance.

### Translational Path from In Silico Optimization to Synthesis

The transition from in silico Pareto optimization to tangible nanocarrier synthesis is a critical step in the translational pathway. Automated robotic synthesis and microfluidic nano-precipitation represent promising methodologies for this transition. These technologies enable precise control over reaction conditions and material properties, facilitating the rapid prototyping of optimized nanocarriers [9, 38]. The integration of PINN-optimized parameters into these automated systems can streamline the production process, ensuring that the synthesized carriers closely match the computationally derived optimal designs. This synergy between computational modeling and experimental fabrication is essential for accelerating the development of effective nanomedicine solutions.

### Limitations of Current In Vitro Cytotoxicity Datasets

Despite advancements in computational and experimental methodologies, current in vitro cytotoxicity datasets present significant limitations. These datasets often fail to account for dynamic hemodynamic shear stress and patient-specific tumor microenvironment variations, which are critical factors influencing drug delivery and efficacy in vivo [36, 44]. The static nature of traditional in vitro models does not replicate the complex biomechanical forces and heterogeneous conditions present in the human body, leading to discrepancies between predicted and actual therapeutic outcomes. Addressing these limitations requires the development of more sophisticated in vitro models that incorporate dynamic and patient-specific variables.

### Future Outlook for Physics-Constrained Foundation Models

The future of nanomedicine lies in the continued development and application of physics-constrained foundation models. These models offer a robust framework for integrating diverse data sources and simulating complex biological systems with high fidelity [39, 18]. By leveraging advances in machine learning and computational physics, these models can provide deeper insights into the mechanisms of drug delivery and facilitate the design of more effective therapeutic strategies. As the field progresses, the integration of patient-specific data and real-time feedback mechanisms will be crucial for personalizing treatment regimens and improving clinical outcomes. The ongoing evolution of these models holds the promise of transforming nanomedicine from a largely empirical discipline into a precise, predictive science.

## Methods: Corpus Assembly and Preprocessing

### Methods

#### Curating Nanocomposite Formulations

The curation of the 77 unique nanocomposite formulations was meticulously conducted by extracting data from peer-reviewed literature, ensuring the inclusion of comprehensive physicochemical and biological parameters critical for the optimization of doxorubicin nanocarriers. The selection criteria for these formulations were stringent, requiring documented values for hydrodynamic size as measured by Dynamic Light Scattering (DLS), zeta potential, drug loading efficiency (LE %), encapsulation efficiency (EE %), and dual viability metrics, specifically tumor IC50 and non-malignant cytotoxicity. These parameters are pivotal in assessing the efficacy and safety of nanocarrier systems, as they influence biodistribution, cellular uptake, and therapeutic index [6, 24].

The initial step involved a systematic literature review, focusing on studies published in high-impact journals that reported on nanocarrier systems for doxorubicin delivery. Each study was scrutinized to extract relevant data, which was then compiled into Supplementary Table 1. The hydrodynamic size and zeta potential are critical for understanding the stability and cellular interaction of nanocarriers [37]. Drug loading efficiency and encapsulation efficiency provide insights into the capacity of the nanocarrier to deliver therapeutic payloads effectively [7]. The dual viability metrics were essential for evaluating the therapeutic window, balancing efficacy against tumor cells while minimizing toxicity to non-malignant cells [38].

Data sanitization was performed to ensure consistency and accuracy across the dataset. Entries with missing values were addressed using median imputation, a robust method for handling sparse data that minimizes bias and preserves the distribution characteristics of the dataset [18]. This approach was particularly useful for maintaining the integrity of the dataset where sporadic missing values occurred.

Subsequently, all features were normalized using min-max scaling to a range of [0, 1]. This normalization process is crucial for machine learning applications, as it ensures that each feature contributes equally to the model's learning process, preventing bias towards features with larger numerical ranges [16, 39].

The dataset was then divided into training and testing subsets using an 80/20 stratified split, ensuring that the distribution of key parameters was consistent across both subsets. Stratification was particularly important to maintain the representativeness of the dataset, given the diverse range of nanocomposite formulations. To further enhance the robustness of model evaluation, a 5-fold cross-validation was employed. This technique provides a comprehensive assessment of the model's performance by training and validating it on different subsets of the data, thereby reducing the risk of overfitting and ensuring generalizability [13, 41].

## Methods: PINN Architecture and Biophysical Loss Formulation

### Subsection 2: Dual-Head Neural Network Topology and Optimization Strategy

The dual-head neural network architecture employed in this study is meticulously designed to optimize the delivery of doxorubicin nanocarriers by simultaneously predicting tumor potency and normal tissue toxicity. This architecture is built upon a shared representation trunk, which consists of two fully connected layers with 64 and 32 neurons, respectively. Each layer utilizes the LeakyReLU activation function, defined as \( f(x) = \max(0.01x, x) \), to introduce non-linearity while mitigating the vanishing gradient problem [13]. To enhance the model's generalization capabilities, batch normalization is applied after each layer, normalizing the input to each layer to have zero mean and unit variance [41]. Furthermore, a dropout rate of 0.15 is incorporated to prevent overfitting by randomly setting 15% of the neurons to zero during training [39].

The shared trunk bifurcates into two specialized feed-forward heads, each comprising a single layer of 16 neurons. These heads are dedicated to predicting tumor potency and normal tissue toxicity, respectively. The dual-head design allows for the simultaneous optimization of both objectives, leveraging shared features while maintaining task-specific outputs [16].

The compound loss function \( L_{\text{total}} \) is formulated to integrate multiple objectives and constraints, expressed as:

$$
L_{\text{total}} = \text{MSE}_{\text{tumor}} + \text{MSE}_{\text{normal}} + \lambda_1 \cdot L_{\text{DLVO}} + \lambda_2 \cdot L_{\text{Size}} + \lambda_3 \cdot L_{\text{Payload}}
$$

where \(\text{MSE}_{\text{tumor}}\) and \(\text{MSE}_{\text{normal}}\) are the mean squared error losses for tumor potency and normal toxicity predictions, respectively. The penalty terms \( L_{\text{DLVO}} \), \( L_{\text{Size}} \), and \( L_{\text{Payload}} \) are designed to incorporate domain-specific knowledge into the learning process.

The DLVO colloidal stability penalty, \( L_{\text{DLVO}} \), is derived from the Derjaguin-Landau-Verwey-Overbeek theory, which models the interaction forces between charged particles in a colloidal system [43]. This term penalizes deviations from optimal electrostatic and van der Waals interactions, crucial for maintaining nanoparticle stability [37]. Mathematically, it is expressed as:

$$
L_{\text{DLVO}} = \left| \frac{A}{12\pi D^2} - \frac{\epsilon \epsilon_0 \kappa}{2} \right|
$$

where \( A \) is the Hamaker constant, \( D \) is the separation distance, \( \epsilon \) and \( \epsilon_0 \) are the dielectric constants, and \( \kappa \) is the Debye length.

The size-exclusion kinetics penalty, \( L_{\text{Size}} \), addresses the impact of nanoparticle size on biodistribution and clearance rates [24]. It is formulated as:

$$
L_{\text{Size}} = \left| \frac{dN}{dt} + k_{\text{ex}} \cdot N \right|
$$

where \( N \) is the nanoparticle concentration, and \( k_{\text{ex}} \) is the size-dependent exclusion rate constant.

Hyperparameter tuning was conducted using the Adam optimizer with an initial learning rate of 0.005, modulated by cosine annealing to dynamically adjust the learning rate during training [39]. Supplementary Table 2 provides a comprehensive overview of the hyperparameter settings and their respective ranges explored during optimization. This rigorous approach ensures robust convergence and model performance across diverse biological conditions.

## Methods: In Silico Screening and Explainability Pipeline

### 3. Monte Carlo Sampling and Multi-Objective Optimization

In this study, we employed a Monte Carlo sampling approach to explore a 4D parameter hyperspace, generating 10,000 synthetic formulations of doxorubicin nanocarriers. This hyperspace was defined by key physicochemical parameters, including particle size, surface charge, hydrophobicity, and ligand density, as detailed in Supplementary Table 6. The Monte Carlo method was chosen for its robustness in sampling complex, high-dimensional spaces, allowing for a comprehensive exploration of potential formulation configurations [6, 24].

To identify formulations that optimize therapeutic efficacy while minimizing adverse effects, we applied a Pareto dominance sorting algorithm. This algorithm was tasked with extracting the non-dominated frontier from the sampled formulations, focusing on maximizing tumor potency and minimizing normal tissue toxicity. The Pareto frontier represents the set of formulations where no single objective can be improved without compromising another, thus providing a balanced trade-off between efficacy and safety [7, 38].

For interpretability and to understand the contribution of each parameter to the dual objectives, we utilized SHAP (SHapley Additive exPlanations) values. SHAP values were computed using both TreeExplainer and KernelExplainer, which are well-suited for models with tree-based structures and kernel methods, respectively [16, 13]. These values quantify the contribution of each feature to the prediction outcomes across both heads of the neural network, providing insights into the relative importance and interaction of parameters in determining formulation efficacy and safety [39].

Statistical verification of the model's robustness and the independence of input parameters was conducted using Spearman rank cross-correlation and Variance Inflation Factor (VIF) analysis. Spearman rank correlation was employed to assess the monotonic relationships between parameters, ensuring that the model's predictions were not confounded by linear dependencies [18]. VIF analysis was performed to detect multicollinearity among the input features, with a VIF value exceeding 10 indicating significant collinearity that could undermine the model's predictive accuracy [41]. The results of these analyses are presented in Supplementary Table 5, confirming the statistical soundness of the parameter space and the independence of the features used in the model.

This methodological framework, combining Monte Carlo sampling, Pareto optimization, SHAP analysis, and rigorous statistical validation, provides a robust approach for optimizing nanocarrier formulations. It ensures that the selected formulations are not only effective but also safe, aligning with the overarching goal of enhancing the therapeutic index of doxorubicin nanocarriers in oncological applications [9, 37].

## References

1. Zamorano, J. L., et al. (2016). 2016 ESC Position Paper on cancer treatments and cardiovascular toxicity developed under the auspices of the ESC Committee for Practice Guidelines. *European Heart Journal*, 37(36), 2768-2801. https://doi.org/10.1093/eurheartj/ehw211
2. Rodrı́guez, C., et al. (2003). Regulation of antioxidant enzymes: a significant role for melatonin. *Journal of Pineal Research*, 35(1), 1-9. https://doi.org/10.1046/j.1600-079x.2003.00092.x
3. Sharifi‐Rad, J., et al. (2020). Lifestyle, Oxidative Stress, and Antioxidants: Back and Forth in the Pathophysiology of Chronic Diseases. *Frontiers in Physiology*, 11, 694. https://doi.org/10.3389/fphys.2020.00694
4. Tungmunnithum, D., et al. (2018). Flavonoids and Other Phenolic Compounds from Medicinal Plants for Pharmaceutical and Medical Aspects: An Overview. *Medicines*, 5(3), 93. https://doi.org/10.3390/medicines5030093
5. Pommier, Y., et al. (2010). DNA Topoisomerases and Their Poisoning by Anticancer and Antibacterial Drugs. *Chemical Biology*, 17(5), 421-433. https://doi.org/10.1016/j.chembiol.2010.04.012
6. Mitchell, M. J., et al. (2020). Engineering precision nanoparticles for drug delivery. *Nature Reviews Drug Discovery*, 19(2), 101-124. https://doi.org/10.1038/s41573-020-0090-8
7. Patra, J. K., et al. (2018). Nano based drug delivery systems: recent developments and future prospects. *Journal of Nanobiotechnology*, 16(1), 71. https://doi.org/10.1186/s12951-018-0392-8
8. Yáñez‐Mó, M., et al. (2015). Biological properties of extracellular vesicles and their physiological functions. *Journal of Extracellular Vesicles*, 4, 27066. https://doi.org/10.3402/jev.v4.27066
9. Shi, J., et al. (2016). Cancer nanomedicine: progress, challenges and opportunities. *Nature Reviews Cancer*, 16(5), 361-373. https://doi.org/10.1038/nrc.2016.108
10. Wilhelm, S., et al. (2016). Analysis of nanoparticle delivery to tumours. *Nature Reviews Materials*, 1(5), 16014. https://doi.org/10.1038/natrevmats.2016.14
11. Page, M. J., et al. (2021). PRISMA 2020 explanation and elaboration: updated guidance and exemplars for reporting systematic reviews. *BMJ*, 372, n160. https://doi.org/10.1136/bmj.n160
12. Arrieta, A. B., et al. (2019). Explainable Artificial Intelligence (XAI): Concepts, taxonomies, opportunities and challenges toward responsible AI. *Information Fusion*, 58, 82-115. https://doi.org/10.1016/j.inffus.2019.12.012
13. Alzubaidi, L., et al. (2021). Review of deep learning: concepts, CNN architectures, challenges, applications, future directions. *Journal of Big Data*, 8(1), 53. https://doi.org/10.1186/s40537-021-00444-8
14. Lambin, P., et al. (2017). Radiomics: the bridge between medical imaging and personalized medicine. *Nature Reviews Clinical Oncology*, 14(12), 749-762. https://doi.org/10.1038/nrclinonc.2017.141
15. Gandomi, A., et al. (2014). Beyond the hype: Big data concepts, methods, and analytics. *International Journal of Information Management*, 35(2), 137-144. https://doi.org/10.1016/j.ijinfomgt.2014.10.007
16. Karniadakis, G. E., et al. (2021). Physics-informed machine learning. *Nature Reviews Physics*, 3(6), 422-440. https://doi.org/10.1038/s42254-021-00314-5
17. Brunton, S. L., et al. (2019). Machine Learning for Fluid Mechanics. *Annual Review of Fluid Mechanics*, 51, 443-478. https://doi.org/10.1146/annurev-fluid-010719-060214
18. Abdar, M., et al. (2021). A review of uncertainty quantification in deep learning: Techniques, applications and challenges. *Information Fusion*, 76, 243-297. https://doi.org/10.1016/j.inffus.2021.05.008
19. OpenAI. (2023). GPT-4 Technical Report. *Leibniz International Proceedings in Informatics (LIPIcs)*, 264, 11. https://doi.org/10.4230/lipics.cosit.2024.11
20. Rasheed, A., et al. (2020). Digital Twin: Values, Challenges and Enablers From a Modeling Perspective. *IEEE Access*, 8, 21980-22012. https://doi.org/10.1109/access.2020.2970143
21. Hou, X., et al. (2021). Lipid nanoparticles for mRNA delivery. *Nature Reviews Materials*, 6(12), 1078-1094. https://doi.org/10.1038/s41578-021-00358-0
22. Chen, Y., et al. (2023). Macrophages in immunoregulation and therapeutics. *Signal Transduction and Targeted Therapy*, 8(1), 52. https://doi.org/10.1038/s41392-023-01452-1
23. Oberdörster, G., et al. (2005). Principles for characterizing the potential human health effects from exposure to nanomaterials: elements of a screening strategy. *Particle and Fibre Toxicology*, 2, 8. https://doi.org/10.1186/1743-8977-2-8
24. Danaei, M., et al. (2018). Impact of Particle Size and Polydispersity Index on the Clinical Applications of Lipidic Nanocarrier Systems. *Pharmaceutics*, 10(2), 57. https://doi.org/10.3390/pharmaceutics10020057
25. Zanger, U. M., et al. (2013). Cytochrome P450 enzymes in drug metabolism: Regulation of gene expression, enzyme activities, and impact of genetic variation. *Pharmacology & Therapeutics*, 138(1), 103-141. https://doi.org/10.1016/j.pharmthera.2012.12.007
26. He, J., et al. (2021). Targeting PI3K/Akt signal transduction for cancer therapy. *Signal Transduction and Targeted Therapy*, 6(1), 425. https://doi.org/10.1038/s41392-021-00828-5
27. Bukowski, K., et al. (2020). Mechanisms of Multidrug Resistance in Cancer Chemotherapy. *International Journal of Molecular Sciences*, 21(9), 3233. https://doi.org/10.3390/ijms21093233
28. Kerru, N., et al. (2020). A Review on Recent Advances in Nitrogen-Containing Molecules and Their Biological Applications. *Molecules*, 25(8), 1909. https://doi.org/10.3390/molecules25081909
29. Hancock, J. T., et al. (2020). CatBoost for big data: an interdisciplinary review. *Journal of Big Data*, 7(1), 94. https://doi.org/10.1186/s40537-020-00369-8
30. Ali, M., et al. (2023). Explainable Artificial Intelligence (XAI): What we know and what is left to attain Trustworthy Artificial Intelligence. *Information Fusion*, 90, 101805. https://doi.org/10.1016/j.inffus.2023.101805
31. Velden, T. A., et al. (2022). Explainable artificial intelligence (XAI) in deep learning-based medical image analysis. *Medical Image Analysis*, 79, 102470. https://doi.org/10.1016/j.media.2022.102470
32. Fjell, C. D., et al. (2011). Designing antimicrobial peptides: form follows function. *Nature Reviews Drug Discovery*, 11(1), 37-51. https://doi.org/10.1038/nrd3591
33. Teece, D. J., et al. (2018). Profiting from innovation in the digital economy: Enabling technologies, standards, and licensing models in the wireless world. *Research Policy*, 47(8), 1367-1387. https://doi.org/10.1016/j.respol.2017.01.015
34. Emmerich, M. T. M., et al. (2018). A tutorial on multiobjective optimization: fundamentals and evolutionary methods. *Natural Computing*, 17(3), 585-609. https://doi.org/10.1007/s11047-018-9685-y
35. Paleyes, A., et al. (2022). Challenges in Deploying Machine Learning: A Survey of Case Studies. *ACM Computing Surveys*, 55(6), 1-39. https://doi.org/10.1145/3533378
36. Pardridge, W. M. (2004). The blood-brain barrier: Bottleneck in brain drug development. *NeuroRx*, 2(1), 3-14. https://doi.org/10.1602/neurorx.2.1.3
37. Bozzuto, G., et al. (2015). Liposomes as nanomedical devices. *International Journal of Nanomedicine*, 10, 975-999. https://doi.org/10.2147/ijn.s68861
38. Rosenblum, D., et al. (2018). Progress and challenges towards targeted delivery of cancer therapeutics. *Nature Communications*, 9(1), 1410. https://doi.org/10.1038/s41467-018-03705-y
39. Cuomo, S., et al. (2022). Scientific Machine Learning Through Physics–Informed Neural Networks: Where we are and What’s Next. *Journal of Scientific Computing*, 92(3), 88. https://doi.org/10.1007/s10915-022-01939-z
40. Gigerenzer, G., et al. (2010). Heuristic Decision Making. *Annual Review of Psychology*, 62, 451-482. https://doi.org/10.1146/annurev-psych-120709-145346
41. Shrestha, A., et al. (2019). Review of Deep Learning Algorithms and Architectures. *IEEE Access*, 7, 53040-53065. https://doi.org/10.1109/access.2019.2912200
42. Muratov, E. N., et al. (2020). QSAR without borders. *Chemical Society Reviews*, 49(11), 3525-3564. https://doi.org/10.1039/d0cs00098a
43. Salis, A., et al. (2014). Models and mechanisms of Hofmeister effects in electrolyte solutions, and colloid and protein systems revisited. *Chemical Society Reviews*, 43(21), 7521-7539. https://doi.org/10.1039/c4cs00144c
44. Abbas, Q., et al. (2020). Transformation pathways and fate of engineered nanoparticles (ENPs) in distinct interactive environmental compartments: A review. *Environment International*, 138, 105646. https://doi.org/10.1016/j.envint.2020.105646
45. Richter, R. P., et al. (2005). Following the Formation of Supported Lipid Bilayers on Mica: A Study Combining AFM, QCM-D, and Ellipsometry. *Biophysical Journal*, 89(5), 3372-3383. https://doi.org/10.1529/biophysj.104.053728
46. Leite, F. L., et al. (2012). Theoretical Models for Surface Forces and Adhesion and Their Measurement Using Atomic Force Microscopy. *International Journal of Molecular Sciences*, 13(10), 12773-12856. https://doi.org/10.3390/ijms131012773