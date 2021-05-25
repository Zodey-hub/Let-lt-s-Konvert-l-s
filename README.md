# Letöltés
## Internet Download Manager
### IDM letöltése:
https://www.internetdownloadmanager.com/

Először is töltsük le a programot, majd telepítsük fel.
A program felajánlja, hogy a bővítményt adjuk hozzá a böngészőhöz, ezt feltétlenül fogadjuk el.
### **Böngésző beállítások:**
-A böngészőnkben nyissuk meg a bővítményeket (Chrome esetében másoljuk be az alábbi linket ```chrome://extensions/``` ) pipáljuk be az IDM-et, ha nem lenne, majd kattintsunk a ```Részletek``` fülre.
- Az összes webhelyen engedélyezzük a hozzáférést és az alsó három csúszkát is csúsztassuk zöldre. 
- ![Kép1](https://i.imgur.com/ayCwxlz.png)
### **IDM beállítások:**
![Kép2](https://i.imgur.com/RQ6NcQi.png)
![Kép3](https://i.imgur.com/eyZn5ib.png)

-A többi beállításhoz ne nyúljunk, esetleg a ```Letöltés helye``` menüpontban álligassunk, ha az alapértelmezett nem lenne jó.
### **Maga a letöltés:**
- Nyissunk meg a letöltendő filmet, (az én esetemben: https://waaw.to/f/mQ5qhI7zUrqe#.YKzMaqH_OyM.link) indítsuk el a videót, majd kattintsunk a `Videó letöltése` gombra, ami jelen esetben a jobb felső sarokban volt. Itt láthatjuk, hogy a videót TS formátumként fogjuk lementeni, de ne ijedjünk meg, ezt könnyedén mp4-é alakíthatjuk egy nagyon hasznos és ingyenes programmal, amivel a régebbi DVD lejátszókhoz megfelelő videókat is konvertálhatuk.
- ![Kép4](https://i.imgur.com/saqZiPa.png)
- (FIGYELEM: Sok oldalon mp4-ként fogjuk tudni letölteni a videókat, de lesznek oldalak, ahol csak TS-ként fogunk tudni letölteni. Törekedjünk arra, hogy az első verziót használó oldalakról töltsünk le, mert a második verzió komplikáltabb, mint a jelen esetben. A waaw.to oldalán láthatjuk, hogy lesz egy már kB-os mp4 fájl, ez nem az ami nekünk kell. A TS fájloknak nem is tudja a letöltőnk a méretét, ezért ír ki csak hosszt. Ennek az az oka, hogy az ilyen videómegosztó szervereken valójában nincs fent a videó, csak egy .m3u8 kiterjesztésű fájl, ami valós időben jeleníti meg a videót. Amikor TS fájlként töltünk le, valójában nem letöltünk, hanem az IDM végigfut az m3u8 fájlon és képkockáról képkockára rendereli le, ez az oka annak, hogy a TS fájlokat csak egy szálon tudjuk letölteni és sokkal lassabban, tehát amikor csak tehetjük válasszunk olyan oldalakat, ahol mp4 videókat tudunk letölteni pl.: vidoza, mixdrop. Amennyiben erre nincs lehetőségünk mutatni fogok egy gyorsabb módszert a letöltéshez, (rendereléshez) de ahhoz le már az FFMPEG program kell, amelyet a videókódoláshoz is használni fogunk.)

# Konvertálás
## FFMPEG
### FFMPEG letöltése:
-Menjünk fel az FFMPEG honlapjára és kattintsunk a letöltésre. (https://www.ffmpeg.org/download.html)
-Görgessünk lejjebb és kattintsunk a `Windows builds from gyan.dev` gombra.

![Kép5](https://i.imgur.com/SmcFPu3.png)

-Görgessünk le a `release`-ig majd nyissunk meg a képen látható linket.

![Kép6](https://i.imgur.com/WFqvhLO.png)

-Emlékeim szerint fel fog jönni egy piros figyelmeztető ablak, de tartsuk meg a fájlt, nem tartalmaz vírust.
-Amennyiben nincs semmilyen speciális kicsomagolónk mint pl. a WinRar, akkor nyugodtan letölthetjük a 3. sima ZIP-et, amit az alapértelmezett windowsos kicsomagolóval is ki lehet bontani.
-Csomagoljuk ki a fájlt, menjünk bele a mappába és azon belül is a `bin` mappába.
-Készítsünk egy `FFMPEG` nevű mappát a C:\ meghajtóra majd másoljuk bele a 3 exe fájlt amit a `bin`-ben találtunk. Ezután le is törölhetjük az eredeti mappát, hogy ne foglalja a helyet.
-Most hozzá kell adnunk a `path`-hoz az FFMPEG mappát. Ehhez jobb klikk a Windows gombra bal alul, és ott kattintsunk a `Rendszer`fülre.
-Jobb oldalt kattintsunk a `Speciális rendszerbeállítások` gombra.

![Kép7](https://i.imgur.com/ZjihPX8.png)

-A felugró ablakban gattintsunk a `Környezeti változók...` gombra.
-Kattintsunk a `Path`-ra, majd a `Szerkesztés`gombra. FONTOS: A Rednszerváltozói Pathba kattintsunk!
-Itt kattintsunk a `Tallózás` gombra, majd tallózuk be az FFMPEG mappát a C-n.

![Kép8](https://i.imgur.com/fC6oBK5.png)

-Ezután csak nyomkodjuk az `OK`gombot, míg be nem zárja az összes ablakot.
-Mindeközben letöltődött a filmünk, konvártáljuk is át, hogy nézhető legyen a DVD lejátszón!
-Az Intézőben menjünk bele abba a mappába, ahová a filmet letöltöttük.
-Kattintsunk bele a mappa elérhetőségének útjába, majd gépeljük be, hogy `cmd`.

![Kép9](https://i.imgur.com/WvLGEkQ.png)

-Nyomjunk entert.
-Egy fekete ablak fogad, ez a Command Prompt.
-Másoljuk ki az alábbi parancsot úgy, hogy a -i után az a fájlnév szerepeljen, ami a videónk neve. Ügyeljünk arra, hogy a kiterjesztés is egyezzen. 
`ffmpeg -i input.mp4 -target pal-dvd -ps 2000000000 -aspect 16:9 output.mpeg`
-Az output nevét is megváltoztathatjuk, de ügyeljünk arra, hogy a kiterjesztés mpeg legyen és, hogy ne használjunk szóközöket!
-Nyomjunk Entert!
-A konvertálás akkor fejeződött be, amikor újra lehetőségünk lesz gépelni, tehát már nem pörög alul a frame számlálója a programnak.
-Kellemes filmnézést kívánok!


# Egyéb dolgok:
-Az ffpmeg tökéletesen működik hangok illetve képek konvertálására is.
-Néhány hasznos parancsot feltöltök még parancsok.txt néven. Az egyik parancsnak a leírása az lesz, hogy Másik talán jó. Ez egy másik parancs régebbi tévékre, lejátszókra, ki kell tapasztalni melyik a jobb.


Készítette: Zodey
