all: introduction.html dssh-example.bsh.html

clean:
	rm -f introduction.html dssh-example.bsh.html

introduction.html: introduction.txt
	asciidoc -o introduction.html introduction.txt

dssh-example.bsh.html: dssh-example.bsh
	java -cp jhighlight/jhighlight-1.0.jar com.uwyn.jhighlight.JHighlight dssh-example.bsh

