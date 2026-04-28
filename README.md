# Free-image-generator-running-in-google-colab
This is a free (and uncensored) image generator using the latest version on Juggernaut SDXL and running on a free Google Colab GPU giving you roughly 2 hours of daily use for free but it could be more or less. I've made this guide easy for anyone to use without any tech experience, just follow the steps below. Also after the easy setup i'll make the techincal setup for developers through VSCode.

Notes:
1. Yes this is a true uncensored model and you can use it to make any kind of image. Including NSFW Content that is intended for 18+ year old users.
2. Images will be saved to your google drive under the 'Colab_outputs" folder so make sure you have space on your google drive.
3. Because this is google colab it's basically starting up a Linux computer running in their cloud server, they give you free CPU and free GPU. Just know that everytime you close out google colab you have to essentially start up their cloud computer everytime they dont retain all of the things you download to it. (just follow the setup steps below if this doesn't make sense.)
4. Google colab gives you a free T4 GPU with 15GB of VRAM to use for about 6 hours to start, after you use up all that it replenishes about 2 hours everyday roughly. Google doesn't exactly specify how much GPU time you get on the free tier, but that is from what i've noticed from testing roughly 2 hours daily. You can always pay for google Colab pro for $10USD per month and get access to much bigger GPU's and alot more time but this is entirely optional and not needed for this to work, you can just use the free tier, only understand you are limited to a couple hours perday.

There are two setup options, first the easy setup anyone can use and then the techy setup for coders.

Easy setup for the everyday person:

Step 1. Download the code file.
-
go here: https://github.com/TronCryptoLife/Free-image-generator-running-in-google-colab/blob/main/juggernaut_colab_civitai.ipynb
Then click on the 3 dots menu on the right side to download the code, save it wherever you can remember.

<img width="1912" height="778" alt="Capture1" src="https://github.com/user-attachments/assets/89f8abd0-9edb-4810-9533-e11e09caf532" />


Step 2. Google Colab setup
-
1. Go to google colab here: https://colab.research.google.com/

2. sign in with your google account if you haven't already in the top right corner.

3. At the very top left of the page click 'File' > then click 'upload Notebook' and find the file that you downloaded in Step 1. and the file should open up on google colab. Note that by doing this google saves this code file to your google drive under Colabs notebooks, so it's easier to start up next time.

4. Now at the top right corner click connect (see photo below)

<img width="1909" height="918" alt="image" src="https://github.com/user-attachments/assets/c94100c0-4832-4d7f-9460-c426650d75e7" />

5. Once it connects click the drop down (see photo below)

<img width="1910" height="424" alt="image" src="https://github.com/user-attachments/assets/befda57a-03dd-45e7-a6ff-be12fb7c5fca" />

6. now click 'Change runtime type' (See Photo below)

<img width="541" height="529" alt="image" src="https://github.com/user-attachments/assets/26d0c054-c9b3-4de6-8439-1a0c729f74e7" />

7. Then select 'T4 GPU' and make sure Python 3 is selected if it's not already, and click save. it may ask you if you are sure you want to continue after clicking 'T4 GPU' just click yes. Then wait for it to connect, after which you are all done with the setup process.

<img width="737" height="713" alt="image" src="https://github.com/user-attachments/assets/b8579fc2-3356-4934-b029-56df40dcbe8d" />


Step 3. Configurations
-
<img width="1845" height="748" alt="image" src="https://github.com/user-attachments/assets/88972e65-8842-4dbe-9caf-c2ba37a3bc68" />

