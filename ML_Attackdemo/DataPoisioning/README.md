# ML_Attacks
🛡️ Adversarial ML: Targeted Data Poisoning & Detection
Overview

This project demonstrates a Data Poisoning Attack on a Machine Learning model using the MNIST handwritten digit dataset. It explores how an adversary can compromise the "supply chain" of training data to create a "Sleeper Agent" model—one that functions perfectly for most tasks but fails predictably when a specific "trigger" is presented.
1. The Attack Scenario

In this project, we simulate a Targeted Label-Flipping Attack.

    The Target: The digit 7.

    The Attack: We infiltrate the training pipeline and relabel every instance of 7 as a 1.

    The Goal: To make the model "blind" to the number 7. In a real-world security context, this is equivalent to training a malware scanner to ignore a specific malicious file signature.

2. Key Technical Concepts
The Attack Surface

The attack enters through the Data Labeling Pipeline. By compromising the labels before the model is trained, the attacker dictates the "ground truth" that the AI learns.
Types of Attacks Explored

    Label Flipping: Modifying the classification of existing data points.

    Targeted Attack: Aiming for a specific failure (making 7s look like 1s) rather than a general accuracy drop.

3. Observations & Metrics

During evaluation, the model produced an UndefinedMetricWarning.

    Important: This warning is a direct indicator of attack success. Because the model was taught that 7 does not exist, it produced zero predictions for that class. This results in a Recall score of 0.00, effectively neutralizing the model's ability to detect that specific input.

4. The Defense: Data Sanitization

A core part of this project is the Detection Pipeline. I implemented a K-Nearest Neighbors (KNN) check to audit the training data.

    Method: The algorithm scans the dataset and compares each label to its most similar neighbors.

    Outcome: If a "1" is surrounded by images that mathematically look like "7s," the system flags the sample as "Suspicious." This allows a SOC analyst to purge the poison before it reaches the training phase.

5. How to Run

    Clone this repository.

    Install requirements: pip install scikit-learn numpy matplotlib.

    Open the Data_Poisoning_Demo.ipynb notebook.

    Run all cells to see the attack and defense results.

6. Conclusion

As AI is increasingly integrated into Security Operations Centers (SOC), the integrity of training data becomes a critical security frontier. This project proves that high accuracy (90%+) is a "false security" metric if a targeted backdoor exists.

Built With: Python, Scikit-Learn, and structured with assistance from Gemini AI to simulate adversarial security scenarios.
