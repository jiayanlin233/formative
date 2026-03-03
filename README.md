```
import py7zr
import os

# Extract and rename Buddhism Stack Exchange

extract_dir = os.path.dirname("data/buddhism.stackexchange.com.7z")
with py7zr.SevenZipFile("data/buddhism.stackexchange.com.7z", mode='r') as z:
    z.extractall(extract_dir)

# Rename extracted files to add 'buddhism_' prefix
for filename in os.listdir(extract_dir):
    if filename.endswith('.xml') and not filename.startswith('buddhism_') and not filename.startswith('islam_') and not filename.startswith('christianity_'):
        old_path = os.path.join(extract_dir, filename)
        new_path = os.path.join(extract_dir, f'buddhism_{filename}')
        os.rename(old_path, new_path)

# Extract and rename Christianity Stack Exchange
with py7zr.SevenZipFile("data/christianity.stackexchange.com.7z", mode='r') as z:
    z.extractall(extract_dir)

# Rename extracted files to add 'christianity_' prefix
for filename in os.listdir(extract_dir):
    if filename.endswith('.xml') and not filename.startswith('christianity_') and not filename.startswith('islam_') and not filename.startswith('buddhism_'):
        old_path = os.path.join(extract_dir, filename)
        new_path = os.path.join(extract_dir, f'christianity_{filename}')
        os.rename(old_path, new_path)

# Extract and rename Islam Stack Exchange
with py7zr.SevenZipFile("data/islam.stackexchange.com.7z", mode='r') as z:
    z.extractall(extract_dir)

# Rename extracted files to add 'islam_' prefix
for filename in os.listdir(extract_dir):
    if filename.endswith('.xml') and not filename.startswith('islam_') and not filename.startswith('buddhism_') and not filename.startswith('christianity_'):
        old_path = os.path.join(extract_dir, filename)
        new_path = os.path.join(extract_dir, f'islam_{filename}')
        os.rename(old_path, new_path)

```
