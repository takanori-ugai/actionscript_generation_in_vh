# High Execution Rate Action Script Generation based on LLM in VirtualHome

## VirtualHome Setup
1. Set up [VirtualHome](https://github.com/xavierpuigf/virtualhome).
2. Confirm that VirtualHome works correctly by referring to its GitHub repository.

## VirtualHome AIST Setup
1. Set up [VirtualHome_aist](https://github.com/aistairc/virtualhome_aist/).
2. Confirm that VirtualHome_aist works properly by referring to its GitHub repository.
3. Note that the simulator used in VirtualHome AIST differs from that used in the original VirtualHome. You can download the simulator [here](https://github.com/aistairc/virtualhome_unity_aist/releases/tag/Door_Modified_Build_2023_0404/).

Please note that VirtualHome and VirtualHome AIST have different Python execution environments.

## How to Run Our System on VirtualHome
1. Download the original_vh_program folder and put it under (virtualhome/).
2. Run VirtualHome.exe (virtualhome/simulation/unity_simulator/VirtualHome.exe).
3. Open the jupyter-notebook file (original_vh_program.ipynb) and run it from the top. Enter any action description in the last cell and run it to generate the action script.

Please note that the [OpenAI](https://openai.com/) API is required for execution.

## How to Run Our System on VirtualHome AIST
1. Download the aist_vh_program folder and put it under (virtualhome_aist/).
2. Run VirtualHome.exe (virtualhome_aist/simulation/unity_simulator/VirtualHome.exe).
3. Open the jupyter-notebook file (aist_vh_program.ipynb) and run it from the top. Enter any action description in the last cell and run it to generate the action script.

Please note that the [OpenAI](https://openai.com/) API is required for execution.

## Reproducing Evaluation Experiments
1. Download the evaluation_program_and_data folder.
2. The folder contains programs for each experiment, a folder with scripts generated using the VirtualHome dataset (generated_vh_data) divided into a folder with scripts generated by class name and another folder with scripts generated by object name, a folder with the correct data of VirtualHome dataset (correct_vh_data), a folder with scripts generated using KGRC4SI dataset (generated_kgrc_data), and a folder with the correct data of KGRC4SI (correct_kgrc_data).

### LCSscore
1. Open the jupyter-notebook file [lcs.ipynb](https://github.com/JinAoyama/actionscript_generate_in_vh/blob/main/evaluation_program_and_data/lcs.ipynb).
2. Since the path to the target data has been specified in advance, execution is performed in the same hierarchy as the above folder.
3. The data to be evaluated is noted in the markdown above the cell for which the evaluation value is calculated.

You can find the evaluation values for each experiment in the output history of [lsc.ipynb](https://github.com/JinAoyama/actionscript_generate_in_vh/blob/main/evaluation_program_and_data/lcs.ipynb).

### Correctness
1. Open the jupyter-notebook file [correctness.ipynb](https://github.com/JinAoyama/actionscript_generate_in_vh/blob/main/evaluation_program_and_data/correctness.ipynb).
2. Since the path to the target data has been specified, the execution is performed in the same hierarchy as the above folder.
3. The data to be evaluated is noted in the markdown above the cell for which the evaluation value is calculated.

You can find the evaluation values for each experiment in the output history of [correctness.ipynb](https://github.com/JinAoyama/actionscript_generate_in_vh/blob/main/evaluation_program_and_data/correctness.ipynb).

### Simulator (Execution Rate)
1. The VirtualHome simulator is only required for this evaluation.
2. Run VirtualHome.exe and open the jupyter-notebook file [sim.ipynb](https://github.com/JinAoyama/actionscript_generate_in_vh/blob/main/evaluation_program_and_data/sim.ipynb).
3. Select the VirtualHome scene in the top cell.
4. Choose the evaluation data. Each data name ends with a scene number, so select the file path corresponding to the scene selected in step 3 to load the data.
5. Execute the bottom cell to measure the execution rate.

Note that longer execution times are expected, and bugs may occur due to VirtualHome issues.

Since agents are randomly placed in the environment, it is known that some scripts may or may not be executed depending on the initial location of the agent. Therefore, we may not obtain the same results every time. However, the experimental values are shown below:
- generated_vh_data(object): An average of 99.2% for each scene.
- generated_vh_data(class): An average of 55.3% for each scene.
- generated_kgrc_data: An average of 87.2% for each scene.

### Supplement
The dataset used should be located in the $HOME directory. 

