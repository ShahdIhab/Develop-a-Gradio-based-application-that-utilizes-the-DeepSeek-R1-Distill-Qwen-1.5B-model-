# Develop-a-Gradio-based-application-that-utilizes-the-DeepSeek-R1-Distill-Qwen-1.5B-model-

This is Gradio app leverages two powerful models to perform:

Code Generation using DeepSeek-R1-distill-qwen-1.5b

Image Captioning using BLIP (Salesforce/blip-image-captioning-base)


| Parameter       | Range     | Default | Description                                                                     |
| --------------- | --------- | ------- | ------------------------------------------------------------------------------- |
| **Temperature** | 0.1 - 1.0 | 0.7     | Controls randomness. Higher = more diverse outputs, lower = more deterministic. |
| **Top-p**       | 0.1 - 1.0 | 0.9     | Limits sampling to top-p probability mass. Helps control diversity.             |
| **Max Tokens**  | 10 - 500  | 100     | Limits the number of generated tokens. Longer values yield longer responses.    |


🔧 1. Temperature
Range	Typical Default
0.1 – 1.0	0.7

📌 What it does:
Temperature controls the randomness of the output by scaling the model’s confidence in its predictions.

Low values (e.g., 0.1 – 0.4):

The model becomes more confident and deterministic.

It tends to pick the most likely next word every time.

Result: Factual, repetitive, or safe outputs.

High values (e.g., 0.8 – 1.0):

The model explores more options by giving more weight to lower-probability words.

Result: More creative, diverse, or unexpected outputs — but potentially less relevant or coherent.

🎯 Use Cases:
Use low temperature for tasks requiring accuracy (e.g., math, summarization).

Use high temperature for open-ended tasks (e.g., story writing, idea generation).

🎯 2. Top-p (Nucleus Sampling)
Range	Typical Default
0.1 – 1.0	0.9

📌 What it does:
Top-p sampling chooses from the smallest set of words whose combined probability mass exceeds p.

For example, with top_p=0.9, the model samples from the top 90% most probable next words.

This focuses generation on the most plausible choices without always choosing the highest one.

🧠 Why it's useful:
Prevents the model from using very low-probability (nonsensical) words.

Retains some diversity without being completely random.

🎯 Use Cases:
Ideal for most creative and reasoning tasks.

Lower top_p (e.g., 0.5–0.7) can make output more focused.

Higher top_p (e.g., 0.95–1.0) increases the pool of possible outputs.

📏 3. Max New Tokens
Range	Typical Default
10 – 500	100

📌 What it does:
Controls the maximum number of tokens the model is allowed to generate in response to the input.

Tokens ≠ words. One word can be made of multiple tokens.

For example, “ChatGPT is amazing” might be 4 words but 5 tokens.

💡 Implications:
Short max tokens (e.g., 10–50) may result in truncated or incomplete responses.

Longer max tokens (e.g., 200–500) allow for detailed outputs but can be slower and consume more resources.

🎯 Use Cases:
For brief answers, summaries: use 50–100.

For long explanations, code generation, or storytelling: use 200+.

🧠 How They Work Together
These parameters interact to shape the output:

High temperature + high top_p → highly varied and creative text.

Low temperature + low top_p → safe, repetitive, predictable text.

max_new_tokens limits the length, while the other two control the style and diversity.



**Example Prompts**
- Standard Instructional Prompts
![Capture 5](https://github.com/user-attachments/assets/300c623b-0307-4b73-a1c3-062534c23ec4)
- Constraints & Custom Behavior

![Capture2](https://github.com/user-attachments/assets/76ab8f97-ff1e-46ac-a09e-6baeb43646ab)
- Minimalistic Prompts

![Capture3](https://github.com/user-attachments/assets/e5db0921-0f87-4795-8cbe-3a9a08d6008f)

-Image to text task
![capture4](https://github.com/user-attachments/assets/8cc1e634-8c42-4946-9afb-4ee8f295b744)


Note on Model Usage:

Although I initially considered using more advanced vision-language models such as CmPLUG-Owl2, LLaVA-NeXT, Qwen-VL-Chat, and deepseek-vl-1.3b-4bitill-qwen-1.5b, I ultimately did not incorporate them due to resource limitations. Specifically, when working in Google Colab, these models exceeded the available GPU memory (often leading to out-of-memory errors or runtime crashes). As a result, I opted for lighter-weight models that are more T4-friendly Salesforce/blip-image-captioning-base to ensure a smoother and more responsive user experience during development and testing.
