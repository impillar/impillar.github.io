**Malware after transformation.** Malware may lose its toxicity after transformations. However, different from works that evaluate AVs with obfuscated or transformed malware, our study grasps the different reactions of AVs towards transformed apps and further infers what have happended within AVs. 
We do NOT guarantee the maliciouseness of malware. _Prunning_ can break malicious functions, and we use pruned apps to infer whether AVs harvest features in the removed code or files based on the detection results, rather than measure AVs' abilities.

**Data selection.** We claim the principles of data selection and use at Section 4.1.1. Drebin and Malgenome are indeed out-of-dated, but would be most recognizable by AVs. 
So we can get more result changes from transformation as well as concluded findings. Conversly, new malware is likely missed by many AVs, resulting that we can only get few useful information. 
AMD and VirusShare are relatively newer datasets, but they are flagged largely by VirusTotal, which is not appropriate to use VirusTotal to evalute them again. 
Regardless, we'd like to test with newer malware (e.g., VirusShare 2019 and 2020) that are commonly recognized by AVs.


**Packing.** 

****
