# TinyTroupe

## Step 1: Install Packages
Open a terminal from Codespace on Github. In the terminal, run the following command to clone the repository.
``` bash
git clone https://github.com/microsoft/TinyTroupe.git
```

Change directory into 'tinytroupe' folder:
```bash
cd tinytroupe
```

Install the package:
```bash
pip install .
```

## Step 2: Setup API Key
In the terminal that you just installed packages, use the following command to setup the API Key:

```bash
export OPENAI_API_KEY= "xxxx"
```

## Step 3: Experiments (Simulation)
### Talk to an existing persona
```python
from tinytroupe.examples import create_lisa_the_data_scientist
lisa_ds = create_lisa_the_data_scientist()
lisa_ds.listen_and_act("Tell me about your life")
```

### Talk to a customized persona
This implies you need to define a new person using 'tinytroupe' package

```python
from tinytroupe.agent import TinyPerson
paul = TinyPerson("Paul")
paul.define("age",25)
paul.define("nationality","American")
paul.define("occupation","Student at Pace University")
paul.define("professional_history","Paul is new to the work field has interned at a few companies as a Data Scientist and Data Analyst")
```

Use the method '.listen_and_act' to have a conversation with the persona above

```python
paul.listen_and_act("Tell me about yourself.")
```


### Observe a conversation between two personas

This implies you have at least two personas defined. Since we have one defined above, let us define another one

```python
from tinetroupe.agent import TinyPerson
john = TinyPerson("John")
john.define("age",25)
john.define("occupation", "Student at NYC University")
john.define("professional_history", "John is working in shift in random hours in a governemnt organization in NYC and sometimes gets home late and has irregular schedule. The schedule can change based on the government agency needs. John is looking to get into machine learning.")

```

To instantiate a conversation between two personas above, you will need the `TinyWorld` function

```python
from tinytroupe.environment import TinyWorld
world = TinyWorld("Classroom", [paul, john])
world.make_everyone_accessible()
paul.listen("I want to learn about Machine learning.")
world.run(3)
```


## Questions need to be answered
1. How to install `tinytroupe` packages
2. What is Turing Test? In Today's world with Large Language Models(LLMs), what is the definition of Turing Test?
3. Create a simulation of your own topic and show me the transcript. This implies define at least two personas of your own choice with conflict built in and observe their conversation. You can simply copy/paste the conversation in a `.md` file. Please comment on the transcript whether you think the Turing Test is passed.