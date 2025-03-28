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
from tinytroupe.agent import TinyPerson
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

Clone the Microsoft TinyTroupe Github using the following command
```bash
git clone https://github.com/microsoft/TinyTroupe.git
```

Next, change directory to the TinyTroupe folder using the following command
```bash
cd TinyTroupe
```
Now to Install the packages run the following command
```bash
pip install .
```

2. What is Turing Test? In Today's world with Large Language Models(LLMs), what is the definition of Turing Test?

The Turing Test originally known as the imitation game by Alan Turing is a test to see if a Machine can imitate Human equivalent intelligence in this test a human evaluates 2 responses 1 created by a human and 1 created by a machine and the goal of the interpreter is to see if they can detect which response was created by the machine. The machine is said to pass if the interpreter cannot tell the responses apart.

In Todays world with LLMs the idea of the Turing Test has evolved from what it once was. It now includes better understanding of context, using common sense reasoning and being able to hold a longer conversation while being coherent. In addition to this LLMs today can produce results in various formats other than text such as videos or images. Finally, LLMs today are constantly improving which aims to make them more convincing but overall still lack self-awareness.

3. Create a simulation of your own topic and show me the transcript. This implies define at least two personas of your own choice with conflict built in and observe their conversation. You can simply copy/paste the conversation in a `.md` file. Please comment on the transcript whether you think the Turing Test is passed.

I have attempted to complete this exercise but was getting the [stream] error and do not want to incur costs. I have written out the code for what I attempted to do and put the results of me running it showing the [stream] error.

```python
from tinytroupe.agent import TinyPerson
john = TinyPerson("John")
john.define("age",25)
john.define("occupation", "Student at NYC University")
john.define("professional_history", "John is working in shift in random hours in a governemnt organization in NYC and sometimes gets home late and has irregular schedule. The schedule can change based on the government agency needs. John is Fascinated with AI and thinks that it will be the greatest advancement in human history. John firmly believes in AI becoming a tool to help humans and is vital to the survival of the Human race.")

mike = TinyPerson("Mike")
mike.define("age",40)
mike.define("occupation","Professor in anti-AI studies")
mike.define("professional_history", "Mike has worked at a University in California for the past 10 years studying AI and how it will be a negative impact to humans and will lead to the downfall of the human race. Mike has spoken at numerous anit-AI conferences and has written numerous papers regarding the topic. Mike refuses to believe that AI is a tool to help benefit humans. Mike is regarded as the number 1 expert on this topic.")


from tinytroupe.environment import TinyWorld
world = TinyWorld("Classroom", [mike, john])
world.make_everyone_accessible()
mike.listen("AI is the best thing to happen for humans it makes their lives so easy.")
world.run(3)
```
────────────────────────────────────────────────────────────────────────────────────────────────────── Classroom step 1 of 3 ───────────────────────────────────────────────────────────────────────────────────────────────────────
2025-03-28 14:28:46,187 - tinytroupe - ERROR - [2] Error: 'stream'
2025-03-28 14:28:51,190 - tinytroupe - ERROR - [3] Error: 'stream'
2025-03-28 14:28:56,193 - tinytroupe - ERROR - [4] Error: 'stream'
2025-03-28 14:29:01,196 - tinytroupe - ERROR - [5] Error: 'stream'
2025-03-28 14:29:01,196 - tinytroupe - ERROR - Failed to get response after 5.0 attempts.