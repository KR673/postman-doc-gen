# postman-doc-gen
Generate HTML API documentation from a postman collection. You can use this tool to auto-generate the documentation and host it alongside your API's as detailed <a href="https://medium.com/@karthiks3000/hosting-api-documentation-with-postman-springboot-e3ac141a6663">here.</a>

## Edit

* 修改依赖冲突问题
* 使用UTF-8读取和导出文件

## Usage

- Download the latest release of the executable from <a href="https://github.com/karthiks3000/postman-doc-gen/releases"> here</a>.
- Open a new terminal and call the executable with the parameter -h to see the help info
    ![Screenshot](./img/iTerm_1.png?raw=true "Title")

- To generate documentation using a postman collection, use the following command -
    ```
    ./postman_doc_gen [path/to/collection] -o [path/to/output/folder] 
    ```
    ![Screenshot](./img/iTerm_2.png?raw=true "Title")
   

- To apply environment values to the examples, use the following command - 
    ```
    ./postman_doc_gen [path/to/collection] -o [path/to/output/folder] -e [path/to/environment/json]
    ```
    ![Screenshot](./img/iTerm_3.png?raw=true "Title")
 
- To enable download links to the collection and environment files, use the following command - 
    ```
    ./postman_doc_gen [path/to/collection] -o [path/to/output/folder] -e [path/to/environment/json] -d true
    ```
    ![Screenshot](./img/iTerm_4.png?raw=true "Title")
 

- The output folder should now show the following -
    1. index.html - this is the html documentation generated from the collection
    2. css - this is the css folder consisting of the necessary css files
    3. js - this is the javascript folder consisting of the required js files
    4. collection json - if the download option was enabled, the collection json is also copied
    5. environment json - if the download option was enabled and an env file provided, the env json is also copied


## To build locally

- Clone the repository
- Download Python 3.7
- Create a virtual env (recommended but optional)
    ```
    python -m venv venv
    source ./venv/bin/activate
    ```
- pip install the dependencies from the requirements file 
    ```
    pip install -r requirements.txt
    ```
- run the code
    ```
    python postman_doc_gen.py [path/to/collection] -o [path/to/output/folder] 
    ```
- to create a new executable 
    ```
    pyinstaller -F postman_doc_gen.spec postman_doc_gen.py
    ```

## Sample HTML Documentation

A video of the sample html document generated using the collection and environment json files 
present in the example folder

![Sample HTML](sample_documentation.gif)

 
## Shout outs


The following tools/repos have been instrumental in building this tool

- <a href="https://palletsprojects.com/p/jinja/">Jinja</a>
- <a href="https://github.com/pyinstaller">PyInstaller</a>
- <a href="https://giphy.com/apps/giphycapture">Giphy Capture</a>
- <a href="https://pypi.org/project/bleach/">Bleach</a>
 
    
