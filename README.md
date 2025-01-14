# Datasette Lite

Datasette running in your browser using WebAssembly and [Pyodide](https://pyodide.org)

Live tool: https://lite.datasette.io/

More about this project: [Datasette Lite: a server-side Python web application running in a browser](https://simonwillison.net/2022/May/4/datasette-lite/)

## How this works

Datasette Lite runs the full server-side Datasette Python web application directly in your browser, using the [Pyodide](https://pyodide.org) build of Python compiled to WebAssembly.

When you launch the demo, your browser will download and start executing a full Python interpreter, install the [datasette](https://pypi.org/project/datasette/) package (and its dependencies), download one or more SQLite database files and start the application running in a browser window (actually a [Web Worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) attached to that window).

## Opening other databases

You can use this tool to open any SQLite database file that is hosted online and served with a `access-control-allow-origin: *` CORS header. Files served by GitHub Pages automatically include this header, as do database files that have been published online [using datasette publish](https://docs.datasette.io/en/stable/publish.html).

Copy the URL to the `.db` file and either paste it into the "Load database by URL" prompt, or construct a URL like the following:

    https://lite.datasette.io/?url=https://latest.datasette.io/fixtures.db

Some examples to try out:

- [Global Power Plants](https://lite.datasette.io/?url=https://global-power-plants.datasettes.com/global-power-plants.db) - 33,000 power plants around the world
- [United States members of congress](https://lite.datasette.io/?url=https://congress-legislators.datasettes.com/legislators.db) - the example database from the [Learn SQL with Datasette](https://datasette.io/tutorials/learn-sql) tutorial
