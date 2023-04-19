# Speech Recognition

## Inference

### Quick start
#### Paraformer model
```python
from modelscope.pipelines import pipeline
from modelscope.utils.constant import Tasks

inference_pipeline = pipeline(
    task=Tasks.auto_speech_recognition,
    model='damo/speech_paraformer-large_asr_nat-zh-cn-16k-common-vocab8404-pytorch',
)

rec_result = inference_pipeline(audio_in='https://isv-data.oss-cn-hangzhou.aliyuncs.com/ics/MaaS/ASR/test_audio/asr_example_zh.wav')
print(rec_result)
```

#### API-docs
##### define pipeline
- `task`: `Tasks.auto_speech_recognition`
- `model`: model name in [model zoo](https://alibaba-damo-academy.github.io/FunASR/en/modelscope_models.html#pretrained-models-on-modelscope), or model path in local disk
- `ngpu`: 1 (Defalut), decoding on GPU. If ngpu=0, decoding on CPU
- `ncpu`: 1 (Defalut), sets the number of threads used for intraop parallelism on CPU 
- `output_dir`: None (Defalut), the output path of results if set
- `batch_size`: 1 (Defalut), batch size when decoding
##### infer pipeline
- `audio_in`: the input to decode, which could be: 
  - wav_path, `e.g.`: asr_example.wav, 
  - pcm_path, 
  - audio bytes stream
  - audio sample point
  - wav.scp

#### Inference with you data

#### Inference with multi-threads on CPU

#### Inference with multi GPU

## Finetune with pipeline

### Quick start

### Finetune with your data

## Inference with your finetuned model
