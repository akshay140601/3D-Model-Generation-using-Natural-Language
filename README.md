# Query2CAD

## Abstract
Computer Aided Design (CAD) engineers typically do not achieve their best prototypes in a single attempt. Instead, they iterate and refine their designs to achieve the optimal solution through multiple revisions. Inspired by this iterative approach taken by CAD engineers, we introduce Query2CAD, a novel system designed to generate and self-refine CAD models based on prompts provided by humans and a Large Language Model (LLM). Query2CAD operates without supervised data or additional training, utilizing the LLM as both a generator and a refiner. The refiner uses feedback generated by the BLIP2 model, and to address false negatives, we have incorporated human-in-the-loop feedback into Query2CAD. Additionally, we have developed a dataset that encompasses most operations used in CAD model design and have evaluated our architecture using this dataset. Our findings reveal that the LLM successfully generated the correct design in 32.76% of cases on the first attempt. With subsequent refinements, the accuracy of correct designs increased by an additional 20.69%.

## How to run the system
1. Download and setup the [FreeCAD](https://github.com/FreeCAD/FreeCAD) software. The system has been tested on Windows and Linux OS with a screen size of 1920x1080.
2. Clone the repository.
```
git clone https://github.com/akshay140601/Query2CAD.git
```

3. Set up Together AI API to use Llama models or get the API key of OpenAI to use GPT models. Take a look at args in src/run.py for arguments that you can specify. Assuming the keys are already set, run the below command to run the system.
```
python src/run.py --code_gen_model codellama/chatgpt/llama3/gpt4-turbo --reasoning_model codellama/chatgpt/llama3/gpt4-turbo --human_feedback True
```

4. The results will be stored in the results/ folder and new queries can be added in data/queries.txt
