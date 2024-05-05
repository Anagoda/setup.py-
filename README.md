# setup.py-
##########################trying to create the folders and downloads the tools into the proper folder paths######
import os  # Import the os module at the beginning of the script
import subprocess

def create_folders():
    folders = ['tools', 'downloads']  # Fix the typo here: 'downloads'
    for folder in folders:
        if not os.path.exists(folder):
            os.makedirs(folder)
            print(f"Created folder: {folder}")

def download_tool(url, output_path):
    # Download tool from URL to output_path
    command = f"wget -O {output_path} {url}"
    subprocess.run(command, shell=True)
    print(f"Downloaded tool from {url}")

def main():
    create_folders()
   
    tools_to_download = {
        'eventvwr-bypassuac': 'https://raw.githubusercontent.com/k4sth4/UAC-bypass/main/eventvwr-bypassuac.c'
    }
   
    for tool_name, url in tools_to_download.items():
        output_path = f"downloads/{tool_name}.c"
        download_tool(url, output_path)

if __name__ == "__main__":
    main()
