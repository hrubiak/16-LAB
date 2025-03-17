=============================
Contributor Setup Guide
=============================

This guide provides step-by-step instructions for **cloning, editing, and submitting a pull request** 
to update the Sphinx documentation for the `16-LAB` project.

Repository URL: `https://github.com/hrubiak/16-LAB <https://github.com/hrubiak/16-LAB>`_

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

Creating a New Branch
=====================

A **branch** is an independent line of development that allows contributors to make changes without affecting the main project.  
Before making any edits, create a new branch.

1. Open **GitHub Desktop**.
2. Click **Branch → Create a new branch**.
3. Name it something descriptive (e.g., ``docs-update``).
4. Click **Create branch**.
5. The new branch is now active.

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

1. Open **VSCode**.
2. Locate and open ``source/index.rst`` (or any ``.rst`` file).
3. Make changes and save the file.

Previewing the Documentation Locally
====================================

After making changes, it's important to **build** the documentation and preview how it looks.  
This allows contributors to verify formatting and content before submitting changes.

1. Open the **VSCode terminal**.
2. Navigate to the ``docs/`` folder:

   .. code-block:: bash

      cd docs

3. Run the Sphinx build command:

   .. code-block:: bash

      make html  # macOS/Linux

   .. code-block:: powershell

      .\make.bat html  # Windows

4. Open the generated file:

   .. code-block:: text

      _build/html/index.html

5. Review your changes in a browser.

Committing and Pushing Changes
==============================

In Git, **committing** means saving your changes locally, while **pushing** means uploading 
them to GitHub. This ensures that changes are tracked and shared with the project.

1. Open **GitHub Desktop**.
2. The modified files will appear in the **Changes** panel.
3. Write a commit message (e.g., ``Updated documentation for feature X``).
4. Click **Commit to [your branch name]**.
5. Click **Push origin** (this uploads your changes to GitHub).

Creating a Pull Request (PR)
============================

A **pull request (PR)** is a request to merge your changes into the main repository.  
This allows project maintainers to review your edits before approving them.

1. **Open a pull request**:
   - In the section "Create a Pull Request from your current branch" in GitHub Desktop, click **"Create Pull Request"**. 
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

Common GitHub Desktop Issues
----------------------------
- **Cloned the wrong branch?** → Switch branches in **GitHub Desktop**.
- **Accidentally committed to main?** → Create a new branch and reset main.

Final Notes
===========

This guide provides a **consistent workflow** for contributors to edit and submit documentation updates.  
For any issues, reach out via GitHub **Issues**.

Happy documenting! 🚀