# RuBlog

RuBLog is a **really** simple site generator that supports Markdown, written in ruby.

This idea is to create (one more) site generator, but very simple: <200 lines of code, that you can totally understand in a few minutes (even if you don't know ruby). It's made for those who don't want too many options, or they are ready to implement their own.

As jekyll or pelican, the ``publish`` command will deploy the generated html on the orphan branch gh-pages to allow you to host your website on github.com!  

Currently there is only one template 'mes recettes', designed to share recipes.

## Get started

``vagrant up``  
``cd /vagrant``  
or  
``sudo apt-get installruby-dev``  
``sudo gem install redcarpet``

### Commands

**``./rublog newpage <sub-template> <file-name>``** (file-name: without extension)  
Create a new file in ``./pages`` from ``./templates/<template>/<sub-template>``.

**``./rublog build``**  
Generate all pages and index from ``./pages`` to ``./output``.

**``./rublog runserver``**  
Create a webserver listening on ``dev_port`` (from ``./settings.json``) and will watch for changes in ``./pages``. It will generate the new/updated file.rbg in this folder to output. (It will not regenerate index.html).

**``./rublog publish``**  
This command will run ``build`` and commit the content of ``./output`` folder to the orphan branch ``gh-pages``.

### Structure

```
├── output                       Output directory (generated and non commited)
├── pages                        Website pages directory
│   ├── example                  
│   │   └── example.jpg          
│   ├── example-1.rbg            Rublog page file
│   └── example-2.rbg            Rublog page file
├── rublog                       Executable
├── settings.json                Project settings
├── templates                    Templates directory
│   ├── tempalte-1               Template
│   │   ├── index.html.erb       Main template: required
│   │   ├── foo.html.erb         Subtemplate html (Rublog page is associated with a subtemplate)
│   │   ├── foo.rbg              Subtemplate meta structure
│   │   └── static               Lib, images ... (will be copied in output): required
│   ├── tempalte-2               
│   └── ...                      Other templates
└── Vagrantfile                  
```

## Contribute

### Create a new template

TODO

### TODO

- Finish to write the readme: explain subtemplates behavior and structure
- Support discuss ?
- Google Analytics ?