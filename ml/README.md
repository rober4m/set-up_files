# Machine learning tools


## Install wandb

```bash 
# Install
uv pip install wandb

# Login — opens browser to get API key
wandb login
```
Get your API key at wandb.ai/authorize — paste it when prompted. Stored in ~/.netrc automatically.

### Core concepts with wandb

```bash
wandb
├── Entity        # your username or team name
├── Project       # groups related experiments
│   ├── Run       # single training run
│   │   ├── Config    # hyperparameters
│   │   ├── Metrics   # loss, accuracy, etc.
│   │   ├── Artifacts # models, datasets
│   │   └── Media     # images, plots, tables
```

## Projects structure

```bash
my-project/
├── .env                      # WANDB_API_KEY here
├── .env.example              # template without real key
├── environment.yml
├── requirements.txt
│
├── src/
│   └── my_project/
│       ├── config.py         # project + wandb config
│       ├── data/
│       ├── models/
│       └── training/
│           ├── train.py      # core training logic
│           └── evaluate.py
│
├── scripts/
│   ├── prepare_data.py
│   ├── train.py              # calls training + wandb.init
│   ├── evaluate.py
│   └── sweep.py              # hyperparameter search
│
└── tests/
```
