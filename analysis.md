## 1) Which species are most under threat and how are they distributed across the parks?
### Goal: Identify the most vulnerable species, so the National Park Service can prioritise conservation efforts accordingly.
### Analysis Tips:
#### - Merge both datasets on scientific_name.
#### - Filter out species with a conservation status of 'No Intervention'.
#### - Group by category and conservation status, and count the unique at-risk species.

<img width="1389" height="590" alt="image" src="https://github.com/user-attachments/assets/a7751b78-0e35-49e1-910a-afbb9653861e" />

<img width="1389" height="590" alt="image" src="https://github.com/user-attachments/assets/07829e1f-619f-4a2e-8c8c-de11005bb4e5" />

<img width="885" height="590" alt="image" src="https://github.com/user-attachments/assets/3fd5253e-8b62-4ebb-b74a-a8bf4e23483b" /><br/><br/>

**Table 1: Proportions of proctectiveness grouped by organism category**
| category | protected | not_protected | protection percentage | not protection percentage |
|----------|-----------|---------------|-----------------------|---------------------------|
| Amphibian |	72 | 7 | 91.14 | 8.86 |
| Bird | 413 | 72 | 85.15 |	14.85 |
| Fish | 115 | 11 |	91.27 |	8.73 |
| Mammal | 146 | 30 |	82.95 |	17.05 |
| Nonvascular Plant |	328 |	5 |	98.50 |	1.50 |
| Reptile |	73 | 5 | 93.59 | 6.41 |
| Vascular Plant | 4216 |	46 | 98.92 | 1.08 |<br/><br/>

At first glance, the vast majority of species have a conservation status of 'No Intervention' (as low as 82.95% (for Mammals) and as high as 98.92% (for Vascular Plants)), and so are not protected as they are not under threat. Of the protected species, Mammals and Birds appear the most under threat, with protection percentages of 17.05% and 14.85% respectively. Interestingly, looking at Figures 1-3, whilst mammals have a higher proportion of species under threat, birds have a higher absolute count of species under threat, with the mast vajority of these being 'Species of Concern' however, and not 'Endangered'. Something else to note is that whilst Vascular Plants have the lowest proportion of protected species, looking at their count on Figures 1-3 shows that they boast the 2nd highest absolute number of under threat species, again with most of their numbers being in the 'Species of Concern' category. This appears to be the case with all organism categories, with Reptiles and Nonvascular Plants only possessing species with this status. Fish, however, seem to have an equal amount of species with 'Species of Concern', 'Threatened', and 'Endangered' conservation status.

## 2) Is there a correlation between the number of observations of a species and its conservation status?
### Goal: Understand if rarer (more endangered) species are observed less frequently, which could support prioritising their monitoring.
### Analysis Tips:
#### - Use visualization (e.g. box plots, scatter plots, etc.) to explore relationships between observation frequency and conservation risk.

<img width="1160" height="547" alt="image" src="https://github.com/user-attachments/assets/9809bb5c-503b-4b58-86d1-5ad4a5bbf1bc" /><br/><br/>

**Table 2: Endangered species with over 100 observations**
| category | scientific_name | common_names |	conservation_status |	national_park| observations |	protected |
|----------|-----------------|--------------|---------------------|--------------|--------------|-----------|
| Mammal | Canis lupus | Gray Wolf | Endangered |	Yellowstone |	203 |	True |
| Mammal | Canis lupus | Gray Wolf | Endangered |	Yosemite | 117 | True |
| Mammal | Canis lupus | Gray Wolf, Wolf | Endangered	| Yellowstone |	203 |	True |
| Mammal | Canis lupus | Gray Wolf, Wolf | Endangered |	Yosemite | 117 | True |<br/><br/>

Looking at Figure 4, it appears that there is a visible decrease in observations of species as their conservation status becomes more severe and endangered. This is to be expected, as the more endangered a species is, the less likely one is to see it in the wild. This calls to prioritise their monitoring for conservation and preventing extinction of that species. For the 'Endangered' species on Figure 4, there appears to be two great outliers, having observations around 100 and 200 across the 7 day period, whilst still being classified as endangered. Looking further into the data, shown via Table 2, shows that this particular species is the Grey Wolf (Canis Lupis), observed in Yellowstone and Yosemite National Park, indicating that whilst its numbers appears to be high at first glance, it must have decreased significantly over the years, and so this should not be mistaken as a species not under threat, and so extra prevention methods may need to be deployed to prevent this particular species from going extinct.

## 3) Is there a significant difference between organism categories under threat?
### Goal: Understand if certain organism catergories are more prioritised in conservation than others.
### Analysis Tips:
#### - Create contingency tables of the number of protected and non-protected species of two different organism categories.
#### - Perform chi-square analysis tests too see whether there is statistical significance between the number of protected organism species of different organisms.
### Null Hypothesis: There is no association between the organism category and whether a they are under protection.
Chi-square analysis: P-value for the protection status across all organism species: 6.525703368905795 x 10^-86

<img width="948" height="790" alt="image" src="https://github.com/user-attachments/assets/88f1533b-cf01-455f-98a9-8a677882524b" />

Across all organism categories as a whole, there appears to be very strong evidence to suggest that there is indeed an association between categories and their conservation status. This is shown by the very small p-value of around 6.5 x 10^-86, which is very strong evidence against the null hypothesis that there is no association. However, by comparing each organism category individually with each other, this yields some interesting results. For example, looking at the heat map, 10/21 (almost half) of p-values between individual categories are above the significance threshold of 0.05, meaning there is almost a 50/50 split of whether to reject the null hypothesis or not. Most noteably, between Amphibians and Fish, there is a p-value of 1, meaning there is, theoretically, the strongest evidence to accept the null hypothesis that there is no association between these two categories and their conservation status. This could be due to their shared aquatic/semi-aquatic habitats, or similar ecological threat profiles. Looking closer at the heatmap shows that animal categories, for the most part, only show a significant p-value (below the threshold of 0.05), and so significant evidence to reject the null hypothesis, when compared with plant categories, and vice versa. This suggests that animals and plants are not protected equally, as potentially one gets more attention or different conservation treatments, whilst the other might be underepresented. The exceptions to this are the comparisons between Reptiles and Mammals, which yielded a p-value of about 0.0384, and Reptiles and Nonvascular Plants, which yielded a p-value of about 0.0336. This could point to the evidence that Reptiles are not as equally protected as the rest of the animals, potentially yeilding extra protection methods.

