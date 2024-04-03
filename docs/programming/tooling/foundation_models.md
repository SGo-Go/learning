# LLMs

- legal: TBA <!-- risks and implications -->
- APIs: [OpenAI](https://openai.com/blog/openai-api)

## Tooling

- `Private-GPT`
  [docs](https://docs.privategpt.dev/)
  [github](https://github.com/imartinez/privateGPT)
  [video](https://www.youtube.com/watch?v=XFiof0V3nhA)
  - i-face: [llama.cpp](https://github.com/ggerganov/llama.cpp)
  - core models:
    [Llama 2 7B Chat](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGUF)
    [Mistral 7B Instruct v0.1](https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF)
  - run [quick local installation](https://docs.privategpt.dev/overview/welcome/quickstart#local-installation-steps)

    ```sh
    poetry run python -m private_gpt
    ```
  - troubleshooting

    <details><summary>install with CUDA</summary>

    ```sh
    export CUDACXX=/usr/local/cuda-11.8/bin/nvcc
    CMAKE_ARGS='-DLLAMA_CUBLAS=on' poetry run pip install --force-reinstall --no-cache-dir llama-cpp-python
    ```

    </details>
