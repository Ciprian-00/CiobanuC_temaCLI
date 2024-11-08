1.Care este ordinea de desenare a vertexurilor pentru aceste metode
(orar sau anti-orar)?
Ordinea de desenare a vertexurilor dacă vertexurile sunt specificate în sens orar, OpenGL le va interpreta ca fiind fața din spate (back-face), în funcție de setările implicite.
Dacă vertexurile sunt specificate în sens antiorar, OpenGL le va interpreta ca fiind fața din față (front-face).

2.Ce este anti-aliasing? Prezentați această tehnică pe scurt.
Anti-aliasing este o tehnică utilizată în grafică pentru a reduce sau elimina efectele vizuale neplăcute, cunoscute sub numele de „aliasing”. Aceste efecte apar din cauza rezoluției finite a ecranului și se manifestă prin margini „zimțate” sau „dantelate” la obiectele diagonale sau curbe.

3.Care este efectul rulării comenzii GL.LineWidth(float)? Dar pentru
GL.PointSize(float)? Funcționează în interiorul unei zone
GL.Begin()?
GL.LineWidth(float) : Toate liniile desenate ulterior cu GL_LINES, GL_LINE_STRIP sau GL_LINE_LOOP vor avea grosimea specificată până când se schimbă valoarea sau se revine la valoarea implicită (de obicei, 1 pixel).
GL.PointSize(float):Toate punctele desenate ulterior cu GL_POINTS vor avea dimensiunea specificată, până când valoarea este schimbată.
Comenzile GL.LineWidth() și GL.PointSize() nu funcționează în interiorul unui bloc GL.Begin() ... GL.End(). Aceste setări trebuie efectuate înainte de apelul GL.Begin(), pentru a avea efect asupra liniilor sau punctelor desenate.

4.Răspundeți la următoarele întrebări (utilizați ca referință eventual și
tutorii OpenGL Nate Robbins):
• Care este efectul utilizării directivei LineLoop atunci când
desenate segmente de dreaptă multiple în OpenGL?
• Care este efectul utilizării directivei LineStrip atunci când
desenate segmente de dreaptă multiple în OpenGL?
• Care este efectul utilizării directivei TriangleFan atunci când
desenate segmente de dreaptă multiple în OpenGL?
• Care este efectul utilizării directivei TriangleStrip atunci când
desenate segmente de dreaptă multiple în OpenGL?
- Efectul utilizării directivei GL_LINE_LOOP: Când utilizezi GL_LINE_LOOP, OpenGL va trasa segmente de dreaptă între fiecare pereche consecutivă de puncte și va conecta și ultimul punct cu primul, formând astfel un contur închis.

-Efectul utilizării directivei GL_LINE_STRIP: Spre deosebire de GL_LINE_LOOP, GL_LINE_STRIP nu conectează ultimul punct cu primul, lăsând linia deschisă.

-Efectul utilizării directivei GL_TRIANGLE_FAN: OpenGL desenează o serie de triunghiuri adiacente care împărtășesc un vârf comun (primul vârf specificat). Această tehnică este eficientă pentru desenarea formelor radiale sau a discurilor.

-Efectul utilizării directivei GL_TRIANGLE_STRIP: OpenGL desenează o bandă de triunghiuri conectate, cu fiecare triunghi nou adăugând un singur vârf nou, eficientizând astfel procesul de desenare. Este util pentru a crea suprafețe continue sau benzi de triunghiuri.

6.Culorile per suprafață permit diferențierea între diferitele părți sau elemente ale obiectului, facilitând înțelegerea structurii acestuia.

7.Ce reprezintă un gradient de culoare? Cum se obține acesta în
OpenGL?
Un gradient de culoare reprezintă o tranziție treptată între două sau mai multe culori. În loc de o singură culoare uniformă, gradientele oferă un efect de trecere continuă între culori, adăugând profunzime și un aspect vizual mai atractiv imaginii sau obiectului.
În OpenGL, gradientul de culoare poate fi obținut prin specificarea unor culori diferite pentru fiecare vârf al unei primitive (de exemplu, un triunghi sau un dreptunghi). OpenGL va interpola automat culorile între aceste vârfuri pentru a crea o tranziție lină între ele. Această tehnică este cunoscută sub numele de color interpolation (interpolare de culoare).

10.Ce efect are utilizarea unei culori diferite pentru fiecare vertex
atunci când desenați o linie sau un triunghi în modul strip?
Atunci când se utilizează o culoare diferită pentru fiecare vertex într-un strip de linii (GL_LINE_STRIP) sau într-un strip de triunghiuri (GL_TRIANGLE_STRIP), OpenGL va interpola automat culorile între vertexuri pentru a crea o tranziție lină de-a lungul segmentelor de linie sau a suprafețelor triunghiurilor
