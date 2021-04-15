# Unity-Technical-Guide

### Installation
This documentation is created by Sphinx and hosted on GitHub.
install sphinx and the markdown parser

1\. Install the Markdown parser *recommonmark*:

`pip install recommonmark`
<br>  
2\. Add *recommonmark* to the list of configured extensions:

`extensions = ['recommonmark']`

3\. Ensure that `.md` is in the list of source suffiex in `conf.py`:

```
source_suffix = {
    '.rst': 'restructuredtext',
    '.md': 'markdown',
}
```
----

###Image Directories
For each directory containing md source code, you must manually copy any "images" subdirectories to the corresponding build directories.  Sphinx does not automatically copy image subdirectories to the image build.
So, when built,

```
source_dir
  |--file1.md
  |--file2.md
  |--images_dir
        |--img1.png
        |--img2.png
        
```
will result in

```
source_dir
  |--file1.html
  |--file2.html
  
```
 
You must then manaully copy the `images_dir` directory to the build directory to create a proper tree structure:
 
```
source_dir
  |--file1.html
  |--file2.html
  |--images_dir
        |--img1.png
        |--img2.png
        
```

*Hint: do this one time after building the project.  Then, avoid deleteing the build output directory structure.*

----
### Local HTTP server

Use a local HTTP server to test your website.  Otherwise, your relative image paths won't work.  Worse, your brownser may not have access to files on your local filesystem.

Navigate to the directory where the files live and run a local python server:

`python3 -m http.server 1234`

View the page at `http://localhost:1234` in your browser.

