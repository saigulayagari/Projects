# RetailData Project
import nbformat

# Path to the uploaded notebook
notebook_path = '/mnt/data/RetailData.ipynb'
markdown_path = '/mnt/data/RetailData.md'

# Load the notebook
with open(notebook_path, 'r', encoding='utf-8') as file:
    notebook = nbformat.read(file, as_version=4)

# Convert notebook to Markdown
markdown_content = []
for cell in notebook.cells:
    if cell.cell_type == 'markdown':
        markdown_content.append(cell.source)
    elif cell.cell_type == 'code':
        markdown_content.append(f"```python\n{cell.source}\n```")

# Save the Markdown content to a file
with open(markdown_path, 'w', encoding='utf-8') as md_file:
    md_file.write("\n\n".join(markdown_content))

markdown_path

