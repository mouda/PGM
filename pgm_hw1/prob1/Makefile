N=1
EMTRAINNEW=../bin/gmtkEMtrainNew	# path to put your gmtkEMtrainNew
EMTRIANGULATE=../bin/gmtkTriangulate	# path to put your gmtkTriangulate
PFILE=prob$N.train.pfile

# you can add/modify the arguments below, 
# but you have to make sure that you output the prob[N].cpt.
# 
# gmtkEMtrainNew
# 	-of1: 				observation file
# 	-inputMasterFile: 		master file
# 	-strFile: 			structure file
# 	-iswp1: 			endian swap
# 	-seed T				change the random seed generator
# 	-allocateDenseCpts: 		allocate dense cpts if non-exist
# 	-maxEmIters: 			the maximum iteraion that EM would run
# 	-outputTrainableParameters:	output the cpts.

train: clean
	$(EMTRIANGULATE) -strFile prob$(N).str -rePart T -findBest T -triangulation completed	
	$(EMTRAINNEW)	-of1 $(PFILE) \
			-inputMasterFile prob$(N).master \
			-strFile prob$(N).str \
			-iswp1 \
			-seed T \
			-allocateDenseCpts 1 \
			-maxEmIters 50 \
			-outputTrainableParameters prob$(N).cpt

clean:
	rm -f prob$(N).cpt
	rm -f prob$(N).str.trifile
	rm -f jt_info.txt
