# TUSTEP Standard-Makros
## Von RTF mit \*import zur Weiterverarbeitung mit \*satz 

presented by : Wieland Carls | Thomas Kollatz

presented at : ITUG Jour-Fixe #3

Zoom 2021-04-28

online: [https://ITUG.github.io/ITUGJF03/](https://ITUG.github.io/ITUGJF03/)


# Handout

## [step-3](https://itug.github.io/ITUGJF03/#/step-3) Standard-Makros

```
#informiere,*
#informiere,*import
#informiere,*satz
```

## [step-4](https://itug.github.io/ITUGJF03/#/step-4) #*zebe
```
#informiere,*zebe
#*m,zebe
#*zebe,import
```

## [step-8](https://itug.github.io/ITUGJF03/#/step-8) Spezifikation: Ignorieren
```
#*import,jf03.rtf,jf03_minus.tf,lo=+,ig=-
#e,jf03_minus.tf
	Gib Anweisung>tlh
	Gib Anweisung>tp

#*import,jf03.rtf,jf03_plus.tf,lo=+,ig=+
#e,jf03_plus.tf
	Gib Anweisung>tlh
	Gib Anweisung>tl
#*export,jf03_minus.tf,ziel1.rtf,lo=+,an=+

#e,#e,jf03_plus.tf
	Tausche in <pstyle name=Titel/>  
	fgc=„blue“ bgc=„red“ aus

#*export,jf03_minus.tf,ziel1.rtf,lo=+,an=+	

#e,jf03.def
	Gib Anweisung>tp
#*export,jf03_plus.tf,ziel2.rtf,lo=+,an=+,de=jf03.def

#e,jf03_plus.tf
—> Register einfügen 
--> am Ende der zu exportierenden TUSTEP-Datei 
--> (vor: </section>):

<br type=page/>
<Überschrift-1>Personen</Überschrift-1>
<index name=person cols=1/>
<Überschrift-1>Orte</Überschrift-1>
<index name=ort cols=1/>

#*export,jf03_plus.tf,ziel2.rtf,lo=+,an=+,de=jf03.def
```

## [step-15](https://itug.github.io/ITUGJF03/#/step-15) Spezifikation: Bilder
```
#*import,jf03.rtf,jf03_bild.tf,lo=+,ig=+,bilder=bilder*jf01
#*export,jf03_bild.tf,zielbild.rtf,lo=+,an=+,de=jf03.def
```