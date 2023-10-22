# Latent Consistency Model for Stable Diffusion WebUI

This extension aims to integrate [Latent Consistency Model (LCM)](https://latent-consistency-models.github.io/) into AUTOMATIC1111 Stable Diffusion WebUI.

Note that LCMs are a completely different class of models than Stable Diffusion, and the current available checkpoint is [LCM_Dreamshaper_v7](https://huggingface.co/SimianLuo/LCM_Dreamshaper_v7).

**This is a very barebone implementation written in an hour, so any PRs are welcome.**

## Installation:

Simply clone this repo to your `extensions/` directory.

```
git clone https://github.com/0xbitches/sd-webui-lcm
```

And reload your WebUI.

Generated images will be saved to `outputs/txt2img-images/LCM`. You can use PNG Info to examine generation data.

## Known Issues

If you get `<|startoftext|>` or `<|endoftext|>` related errors, locate your huggingface hub cache directory (something like `~/.cache/huggingface/hub/path_to_lcm_dreamshaper_v7`), and find the file `/tokenizer/added_tokens.json`. You can change the contents to:

```
{
  "<|endoftext|>": 49409,
  "<|startoftext|>": 49408
}
```

or simply remove this file.