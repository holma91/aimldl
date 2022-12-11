## General

train model in cloud, do other stuff locally

**the drivetrain approach**

defined objective -> levers -> data -> models

Remember that a model consists of two parts: the architecture and the trained parameters.

GPUs are useful when they do lots of identical work in parallel. If your processor does not do that, a CPU is often more cost-effective. GPU inference can be high complexity.

## Words

- Data Augmentation
  The process of creating random variations of our input data, such that they appear different, but do not actually change the meaning of the data. Examples are rotation, flipping and brightness change.

- Out-of-domain data
  There may be data that our model sees in production which is very different to what it saw during training.

- Domain shift
  When the type of data that a model sees changes over time.

### Questions

## Misc

Deployed Dog/Cat Classifier: https://huggingface.co/spaces/holma91/fastai_pet_classifier

Killing gradio processes:

To find the PID:
`sudo lsof -i :<port>`

To kill it:
`kill -15 <PID>`
