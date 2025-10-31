# wsn_gui_validate_preset_BaseLine_AAMP
wsn_gui_validate_preset_BaseLine_AAMP
Here is a comprehensive README.md file for a GitHub repository based on the provided research paper. 
AAMP/GDT Protocol Simulator
This repository contains the official Python implementation and simulation framework for the paper:

"AAMP/GDT: An Adaptive Age-Aware Matrix Pruning and Geographic Distance Tracking Protocol for Robust and Efficient Wireless Sensor Networks"

by Kanak Patel and Himanshu S. Mazumdar.

The simulator provides a high-fidelity, GUI-based environment to validate the AAMP/GDT protocol, which efficiently maintains a network-wide distance matrix in resource-constrained Wireless Sensor Networks (WSNs) through intelligent pruning, version-controlled synchronization, and robust geometric reconstruction.

🚀 Key Features
Integrated Protocol Simulation: Models the entire AAMP/GDT pipeline:

Noisy RF-based distance measurement (RSSI)

Adaptive Age-Aware Matrix Pruning (AAMP)

Version-Controlled Flooding for synchronization

Geographic Distance Tracking (GDT) with Multi-Start Optimization for matrix completion

Interactive GUI: Built with Python/Tkinter for real-time visualization of nodes, RF links, and the distance matrix heatmap.

A/B Testing: Easily compare the performance of the full AAMP/GDT protocol against a baseline (no-pruning) mode.

Comprehensive Metrics: Logs communication overhead, memory footprint, and reconstruction accuracy (MAE, RMSE, Stress-1, etc.).

Mobility Trials: Test the protocol's robustness by dynamically displacing nodes and observing its recovery.

Data Export: Export all results (node positions, matrices, metrics) to CSV, JSON, and PNG formats for further analysis.

📊 Protocol Overview
AAMP (Pruning): Each node locally prunes stale or low-confidence entries from its distance matrix row based on a temporal decay model, drastically reducing state size.

Synchronization: Nodes synchronize their pruned state using a version-controlled flooding mechanism that suppresses redundant transmissions.

GDT (Reconstruction): The protocol reconstructs the complete network topology from the sparse, noisy matrix using a multi-start gradient descent strategy, ensuring high accuracy.

📋 Requirements
This simulator is built with Python 3. Ensure you have the following packages installed:

Python 3.6+

tkinter (usually included with standard Python installations)

numpy

matplotlib

scipy

You can install the required libraries using pip:

bash
pip install numpy matplotlib scipy
🛠️ Installation & Usage
Clone the repository:

bash
git clone https://github.com/your-username/AAMP-GDT-Simulator.git
cd AAMP-GDT-Simulator
Run the simulator:
Simply execute the main Python script. This will launch the GUI.

bash
python simulator_main.py
Using the GUI:

Configure: Adjust parameters like number of nodes (N), area size (L), noise level (σ), pruning decay (λ), and confidence threshold (θ). Use the "Best-Practice Preset" for recommended settings.

Run Steps: Execute the protocol steps sequentially using the buttons:

Ping Flood: Perform initial noisy distance measurements.

Prune Matrix: Run the AAMP algorithm to prune the matrix.

Matrix Flood: Synchronize the pruned matrix across the network.

Run GDT: Reconstruct the complete distance matrix.

Validate: Calculate accuracy metrics.

Visualize: Observe the network layout, RF ranges, and matrix heatmap updating in real-time.

Run Mobility Trial: Use the dedicated button to displace nodes and run multiple recovery cycles automatically.

📁 Repository Structure
text
AAMP-GDT-Simulator/
│
├── simulator_main.py          # Main application and GUI logic
├── core_protocol.py           # Implementation of AAMP, Flooding, and GDT algorithms
├── network_model.py           # Classes for Node, Network, and RF propagation model
├── visualization.py           # Functions for drawing the GUI canvas and heatmaps
├── metrics.py                 # Functions for calculating MAE, RMSE, Stress, etc.
├── utils.py                   # Helper functions (export, config loading, etc.)
│
├── /exports/                  # Directory for exported data (CSV, JSON, PNG)
├── /docs/                     # Project documentation (e.g., paper, manual)
└── README.md                  # This file
🔬 Example Experiment
To reproduce the core results from the paper:

Click the "Best-Practice Preset" button to load the parameters (N=32, L=50m, σ=2dB, λ=0.0002, θ=0.3).

Run the protocol steps sequentially to see the effects of pruning and reconstruction.

Observe the "Metrics Panel" to see the reduction in defined pairs (~44%) and the reconstruction error (MAE ~0.8m).

Click "Mobility Trial" to displace 5 nodes and run 6 recovery cycles. Watch the MAE in the metrics panel drop from over 5m to below 1m within 2-3 cycles.

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgments
We would like to acknowledge the use of ChatGPT for assistance with sentence formation and grammar correction in our work. We also express our sincere gratitude for the support provided by the Research and Development Center at Dharmsinh Desai University (DDU) for this project.

📫 Contact
For questions regarding the research paper or the simulator, please contact the corresponding author:

Himanshu S. Mazumdar - hsmazumdar@ddu.ac.in

For technical issues regarding the code, please open an Issue on this GitHub repository.

📚 Citation
If you use this simulator or the AAMP/GDT protocol in your research, please cite our paper:

bibtex
@article{patel2024aampgdt,
  title={AAMP/GDT: An Adaptive Age-Aware Matrix Pruning and Geographic Distance Tracking Protocol for Robust and Efficient Wireless Sensor Networks},
  author={Patel, Kanak and Mazumdar, Himanshu S.},
  journal={Journal/Conference Name},
  year={2024},
  publisher={Publisher}
}
(Note: Replace Journal/Conference Name, 2024, and Publisher with the actual details once published.)

