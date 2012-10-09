EMTRAINNEW=../bin/gmtkEMtrainNew
EMTRIANGULATE=../bin/gmtkTriangulate

train: clean
	$(EMTRIANGULATE) -strFile hmm.str -rePart T -findBest T -triangulation completed	
	$(EMTRAINNEW) -of1 hmm.pfile \
			-inputMasterFile hmm.master \
			-strFile hmm.str \
			-iswp1 \
			-allocateDenseCpts 1 \
			-maxEmIters 100 \
			-outputTrainableParameters hmm.cpt
clean:
	rm -f hmm.cpt
	rm -f hmm.str.trifile
	rm -f jt_info.txt
