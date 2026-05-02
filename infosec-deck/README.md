# Infosec Deck

This repo contains a redux version of the Infosec card game generator.

It includes a container that serves the card files in PDF format generated from ```decks/en/deck.yaml``` to your localhost (http://127.0.0.1:8000).

### How to proceed

First you need to create your cards in ```deck.yaml``` file.

Follow the template in the example file, adding your card title,
description, image URL, etc.

Then, run the commands below.

### Build the container image

In the container, you will have everything you need to generate a PDF with your updated cards. Run the following command:

```docker build -t infosec-deck .```

### Run and map port 8000 to your host

After the build process, start the container with this command:

```docker run -p 8000:8000 infosec-deck```

### Access your cards 

Now, you just need to point your browser to: http://localhost:8000
And print your files (in A3 / A4 format).
You can use different page sizes to print your cards.

### Stop your container

Once you are done copying your PDF files with the cards, you can
shut down the container with the following command:

```docker stop infosec-deck```

### Credits

Many thanks to Fujiro Nakombi for contributing the automatic card generator!

---

That is it folks, enjoy!

- LFRM, sign-off, 11-26-2025

