=============================
Contributor Setup Guide
=============================

This guide provides step-by-step instructions for **cloning, editing, and submitting a pull request** 
to update the Sphinx documentation for the `16-LAB` project.

Repository URL: `https://github.com/hrubiak/16-LAB <https://github.com/hrubiak/16-LAB>`_

Introduction
============

The documentation for this project is **hosted on GitHub** and written using **reStructuredText (.rst)**,  
a lightweight markup language commonly used for technical documentation.

Contributors use **Visual Studio Code (VSCode)** to edit the ``.rst`` files and `Sphinx <https://www.sphinx-doc.org>`_, a Python-based  
documentation generator, to convert them into **HTML web pages**.

The contribution process involves the following steps:

1. **Cloning the repository**: Download the latest documentation source files from GitHub.
2. **Editing the documentation**: Modify the ``.rst`` files in VSCode.
3. **Building and previewing the documentation locally**: Use **Sphinx** to compile the files from ``.rst`` to HTML.
4. **Committing and pushing changes**: Save the updates and upload them back to GitHub.
5. **Creating a pull request (PR)**: Request for the changes to be merged into the main repository.

By following this guide, you will be able to **successfully contribute** to the documentation and ensure  
it remains up to date and well-structured.

Prerequisites: Software Installation
====================================

Before starting, install the following:

1. **Create a GitHub Account**  
   
   - GitHub is an online platform for version control and collaboration.
   - Sign up at `https://github.com <https://github.com>`_.

2. **Install GitHub Desktop**  
   
   - GitHub Desktop is a tool that simplifies Git operations using a graphical interface.
   - Download: `https://desktop.github.com/ <https://desktop.github.com/>`_
   - Install and **sign in** to GitHub.

3. **Install Visual Studio Code (VSCode)**  

   - VSCode is a code editor used to edit the documentation files.
   - Download: `https://code.visualstudio.com/ <https://code.visualstudio.com/>`_.

4. **Install Python 3.12 and Conda (Minimal Setup)**  
   
   - Sphinx, the tool used to build the documentation, requires Python.
   - **Recommended:** Install `Miniconda <https://docs.conda.io/en/latest/miniconda.html>`_.
   - **Alternatively:** Install `Anaconda <https://www.anaconda.com/download/>`_.
   - Restart your computer after installation.

Cloning the Repository
======================

A repository (repo) is a storage location for project files. Cloning a repo means **downloading** a copy 
to your local computer so you can edit files and contribute to the project.

1. Open **GitHub Desktop**.
2. Click **File → Clone repository…**.
3. In the **"Clone a Repository"** window, select the **"URL"** tab.
4. Copy and paste the repository URL:

   .. code-block:: text

      https://github.com/hrubiak/16-LAB

5. Choose a local directory (e.g., ``C:\Users\YourName\Documents\16-LAB``).
6. Click **Clone**.
7. Once cloning is complete, **open the repository in VSCode**:

   - In GitHub Desktop, click **Repository → Open in Visual Studio Code**.

Setting Up the Python Environment
=================================

A Python environment is a self-contained workspace where dependencies like Sphinx can be installed 
without affecting the system Python installation. Conda helps manage these environments efficiently.

1. **Open the VSCode terminal**:
   - Windows/Linux: ``Ctrl + ~``
   - Mac: ``Cmd + ~``

2. **Create a new Conda environment**:

   .. code-block:: bash

      conda create -n sphinx-docs python=3.12 -y

3. **Activate the environment**:

   .. code-block:: bash

      conda activate sphinx-docs

4. **Install Sphinx and dependencies**:

   .. code-block:: bash

      pip install sphinx sphinx_rtd_theme

5. **Verify installation**:

   .. code-block:: bash

      sphinx-build --version

Editing the Documentation
=========================

Editing the documentation means modifying the ``.rst`` (reStructuredText) files, 
which contain the text and formatting used to generate the HTML documentation.

**1. Open the Project Folder in VSCode**

There are two ways to open the repository in **VSCode**:

**Option 1: Open from GitHub Desktop (Recommended)**

