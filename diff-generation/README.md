Required folder structure

```
<parent-folder>
├── Makefile
├── original
│   ├── figures
│   ├── original.tex
│   └── sections
└── revised
	├── figures
	├── revised.tex
	└── sections
```

# Generating a .tex file with all the changes marked

Here are the steps to make this work: 

1. Download the original source from PCS. 
2. Download the revised source from Overleaf. 
3. Download the Makefile from this directory and make sure the folder structure matches the above folder structure. 
4. Make sure you have homebrew installed. If not, follow the instructions [here](https://docs.brew.sh/Installation).
5. Run `make` on your terminal from the parent folder.
6. If everything went well, you should have a new file in your folder named `changes-marked.tex`. 
7. Upload this file to the root folder on your Overleaf project and compile. It should generate a changes marked PDF in the ACM format.