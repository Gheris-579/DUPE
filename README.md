 ![MEDA WITH -GHERIS-](https://github.com/Gheris-579/RANSOMEWARE/assets/103877241/8680eb64-f902-496d-8d48-1b4239340c40) ![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)    


<h1>Description</h1>
<p><em>This software is the ultimate solution for cleaning up your photo library!
Imagine being able to find all the exactly identical photos in a specific folder on your computer. You'll no longer need to manually scroll through hundreds of photos, comparing pixel by pixel to see which ones are the copies.
How it works easily and effectively:
Select the Folder: With just a few clicks, choose the folder on your computer where you know your photos are located (for example, the "Pictures" folder, "Downloads," or a backup folder). Find Exact Copies: The program will meticulously analyze all the photos within the selected folder. Using intelligent technology, it will compare the content of each image to identify those that are 100% identical. View Duplicates: Once the analysis is complete, you will be presented with a clear list of all the duplicate photos found. You can easily see which ones are copies of the same image. Move to Trash (Safely): At this point, you can select the copies you want to delete. Instead of permanently deleting them, the program will move them to your computer's trash or recycle bin. This gives you the peace of mind of being able to easily recover them if you change your mind or make a mistake. The benefits of using this program:
Recover Precious Space: Eliminate unnecessary copies and free up space on your disks or memory. Organize Your Gallery: Make your photo library cleaner and easier to manage. Save Time: Forget the tedious manual search for duplicate photos. Safety: Duplicate photos are moved to the trash, not permanently deleted, offering you extra protection. In short, this program is your ally in tidying up your photos, eliminating annoying identical copies in a simple, fast, and safe way!
</em></p>


  <hr/>
  <h1>Operating System</h1>
  <ul>
    <li>Windows 10 , 11 </li>
    <li>MAC</li>
    <li>LINUX</li>
  </ul>


<h1>The explanation of: hash</h1>
<p>

**dict: A dictionary where keys are hashes of images and values are lists of paths to files with the same hash.**

This is explaining the type of data returned by the `find_duplicate_images(directory)` function. Let's do it step by step:

**dict:** This is short for "dictionary" in Python. A dictionary is a data container that holds collections of things called "key-value" pairs. Imagine you had a real paper dictionary: you know a word (the key) and its meaning (the value). In Python dictionaries, the keys may only occur once in the dictionary.

**An image hash key dictionary:** This subsection explains what the "word" (key) in our Python dictionary is. The key in this case is the **image hash**. Notice that the hash (in this case, an MD5 hash) is a unique string that characterizes what's inside an image. If two images are identical byte for byte, they will have the same MD5 hash.

**and the values are lists of paths to files with that hash:** This is what gets written as the "definition" (value) for each "word" (key) in our dictionary. Each hash has a **list** as its value. This list has as its elements the **full paths** (the actual location on your computer) of all image files that employed that particular hash.

**That is to say:**

The `find_duplicate_images` function scans all the image files in your directory. For each photo, it computes its unique "identification code" (the hash). Then, it constructs a sort of "index" (the dictionary).

If it detects more than one with the same "identification code" (with the same hash), then they are duplicates.
In the dictionary, this "identification code" (the hash) is utilized as the "word" (the key).
The "definition" (the value) for this "word" is a list containing the address (the file path) of each and every image that has that specific "identification code."

**Example:**

For example, let's say you have three image files in your directory: `foto1.jpg`, `copia_foto1.jpg`, and `vacanza.png`.

`foto1.jpg` and `copia_foto1.jpg` are completely identical to the same picture and generate the hash: `a1b2c3d4e5f6.`
`vacanza.png` is another photo and generates the hash: `9876543210fedc.`
The `find_duplicate_images` method would return you a dictionary similar to the following:

```python
{'a1b2c3d4e5f6.': ['/path/to/your/directory/foto1.jpg', '/path/to/your/directory/copia_foto1.jpg'],
 '9876543210fedc.': ['/path/to/your/directory/vacanza.png']}
```

We can notice that:

The hash `'a1b2c3d4e5f6.'` is a key of the entry, and its value is a list with `foto1.jpg` and `copia_foto1.jpg` contained inside it, so these two photos are copies (they employed the same hash).
The hash `'9876543210fedc.'` is another key, and its value is a list with only the path to `vacanza.png` by itself, to mark that there are no other files with the same contents.

The `send_duplicates_to_trash` function then uses this dictionary to find the sets of duplicate files (the lists with more than one path) and ask the user if he/she wants to send them to the trash.

</p>
  
# ScreenShot 🖵

![image](https://github.com/user-attachments/assets/49c4e4b3-e086-4049-ab88-e86299239c44)

![image](https://github.com/user-attachments/assets/3d09eb07-0438-4ffc-8aae-8df5ebbab834)


![Immagine 2025-04-22 233621](https://github.com/user-attachments/assets/fe9a46c4-69bb-4610-b3b9-bf178c088e39)


![Immagine 2025-04-22 233815](https://github.com/user-attachments/assets/72d99dc3-bdbe-4734-a0f5-21bc2f93c754)


# Diagram

![diagram-export-24-04-2025-00_18_22](https://github.com/user-attachments/assets/f0ff8d67-62fa-43b8-8b6c-b88eedacbecf)
