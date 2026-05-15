# Set-up files for different projects

## Installers

* uv
* conda 
* OpenFOAM

## Project Structure Best Practice

```bash
my-project/
├── README.md
├── environment.yml
├── requirements.txt
├── pyproject.toml
├── .gitignore
├── .env
├── .env.example
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── external/
│
├── src/
│   └── my_project/
│       ├── __init__.py
│       ├── config.py
│       ├── data/
│       │   ├── __init__.py
│       │   ├── loader.py
│       │   └── transforms.py
│       ├── models/
│       │   ├── __init__.py
│       │   └── classifier.py
│       ├── training/
│       │   ├── __init__.py
│       │   ├── train.py
│       │   └── evaluate.py
│       └── utils/
│           ├── __init__.py
│           └── helpers.py
│
├── scripts/                 # one-off runnable scripts
│   ├── prepare_data.py      # run once to process data
│   ├── train.py             # entry point for training
│   └── evaluate.py          # entry point for evaluation
│
├── tests/
│   ├── __init__.py
│   ├── test_data.py
│   ├── test_model.py
│   └── test_utils.py
│
├── models/
│   └── checkpoints/
│
└── outputs/
    ├── figures/
    └── reports/
```

## For Rust projects

```bash
my-project/
├── README.md
├── Cargo.toml
├── Cargo.lock
├── rust-toolchain.toml
├── .gitignore
├── .env
├── .env.example
│
├── src/
│   ├── main.rs              # entry point, minimal logic
│   ├── lib.rs               # all reusable logic lives here
│   ├── config.rs
│   ├── error.rs
│   │
│   ├── data/
│   │   ├── mod.rs
│   │   ├── loader.rs
│   │   └── transforms.rs
│   │
│   ├── models/
│   │   ├── mod.rs
│   │   └── classifier.rs
│   │
│   └── utils/
│       ├── mod.rs
│       └── helpers.rs
│
├── tests/                   # integration tests
│   ├── common/
│   │   └── mod.rs
│   └── integration_test.rs
│
├── benches/
│   └── benchmark.rs
│
└── examples/                # replaces notebooks in Rust
    ├── basic_usage.rs
    └── data_loading.rs
```
