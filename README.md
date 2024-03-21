# Summarisation-using-LLM

#### Task:
* To automatically summarize meta review data of academia papers. Fine-tune a GenAI LLM model and then write a prompt which gives you summary of meta reviews using that model.

#### Requirements and Models:

* An open-source pre-trained GenAI LLM model - 'AutoModelForSeq2SeqLM' from Hugging Face.
* Dataset of meta reviews paired with their corresponding summaries - 'zqz979/meta-review'.
* Google Colaboratory 

#### Preprocessing:
* Dataset consisted of test, train and validated subsets.
* Truncated the spaces and converted text to lowercase.
* Dropped the null rows
* Tokenized using 'google-t5/t5-small' model, which used relatively fewer parameters to train

#### Evaluating the model:
* Used the rouge method for evaluating the model and **AutoModelForSeq2SeqLM** specifically for the summarization task. I had to connect to Hugging Face which provides an interactive interface for smooth connection to deploy our model to be public for everyone. Did some hyperparameter tuning but it was limited due to fewer resources at hand. 

#### Prompt Engineering:
* You need to present your data very wisely and in a clear format which requires great preprocessing techniques. I was provided with the **JSONL file** which contained a list of strings and in that were 'metareviews' for which we needed the summaries. So extracting the metareviews in a separate pandas dataframe after analyzing all the data was an interesting task for me. Finally iterated through the dataframe and got the output in the summary array for each of the metareview. 

#### Sample metareview:
* 'This paper proposes a class of neural processes that lifts the limitations of conditional neural processes (CNPs) and produces dependent/correlated outputs but that, as CNPs, is inherently scalable and it is easy to train via maximum likelihood. The proposed model is extended to multi-output regression and to capture non-Gaussian output distributions. Results are presented on synthetic data, an electroencephalogram dataset and on a climate modeling problem. The paper parameterizes the prediction map as a Gaussian, where the mean and covariance are determined using neural networks. Non-Gaussian prediction maps are obtained using copulas. \n\nTechnically speaking, the reviewers found the approach to be incremental and only marginally significant and I agree with them. Issues such as estimates of computational cost, using fixed lengthscales for the covariances and relationships/using normalizing flows have been addressed by the authors satisfactorily. Empirically, the contribution of the paper is somewhat significant, as it provides similar flexibility to other more computationally expensive processes and more general assumptions than conditional neural processes.'

#### Sample summary output:
* 'This paper proposes a class of neural processes that lifts the limitations of conditional neural processes (CNPs) and produces dependent/correlated outputs but that, as CNPs, is inherently scalable and it is easy to train via maximum likelihood. The proposed model is extended to multi-output regression and to capture non-Gaussian output distributions. The paper parameterizes the prediction map as a Gaussian, where the mean and covariance are determined using neural networks.'

Credits: Google Colab, Hugging Face, CHATGPT, Google, StackOverflow, etc.
