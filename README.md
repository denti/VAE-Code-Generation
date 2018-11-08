# VAE Code Generator
- Ipython notebook contains Seq2Seq model for generation of C++ source files.
- To learn sequense distribution VAE layer added between encoder and decoder parts:
SeqEncoder - VAE - SeqDecoder. VAE layer learns distribution of hidden_state and cell_state.
- data/sources.txt - file with C++ source files for training.
- models/w2v_cpp_model.h5 - weights for Word2Vec trainde on c++ sources


#### Work is still in-process. Model is end-to-end now and can be trained, but it need to be fixed to generate correct examples:
- [x] C++ should read -> tokenized -> filtered
- [x] Word2Vec should be trained on C++ sorce code sequences
- [x] Seq2Seq model for source code generation should be implemented (Code -> Seq2Seq -> Code)
- [x] VAE layer should be added
- [x] VAE loss should be added to the main loss
- [ ] cell_state need to be generated from history_state or vice-versa (using Dense layer). When we want to generate some code examples, we need to get one of states from rand normal distribution and then generate another one state from the first one. In other case there will not be correlations between states and output of decoder Seq will not be as we want.  
- [ ] loss of state generation layer need to be added to the main loss
- [ ] generation of syntactically incorrect examples nedd to be added