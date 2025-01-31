# AI-10X Custom Vison demo

Goal is to understand how to programmatically create, train and publish Custom Vison project. It can be used as demo during training or preparation to present Custom Vision as ready to use example. We use [Python azure-cognitiveservices-vision-customvision](https://pypi.org/project/azure-cognitiveservices-vision-customvision/).

# Preparation

- Login to [Azure Cloud Shell](https://shell.azure.com).
- Clone this repository.
  - ```git clone https://github.com/bechynsky/ai100demos.git```
- Install Python libraries.
  - ```pip install azure-cognitiveservices-vision-customvision```
- Goto ```ai100custom_vision_demo``` folder.
- Run ```code .``` to open code editor to see code.
- Run [new_cognitiveservices.ps1](new_cognitiveservices.ps1).
  - All information like endpoint and service key is stored in Environment variables. 
  - Check environment variables we create ```printenv | grep CV_``` or ```Get-ChildItem env:* | Where-Object {$_.Name -like 'CV_*'}```.
  - It is not persistent and information is lost after Azure Cloud Shell restarts.
  - Copy output of script for future reference.
- Download sample images
  - ```sh ./download_images.sh```
- Run ```code .``` to open code editor to see code.

# Demo recommendation

After each step go to [https://www.customvision.ai/](https://www.customvision.ai/) and show changes in portal.

# Step 0 [cv_00_credentials.py](cv_00_credentials.py)

This file only reads requiried environment variables.

# Step 1 [cv_01_upload.py](cv_01_upload.py)

- Creates Custom Vison project.
- Reads directory list and create tag for each directory.
- Upload images with tag based on directory name.

# Step 2 [cv_02_train.py](cv_02_train.py)

- Train model. It usually takes 7-10 minutes. You will see output like this:

```
python ./cv_02_train.py 
Project Garden Birds loaded.
Training...
Training status: Training
...
Training status: Training
Training status: Completed
```

# Step 3 [cv_03_publish.py](cv_03_publish.py)

- Publish model.

# Step 4 [cv_04_test.py](cv_04_test.py)

- Test model using online images. You can change images in code. Outup example:

```
python ./cv_04_test.py

Project: Garden Birds
Iteration: Iteration 1
https://upload.wikimedia.org/wikipedia/commons/5/57/WoodPecker_Pivert_in_59650_%282%29.JPG
        picus_viridis: 99.37%
        parus_major: 4.37%
        pica_pica: 1.11%
        passer_domesticus: 0.32%

https://upload.wikimedia.org/wikipedia/commons/0/01/Un_passerotto_su_un_olivo_nella_primavera_2020_Uccellino.jpg
        passer_domesticus: 96.61%
        parus_major: 4.07%
        pica_pica: 2.37%
        picus_viridis: 1.30%

https://upload.wikimedia.org/wikipedia/commons/b/b2/Pica_1450098_Nevit.jpg
        pica_pica: 99.55%
        parus_major: 3.26%
        picus_viridis: 2.44%
        passer_domesticus: 1.45%

https://upload.wikimedia.org/wikipedia/commons/4/43/Kohlmeise_%2823%29_%2834632808830%29.jpg
        parus_major: 96.34%
        picus_viridis: 5.78%
        pica_pica: 1.33%
        passer_domesticus: 0.46%

https://upload.wikimedia.org/wikipedia/commons/4/42/Merel_%28Turdus_merula%29.jpg
        passer_domesticus: 74.27%
        pica_pica: 13.87%
        picus_viridis: 7.53%
        parus_major: 2.71%
```

# Credits

List of pictures and credits used for Custom Vison training. We use some birds photos from [Wikimedia Commons](https://commons.wikimedia.org/wiki/Main_Page).

## [Parus Major](https://commons.wikimedia.org/wiki/Category:Parus_major)

- [https://commons.wikimedia.org/wiki/File:Birds_in_the_garden_(15951425228).jpg](https://commons.wikimedia.org/wiki/File:Birds_in_the_garden_(15951425228).jpg)
- [https://commons.wikimedia.org/wiki/File:CAN_0353.jpg](https://commons.wikimedia.org/wiki/File:CAN_0353.jpg)
- [https://commons.wikimedia.org/wiki/File:Carbonero_Ii_(92641587).jpeg](https://commons.wikimedia.org/wiki/File:Carbonero_Ii_(92641587).jpeg)
- [https://commons.wikimedia.org/wiki/File:Cinciallegra_(Parus_major).jpg](https://commons.wikimedia.org/wiki/File:Cinciallegra_(Parus_major).jpg)
- [https://commons.wikimedia.org/wiki/File:Cold_feet_(31589329683).jpg](https://commons.wikimedia.org/wiki/File:Cold_feet_(31589329683).jpg)
- [https://commons.wikimedia.org/wiki/File:Eating_sunflower_seeds_(26103312813).jpg](https://commons.wikimedia.org/wiki/File:Eating_sunflower_seeds_(26103312813).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_Tit._Parus_major_-_Flickr_-_gailhampshire.jpg](https://commons.wikimedia.org/wiki/File:Great_Tit._Parus_major_-_Flickr_-_gailhampshire.jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(22386339245).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(22386339245).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(24205522987).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(24205522987).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(24433945428).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(24433945428).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(31739061575).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(31739061575).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(37297112312).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(37297112312).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(37591576475).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(37591576475).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(40131839242).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(40131839242).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(42846328752).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(42846328752).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_(parus_major)_(21029472382).jpg](https://commons.wikimedia.org/wiki/File:Great_tit_(parus_major)_(21029472382).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_Tit_-_9-23-14_-_Bois_de_Vincennes,_Paris,_FR_(20141872222).jpg](https://commons.wikimedia.org/wiki/File:Great_Tit_-_9-23-14_-_Bois_de_Vincennes,_Paris,_FR_(20141872222).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_Tit_-_Castelletto_Merli_-_Italy_FJ0A2302_(43958521434).jpg](https://commons.wikimedia.org/wiki/File:Great_Tit_-_Castelletto_Merli_-_Italy_FJ0A2302_(43958521434).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_tit_2.jpg](https://commons.wikimedia.org/wiki/File:Great_tit_2.jpg)
- [https://commons.wikimedia.org/wiki/File:Great_Tit_2c_(6653986509).jpg](https://commons.wikimedia.org/wiki/File:Great_Tit_2c_(6653986509).jpg)
- [https://commons.wikimedia.org/wiki/File:Great_Tit_on_Tray_(10612305334).jpg](https://commons.wikimedia.org/wiki/File:Great_Tit_on_Tray_(10612305334).jpg)
- [https://commons.wikimedia.org/wiki/File:IMG%D1%80%D1%80%D0%BE%D1%82.jpg](https://commons.wikimedia.org/wiki/File:IMG%D1%80%D1%80%D0%BE%D1%82.jpg)
- [https://commons.wikimedia.org/wiki/File:Kohlmeise_(18)_(35020250075).jpg](https://commons.wikimedia.org/wiki/File:Kohlmeise_(18)_(35020250075).jpg)
- [https://commons.wikimedia.org/wiki/File:Kohlmeise_(20)_(35020241235).jpg](https://commons.wikimedia.org/wiki/File:Kohlmeise_(20)_(35020241235).jpg)
- [https://commons.wikimedia.org/wiki/File:Kohlmeise_(24)_(34856500362).jpg](https://commons.wikimedia.org/wiki/File:Kohlmeise_(24)_(34856500362).jpg)


## [Pica Pica](https://commons.wikimedia.org/wiki/Category:Pica_pica)

- [https://commons.wikimedia.org/wiki/File:2010-06-03_(25)_Elster,_Magpie,_Pica_pica.JPG](https://commons.wikimedia.org/wiki/File:2010-06-03_(25)_Elster,_Magpie,_Pica_pica.JPG)
- [https://commons.wikimedia.org/wiki/File:2013.03.24.-1-Mannheim_Vogelstang-Elster.jpg](https://commons.wikimedia.org/wiki/File:2013.03.24.-1-Mannheim_Vogelstang-Elster.jpg)
- [https://commons.wikimedia.org/wiki/File:2017.03.25.-25-Mannheim_Vogelstang--Elster.jpg](https://commons.wikimedia.org/wiki/File:2017.03.25.-25-Mannheim_Vogelstang--Elster.jpg)
- [https://commons.wikimedia.org/wiki/File:2017.03.25.-26-Mannheim_Vogelstang--Elster.jpg](https://commons.wikimedia.org/wiki/File:2017.03.25.-26-Mannheim_Vogelstang--Elster.jpg)
- [https://commons.wikimedia.org/wiki/File:2017.03.25.-27-Mannheim_Vogelstang--Elster.jpg](https://commons.wikimedia.org/wiki/File:2017.03.25.-27-Mannheim_Vogelstang--Elster.jpg)
- [https://commons.wikimedia.org/wiki/File:A%C4%9Fa%C3%A7ta_bir_karga.JPG](https://commons.wikimedia.org/wiki/File:A%C4%9Fa%C3%A7ta_bir_karga.JPG)
- [https://commons.wikimedia.org/wiki/File:Birds_of_Sweden_2016_35.jpg](https://commons.wikimedia.org/wiki/File:Birds_of_Sweden_2016_35.jpg)
- [https://commons.wikimedia.org/wiki/File:Common_Magpie_(Pica_pica).JPG](https://commons.wikimedia.org/wiki/File:Common_Magpie_(Pica_pica).JPG)
- [https://commons.wikimedia.org/wiki/File:Common_Magpie_Lodz(Poland)(js)01.jpg](https://commons.wikimedia.org/wiki/File:Common_Magpie_Lodz(Poland)(js)01.jpg)
- [https://commons.wikimedia.org/wiki/File:Ekster-1_(28031980363).jpg](https://commons.wikimedia.org/wiki/File:Ekster-1_(28031980363).jpg)
- [https://commons.wikimedia.org/wiki/File:Commonmagpiewalking.jpg](https://commons.wikimedia.org/wiki/File:Commonmagpiewalking.jpg)
- [https://commons.wikimedia.org/wiki/File:Elster2.jpg](https://commons.wikimedia.org/wiki/File:Elster2.jpg)
- [https://commons.wikimedia.org/wiki/File:Eurasian_magpie_-2020.jpg](https://commons.wikimedia.org/wiki/File:Eurasian_magpie_-2020.jpg)
- [https://commons.wikimedia.org/wiki/File:Eurasian_Magpie._Pica_pica_(32275730438).jpg](https://commons.wikimedia.org/wiki/File:Eurasian_Magpie._Pica_pica_(32275730438).jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie_%27%27Pica_pica%27%27.jpg](https://commons.wikimedia.org/wiki/File:Magpie_%27%27Pica_pica%27%27.jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie_(15563869424).jpg](https://commons.wikimedia.org/wiki/File:Magpie_(15563869424).jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie_(19525789631).jpg](https://commons.wikimedia.org/wiki/File:Magpie_(19525789631).jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie_(Pica_pica)_(5561760354).jpg](https://commons.wikimedia.org/wiki/File:Magpie_(Pica_pica)_(5561760354).jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie_(Pica_pica)_(8).jpg](https://commons.wikimedia.org/wiki/File:Magpie_(Pica_pica)_(8).jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie_001.JPG](https://commons.wikimedia.org/wiki/File:Magpie_001.JPG)
- [https://commons.wikimedia.org/wiki/File:Magpie_arp.jpg](https://commons.wikimedia.org/wiki/File:Magpie_arp.jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie_at_Smethwick_Galton_Bridge_railway_station_(low_level)_-_DSCF1015.JPG](https://commons.wikimedia.org/wiki/File:Magpie_at_Smethwick_Galton_Bridge_railway_station_(low_level)_-_DSCF1015.JPG)
- [https://commons.wikimedia.org/wiki/File:Magpie._Pica_pica_-_Flickr_-_gailhampshire_(1).jpg](https://commons.wikimedia.org/wiki/File:Magpie._Pica_pica_-_Flickr_-_gailhampshire_(1).jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie.arp.750pix.jpg](https://commons.wikimedia.org/wiki/File:Magpie.arp.750pix.jpg)
- [https://commons.wikimedia.org/wiki/File:Magpie2_(3613486671).jpg](https://commons.wikimedia.org/wiki/File:Magpie2_(3613486671).jpg)
- [https://commons.wikimedia.org/wiki/File:Skata_Common_Magpie_(14472419314).jpg](https://commons.wikimedia.org/wiki/File:Skata_Common_Magpie_(14472419314).jpg)

## [Passer domesticus](https://commons.wikimedia.org/wiki/Category:Passer_domesticus)

- [https://commons.wikimedia.org/wiki/File:1_House_Sparrow_01.jpg](https://commons.wikimedia.org/wiki/File:1_House_Sparrow_01.jpg)
- [https://commons.wikimedia.org/wiki/File:1_House_Sparrow_03.jpg](https://commons.wikimedia.org/wiki/File:1_House_Sparrow_03.jpg)
- [https://commons.wikimedia.org/wiki/File:2017.07.15.-02-Wochowsee-Storkow_(Mark)--Haussperling-Maennchen.jpg](https://commons.wikimedia.org/wiki/File:2017.07.15.-02-Wochowsee-Storkow_(Mark)--Haussperling-Maennchen.jpg)
- [https://commons.wikimedia.org/wiki/File:Aire_du_Creux_Moreau_(juin_2020)_un_petit_oiseau_pas_farouche.jpg](https://commons.wikimedia.org/wiki/File:Aire_du_Creux_Moreau_(juin_2020)_un_petit_oiseau_pas_farouche.jpg)
- [https://commons.wikimedia.org/wiki/File:Birds_of_Nepal_42.jpg](https://commons.wikimedia.org/wiki/File:Birds_of_Nepal_42.jpg)
- [https://commons.wikimedia.org/wiki/File:Cute_House_Sparrow.jpg](https://commons.wikimedia.org/wiki/File:Cute_House_Sparrow.jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(13896236477).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(13896236477).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(14286968789).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(14286968789).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(19728335804).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(19728335804).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(19730184443).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(19730184443).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20163110298).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20163110298).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20163112498).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20163112498).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20324744496).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20324744496).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20164483449).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20164483449).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20351007225).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20351007225).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20342624382).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20342624382).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20342644722).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%A5sparv_House_Sparrow_(20342644722).jpg)
- [https://commons.wikimedia.org/wiki/File:House_Sparrow_(Passer_domesticus)_(48088916678).jpg](https://commons.wikimedia.org/wiki/File:House_Sparrow_(Passer_domesticus)_(48088916678).jpg)
- [https://commons.wikimedia.org/wiki/File:House_Sparrow_(Passer_domesticus)_(48332460202).jpg](https://commons.wikimedia.org/wiki/File:House_Sparrow_(Passer_domesticus)_(48332460202).jpg)
- [https://commons.wikimedia.org/wiki/File:House_sparrow_003.jpg](https://commons.wikimedia.org/wiki/File:House_sparrow_003.jpg)
- [https://commons.wikimedia.org/wiki/File:House_sparrow_(Passer_domesticus)_SRI_08.jpg](https://commons.wikimedia.org/wiki/File:House_sparrow_(Passer_domesticus)_SRI_08.jpg)
- [https://commons.wikimedia.org/wiki/File:House_Sparrow_female_erythristic_best_DSCN8903_(2).jpg](https://commons.wikimedia.org/wiki/File:House_Sparrow_female_erythristic_best_DSCN8903_(2).jpg)
- [https://commons.wikimedia.org/wiki/File:House_Sparrow_female_erythristic_Mumbai_22_Aug_2020_DSCN8847_(12).jpg](https://commons.wikimedia.org/wiki/File:House_Sparrow_female_erythristic_Mumbai_22_Aug_2020_DSCN8847_(12).jpg)
- [https://commons.wikimedia.org/wiki/File:Passer_domesticus_EM1B1381_(49116644222).jpg](https://commons.wikimedia.org/wiki/File:Passer_domesticus_EM1B1381_(49116644222).jpg)
- [https://commons.wikimedia.org/wiki/File:Passer_domesticus_EM1B6607_(49670777446).jpg](https://commons.wikimedia.org/wiki/File:Passer_domesticus_EM1B6607_(49670777446).jpg)
- [https://commons.wikimedia.org/wiki/File:Passer_domesticus_in_Aveyron_(6).jpg](https://commons.wikimedia.org/wiki/File:Passer_domesticus_in_Aveyron_(6).jpg)

## [Picus viridis](https://commons.wikimedia.org/wiki/Category:Picus_viridis)

- [https://commons.wikimedia.org/wiki/File:18.04.24_Gr%C3%BCnspecht-H%C3%B6rnle.jpg](https://commons.wikimedia.org/wiki/File:18.04.24_Gr%C3%BCnspecht-H%C3%B6rnle.jpg)
- [https://commons.wikimedia.org/wiki/File:2010-04-07_(14)_Gr%C3%BCnspecht,_(Eurasian)_green_woodpecker,_Picus_viridis.JPG](https://commons.wikimedia.org/wiki/File:2010-04-07_(14)_Gr%C3%BCnspecht,_(Eurasian)_green_woodpecker,_Picus_viridis.JPG)
- [https://commons.wikimedia.org/wiki/File:2019_Gr%C3%BCnspecht_im_Winter.jpg](https://commons.wikimedia.org/wiki/File:2019_Gr%C3%BCnspecht_im_Winter.jpg)
- [https://commons.wikimedia.org/wiki/File:20190929_groene_specht.jpg](https://commons.wikimedia.org/wiki/File:20190929_groene_specht.jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(21347414864).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(21347414864).jpg)
- [https://commons.wikimedia.org/wiki/File:Erdspecht,_Grasspecht_(32652506614).jpg](https://commons.wikimedia.org/wiki/File:Erdspecht,_Grasspecht_(32652506614).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(21490437814).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(21490437814).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(22281005866).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(22281005866).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(22310327888).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(22310327888).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(22910419309).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(22910419309).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(23314528740)_(cropped).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(23314528740)_(cropped).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(23314528740).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(23314528740).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(25886166618).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(25886166618).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(26451522211).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(26451522211).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(27581342702).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(27581342702).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(23417704964).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(23417704964).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_Woodpecker_(34520085764).jpg](https://commons.wikimedia.org/wiki/File:Green_Woodpecker_(34520085764).jpg)
- [https://commons.wikimedia.org/wiki/File:Picus_viridis_%C5%81azienki_Kr%C3%B3lewskie_02.jpg](https://commons.wikimedia.org/wiki/File:Picus_viridis_%C5%81azienki_Kr%C3%B3lewskie_02.jpg)
- [https://commons.wikimedia.org/wiki/File:Picus_viridis_Schwetzingen_01.jpg](https://commons.wikimedia.org/wiki/File:Picus_viridis_Schwetzingen_01.jpg)
- [https://commons.wikimedia.org/wiki/File:Green_Woodpecker_(Picus_viridis)_silhouette_(9799408304).jpg](https://commons.wikimedia.org/wiki/File:Green_Woodpecker_(Picus_viridis)_silhouette_(9799408304).jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_11-1.jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_11-1.jpg)
- [https://commons.wikimedia.org/wiki/File:Green_woodpecker_(37601231346).jpg](https://commons.wikimedia.org/wiki/File:Green_woodpecker_(37601231346).jpg)
- [https://commons.wikimedia.org/wiki/File:Gr%C3%B6ng%C3%B6ling_European_Green_Woodpecker_(19730386273).jpg](https://commons.wikimedia.org/wiki/File:Gr%C3%B6ng%C3%B6ling_European_Green_Woodpecker_(19730386273).jpg)
- [https://commons.wikimedia.org/wiki/File:Hunting_for_ants_(23473243160).jpg](https://commons.wikimedia.org/wiki/File:Hunting_for_ants_(23473243160).jpg)
- [https://commons.wikimedia.org/wiki/File:In_the_grass_(27114854860).jpg](https://commons.wikimedia.org/wiki/File:In_the_grass_(27114854860).jpg)
- [https://commons.wikimedia.org/wiki/File:Mrs_Woodpecker_(35201395064).jpg](https://commons.wikimedia.org/wiki/File:Mrs_Woodpecker_(35201395064).jpg)

## Test Images

We do not download test images. We use URL in [cv_04_test.py](cv_04_test.py) script.

- [https://commons.wikimedia.org/wiki/File:WoodPecker_Pivert_in_59650_(2).JPG](https://commons.wikimedia.org/wiki/File:WoodPecker_Pivert_in_59650_(2).JPG)
- [https://commons.wikimedia.org/wiki/File:Un_passerotto_su_un_olivo_nella_primavera_2020_Uccellino.jpg](https://commons.wikimedia.org/wiki/File:Un_passerotto_su_un_olivo_nella_primavera_2020_Uccellino.jpg)
- [https://commons.wikimedia.org/wiki/File:Pica_1450098_Nevit.jpg](https://commons.wikimedia.org/wiki/File:Pica_1450098_Nevit.jpg)
- [https://commons.wikimedia.org/wiki/File:Kohlmeise_(23)_(34632808830).jpg](https://commons.wikimedia.org/wiki/File:Kohlmeise_(23)_(34632808830).jpg)
- [https://commons.wikimedia.org/wiki/File:Merel_(Turdus_merula).jpg](https://commons.wikimedia.org/wiki/File:Merel_(Turdus_merula).jpg)