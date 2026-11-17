# AI from zero to university

AI can already explain almost anything. Learning on purpose takes more: a program, a clear order of topics, a placement test, careful answer checking and saved progress. SmashTutor gives you all of that for free, inside your own ChatGPT.

This repository is an open map of one such path: from school algebra and a little Python to the topics of first university courses in machine learning and deep learning. It shows what to learn and in what order, the best free material for each step, and small exercises you can do with pencil and paper. It is a path to university-level topics, not a promise of admission to any university.

SmashTutor is made by SmashOne — AI employees for small business: <https://smashone.us/?utm_source=github&utm_medium=readme>

**Work through it with answer checking — free, in your own ChatGPT: <https://smashtutor.com/?utm_source=github&utm_medium=readme>**

## Who it is for

- You know school algebra and want to understand how AI models work inside, not only how to use them.
- You are changing careers toward data or AI and want an order of topics without gaps.
- You are a student about to take a machine learning course and want to be ready for the math and the code.

## How to use it

1. Go through the stages in order. Each stage lists its topics, a few free resources, and three hand-calculation exercises.
2. Pick one resource per stage and work through it; the others are there if one explanation does not click.
3. Do the exercises on paper first, then open the answer under "Show answer".
4. Run code on your own computer or in a free online notebook (for example Google Colab or Kaggle). Companion notebooks live in the `smashtutor-notebooks` repository.

## The eight stages

### Stage 1. Linear algebra for AI

**Topics:** vectors as lists, arrows and data points; adding vectors and multiplying by a number; dot product, length (norm) and cosine similarity; matrices as tables and as functions; matrix times vector and matrix times matrix (the shape rule); systems of equations and Gaussian elimination; inverse and transpose; column space, null space, independence, basis, rank; orthogonality, projections and least squares; eigenvalues of 2x2 matrices; SVD and low-rank approximation as the idea behind PCA and embeddings.

**Free resources**