1. In **GitHub Desktop**, go to **Repository → Open in Visual Studio Code**.

**Option 2: Open Manually from File Explorer**

1. Open **File Explorer (Windows)** or **Finder (Mac)**.
2. Navigate to the cloned repository folder:
   
   - **Windows:** ``C:\Users\YourName\Documents\16-LAB\``
   - **Mac/Linux:** ``/Users/YourName/Documents/16-LAB/``
  
3. Open the ``docs/`` folder where the documentation files are located.

**2. Locate and Open the reStructuredText (.rst) Files**

1. Inside the ``docs/`` folder, you will find the main documentation files.
2. The most important file is:
   
   - ``index.rst`` → This is the main documentation entry point.
  
3. To edit, **double-click** an ``.rst`` file in VSCode to open it.

**3. Edit the Documentation**

1. Make the necessary changes in the ``.rst`` files.
2. Follow the reStructuredText syntax for formatting.
3. Save the file after editing (``Ctrl + S`` or ``Cmd + S`` on macOS).

Previewing the Documentation Locally
====================================

After making changes, it's important to **build** the documentation and preview how it looks.  
This allows contributors to verify formatting and content before submitting changes.

1. **Open the VSCode terminal**:
   
   - If the terminal is not open by default:
     - Windows/Linux: Press ``Ctrl + ~``.
     - macOS: Press ``Cmd + ~``.
     - OR go to **View → Terminal** in the top menu.

2. **Activate the Conda environment**:
   
   - Ensure that you are using the correct Conda environment before running any Sphinx commands.
   - If the environment is not already activated, run:

     .. code-block:: bash

        conda activate sphinx-docs

     If you see an error like ``Command 'conda' not found``, ensure Miniconda/Anaconda is installed correctly and restart VSCode.

3. **Navigate to the `docs/` folder**:
   
   - If you are not already inside the documentation directory, run:

     .. code-block:: bash

        cd docs

4. **Run the Sphinx build command**:
   
   - On macOS/Linux:

     .. code-block:: bash

        make html

   - On Windows:

     .. code-block:: powershell

        .\make.bat html

5. **Open the generated documentation**:
   
   - After the build completes, open the following file in your web browser:

     .. code-block:: text

        _build/html/index.html

6. **Review your changes**:
   
   - Navigate through the generated HTML files to ensure everything appears as expected.
   - If something looks incorrect, go back to your ``.rst`` files, edit them, save the changes, and re-run ``make html``.

Committing and Pushing Changes
==============================

In Git, **committing** means saving your changes locally, while **pushing** means uploading 
them to GitHub. This ensures that changes are tracked and shared with the project.

1. Open **GitHub Desktop**.
2. The modified files will appear in the **Changes** panel.
3. Write a commit message (e.g., ``Updated documentation for feature X``).
4. Click **Commit to main**.
5. Click **Push origin** (this uploads your changes to GitHub).

Creating a Pull Request (PR)
============================

A **pull request (PR)** is a request to merge your changes into the main repository.  
This allows project maintainers to review your edits before approving them.

1. **Open a pull request**:
   
   - Click **"Create Pull Request"** in GitHub Desktop.
   - This opens GitHub in a browser.
   - Click **"Create Pull Request"** and add a short description.

2. Once the PR is reviewed and approved, it will be merged.

Keeping the Repository Updated
==============================

Before making new changes, it's important to **synchronize** with the latest version of the repository.  
Pulling updates ensures that you are working with the latest files and avoid conflicts.

1. Open **GitHub Desktop**.
2. Click **Fetch Origin → Pull changes**.
3. Then proceed with editing.

Troubleshooting
===============

VSCode Doesn't Detect Conda Environment
----------------------------------------
- Open **Command Palette** (``Ctrl + Shift + P`` on Windows/Linux, ``Cmd + Shift + P`` on macOS).
- Type **"Python: Select Interpreter"**.
- Choose **Conda (sphinx-docs)**.

Sphinx Build Errors?
--------------------
- Ensure dependencies are installed:

  .. code-block:: bash

     pip install -r requirements.txt

