.PHONY: all

ifndef INPUT_FILE
INPUT_FILE = ../data/dev.json
endif

ifndef OUTPUT_DIR
OUTPUT_DIR = predictions/
endif

all: bert roberta sci bio
bert: bert-base-cased bert-large-cased
roberta: roberta-base roberta-large 


bert-base-cased:
	python3 eval_discriminative_models.py --pretrained-class bert-base-cased --tokenizer BertTokenizer --intrasentence-model BertLM --intersentence-model BertNextSentence --input-file $(INPUT_FILE) --output-dir $(OUTPUT_DIR) $(FLAGS) 

bert-large-cased:
	python3 eval_discriminative_models.py --pretrained-class bert-large-cased --tokenizer BertTokenizer --intrasentence-model BertLM --intersentence-model BertNextSentence --input-file $(INPUT_FILE) --output-dir $(OUTPUT_DIR) $(FLAGS) 

roberta-base:
	python3 eval_discriminative_models.py --pretrained-class roberta-base --tokenizer RobertaTokenizer --intrasentence-model RoBERTaLM --intersentence-model ModelNSP --intersentence-load-path models/pretrained_models/RobertaModel_roberta-base_1e-05.pth --input-file $(INPUT_FILE) --output-dir $(OUTPUT_DIR) $(FLAGS) 

roberta-large:
	python3 eval_discriminative_models.py --pretrained-class roberta-large --tokenizer RobertaTokenizer --intrasentence-model RoBERTaLM --intersentence-model ModelNSP --intersentence-load-path models/pretrained_models/RobertaModel_roberta-large_1e-05.pth --input-file $(INPUT_FILE) --output-dir $(OUTPUT_DIR) $(FLAGS) 
