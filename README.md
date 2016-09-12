# tf_experiment

Build the target in msys:

`bazel build tensorflow/tools/example_pip_package:simple_console --cpu=x64_windows_msvc`

Run the target in cmd.exe:

```
python ./bazel-bin/tensorflow/tools/example_pip_package/simple_console
>>> import tensorflow.tools.example_pip_package.pywrap_example as tf
>>> tf.get_time()
'Fri Sep  9 18:13:24 2016\n'
>>> tf.fact(10)
3628800
```
