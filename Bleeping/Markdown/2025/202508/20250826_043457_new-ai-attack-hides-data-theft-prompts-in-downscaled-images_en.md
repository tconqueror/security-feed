# New AI attack hides data-theft prompts in downscaled images

![New AI attack hides data-theft prompts in downscaled images](https://www.bleepstatic.com/content/hl-images/2022/05/12/ai-cybersecurity-hacker.jpg)

Researchers have developed a novel attack that steals user data by injecting malicious prompts in images processed by AI systems before delivering them to a large language model.

The method relies on full-resolution images that carry instructions invisible to the human eye but become apparent when the image quality is lowered through resampling algorithms.

Developed by [Trail of Bits researchers](https://blog.trailofbits.com/2025/08/21/weaponizing-image-scaling-against-production-ai-systems/) Kikimora Morozova and Suha Sabi Hussain, the attack builds upon a theory presented in a [2020 USENIX paper](https://www.usenix.org/conference/usenixsecurity20/presentation/quiring) by a German university (TU Braunschweig) exploring the possibility of an image-scaling attack in machine learning.

## How the attack works

When users upload images onto AI systems, these are automatically downscaled to a lower quality for performance and cost efficiency.

Depending on the system, the image resampling algorithms could make an image lighter using nearest neighbor, bilinear, or bicubic interpolation.

All of these methods introduce aliasing artifacts that allow for hidden patterns to emerge on the downscaled image if the source is specifically crafted for this purpose.

In the Trail of Bits example, specific dark areas of a malicious image turn red, allowing hidden text to emerge in black when bicubic downscaling is used to process the image.

![Example of a hidden message appearing on the downscaled image](https://www.bleepstatic.com/images/news/u/1220909/2025/August/example.jpg)

**Example of a hidden message appearing on the downscaled image**  
_Source: Zscaler_

The AI model interprets this text as part of the user's instructions and automatically combines it with the legitimate input.

From the user's perspective, nothing seems off, but in practice, the model executed hidden instructions that could lead to data leakage or other risky actions.

In an example involving [Gemini CLI](https://www.bleepingcomputer.com/news/security/flaw-in-gemini-cli-ai-coding-assistant-allowed-stealthy-code-execution/), the researchers were able to exfiltrate Google Calendar data to an arbitrary email address while using Zapier MCP with 'trust=True' to approve tool calls without user confirmation.

Trail of Bits explains that the attack needs to be adjusted for each AI model according to the downscaling algorithm used in processing the image. However, the researchers confirmed that their method is feasible against the following AI systems:

* Google Gemini CLI
* Vertex AI Studio (with Gemini backend)
* Gemini's web interface
* Gemini's API via the llm CLI
* Google Assistant on an Android phone
* Genspark

As the attack vector is widespread, it may extend well beyond the tested tools. Furthermore, to demonstrate their finding, the researchers also created and published [Anamorpher](https://github.com/trailofbits/anamorpher) (currently in beta), an open-source tool that can create images for each of the mentioned downscaling methods.

The researchers argue that 

As mitigation and defense actions, Trail of Bits researchers recommend that AI systems implement dimension restrictions when users upload an image. If downscaling is necessary, they advise providing users with a preview of the result delivered to the large language model (LLM).

They also argue that users explicit users' confirmation should be sought for sensitive tool calls, especially when text is detected in an image.

"The strongest defense, however, is to implement secure design patterns and systematic defenses that mitigate impactful prompt injection beyond multi-modal prompt injection," the researchers say, referencing a [paper published in June](https://arxiv.org/pdf/2506.08837) on design patterns for building LLMs that can resist prompt injection attacks.