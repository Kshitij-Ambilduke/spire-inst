# Spire Instruction Tuning

### Pre-requisites

Create an environment:
```bash
git clone https://github.com/axolotl-ai-cloud/axolotl.git
cd axolotl
pip3 install torch
pip3 install -U packaging==23.2 setuptools==75.8.0 wheel ninja
pip3 install --no-build-isolation axolotl[flash-attn,deepspeed]
```

The configuration used for training the various variants of SpireLM are present in `configs/` along with the default, all differ in the ***dataset path*** field. 

### Data format
For training SpireLM we used the chatML prompt format. An example of a single line from the required data JSON file is shown below:

```json
{
    "conversations": [
            {"from": "human", "value": "<< INPUT TO THE MODEL >>"}, 
            {"from": "gpt", "value": "<< OUTPUT OF FROM MODEL >>"}, 
            {"from": "human", "value": "<< FOLLOWUP INPUT TO THE MODEL >>"}, 
            {"from": "human", "value": "<< OUTPUT FROM THE MODEL >>"}
        ]
}
```