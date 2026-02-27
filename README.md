import zipfilE
import os

def create_zip(source_dir, output_filename):
    with zipfile.ZipFile(output_filename, 'w', zipfile.ZIP_DEFLATED) as zipf:
        for root, dirs, files in os.walk(source_dir):
            for file in files:
                zipf.write(os.path.join(root, file), 
                           os.path.relpath(os.path.join(root, file), 
                           os.path.join(source_dir, '..')))
    print(f"Archive '{output_filename}' created successfully!")

if __name__ == "__main__":
    # Example: create_zip('my_folder', 'archive.zip')
    print("Zipper tool ready.")
