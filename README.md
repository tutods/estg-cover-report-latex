<h1 align="center">Template de Relatório em LaTeX</h1>
<h2 style="font-weight: 300; margin-top: 0" align="center">Para relatório de estágio da ESTG P.Porto</h2>

<div align="center">
<a href="#">
<img alt="LaTex" src="https://img.shields.io/badge/Latex%20-%23008080.svg?&style=for-the-badge&logo=latex&logoColor=white"/>
</a>
<a href="#">
<img alt="VS Code" src="https://img.shields.io/badge/Visual%20Studio%20Code%20-%23007ACC.svg?&style=for-the-badge&logo=visual-studio-code&logoColor=white"/>
</a>
</div>

<br />

<h2 style="font-weight: 300;">Resultado</h2>

<a href="#"><img src="https://i.ibb.co/fpYTqhx/image.png" alt="image" border="0"></a>

<br />

<h2 style="font-weight: 300;">O que contêm este projeto?</h2>

- Capa;
- Contra-capa;
- Página em branco;
- Índice;
- Lista de Figuras;
- Lista de Tabelas;
- Glossário;
- Acrónimos;
- Utilização do **[tipo de letra do P.Porto](https://www.ipp.pt/comunicacao/marca-pporto)**


<br />

<h2 style="font-weight: 300;">Editor:</h2>

Para **LaTex** uso sempre ou o **Visual Studio Code** ou o **TexPad**, porém deixo as configurações utilizadas no **Visual Studio Code**:


<h3 style="font-weight: 300;">Extensões</h3>

<a href="https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop">
<img src="https://i.ibb.co/VvKLgBp/image.png" alt="image" border="0">
</a>

<h3 style="font-weight: 300;">Configurações</h3>

```json
{
	"[latex]": {
		"editor.formatOnPaste": false,
		"editor.formatOnSave": true
	},
	"latex-workshop.bibtex-format.sort.enabled": true,
	"latex-workshop.bibtex-format.sortby": [
		"title"
	],
	"latex-workshop.message.log.show": false,
	"latex-workshop.view.pdf.viewer": "tab",
	"latex-workshop.synctex.afterBuild.enabled": true,
	"latex-workshop.latex.autoClean.run": "onBuilt",
	"latex-workshop.message.error.show": false,
	"latex-workshop.latex.autoBuild.cleanAndRetry.enabled": true,
	"latex-workshop.latex.autoBuild.run": "onFileChange",
	"latex-workshop.message.update.show": false,
	"latex-workshop.latex.clean.fileTypes": [
		"*.aux",
		"*.bbl",
		"*.blg",
		"*.idx",
		"*.ind",
		"*.lof",
		"*.lot",
		"*.out",
		"*.toc",
		"*.acn",
		"*.acr",
		"*.alg",
		"*.glg",
		"*.glo",
		"*.gls",
		"*.fls",
		"*.log",
		"*.fdb_latexmk",
		"*.snm",
		"*.synctex(busy)",
		"*.synctex.gz(busy)",
		"*.nav"
	]
}
```

<h4 style="font-weight:300">Nota:</h4>

No caso deste relatório é utilizada o tipo de letra do P.Porto (referida acima) e como tal é necessário utilizar ou o **XeLaTex** ou o **LuaLaTex**, para isso é necessário adicionar as seguintes configurações ao **`.json`** anterior:

```json
"latex-workshop.latex.recipes": [
	{
		"name": "lualatex->biber->lualatex",
		"tools": [
			"lualatex",
			"biber",
			"lualatex"
		]
	},
	{
		"name": "lualatex",
		"tools": [
			"lualatex"
		]
	}
],
"latex-workshop.latex.tools": [
	{
		"name": "lualatex",
		"command": "lualatex",
		"args": [
			"-synctex=1",
			"-interaction=nonstopmode",
			"-file-line-error",
			"-pdf",
			"%DOC%"
		]
	},
	{
		"name": "biber",
		"command": "biber",
		"args": [
			"%DOCFILE%"
		]
	}
]
```
