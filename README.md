# claude-gemini

A way to use *Google AI Studio's* Free Tier and its *Gemini* models in *Claude Code* instead of *Anthropic* models. Uses *LiteLLM* to proxy the API calls.

1. Install *LiteLLM Proxy Server* using *uv*: 
  ```bash
  uv tool install 'litellm[proxy]'
  ```
2. `cp settings.json.example settings.json`
3. `cp litellm_config.yaml.example litellm_config.yaml`
4. [Create a *Google AI Studio* API key](https://aistudio.google.com/api-keys) using the Free Tier.
4. Add your *Google AI Studio* API Key to `settings.json` in `ANTHROPIC_API_KEY`.
5. Add your *Google AI Studio* API Key to `litellm_config.yaml` in each `api_key` field.
6. `cp settings.json ~/.claude/settings.json`
7. `cp litellm_config.yaml ~/.claude/litellm_config.yaml`
8. Add an alias to your `~/.bash_aliases` or `~/.zshrc` or similar:
  ```bash
  alias liteproxy="litellm --config ~/.claude/litellm_config.yaml --port 4000"
  ```
9. Run the proxy with `liteproxy`
10. In another terminal run *Claude Code* with `claude`
11. Choose **Yes** when asked if you want to use the defined API key.
