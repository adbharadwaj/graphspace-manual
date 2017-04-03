[![Documentation Status](https://readthedocs.org/projects/graphspace/badge/?version=latest)](http://manual.graphspace.org/en/latest/?badge=latest)

# graphspace-manual

## GraphSpace User Manual


This project contains the complete user manual for GraphSpace. While the manual sources are maintained in GitHub, the document is actually assembled, formatted, and staged by the ReadTheDocs.org site. ReadTheDocs presents online and PDF versions, and we will use both.

## Editing the Manual

To edit manual text, you must first check out this repository and use a text editor on your workstation. (You can use GitHub's native Markdown editor, too, for small edits.)

All document components are in the "docs" directory. Each chapter is contained in its own file, and the files are assembled as a complete document by naming them in the "docs/index.rst" file.

Images are stored in the "docs/_static/images" directory, organized into subdirectories by chapter. For high quality images, vector graphic files produce best results (e.g., .png).

Simple tables can be represented in Markdown, but high quality formatting requires direct HTML coding. By convention, we encode tables as HTML-tagged data, but do not specify visual attributes and layout inline. Instead, we use preset table styles contained in "docs/_static/css" for formatting -- we do not use Markdown's table formatting. Note that additional CSS files can be added, but must be accounted for in "_templates/layout.html" and "conf.py". Note that while the tables appear in the HTML document, they do not appear in the PDF version -- we're working on this.

Note that the GitHub file viewer displays Markdown files reasonably well. However, it only approximates the look of tables created via HTML. For an accurate view of a table, you must look at a document rendered by ReadTheDocs.

## Rebuilding the Manual

The "latest" manual is automatically rebuilt by ReadTheDocs when the GitHub repository is updated. (This is courtesy of a WebHook that I installed per http://docs.readthedocs.org/en/latest/webhooks.html). To rebuild other versions, you'll need to be in the ReadTheDocs web site on the Build page -- there should be little/no reason to ever do this.

The rebuild can be observed by logging into the ReadTheDocs account (see me for credentials) and choosing the "graphspace" project. To see the build log, click on the grey Builds button. You can watch the progress of the build by manually refreshing your browser window until the build status shows either Passed or Failed - a build can take anywhere from 3 minutes to 10 minutes, depending on how busy the build server is. When the build is complete, if the status shows Passed, you can view the build result by clicking on the green View Docs button.

The document will also be available via http://manual.graphspace.org/en/latest.

