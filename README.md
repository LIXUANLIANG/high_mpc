## Policy Search for Model Predictive Control with Application to Agile Drone Flight

[![Method](docs/figures/method.png)](https://youtu.be/Qei7oGiEIxY)

![High_MPC_Demo](docs/gifs/prompc.gif)

<!-- <img src="https://youtu.be/2uQcRnp7yI0" alt="drawing" style="width:300px;"/> -->

Policy Search and Model Predictive Control (MPC) are two different paradigms for robot control: policy search has the strength of automatically learning complex policies using experienced data, while MPC can offer optimal control performance using models and trajectory optimization. An open research question is how to leverage and combine the advantages of both approaches. In this work, we provide an answer by using policy search for automatically choosing high-level decision variables for MPC, which leads to a novel policy-search-for-model-predictive-control framework. Specifically, we formulate the MPC as a parameterized controller, where the hard-to-optimize decision variables are represented as high-level policies. Such a formulation allows optimizing policies in a self-supervised fashion. We validate this framework by focusing on a challenging problem in agile drone flight: flying a quadrotor through fast-moving gates. Experiments show that our controller achieves robust and real-time control performance in both simulation and the real world. The proposed framework offers a new perspective for merging learning and control.

### Publication

If you use this code in a publication, please cite the following paper:
Y. Song and D. Scaramuzza,
"**Policy Search for Model Predictive Control with Application to Agile Drone Flight**," [[PDF](http://rpg.ifi.uzh.ch/docs/TRO20_Yunlong.pdf)]

```
@article{song2021policy,
  title={Policy Search for Model Predictive Control with Application to Agile Drone Flight},
  author={Song, Yunlong and Scaramuzza, Davide},
  journal={arXiv preprint arXiv:2112.03850},
  year={2021}
}
```

## Learning High-Level Policies for Model Predictive Control

Y. Song and D. Scaramuzza,
"**Learning High-Level Policies for Model Predictive Control**,"
IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), Las Vegas, 2020. [[PDF](http://rpg.ifi.uzh.ch/docs/IROS20_Yunlong.pdf)]
Please find a list of demonstrations in [here](docs/gifs/README.md).

```
@inproceedings{song2020learning,
  title={Learning high-level policies for model predictive control},
  author={Song, Yunlong and Scaramuzza, Davide},
  booktitle={2020 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  pages={7629--7636},
  organization={IEEE}
}
```

### Installation

Clone the repo

```
git clone git@github.com:uzh-rpg/high_mpc.git
```

Installation Dependencies:

```
cd high_mpc
pip install -r requirements.txt
```

Add the repo path to your PYTHONPATH by adding the following to your ~/.bashrc

```
export PYTHONPATH=${PYTHONPATH}:/path/to/high_mpc
```

### Run

Standard MPC

```
cd high_mpc
python3 run_mpc.py
```

Learning a High-Level Policy

```
python3 run_highmpc.py
```

Learning a Deep High-Level Policy

```
# collect training data for the MLP
python3 run_deep_highmpc.py --option 0

# train the deep high-level policy with pre-collected data
python3 run_deep_highmpc.py --option 1

# evaluate the performance with pre-trained deep high-level policy
python3 run_deep_highmpc.py --option 2
```
