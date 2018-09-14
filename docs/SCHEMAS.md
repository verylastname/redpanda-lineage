# Red Panda Lineage
----

### Schemas 

#### /pandas

This is the main dataset for red pandas, and where the graph database is
generated from. Each panda will be stored in a single flat-text file, with
the panda's name as the filename (either English or Japanese).

Photo and Video URIs are intended to aid in identification of the animal.
We'll have a timeline strategy later to track arbitrary photos/videos/events
from a panda's life in a time-ordered way.

```
[panda]
_id: <monotonic-ascending-number, assign one if none given> 
birthday: <date string> 
birthplace: <zoo-names-translated-into-zoo-id> 
children: <list-of-names-translated-into-panda-ids, alert on name collisions> 
en.name: harumaki 
en.nicknames: <common nicknames>
en.othernames: <alternate spellings> 
gender: <m|f, or japanese male/female terms>
jp.name: <utf8-string>
jp.nicknames: <utf8-strings with comma separator>
jp.othernames: <utf8-strings with comma separator>
litter: <list-of-names-translated-into-panda-ids, alert on name collisions> 
photo.1: <image-uri usable in an HTML img tag>
photo.1.author: <name>
photo.1.link: <uri>
photo.2: <image-uri>
photo.2.author: <name>
photo.2.link: <uri>
species: <1 for Ailurus fulgens fulgens, 2 for Ailurus fulgens styani>
video.1: <video-uri>
video.1.author: <name>
video.1.link: <uri>
zoo: <zoo-names-translated-into-zoo-id> 
```
 
#### /zoos

To make it simpler to write panda files, the Zoo information is split off into
a separate folder and schema. Note that in the final compiled graph of zoos and
pandas, the zoos are distinguished from pandas by their negative ID numbers,
while pandas have positive ID numbers. Hackity hack!

```
[zoo]
_id: <monotonic-ascending-number, assign one if none given> 
en.address: <google maps address info from google.com> 
en.location: chiba prefecture, japan 
en.name: ichikawa zoological park and gardens 
jp.address: <google maps address info from google.jp>
jp.location: <utf8-string> 
jp.name: <utf8-string>
photo: <uri usable ins an HTML img tag>
photo.author: <name>
photo.link: <uri>
video: <video-uri>
video.author: <name>
video.link: <uri>
website: <zoo-homepage-uri> 
```
