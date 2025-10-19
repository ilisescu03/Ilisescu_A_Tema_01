1. Introducere

OpenGL (Open Graphics Library) este o bibliotecă grafică multiplatformă destinată randării grafice 2D și 3D, dezvoltată inițial de Silicon Graphics (SGI) în anii 1990. Scopul său principal este de a oferi un set standardizat de funcții pentru accelerarea hardware a graficii, permițând programatorilor să dezvolte aplicații vizuale complexe (jocuri, simulatoare, aplicații CAD etc.) fără a depinde direct de un anumit sistem de operare sau placă video.

De-a lungul timpului, OpenGL a stat la baza multor alte tehnologii și API-uri moderne, cum ar fi:

WebGL – pentru randare 3D în browser prin JavaScript;

Vulkan – succesorul modern, cu performanță ridicată și control explicit asupra resurselor;

OpenGL ES (Embedded Systems) – versiunea adaptată pentru dispozitive mobile și console;

GLSL (OpenGL Shading Language) – limbaj de programare pentru scrierea shader-elor personalizate.

2. Arhitectura și principiile de funcționare

OpenGL funcționează pe principiul unei pipeline grafice, adică un lanț de etape prin care datele (vârfuri, culori, texturi) sunt procesate până se ajunge la imaginea finală afișată pe ecran. Printre etapele importante se numără:

Transformarea vârfurilor (vertex transformation);

Aplicarea texturilor și iluminării (fragment shading);

Rasterizarea și scrierea în framebuffer.

Această structură modulară permite programatorilor să intervină în fiecare etapă prin shader-e personalizate, oferind o mare flexibilitate vizuală.

3. Modelul de automat cu stări finite al OpenGL

OpenGL este construit pe principiul unui automat cu stări finite (finite state machine – FSM).
Asta înseamnă că biblioteca are un set intern de stări (de exemplu: culoarea curentă, textura activă, matricea de transformare, shader-ul selectat etc.), iar apelurile de funcții modifică sau utilizează aceste stări.

Explicație simplificată:

OpenGL menține un context (un set de stări active).

Când apelăm funcții precum glEnable(GL_DEPTH_TEST) sau glBindTexture(), modificăm starea curentă a contextului.

Randarea se face în funcție de starea curentă: toate comenzile ulterioare vor fi influențate de această configurație.

Efect asupra randării:

Acest model permite coerență și simplitate în designul API-ului, dar poate duce la confuzie și erori dacă stările nu sunt gestionate corect.

Din cauza acestui model, OpenGL este considerat mai „implicit” (stateful), spre deosebire de Vulkan, care este „stateless” și necesită specificarea explicită a tuturor parametrilor pentru fiecare operație.

În concluzie, modelul FSM face OpenGL ușor de folosit la început, dar dificil de optimizat și de întreținut în proiecte mari, unde gestionarea stărilor devine complexă.

4. Tehnologii derivate din OpenGL
a) OpenGL ES

Variante optimizate pentru dispozitive mobile și sisteme încorporate.

Reduce complexitatea și consumul de energie.

Este folosit pe scară largă în Android și iOS pentru aplicații 3D și jocuri.

b) WebGL

Permite afișarea graficii 3D direct în browser, folosind JavaScript.

Folosește aceleași principii ca OpenGL ES.

Este folosit în aplicații web interactive, modele 3D, vizualizări științifice și educaționale.

c) Vulkan

Urmaș direct al OpenGL, dezvoltat de Khronos Group.

Oferă control mai detaliat asupra GPU-ului și performanță mai mare.

Elimină dependența de modelul de stare, oferind o abordare explicită și predictibilă.
