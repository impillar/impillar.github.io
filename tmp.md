**Malware after transformation.** _(RA)_ Malware may lose its toxicity after transformations. However, different from works that evaluate AVs with obfuscated or transformed malware, our study grasps the different reactions of AVs towards transformed apps and further infers what have happended within AVs. 
We do NOT guarantee the maliciouseness of malware. 
Specificially, _unsigning_ makes apps unable to be installed and unsigned apps are supposed to be non-harmful. But we can infer much from AVs' reaction. 
If one AV makes a positive flip for all unsigned malicious apps, it can be determined that app integrity is checked and serves as a significant clue for detection. Otherwise, the app is analyzed in a static manner. An altered label can imply that a covert detection chain that AV first uses signature to perform a match and then employs other heuristic approaches (e.g., machine learning or pattern that can be further explored by other transformations).
_Prunning_ can break malicious functions, and we use pruned apps to infer whether AVs harvest features in the removed code or files based on the detection results, rather than measure AVs' abilities. 
(RD) Generally, AVs claim they are resilient to transformations, and we have communicated with some AV vendors and learn that they are usign essembled engines to detect malware. That's the assumption of the paper, so we make transformations and explore how these engines work.

**Data selection.** (RA) We have claimed the principles of data selection and use at Section 4.1.1. Drebin and Malgenome are indeed out-of-dated, but would be most recognizable by AVs. 
So we can get more result changes from transformation as well as concluded findings. Conversly, new malware is likely missed by many AVs, resulting that only get few useful information can be captured. 
AMD and VirusShare are relatively newer datasets, but they are flagged largely by VirusTotal, which is not appropriate to use VirusTotal to evalute them again. 
Regardless, we'd like to test with newer malware (e.g., VirusShare 2019 and 2020) that are commonly recognized by AVs.
(RA) The benign apps are all from ANVA and Chinese markets now. We avoid to use them for AVs' capability evaluation, which may produce biased conclusions. 

**Packing.** We use an open-source tool Bangcle to pack apps, which provide a dynamic load of encrypted dex from memory. We also pack benign apps which are likely detected as unwanted programs discussed in Section 5.2.3. (RA,RB)

**Label Changes (Section 5.4)** (RB) The intention by fusing two apps (either malware or benignware) is to investigate how AVs report to their users-whether one innocent apps can dilute the maliciousness. Additionally, when AVs are performing static analysis and find both patterns from malicious apps and grayware, which labels will come out first. This is an important evaluation especially on how AVs make the decision after the knowledge.

**Introduction** We have made the scope clear to Android at all necessary points that may mislead readers. (RB)

**AVs on real devices** (RB) We do not run our experiments with AVs on real devices twofold: 1) [80] has experimentally verified that standalone AVs underperform AVs in VirusTotal. The test objects are not Android apps, but why are standalone AVs better than cloud AVs in detecting apps? 2) Many research studies are conducted by obtaining results from VirusTotal, and another goal of this paper is to uncover whether there is misuse of VirusTotal.

**Improvement suggestions** We have discussed some potential improvements in Section 6.

**VirusShare** We have downloaded all data from 2016 to 2018 and randomly select XXX apps from it.  (RC)

**Capabilities over time** (RD) We can add this experiment if necessary.






