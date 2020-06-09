Generate train/test data:  
python -m chatette data\main.txt -o data\rasa_nlu -s abcd -f --base-file data\base.json

Train model:  
rasa train nlu -u data\rasa_nlu\train --fixed-model-name crf_model

Test model:  
rasa test nlu -u data\rasa_nlu\test -m models\crf_model.tar.gz

Launch server:  
rasa run --enable-api -m models\crf_model.tar.gz