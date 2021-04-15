# Wanneer ik de code uitvoer in VSC werkt deze en krijg ik alle waarden die ik zou moeten krijgen.
# Echter, wanneer ik de code controleer met Wincpy check krijg ik een error dat hij het bestand /cache/throwaway niet kan vinden.
# Ik snap niet waarom hij op zoek is naar een bestand /cache/throwaway...

import os
import shutil
import zipfile

__winc_id__ = 'ae539110d03e49ea8738fd413ac44ba8'
__human_name__ = 'files'

def clean_cache():
    path = 'files/cache'
    if os.path.isdir(path):
        #delete folder
        shutil.rmtree(path) 
        #create folder
        os.mkdir(path)
        print('Folder already exists, everything in folder is deleted')
    else:
        os.mkdir(path)
        print('Folder created')

def cache_zip(zip_path, cache_path):
    with zipfile.ZipFile(zip_path, 'r') as zipObj:
        zipObj.extractall(cache_path)
        print('Zip file unpacked')

def cached_files():
    list_files = [os.path.join('files/cache', file) for file in os.listdir('files/cache')]
    return list_files

def find_password(list_file_paths):
    for file in list_file_paths:
        lines = open(file, 'r').readlines()
        for line in lines:
            if 'password' in line:
                password = line[len('password: '):]
                return password

if __name__ == '__main__':
    clean_cache()
    cache_zip('files/data.zip', 'files/cache')
    cached_files()
    find_password(cached_files())
