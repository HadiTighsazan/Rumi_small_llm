Transformer from Scratch: Rumi Poetry Generator

### معرفی پروژه (Project Overview)
این پروژه بر روی پیاده‌سازی عمیق و از پایه (From Scratch) معماری ترانسفورمرها (Transformers) تمرکز دارد. هدف اصلی، درک دقیق و پیاده‌سازی الگوریتم‌های زیرساختی هوش مصنوعی بدون استفاده از کتابخانه‌های سطح بالا یا مدل‌های از پیش آماده بوده است.

ویژگی‌های کلیدی این پیاده‌سازی عبارتند از:
* پیاده‌سازی خالص: تمامی اجزا، از جمله مکانیسم توجه (Self-Attention)، لایه‌های نرمال‌سازی و بلاک‌های ترانسفورمر، به صورت دستی کدنویسی شده‌اند.
* توکنایزر اختصاصی: توکنایزر مدل (Tokenizer) مشابه معماری GPT و با استفاده از الگوریتم BPE (Byte Pair Encoding) به صورت دستی پیاده‌سازی شده است تا ساختار زبان فارسی و اشعار مولانا را بهینه پردازش کند.
* منابع: این پروژه بر اساس مفاهیم مقاله انقلابی "Attention Is All You Need" و آموزش‌های ارزشمند Andrej Karpathy (پروژه nanoGPT) توسعه یافته است.

---

### Model Architecture & Data Flow
The architecture follows a Decoder-only Transformer design (similar to GPT). Below is the step-by-step data flow through the network:

1. Embeddings (The Entry Point):
* The input token indices are passed through a Token Embedding Table to convert them into dense vectors.
* Simultaneously, a Positional Embedding Table generates vectors representing the position of each token in the sequence.
* These two vectors are summed ($Token + Position$) to form the initial input representation ($x$).

2. The Transformer Block (The Core):
The input $x$ passes through a stack of $N$ identical layers (Blocks). Inside each block:
* Multi-Head Self-Attention: The data is normalized (LayerNorm) and passed to the attention heads. Here, the model learns the relationships and context between tokens (using Query, Key, Value matrices).
* Residual Connection: The output of attention is added back to the original input ($x + Attention(x)$).
* Feed-Forward Network (FFN): The result is normalized again and passed through a Multi-Layer Perceptron (Linear -> ReLU -> Linear) to process the features individually.
* Residual Connection: The output is added back again ($x + FFN(x)$).

3. The Head (The Output):
* After passing through all blocks, the final representation goes through a final LayerNorm.
* It is then projected by a Linear Layer (Language Model Head) to the size of the vocabulary.
* Finally, a Softmax function (implicit in CrossEntropyLoss during training) converts the logits into probabilities for the next token prediction.
 
