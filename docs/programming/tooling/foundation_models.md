# LLMs

- legal: TBA <!-- risks and implications -->
- APIs: [OpenAI](https://openai.com/blog/openai-api)

## Tooling

- visualization:
  [overview](https://github.com/ashishpatel26/Tools-to-Design-or-Visualize-Architecture-of-Neural-Network)
  - generic:
    - GUI:
      [**NN-SVG**](https://alexlenail.me/NN-SVG/LeNet.html) (SVG export, FCNN/LeNet/AlexNet styles)
      [tensorflow.playground](https://playground.tensorflow.org) (FCNN style)
    - arch:
      [Netron](https://github.com/lutzroeder/Netron)
      <!-- [Keras.js](https://transcranial.github.io/keras-js/) -->
  - [CNNs](https://en.wikipedia.org/wiki/Convolutional_neural_network):
    <!-- - FCNN style: -->
    - [LeNet](https://en.wikipedia.org/wiki/LeNet) style:
      [draw_convnet](https://github.com/gwding/draw_convnet)
      ![LeNet style example](https://upload.wikimedia.org/wikipedia/commons/6/61/LeNet_architecture.png)
    - AlexNet style
      [visualkeras](https://github.com/paulgavrikov/visualkeras/) (Python for Keras / TensorFlow)
      [**PlotNeuralNet**](https://github.com/HarisIqbal88/PlotNeuralNet) (Python / \LaTeX )
      <!-- ![AlexNet style example](https://upload.wikimedia.org/wikipedia/commons/1/1d/AlexNet_architecture.png) -->
      ![AlexNet style example](https://user-images.githubusercontent.com/17570785/50308846-c2231880-049c-11e9-8763-3daa1024de78.png)
  - readings:
    - [Chris Olah](https://colah.github.io/about.html)
      (2014) [*Neural Networks, Manifolds, and Topology*](https://colah.github.io/posts/2014-03-NN-Manifolds-Topology/)

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
