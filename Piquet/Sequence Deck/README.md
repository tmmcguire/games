# Sequence Deck

These are the cards from Piquet's sequence deck, from the Master Rules. They may not all be appropriate for every expansion.

* `card_front.sla` This is the template for the card fronts, in Scribus format. I have used the Scribus Generator script to generate the cards from...

* `cards.gnumeric` A Gnumeric spreadsheet with card titles, details, and text sizes. This is exported in CSV format as...

* `cards.csv` The CSV file read by Scribus Generator.

Scribus Generator produces PDF files; those files are converted to PNG with the command:

```sh
for j in *.pdf
do
  pdftocairo -antialias gray $j -png
done
```

The individual files are placed in an array by 

```sh
montage -geometry +5+6 *-1.png back.png deck.png
```
