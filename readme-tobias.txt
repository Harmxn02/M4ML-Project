	// LATEX: This hides all LaTeX intermediate files from VS Code. This means I can not see these files
	// They will still show up in the Source Control tab though, so if you're ever wondering why there are
	// files showing up there but you cannot see them in the Explorer, this is (probably) why.
	"files.exclude": {
		"**/*.aux": true,
		"**/*.log": true,
		"**/*.out": true,
		"**/*.toc": true,
		"**/*.synctex.gz": true,
		"**/*.fdb_latexmk": true,
		"**/*.fls": true,
		"**/*.bbl": true, // bibliography files
		"**/*.blg": true, // bibliography files
	},

	"latex-workshop.latex.tools": [
		{
			"name": "pdflatex",
			"command": "pdflatex",
			"args": ["-interaction=nonstopmode", "-synctex=1", "%DOCFILE%"]
		},
		{
			"name": "biber",
			"command": "biber",
			"args": ["%DOCFILE%"]
		}
	],
	"latex-workshop.latex.recipes": [
		{
			"name": "default (fast)",
			"tools": ["pdflatex"]
		},
		{
			// deze is enkel nodig voor ons project, maar is traag voor ander gebruik.
			// De recipe hierboven is sneller, en zal default gebruikt worden omdat hij hoger staat
			// Om deze recipe te gebruiken, moet je hem manueel selecteren in de command palette
				// (Ctrl+Shift+P) -> LaTeX Workshop: Build with recipe -> pdflatex -> biber -> pdflatex*2
			"name": "pdflatex -> biber -> pdflatex*2",
			"tools": ["pdflatex", "biber", "pdflatex", "pdflatex"]
		}
	]





Je kan dit in je VS Code settings.json zetten zodat je niet 10 miljard bestanden ziet door latex, maar enkel degene dat je nodig hebt