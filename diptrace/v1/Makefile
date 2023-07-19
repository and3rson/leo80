SOURCES := Top.gbr Bot.gbr TopMask.gbr BotMask.gbr TopSilk.gbr BotSilk.gbr Board.gbr DrillPlated.drl MillPlated.drl

v1.zip: $(SOURCES)
	rm -f v1.zip
	zip -r v1.zip $(SOURCES)

Top.gbr: 1\ -\ Top.gbr
	cp "1 - Top.gbr" Top.gbr

Bot.gbr: 2\ -\ Bot.gbr
	cp "2 - Bot.gbr" Bot.gbr

BotMask.gbr: BottomMask.gbr
	cp BottomMask.gbr BotMask.gbr

BotSilk.gbr: BottomSilk.gbr
	cp BottomSilk.gbr BotSilk.gbr

Board.gbr: BoardOutline.gbr
	cp BoardOutline.gbr Board.gbr

.PHONY: clean
clean:
	rm -f *.gbr *.drl v1.zip

.PHONY: view
view:
	gerbview $(SOURCES)
