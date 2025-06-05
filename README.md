# Develop-a-Gradio-based-application-that-utilizes-the-DeepSeek-R1-Distill-Qwen-1.5B-model-

This is Gradio app leverages two powerful models to perform:

Code Generation using DeepSeek-R1-distill-qwen-1.5b

Image Captioning using BLIP (Salesforce/blip-image-captioning-base)


| Parameter       | Range     | Default | Description                                                                     |
| --------------- | --------- | ------- | ------------------------------------------------------------------------------- |
| **Temperature** | 0.1 - 1.0 | 0.7     | Controls randomness. Higher = more diverse outputs, lower = more deterministic. |
| **Top-p**       | 0.1 - 1.0 | 0.9     | Limits sampling to top-p probability mass. Helps control diversity.             |
| **Max Tokens**  | 10 - 500  | 100     | Limits the number of generated tokens. Longer values yield longer responses.    |




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
