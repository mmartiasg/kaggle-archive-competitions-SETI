# kaggle-archive-competitions-SETI

This competition from 2021 had the objective of detecting extraterrestial signals, and that is by no mean an easy task...

- Data is 70GB
- Signals are really few
- Each sample consist in 6 spectrograms.
- Each spectrograms is the taken from the telescope for 5 minutes or 300 seconds

This was particularly challenging in several ways:
 - First there is a huge dataset consisiting on 70GB
  - On a first approach what I did was to read the spectograms as numpy arrays on disk each time up to 256 at once.
  - In the end what works best was building a TF Record to latter load in batches faster. This approach allowed me to train way faster.
 - Then the other proble is how to process the spectograms, and for that I've decided to treat them as images.
  But that is not all also as a sequence. Thus my data consist on a sequence of 6 images.
 - Data proportions arroud only 10% are signals the other 90% are not. Thus that is my baseline. If I always predict 0 I would get a 90% accuracy.
 - Data can be found here ```kaggle competitions download -c seti-breakthrough-listen```
  Or here for manual download ```https://www.kaggle.com/competitions/seti-breakthrough-listen/data```
 
 Reflexions:
  I did not get a good result, but at the same time I do not think the approach was all wrong.
  I've realized to treating it as a classification problem is not the correct way to deal with this kind of problem.
  This is in nature a detection problem not a classification one.
  
  That is, for now, I will go back to this competition with another approach later this year.
