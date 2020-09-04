Thanks for the insightful reviews.

**Malware after transformation.** _(RA,RD,RE)_ Malware may lose its toxicity after transformations. However, different from works that evaluate AVs with obfuscated or transformed malware, our study grasps the different reactions of AVs towards transformed apps and further infers what have happened within AVs. 
We do NOT guarantee the maliciouseness of malware. 


(RE) Specificially, _unsigning_ makes apps unable to be installed and unsigned apps are supposed to be non-harmful. But we can infer much from AVs' reaction. 
If one AV makes a positive flip for all unsigned malicious apps, it can be determined that app integrity is checked and serves as a significant clue for detection. Otherwise, the app is analyzed in a static manner. An altered label can imply that a covert detection chain that AV first uses signature to perform a match and then employs other heuristic approaches (e.g., machine learning or pattern that can be further explored by other transformations).
_Prunning_ can break malicious functions, and we use pruned apps to infer whether AVs harvest features in the removed code or files based on the detection results, rather than measure AVs' abilities. 

(RE) As for fine-prunning, functions are actually not well separated as per files, so we prune apps from the point of static-based detectors where they may do a taint analysis or icc analysis to aggregate files for detection. We compare the detection results of the pruned apps with their resigned versions to remove the noise.


(RD) Generally, AVs claim they are resilient to transformations, and we have communicated with some AV vendors and learn that they are usign essembled engines to detect malware. That's the assumption of the paper, so we make transformations and explore how these engines work.

**Data selection.** (RA,RC,RE) We have claimed the principles of data selection and use at Section 4.1.1. Drebin and Malgenome are indeed out-of-dated, but would be most recognizable by AVs. 
So we can get more result changes from transformation as well as concluded findings. Conversly, new malware is likely missed by many AVs, resulting that only get few useful information can be captured. 
AMD and VirusShare are relatively newer datasets, but they are flagged largely by VirusTotal, which is not appropriate to use VirusTotal to evalute them again. 
Regardless, we'd like to test with newer malware (e.g., VirusShare 2019-2020 and AndroZoo) that are commonly recognized by AVs.

(RA) The benign apps are all from ANVA and Chinese markets now. We avoid to use them for AVs' capability evaluation, which may produce biased conclusions. 

(RC) As for VirusShare samples, we have downloaded all data from 2016 to 2018 and randomly select 6,017 samples.

**Packing.** (RA,RB) We use an open-source tool Bangcle to pack apps, which provide a dynamic load of encrypted dex from memory. We also pack benign apps which are likely detected as unwanted programs discussed in Section 5.2.3. We agree to shrink the space and supplement more analysis results in this part as suggested.

**Label Changes (Section 5.4)** (RB) The transformation of app fusion is based on the hypothesis that AVs harvest features from code for detection and reporting. The hypothesis is proved in static-based detection (Section 5.2), so we attemp to speculate how they use and prioritize these features. In particular, whether benign code can dilute app's maliciousness,  whether grayware can weaken the toxicity of apps, how AVs react in front of two malware samples, i.e., which label will them preferentially output. So this is very significant and necessary for AV reverse engineering.

**Evaluation accuracy** (RB) We agree that 23K may not be adequate for evaluting AVs fairly, so we do NOT ever assess their quality with these apps, except we found the whitelisted apps (ANVA) are not that spotless where some AVs recognize them as malware. To eliminate the susicion of unfairness, we have already removed this analysis. **Additionally, "massive" does not refer to the number of base 23K apps, but together with transformed apps (253K) and collected scanning reports (971K).**

**AVs on real devices** (RB,RC) We do not run our experiments with AVs on real devices twofold: 1) [80] has experimentally verified that standalone AVs underperform AVs in VirusTotal. The test objects are not Android apps, but why are standalone AVs better than cloud AVs in detecting apps? 2) Many research studies are conducted by obtaining results from VirusTotal, and another goal of this paper is to uncover whether there is misuse of VirusTotal.

**Improvement suggestions** (RB) We have discussed some potential improvements in Section 6.

**Threats and ethics** (RC) We thank the comments and would like to include this.

**Capability evolution** (RD) It is a helpful suggestion, and we did find a phenomenon that after we used one self-signed certificate to sign a large number (>10K) of malware, a few AVs remember the ceriticate and "blindly" classify the beign apps with the same certificate as malware. It is however difficult to reproduce, and we'd like to spend more efforts on this.






