# NoteSet

This is C++ code to implement monophony given midi note information.  I don't exactly know what this algorithm is called but it's implemented in almost every synthesizer and was surprised not to see a version on the web for C++. 

Use it by

Note stack by Olivier Gillet >> NoteSet by kschaffer >> C++ version of NoteSet
This is a version of Kat Schaffer's code that is not reliant on <Arduino.h>.  Should work in C++
```
NoteSet *nnn =new NoteSet( );
nnn->init(NOTE_PRIORITY_LAST);

NoteInfo ni;

nnn->note_on(10,10);
nnn->note_on(20,20);
nnn->note_on(30,30);
nnn->note_on(40,40);
nnn->note_on(50,50);
nnn->note_off(40);
ni = nnn->get_next_note();
printf("ni %hd %ld\n",ni.note,ni.velocity);


nnn->note_off(50);
ni = nnn->get_next_note();
printf("ni %hd %ld\n",ni.note,ni.velocity);


nnn->note_off(30);
nnn->note_off(20);
nnn->note_off(10);
ni = nnn->get_next_note();
printf("ni %hd %ld\n",ni.note,ni.velocity);
``` 
    


Keywords:
Monophony Monophonic Note priority midi stack cv voicing
