# Text-Classification-using-Bert
***Winning solution of Instabase Encipher Hackathon 2022***
![image](https://user-images.githubusercontent.com/45576314/153232282-2f08756a-951e-4d83-a23a-6110acbff7e0.png)

* Instabase Encipher Hackathon 2022 was organized from 10 Jan'22 to 31 Jan'22.
* It was organized on Dare2Compete platform.
* This opportunity was open to passionate women pursuing their pre-final or final year BTech and IDD course from 100+ Engineering institutes in India.
* There were almost 2800 participants from different engineering colleges.

## Stages of Encipher
All the rounds were eliminatory
* **Cliff 1-Coding Fundamentals**(2800 participants)  
  A competitive programming round based on Coding fundamentals(2 coding problems)
* **Cliff 2-Encipher Code Pro**(600 participants shortlisted)  
  Participants had to code in a stipulated time period to advance further.(3 Coding problems)
* **Cliff 3 - Problem Statement Launch**(57 participants shortlisted)  
  Submit prototypes/solutions based on the dynamic problem statement shared!.Two problem statements were shared.Participant had to do any one of them.One was a -TEXT             CLASSIFICATION problem and one was DISTRIBUTED WORKFLOW PROCESSING problem.I decided to do Text classification problem.Participants were given 2 days to submit their           solutions.They had to submit the code, [powerpoint presentation](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/Instabase-Encipher%20Text%20Classification-Presentation-Ishita_Jain.pptx) and a video explaining the solution.[Guidelines](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/Guidelines%20to%20attempt%20the%20Encipher%20Problem%20Statement.pdf) for solving problem statements.
* **Cliff 4 - Finale and IB Interviews**(26 participants shortlisted)  
  The top 26 participants shortlisted presented their solutions to the esteemed jury and winners were declared.Shortlisted students interveiwed with Instabase for FTE and 
  intern roles on the same day.I am glad to say that I got first prize and a FTE offer from Instabase.Prize money was Rs200000 for winner, Rs100000 for first runner up and       Rs50000 for second runner up.7 students were given FTE and Intern offers(Package - CTC ₹31.32L + ESOPs worth ₹15L + Benefits).
  
  # Introduction
  ## Problem Statement-*Text Classification*
  I was provided with 26 legal clauses extracted from credit agreements along with their labels.The mission was to come up with a model that will help classify the given passages into their legal clause types.  
  Refer to [complete problem statement](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/Instabase%20Encipher%20Problem%20Statement%20(1)%20Text%20Classification.pdf)
  
  ## My approach
  **MODEL OPTIONS CONSIDERED**  
  
* [**LSTM Model(Artificial RNN)**](https://colab.research.google.com/drive/1-1i0S_kIAQDDggv8sFn-Ao2csQTbz2WR?usp=sharing)   
The performance of the LSTM model on test data was not good.It was overfitting on the training data.It was not the best for capturing  the true meaning of words.  
* [**Bert model (pretrained on BookCorpus dataset)**](https://colab.research.google.com/drive/1kc_ypj5diUcdQyjpGWmhQY-k7R2BbYqH?usp=sharing)  
The model was not able to fit the training data well. It was underfitting. The accuracy was not so good in this model. It was not able to capture the law terminology which might be the reason for its poor performance. I wanted to pretrain it on some law data so that it gets familiar with the terminology.
* [**Fine tuning bert model(Pretrained on law data)** ]( https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/Ishita_Jain_text_classification_Submission_code.ipynb)  
Finally,the pretrained bert model got familiar with law terminology and was fine tuned with my augmented training data. It produced accurate results and was working well.

* Check [comparison of three models](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/Comparision%20of%203%20models.pdf)

## [Final Solution- Bert Model](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/Ishita_Jain_text_classification_Submission_code.ipynb)
* Bert, stands for Bidirectional Encoder Representations for Transformers.
* Firstly, input data given in the problem statement had some 25 data points which was very less. So, I made some more data points from [law insider website](https://www.lawinsider.com/clauses) and prepared a [csv file](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/inputs_final.csv).The 5 given labels were encoded using one-hot encoding as it was a classic multiclass classification problem.
* Input sentences were encoded using *Bert Tokenizers*. Tokenization is a process to take raw texts and split into tokens, which are numeric data to represent words. Used custom datasets class to feed data into our model.
* Transformers gave Bert its increased capacity for understanding context and ambiguity in languages. Bert model pre-trained on law dataset was fine tuned using our training data.

## Model metrics
* For the final model: Average values-  
* Validation accuracy = 90.00%  
* F1 score(micro) = 0.90  
* F1 score(macro) = 0.86  
* Precision = 0.93  
* Recall = 0.9  
* Random search was used for the hyperparameter optimization of our model   
* Accuracy on the training set is 100%  
* Accuracy on validation set was 80%, but after adding regularization I was able to achieve 90% validation accuracy(which is neither overfitting nor underfitting I believe)
* Check [test datasets](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/output%20_final.csv) given and their [predictions](https://github.com/ishitajain123/Text-Classification-using-Bert/blob/main/predictions_final.json) with confidence score.  
![image](https://user-images.githubusercontent.com/45576314/153241595-7ec86ef6-491d-4c5a-9b04-d37f0f3b10cc.png)

## Further Improvements
* More accuracy can be obtained if we have more data.
* Bert can be pre-trained on multiple law datasets and fine tuned using our dataset(As of now we pre- trained  it on only  one law dataset)
* A larger version of Bert might be used which is computationally expensive.
* One of the weaknesses when using Bert architecture is that it is limited to 512 tokens,that means the maximum sequence length allowed as input is 512 words.



  
  

