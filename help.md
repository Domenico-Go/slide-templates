---
layout: default
title: 'Tutorial'
---

Queste istruzioni sono illustrate per esempi.

## Caricamento di nuovi file

1. caricare i file all'interno della directory `assets/slides`, divisi per
   tipo. Questa è la struttura della directory:

   ```
   assets
    └── slides
        ├── general
        │   ├── pptx
        │   │   ├── 0.pptx
        │   │   └── 1.pptx
        │   └── preview
        │       ├── 0.jpg
        │       └── 1.jpg
        └── organigram
            ├── pptx
            │   ├── 2.pptx
            │   └── 3.pptx
            └── preview
                ├── 2.jpg
                └── 3.jpg
   ```

   <div class="alert alert-info" role="alert">
     <code>general</code> è il tipo (categoria) di default, ed è anche il nome
     della directory che viene utilizzato.
   </div>

2. aggiornare l'oggetto `data` all'interno del file `_config.yml` in questo modo:

   ```yaml
   slide:
     data:
       - path: 'assets/slides/general/pptx/5.pptx'
         preview: 'assets/slides/general/preview/5.jpg'
         alt: 'Slide 5'
   ```

   - `path`: il precorso relativo del file powerpoint, partendo dalla root del
     progetto
   - `preview`: il file immagine che funge da anteprima, partendo dalla root
     del progetto
   - `alt`: testo alternativo al posto dell'immagine anteprima quando questa
     non è presente

   <div class="alert alert-info" role="alert">
     È sempre possibile aggiungere nuovi campi da integrare in futuro,
     se necessario.
   </div>

3. fare il commit Git

## Aggiunta nuovi tipi (categorie)

1. aggiornare l'oggetto `tags` all'interno del file `_config.yml` in questo
   modo:

   ```yaml
   slide:
     tags:
       - key: 'calendar'
         value: 'Calendari'
   ```

   - `key`: il nome della categoria (tipo) usato negli URL.
   - `value`: usato nei titoli delle pagine e visivamente nei link

   <div class="alert alert-warning" role="alert">
     Il nome della nuova directory deve corrispondere al valore di
     <code>key</code>.
   </div>


2. Creare un nuovo file all'interno di della directory `_tags`, chiamato
   `calendar.md` e aggiungere questo contenuto

   ```markdown
   ---
   layout: type
   title: 'Calendari'
   type: 'calendar'
   ---
   ```

   <div class="alert alert-warning" role="alert">
     Il nome della nuova directory deve corrispondere al valore di
     <code>type</code>.
   </div>


3. creare una nuova directory `calendar`, come illustrato in questo listing:

   ```
   assets
    └── slides
        ├── calendar
        │   ├── pptx
        │   └── preview
        ├── general
        │   ├── pptx
        │   │   ├── 0.pptx
        │   │   └── 1.pptx
        │   └── preview
        │       ├── 0.jpg
        │       └── 1.jpg
        └── organigram
            ├── pptx
            │   ├── 2.pptx
            │   └── 3.pptx
            └── preview
                ├── 2.jpg
                └── 3.jpg
   ```

4. aggiungere gli opportuni file come spiegato nella sezione precedente
5. fare il commit Git

<div class="alert alert-info" role="alert">
    Le categorie compaiono automaticamente nella barra di navigazione in alto
    con il valore di <code>value</code>.
</div>

## Aggiunta nuove pagine generiche

1. creare una file markdown nella root del progetto:

   ```markdown
   ---                                                                             
   layout: default
   title: 'Il mio titolo'
   ---
   # Titolo

   Contenuto...
   ```

2. linkare il file dalla pagina principale o da altri file esistenti