- [Linear algebra video lectures with notes and problem sets](https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/) — MIT OpenCourseWare, 18.06SC with Gilbert Strang; the classic first course.
- [Short linear algebra videos with practice](https://www.khanacademy.org/math/linear-algebra) — Khan Academy; good when a single idea needs a slower explanation.
- [Free PDF of the book "Mathematics for Machine Learning"](https://mml-book.github.io/) — Deisenroth, Faisal and Ong; chapters 2–4 cover the linear algebra used in ML.
- [Matrix methods for data analysis and machine learning](https://ocw.mit.edu/courses/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/) — MIT OpenCourseWare, 18.065; the next step after the first course, with SVD and least squares in depth.

**Calculate by hand**

1. Find the dot product of u = [2, -1, 3] and v = [4, 0, -2].

   <details><summary>Show answer</summary>

   2·4 + (-1)·0 + 3·(-2) = 8 + 0 − 6 = **2**.

   </details>

2. Find the cosine similarity of a = [3, 4] and b = [4, 3].

   <details><summary>Show answer</summary>

   a·b = 12 + 12 = 24; |a| = |b| = 5; cosine similarity = 24 / (5·5) = **24/25 = 0.96**. The vectors point in almost the same direction.

   </details>

3. A = [[1, 2, 0], [0, -1, 3]] and x = [2, 1, 1]. What is the shape of A, and what is A·x?

   <details><summary>Show answer</summary>

   A is 2 by 3, x has 3 entries, so A·x has 2 entries. Row one: 1·2 + 2·1 + 0·1 = 4. Row two: 0·2 + (−1)·1 + 3·1 = 2. **A·x = [4, 2]**.

   </details>

### Stage 2. Calculus and optimization for AI

**Topics:** derivatives; the chain rule on a computation graph; partial derivatives and the gradient; Jacobian and Hessian in words; convexity; gradient descent by hand and the learning rate; stochastic and mini-batch gradient descent; momentum and Adam (the idea); backpropagation on a small graph; gradients of mean squared error and cross-entropy; numerical gradient checking.

**Free resources**

- [Multivariable calculus videos with practice](https://www.khanacademy.org/math/multivariable-calculus) — Khan Academy; partial derivatives and gradients from the start.
- [Free PDF of the book "Mathematics for Machine Learning"](https://mml-book.github.io/) — Deisenroth, Faisal and Ong; chapter 5 (vector calculus) and chapter 7 (optimization).
- [Lecture videos "Neural Networks: Zero to Hero"](https://github.com/karpathy/nn-zero-to-hero) — Andrej Karpathy; the first lecture builds backpropagation from scratch in plain Python.
- [Course notes on optimization and backpropagation](https://cs231n.github.io/optimization-2/) — Stanford CS231n notes; gradients on small computation graphs, step by step.

**Calculate by hand**

1. f(x) = x² − 6x + 10. Find f′(1). At which x is f smallest?

   <details><summary>Show answer</summary>

   f′(x) = 2x − 6, so **f′(1) = −4**. f′(x) = 0 at **x = 3** (there f(3) = 1), and since x² opens upward this is the minimum.

   </details>

2. Minimize f(w) = (w − 5)² with gradient descent. Start at w = 1, learning rate 0.1. What is w after one step? After two steps?

   <details><summary>Show answer</summary>

   f′(w) = 2(w − 5). Step 1: f′(1) = −8, w = 1 − 0.1·(−8) = **1.8**. Step 2: f′(1.8) = −6.4, w = 1.8 + 0.64 = **2.44**. Each step moves w toward 5.

   </details>

3. L = (3w + 1)². Use the chain rule to find dL/dw at w = 1.

   <details><summary>Show answer</summary>

   Let u = 3w + 1, L = u². dL/dw = 2u · 3. At w = 1, u = 4, so **dL/dw = 2·4·3 = 24**.

   </details>

### Stage 3. Probability for AI

**Topics:** conditional probability; Bayes' rule and base rates; independence; Bernoulli, binomial, Poisson and normal distributions; expectation, variance, covariance; law of large numbers and central limit theorem; Monte Carlo; likelihood and maximum likelihood (least squares and cross-entropy as maximum likelihood); prior and posterior, MAP and regularization; entropy and KL divergence; Markov chains.

**Free resources**

- [Free PDF of the textbook "Introduction to Probability"](http://probabilitybook.net) — Blitzstein and Hwang, shared by the authors; the textbook of Harvard's Stat 110, with many worked examples.
- [Probability lectures, notes and problem sets](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/) — MIT OpenCourseWare, 6.041.
- [Statistics and probability videos with practice](https://www.khanacademy.org/math/statistics-probability) — Khan Academy; a gentle start if conditional probability is new.

**Calculate by hand**

1. 1 person in 100 has a condition. A test finds it in 90% of people who have it and wrongly says "yes" for 5% of people who do not. A person tests positive. What is the probability they have the condition?

   <details><summary>Show answer</summary>

   P(positive) = 0.01·0.9 + 0.99·0.05 = 0.009 + 0.0495 = 0.0585. P(condition | positive) = 0.009 / 0.0585 = **2/13 ≈ 0.154**. Most positives are false positives because the condition is rare.

   </details>

2. Roll one fair six-sided die. Find the expected value and the variance.

   <details><summary>Show answer</summary>

   E = (1+2+3+4+5+6)/6 = **3.5**. E[X²] = (1+4+9+16+25+36)/6 = 91/6. Variance = 91/6 − 3.5² = **35/12 ≈ 2.92**.

   </details>

3. Flip a fair coin 3 times. What is the probability of exactly 2 heads?

   <details><summary>Show answer</summary>

   There are 8 equally likely outcomes; 3 of them have exactly 2 heads (HHT, HTH, THH). **3/8 = 0.375**.

   </details>

### Stage 4. Python for data

**Topics:** your setup (your own computer or a free online notebook); NumPy arrays, shapes, slicing, masks, vectorization, broadcasting, random numbers with a seed; pandas tables, filters, missing values, groupby, merge; plots and honest plots; exploratory analysis; train/test split and data leakage; reading a traceback.

**Free resources**

- [Course notes on data science with Python](https://ds100.org/course-notes/) — UC Berkeley Data 100; pandas, visualization and modeling in one place.
- [NumPy for absolute beginners](https://numpy.org/doc/stable/user/absolute_beginners.html) — the NumPy project's own guide to arrays, shapes and broadcasting.
- [Getting started with pandas](https://pandas.pydata.org/docs/getting_started/index.html) — the pandas project's own tutorials on tables.
- [Python and NumPy tutorial](https://cs231n.github.io/python-numpy-tutorial/) — Stanford CS231n notes; a compact refresher before the ML stages.

**Calculate by hand** (predict the output, then run it to check)

1. ```python
   import numpy as np
   a = np.array([[1, 2, 3], [4, 5, 6]])
   print(a.shape, a[:, 1], a.sum(axis=0))
   ```

   <details><summary>Show answer</summary>

   `(2, 3) [2 5] [5 7 9]` — two rows and three columns; the second column; the sum of each column.

   </details>

2. ```python
   import numpy as np
   b = np.array([[1], [2]]) + np.array([10, 20, 30])
   print(b.shape)
   print(b)
   ```

   <details><summary>Show answer</summary>

   Broadcasting stretches the 2 by 1 column and the row of 3 into a 2 by 3 table:

   ```
   (2, 3)
   [[11 21 31]
    [12 22 32]]
   ```

   </details>

3. ```python
   import numpy as np
   x = np.array([4, -1, 7, 0, -3])
   print(x[x > 0], (x > 0).mean())
   ```

   <details><summary>Show answer</summary>

   `[4 7] 0.4` — the mask keeps the positive values; 2 of 5 values are positive, and the mean of True/False values is 2/5.

   </details>

### Stage 5. Classic machine learning

**Topics:** framing a problem; features and labels; loss functions; linear regression; regularization; overfitting and the bias–variance trade-off; cross-validation; logistic regression; metrics (accuracy, precision, recall, F1, ROC); class imbalance; k-nearest neighbors; decision trees, random forests and boosting; k-means; PCA; debugging ML; a final project.

**Free resources**

- [Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course) — Google; short lessons with interactive exercises on regression, classification and data.
- [Introduction to machine learning lecture notes](https://introml.mit.edu/notes/) — MIT 6.390; clear notes from regression to neural networks.
- [Machine learning lecture notes (PDF)](https://cs229.stanford.edu/main_notes.pdf) — Stanford CS229 main notes; the mathematical treatment of the same topics.
- [Free draft of the book "Probabilistic Machine Learning: An Introduction"](https://probml.github.io/pml-book/book1.html) — Kevin Murphy; a reference for when you want depth.

**Calculate by hand**

1. A model predicts [2, 4, 6]; the true values are [3, 4, 8]. Find the mean squared error.

   <details><summary>Show answer</summary>

   Errors: −1, 0, −2. Squares: 1, 0, 4. MSE = 5/3 ≈ **1.667**.

   </details>

2. A spam filter on 100 emails: 40 true positives, 10 false positives, 20 false negatives, 30 true negatives. Find accuracy, precision, recall and F1.

   <details><summary>Show answer</summary>

   Accuracy = (40 + 30)/100 = **0.7**. Precision = 40/(40 + 10) = **0.8**. Recall = 40/(40 + 20) = **2/3 ≈ 0.667**. F1 = 2·0.8·(2/3)/(0.8 + 2/3) = **8/11 ≈ 0.727**.

   </details>

3. Fit a least-squares line y = a + bx to the points (1, 2), (2, 4), (3, 5).

   <details><summary>Show answer</summary>

   Mean x = 2, mean y = 11/3. b = Σ(x − 2)(y − 11/3) / Σ(x − 2)² = 3/2 = **1.5**. a = 11/3 − 1.5·2 = **2/3**. The line is **y = 2/3 + 1.5x**.

   </details>

### Stage 6. Neural networks and deep learning

**Topics:** the neuron; multi-layer perceptrons; activation functions; the forward pass with shapes; backpropagation and autograd; the training loop; initialization; normalization; optimizers; regularization; learning curves; using a free GPU notebook; convolutions and CNNs; transfer learning; embeddings; attention and the transformer block; generative models (overview).

**Free resources**

- [Lecture videos "Neural Networks: Zero to Hero"](https://github.com/karpathy/nn-zero-to-hero) — Andrej Karpathy; builds neural networks and a small GPT from scratch in code.
- [Free interactive book "Dive into Deep Learning"](https://d2l.ai/) — Zhang, Lipton, Li and Smola; every chapter is runnable code.
- [Practical Deep Learning for Coders](https://course.fast.ai/) — fast.ai; top-down course that trains real models from the first lesson.
- [Course notes on neural networks and CNNs](https://cs231n.github.io/neural-networks-1/) — Stanford CS231n notes.
- [Introduction to deep learning lectures](https://introtodeeplearning.com/) — MIT 6.S191; short lecture videos with labs.

**Calculate by hand**

1. A neuron has weights w = [0.5, −1], bias b = 1 and ReLU activation. What is its output for x = [4, 1]?

   <details><summary>Show answer</summary>

   z = 0.5·4 + (−1)·1 + 1 = 2. ReLU(2) = **2**.

   </details>

2. The sigmoid is σ(z) = 1 / (1 + e^(−z)). Find σ(0) and its derivative at 0, using σ′(z) = σ(z)(1 − σ(z)).

   <details><summary>Show answer</summary>

   σ(0) = 1/(1 + 1) = **0.5**. σ′(0) = 0.5·0.5 = **0.25**.

   </details>

3. A network has 4 inputs, one hidden layer of 8 neurons and 3 outputs, with biases in every layer. How many parameters does it have?

   <details><summary>Show answer</summary>

   Input to hidden: 4·8 weights + 8 biases = 40. Hidden to output: 8·3 + 3 = 27. Total **67**.

   </details>

### Stage 7. Large language models

**Topics:** next-token prediction; tokenization and BPE; the context window; the decoder-only transformer and its mask; temperature, top-k and top-p sampling; pretraining and scale; fine-tuning (SFT, RLHF, DPO) and LoRA; prompting and in-context learning; retrieval-augmented generation; tools and agents; evaluation (perplexity, benchmarks and contamination); hallucinations; prompt injection.

**Free resources**

- [LLM Course](https://huggingface.co/learn/llm-course/chapter1/1) — Hugging Face; transformers, tokenizers and fine-tuning with free code.
- [Chapter on attention and transformers](https://d2l.ai/chapter_attention-mechanisms-and-transformers/index.html) — "Dive into Deep Learning"; the math and code of attention.
- [Visual explanation "The Illustrated Transformer"](https://jalammar.github.io/illustrated-transformer/) — Jay Alammar; a picture-first walk through one transformer block.
- [Lecture videos "Neural Networks: Zero to Hero"](https://github.com/karpathy/nn-zero-to-hero) — Andrej Karpathy; the later lectures build a tokenizer and a small GPT.

**Calculate by hand**

1. After exponentiating, a model's scores for the next tokens "cat", "dog", "car" are 4, 2, 2. What are the probabilities? With temperature 0.5 the exponentiated scores become their squares (16, 4, 4). What are the probabilities now?

   <details><summary>Show answer</summary>

   Divide by the total 8: **0.5, 0.25, 0.25**. With temperature 0.5 the total is 24: **2/3, 1/6, 1/6**. A lower temperature makes the most likely token even more likely.

   </details>

2. Next-token probabilities are 0.4, 0.3, 0.2, 0.1. With top-p sampling at p = 0.75, which tokens are kept, and what are their new probabilities?

   <details><summary>Show answer</summary>

   Keep the most likely tokens until the total reaches 0.75: 0.4 + 0.3 = 0.7 is not enough, adding 0.2 gives 0.9. **Three tokens are kept**; dividing by 0.9 gives **4/9, 1/3, 2/9**.

   </details>

3. A model gives the three tokens of a sentence probabilities 1/2, 1/4 and 1/8. What is its perplexity on the sentence?

   <details><summary>Show answer</summary>

   Product = 1/64. Perplexity = (1/64)^(−1/3) = 64^(1/3) = **4**. The model is as unsure as if it picked from 4 equally likely tokens each time.

   </details>

### Stage 8. Responsible AI and a capstone project

**Topics:** harm and benefit; accountability; transparency; privacy; human rights; definitions of fairness and why they conflict; sources of bias; fairness metrics on the model from stage 5; datasheets and model cards; risks of LLMs; risk-management frameworks (check the current version, they change); red-teaming; a capstone project.

**Free resources**

- [Ethics of AI online course](https://ethics-of-ai.mooc.fi/) — University of Helsinki; free course on accountability, transparency, fairness and rights.
- [Fairness module](https://developers.google.com/machine-learning/crash-course/fairness) — Google Machine Learning Crash Course; types of bias and how to measure them.
- [AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) — US National Institute of Standards and Technology; a widely used framework for managing AI risks.
- [Case studies on the social and ethical responsibilities of computing](https://ocw.mit.edu/courses/res-tll-008-social-and-ethical-responsibilities-of-computing-serc/pages/ai-algorithms/) — MIT OpenCourseWare; readings on algorithms and their impact.

**Calculate by hand**

1. A loan model approves 30 of 100 applicants from group A and 18 of 60 from group B. Are approval rates equal (demographic parity)?

   <details><summary>Show answer</summary>

   Group A: 30/100 = 0.3. Group B: 18/60 = 0.3. **Yes, both are 0.3.** Equal approval rates alone do not show the model is fair; check the next exercise.

   </details>

2. Among applicants who would repay, the model approves 40 of 50 in group A and 12 of 20 in group B. Compare the true positive rates (equal opportunity).

   <details><summary>Show answer</summary>

   Group A: 40/50 = **0.8**. Group B: 12/20 = **0.6**. The gap is **0.2**: qualified people in group B are approved less often.

   </details>

3. In a dataset 95% of cases are "no". A model always answers "no". What are its accuracy and its recall for "yes"?

   <details><summary>Show answer</summary>

   Accuracy = **0.95**, recall = **0** — it never finds a single "yes" case. High accuracy can hide a useless model when classes are imbalanced.

   </details>

## Please note

This is an independent study guide. It is not affiliated with or endorsed by Stanford, MIT, Harvard, UC Berkeley, Google, OpenAI or any other university or company named in the resource descriptions; they are named only as the source of a free resource. This is not a university course, and completing it gives no credential or academic credit. All exercises in this repository are our own.

## License and contributions

The text and exercises in this repository are © SMASHONE CORPORATION and licensed under [CC BY 4.0](LICENSE): you may share and adapt them, including commercially, with attribution and a link to this repository. The linked resources belong to their authors and keep their own licenses.

We are not accepting pull requests yet. Questions and suggestions: <https://smashtutor.com/help/>

**Work through it with answer checking — free, in your own ChatGPT: <https://smashtutor.com/?utm_source=github&utm_medium=readme>**

SmashTutor is made by SmashOne — AI employees for small business: <https://smashone.us/?utm_source=github&utm_medium=readme>
