# NoteSet

This is C++ code to implement monophony given midi note information.  I don't exactly know what this algorithm is called but it's implemented in almost every synthesizer and was surprised not to see a version on the web for C++. 


Note stack by Olivier Gillet >> NoteSet by kschaffer >> C++ version of NoteSet
This is a version of Kat Schaffer's code that is not reliant on <Arduino.h>.  Should work in C++


Quick example code
```
NoteSet *nSet =new NoteSet( );
nSet->init(NOTE_PRIORITY_LAST);  
/*
or NOTE_PRIORITY_LOW or NOTE_PRIORITY_HIGH
*/

NoteInfo nsetSpatOut;

nSet->note_on(10,10);
nSet->note_on(20,20);
nSet->note_on(30,30);
nSet->note_on(40,40);
nSet->note_on(50,50);
nSet->note_off(40);
nsetSpatOut = nSet->get_next_note();
printf("spit this out: %hd %hd\n",nsetSpatOut.note,nsetSpatOut.velocity);


nSet->note_off(50);
nsetSpatOut = nSet->get_next_note();
printf("spit this out: %hd %hd\n",nsetSpatOut.note,nsetSpatOut.velocity);


nSet->note_off(30);
nSet->note_off(20);
nSet->note_off(10);
nsetSpatOut = nSet->get_next_note();
printf("spit this out: %hd %hd\n",nsetSpatOut.note,nsetSpatOut.velocity);
``` 
    


Keywords:
Monophony Monophonic Note priority midi stack cv voicing