Under 'Configuration' you will see all the setting such as:

  1. DEFAULT_PROMPT   this is where you type in your image prompt (the image you want to make).
     
  Example:
  
  DEFAULT_PROMPT = "A cat walking down the street"
  
  3. DEFAULT_NEGATIVE_PROMPT   this is anything you dont want in you image, but I suggest leaving it as it is right now which is blank>> DEFAULT_NEGATIVE_PROMPT = "" and later try it out if your getting things in your image you dont want, you can use this to get rid of them.
     
  Example:
  
  DEFAULT_NEGATIVE_PROMPT = "no people in the background."
  
  4. DEFAULT_WIDTH = 1024 and DEFAULT_HEIGHT = 1024    this is the size of your image 1024x1024 pixels which is the default, a 1080p square image. You can change this to a landscape horizontal image or vertical portrait image by changing these numbers, but i dont recommend going over 1024 on the largest side as you may run out of GPU power and crash the app (you'll know if you get the OUT_OF_MEMORY error).
     
  Example:
  
  For vertical portrait style images:
  
  2:3 ratio would be → 682 × 1024
  
  3:4 ratio would be → 768 × 1024
  
  4:5 ratio would be → 819 × 1024 (very popular for social media)
  
  9:16 ratio would be → 576 × 1024 (TikTok / Reels / Shorts)
  
  For landscape horizontal style images:
  
  3:2 → 1024 × 682
  
  4:3 → 1024 × 768
  
  5:4 → 1024 × 819
  
  16:9 → 1024 × 576 (YouTube / common video/TV standard)
  
  5. DEFAULT_CFG  this is for more experienced users, but it's basically how much you want the image to adhere to your prompt, more literal or more creative. it's recommended between 3 - 6     3 is slightly more realistic, 6 is less so. or keep it in the middle if you dont know which is 4.
     
  
  6. DEFAULT_NUM_IMAGES   this is how many images you want to generate
  
  Example:
  
  DEFAULT_NUM_IMAGES = 4

  7. ENABLE_HIRES and HIRES_UPSCALE When ENABLE_HIRES = True this will upscale your image and make it larger and higher quality using some AI magic. Now how much larger you want the image is where HIRES_UPSCALE comes into play. if you dont want a higher quality and larger image then set ENABLE_HIRES = False   Note that the T in True and the F in Flase needs to be capitalized.
  
  Example:
  
  DEFAULT_WIDTH = 1024
  
  DEFAULT_HEIGHT = 1024
  
  ENABLE_HIRES = True
  
  HIRES_UPSCALE = 1.5   this makes your image 1.5x bigger so the final image will be 1536x1536 a 1.5k image
  
  if HIRES_UPSCALE = 2  this makes your image 2x bigger so the final image will be 2048x2048 a 2k image
  
  if HIRES_UPSCALE = 4  this makes your image 4x bigger so the final image will be 4096x4096 a 4k image
  
  although you can go up to 4k image quality The upscaler works best around 1.5 - 2
  
Step 4. running the code and generating images
-
After you have all your configurations set up how you want you need to run the code cell by cell, one at time, by clicking the play button, and after you see the green check mark you can move on to the next cell. Note some cells will take a few minutes to run while other will be finished immediately, please be patient.

  0. Start off by clicking the play button in the configurations cell (see photo below)

  <img width="1816" height="522" alt="image" src="https://github.com/user-attachments/assets/898a2d4e-f035-4b7c-8fe4-4f0a17a340dc" />

  Once you see the green check mark, you move on to the next cell(see photo below)

  <img width="1829" height="527" alt="image" src="https://github.com/user-attachments/assets/8a49cdef-cdb0-4b68-9c63-92b498df0405" />

  1. Install the dependencies, click play, wait for it to finish, once you see the green check mark move on to the next cell (see photo below)

  <img width="1832" height="255" alt="image" src="https://github.com/user-attachments/assets/237b9f58-da52-4caf-ba48-b1afcb962859" />

  2. Mount Google Drive for Outputs, this part is setting up your google drive, so after you generate images it saves to your google drive. 
  
  Click the play button in this cell.

  Then click 'connect to google drive'. (See photo below)

  <img width="1814" height="509" alt="image" src="https://github.com/user-attachments/assets/321ca9e1-87ab-4791-a05e-c8f529d603f4" />

  Then click continue (See photo below)

  <img width="435" height="576" alt="image" src="https://github.com/user-attachments/assets/50610ed5-3db2-40ad-b0db-446c27ba0462" />

  Then click continue again (See photo below)

  <img width="482" height="712" alt="image" src="https://github.com/user-attachments/assets/9363c7fc-5b74-410a-b1c3-930dfa38f30f" />

  3. Download models files, click play, wait for it to finish (about 1 minute), once you see the green check mark move on to the next cell (see photo below)

  <img width="1802" height="659" alt="image" src="https://github.com/user-attachments/assets/7fdba0af-a288-4a89-90ed-08d0d7077267" />

  4. Load the SDXL Pipelines, click play, wait for it to finish (about 30 seconds), once you see the green check mark move on to the next cell (see photo below)

  <img width="1833" height="676" alt="image" src="https://github.com/user-attachments/assets/5cb556e3-a13d-4c33-88cb-a2458b1245bd" />

  5. Batch Generate and Save Images, You've finally made to the point of generating images! Click the play button and scroll down to the very bottom of the code  and watch your images generate one by one (see photo below). Just be patient as each image takes about a minute and a half to generate. Your images will be saved automatically to your google drive under the 'colab_outputs' folder. Enjoy! 
  
  BE SURE TO READ THE NEXT SECTION AS IT IS IMPORTANT FOR GENERATING IMAGES AGAIN!
-
  <img width="1873" height="797" alt="image" src="https://github.com/user-attachments/assets/f67093e8-157a-4fef-a27d-437cf62fe87c" />


Important notes on generating images again
-
1. If you want to generate images again with the same configurations settings, same image prompt, same everything, just click the play button again in the code on step 5. Batch Generate and Save Images. 
2. If you change anything in the configurations Cell for example: image size, or change your image prompt, then you need to click the play button again in the configurations cell after you change something. After that you can click the play button again in step 5. (Batch Generate and Save Images) to generate images with the new configuration settings.
3. Remember when your finished to disconnect your GPU to say your free GPU hours (see photo below). When you do this or close out of colab you will need to run all the cells over again or if something is not working and you want to start over this helps by disonnecting and reconnecting, and running all the cells over again.

<img width="570" height="591" alt="image" src="https://github.com/user-attachments/assets/f0e206e8-ccb9-4f4b-ad5d-312bfc050493" />

4. You can check your how much time you have left on your free GPU by click on the RAM Disk button in the top right corner of google colab (see photo below)

<img width="1913" height="816" alt="image" src="https://github.com/user-attachments/assets/f5287d0c-ebe5-45b2-a7b1-1a954b885494" />

5. Enjoy your free image generator😁, and follow me on twitter: https://x.com/That_Teck_Guy






  


  









