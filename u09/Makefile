Images=$(wildcard *.jpg)
Thumbs=$(Images:.jpg=.thumb.jpg)

all: index.html

index.html: $(Thumbs)
	printf '%s\n' $(Images) | sed -e '1i<html><body>' -e 's_\(.*\)jpg_<a href="\0"><img src="\1thumb.jpg"></a>_' -e '$$a</body></html>' > index.html

%.thumb.jpg: %.jpg
	convert $< -scale 100x100 $@

clean:
	rm -f *.thumb.jpg index.html

